---
title: Använda CJA med arrayer med objekt
description: Lär dig hur CJA rapporterar om datahierarkier.
translation-type: tm+mt
source-git-commit: b7cd74f3fe2f0222e78452f58a7c387f6e0c86d2
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# Använda CJA med arrayer med objekt

Vissa plattformsscheman kan ha objektarrayer. Ett av de vanligaste exemplen är en varukorg som innehåller flera produkter. Varje produkt har ett namn, SKU, kategori, pris, kvantitet och andra dimensioner som du vill spåra. Alla de här ansiktena har olika krav, men måste alla få plats i samma träff.

I tidigare versioner av Adobe Analytics utfördes den här funktionen med hjälp av `products` variabeln. Det var en sammanfogad sträng som separerades med semikolon (`;`) för att separera en produkts delar, medan kommatecken (`,`) avgränsade produkter. Den var den enda variabeln med begränsat stöd för&quot;objektarrayer&quot;. Multivärdesvariabler som listvariabler kan ha stöd för motsvarande arrayer, men de kan inte ha stöd för &quot;objektarrayer&quot;. CJA bygger vidare på detta koncept genom att ha stöd för godtyckligt djupa hierarkier i en enda datarad, en funktion som inte finns i någon tidigare version av Adobe Analytics.

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

Eftersom du kan kombinera alla dimensioner med alla mätvärden visas i följande tabell hur data skulle kunna kombineras med ospecificerade dimensionsvärden:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Det finns en produktorder utan ett garantinamn som är knutet till den, så dimensionsvärdeattributen är &#39;Ospecificerad&#39;. Samma situation gäller även för produktgarantiordern:

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
