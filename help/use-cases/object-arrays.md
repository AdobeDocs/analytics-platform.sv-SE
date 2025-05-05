---
title: Använda arrayer med objekt
description: Lär dig hur Customer Journey Analytics rapporterar om datahierarkier.
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Använda arrayer med objekt

Vissa plattformsscheman kan ha objektarrayer. Adobe Customer Journey Analytics stöder inmatning och rapportering av objektarrayer i händelse-, uppslags- och profildata. Ett av de vanligaste exemplen är en varukorg som innehåller flera produkter. Varje produkt har ett namn, SKU, kategori, pris, kvantitet och andra dimensioner som du vill spåra. Alla de här ansiktena har olika krav, men måste alla få plats i samma träff.

I tidigare versioner av Adobe Analytics utfördes den här funktionen med variabeln `products`. Det var en sammanfogad sträng som avgränsades med semikolon (`;`) för att separera en produkts delar, medan produkter avgränsas med kommatecken (`,`). Den var den enda variabeln med begränsat stöd för&quot;objektarrayer&quot;. Multivärdesvariabler som listvariabler kan ha stöd för motsvarande arrayer, men de kan inte ha stöd för &quot;objektarrayer&quot;. Customer Journey Analytics utnyttjar detta koncept ytterligare genom att stödja godtyckligt djupa hierarkier i en enda datarad, en funktion som inte finns i någon tidigare version av Adobe Analytics.

## Exempel på samma händelse

Följande händelse är ett JSON-objekt som representerar ett köp som kunden gjort av en tvättmaskin och torktumlare.

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

När du skapar en datavy är följande mått och mått tillgängliga (baserat på schema):

* **Dimensioner:**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : warranty : cover
   * product : warranty : length
   * product : warranty : name
   * product : warranty : type
* **Mått:**
   * product:order
   * product:units
   * product : omsättning
   * product : warranty
   * product : warranty : revenue

### Exempel på samma händelse (rapporteringsbeteende)

Med hjälp av ovanstående händelse visar följande tabeller Workspace-rapporter med vissa mått- och måttkombinationer.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

Customer Journey Analytics tittar selektivt på objektets mått och mått baserat på tabellen.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Om du bara vill rapportera garantiintäkter ser ditt projekt ut ungefär så här:

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

Customer Journey Analytics tittar på dessa delar av händelsen för att generera rapporten:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

Eftersom torktumlaren inte innehöll någon garanti ingår den inte i tabellen.

Eftersom du kan kombinera alla dimensioner med alla mätvärden, visar följande tabell hur data skulle kunna användas med ospecificerade dimensionsobjekt:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Det finns en produktorder utan ett garantinamn som är knutet till den, så dimensionsobjektsattributen är &#39;Ospecificerad&#39;. Samma situation gäller även för produktgarantiordern:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Observera order som inte har ett namn som är knutet till dem. Detta är de order som har tilldelats dimensionsobjektet &#39;Ospecificerad&#39;.

### Kombinera mätvärden

Customer Journey Analytics kombinerar inte mätvärden med liknande namn om de finns på olika objektnivåer.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Du kan dock skapa ett beräknat mått som kombinerar de önskade måtten:

Beräknad&quot;total intäkt&quot;: `[product : revenue] + [product : warranty : revenue]`

När du använder det här beräknade måttet visas det önskade resultatet:

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |



## Begränsningar

Det finns begränsningar för arrayer i data som används av Customer Journey Analytics och modelleras som en del av ett schema i Experience Platform. Se [Begränsningar för datamodell](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/guardrails#data-model-limits) och [Begränsningar för datastorlek](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/guardrails#data-size-limits) i [standardguarutorna för kundprofildata och segmentering i realtid](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/guardrails).

