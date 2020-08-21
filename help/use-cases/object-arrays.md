---
title: Använda arrayer med objekt
description: Förstå hur CJA rapporterar om datalänkar.
translation-type: tm+mt
source-git-commit: 76cedb931085e8b5b59d7c5c3929bf4b5c010d9d
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---


# Använda arrayer med objekt

Vissa plattformsscheman kan ha objektarrayer. Ett av de vanligaste exemplen skulle vara en shoppingvagn som innehåller flera produkter. Varje produkt har ett namn, SKU, kategori, pris, kvantitet och andra dimensioner som du vill spåra. Alla dessa aspekter har separata krav, men måste alla passa in i samma träff.

I tidigare versioner av Adobe Analytics utfördes den här funktionen med hjälp av `products` variabel. Det var en sammanfogad sträng åtskild med semikolon (`;`) för att separera olika aspekter av en produkt, medan kommatecken (`,`) avgränsade produkter. Det var den enda variabeln med begränsat stöd för &quot;objektmatriser&quot;. Multivärdiga variabler som listvars kan stödja motsvarande arrayer, men de kan inte stödja &quot;objektarrayer&quot;. CJA utökar konceptet genom att stödja godtyckligt djupa hierarkier i en enda rad data, en funktion som inte finns tillgänglig i någon tidigare version av Adobe Analytics.

## Samma träffexempel

Följande träff är ett JSON-objekt som representerar ett köp som en kund gjort av en tvättmaskin och en torktumlare.

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

När du skapar en datavy är följande dimensioner och mått tillgängliga (baserat på schema):

* **Dimensioner:**
   * ID
   * produkt: SKU
   * produkt: namn
   * produkt: order_id
   * produkt: garanti: täckning
   * produkt: garanti: längd
   * produkt: garanti: namn
   * produkt: garanti: typ
* **Mätvärden:**
   * produkt: order
   * produkt: enheter
   * produkt: inkomster
   * produkt: garanti
   * produkt: garanti: inkomster

### Samma träffexempel (rapporteringsbeteende)

Med hjälp av bara träffen ovan visar följande tabeller arbetsyterapporter med vissa dimensioner och metriska kombinationer.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA tittar selektivt på objektets dimension och mått baserat på tabellen.

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

Om du vill rapportera om enbart garantiintäkter ser ditt projekt ut så här:

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

Eftersom du kan kombinera alla dimensioner med alla mått visar följande tabell hur data skulle användas med ospecificerade dimensionsobjekt:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Det finns en produktorder som inte har något garantinamn som är kopplat till den, så dimensionsobjektets attribut är &quot;Ospecificerat&quot;. Samma situation gäller även för produktgarantiordern:

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

Observera order som inte har ett namn som är kopplat till dem. Detta är de order som tilldelats till dimensionsartikeln Ospecificerad.

### Kombinera mått

I CJA kombineras inte måtten med liknande namn om de finns på olika objektnivåer.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Du kan dock skapa ett beräknat mått som kombinerar de önskade måtten:

Beräknad &quot;summa inkomster&quot;: `[product : revenue] + [product : warranty : revenue]`

Om du använder det här beräknade måttet visas önskade resultat:

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |

## Persistensexempel

