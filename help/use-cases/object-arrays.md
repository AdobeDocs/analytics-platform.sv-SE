---
title: Använda arrayer med objekt
description: Lär dig hur CJA rapporterar om datahierarkier.
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 04aaf9ae9f720255c97c9dc148953b5b9d6967ae
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# Använda arrayer med objekt

Vissa plattformsscheman kan ha objektarrayer. CJA stöder inmatning och rapportering av objektarrayer i händelse-, uppslags- och profildata. Ett av de vanligaste exemplen är en varukorg som innehåller flera produkter. Varje produkt har ett namn, SKU, kategori, pris, kvantitet och andra dimensioner som du vill spåra. Alla de här ansiktena har olika krav, men måste alla få plats i samma träff.

I tidigare versioner av Adobe Analytics utfördes den här funktionen med `products` variabel. Det var en sammanfogad sträng avgränsad med semikolon (`;`) för att separera olika delar av en produkt, medan kommatecken (`,`) avgränsade produkter. Den var den enda variabeln med begränsat stöd för&quot;objektarrayer&quot;. Multivärdesvariabler som listvariabler kan ha stöd för motsvarande arrayer, men de kan inte ha stöd för &quot;objektarrayer&quot;. CJA bygger vidare på detta koncept genom att ha stöd för godtyckligt djupa hierarkier i en enda datarad, en funktion som inte finns i någon tidigare version av Adobe Analytics.

## Samma träffexempel

Följande träff är ett JSON-objekt som representerar ett köp av en kund gjord av en tvättmaskin och torktumlare.

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
   * product: SKU
   * product: name
   * product: order_id
   * product: garanti: täckning
   * product: garanti: length
   * product: garanti: name
   * product: garanti: type
* **Mätvärden:**
   * product: order
   * product: enheter
   * product: omsättning
   * product: garanti
   * product: garanti: omsättning

### Samma träffexempel (rapporteringsbeteende)

Med hjälp av bara träffen ovan visas Workspace-rapporter med mått och måttkombinationer i följande tabeller.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA tittar selektivt på objektets mått och mått baserat på tabellen.

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

CJA tittar på de här delarna av träffen för att generera rapporten:

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

CJA kombinerar inte mätvärden med liknande namn om de finns på olika objektnivåer.

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
