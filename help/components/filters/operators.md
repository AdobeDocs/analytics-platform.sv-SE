---
title: Filteroperatorer
description: Bestäm hur en komponent interagerar med ett värde i ett filter.
source-git-commit: 1334e1edb36583ba978936fecbff2657e63a94bf
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# Filteroperatorer

Med filterverktyget kan du jämföra och begränsa värden med valda operatorer. Det finns två kategorier av operatorer: [!UICONTROL Standard] och [!UICONTROL Distinct Count].

## Standardoperatorer

| Operator | Beskrivning |
| är lika med | Returnerar objekt som matchar exakt för ett numeriskt värde eller strängvärde. Om du använder jokertecken använder du operatorn &quot;match&quot;. |
| är inte lika med | Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet.  Om du använder jokertecken använder du operatorn &quot;matchar inte&quot;. |
| innehåller | Returnerar objekt som jämför med delsträngarna för de angivna värdena. Om regeln för en strängdimension till exempel innehåller `"Search"`, matchar den alla sidor som innehåller delsträngen `"Search"`, inklusive `"Search Results"`, `"Search"` och `"Searching"`. Den här operatorn är skiftlägeskänslig. |
| innehåller inte | Alla objekt som matchar det angivna värdet tas inte med i resultatet. Om regeln för en strängdimension till exempel inte innehåller `"Search"`, utesluter den alla sidor som innehåller delsträngen `"Search"`, inklusive `"Search Results"`, `"Search"` och `"Searching"`. |
| innehåller alla | Returnerar objekt som innehåller alla delsträngar (avgränsade med blanksteg) i valfri ordning. Om du till exempel anger `"Search Results"` med den här operatorn skulle det matcha `"Search Results"` och `"Results of Search"`, men inte `"Search"` eller `"Results"` separat. Den här operatorn stöder upp till 100 ord avgränsade med blanksteg. |
| innehåller inte alla | Alla objekt som matchar alla angivna värden tas inte med i resultatet. Om du till exempel anger `"Search Results"` med den här operatorn skulle `"Search Results"` och `"Results of Search"` exkluderas, men inte `"Search"` eller `"Results"`. Den här operatorn stöder upp till 100 ord avgränsade med blanksteg. |
| innehåller något av | Returnerar objekt som innehåller någon av de angivna delsträngarna. Om du till exempel anger `"Search Results"` med den här operatorn skulle det matcha `"Search Results"`, `"Results of Search"`, `"Search"` och `"Results"`. Den här operatorn stöder upp till 100 ord avgränsade med blanksteg. |
| innehåller inte något av | Alla objekt som matchar en delsträng tas inte med i resultatet. Om du till exempel anger `"Search Results"` utesluts `"Search Results"`, `"Results of Search"`, `"Search"` och `"Results"`. Den här operatorn stöder upp till 100 ord avgränsade med blanksteg. |
| börjar med | Returnerar objekt som börjar med tecknet eller strängarna för det angivna värdet. |
| börjar inte med | Returnerar alla objekt som inte börjar med tecknen eller strängarna för de värden som anges. |
| slutar med | Returnerar objekt som slutar med tecknet eller strängarna för det angivna värdet. |
| slutar inte med | Returnerar alla objekt som inte slutar med de tecken eller strängar som anges för värdet. |
| träffar | Returnerar objekt som matchar exakt baserat på ett givet numeriskt värde eller strängvärde. Stöder jokertecken med hjälp av en asterisk (`*`). Den här operatorn är skiftlägeskänslig. Exempel:<ul><li>`a*e` matchar  `ae`,  `abcde`,  `adobe`och  `a whole sentence`.</li><li>`adob*` matchar  `adobe`,  `adobe analytics`och  `adobo recipe`</li><li>`*dobe` matchar  `dobe`,  `adobe`och  `cute little dobe`.</li></ul>|
| matchar inte | Alla objekt som matchar strängen exkluderas. Stöder jokertecken med hjälp av en asterisk (`*`). |
| finns | Returnerar objekt om värdet inte är null. |
| finns inte | Returnerar objekt om värdet är null. |

## Distinkta räkningsoperatorer

Du kan segmentera ett visst antal artiklar i en dimension. Du kan till exempel skapa filter för besökare som har tittat på mer än fem olika produkter eller besök där mer än fem olika sidor har visats.

| Operator | Beskrivning |
| --- | --- |
| är lika med | Returnerar dimensionsobjekt vars unika antal är lika med det angivna värdet. |
| är inte lika med | Returnerar dimensionsobjekt vars unika antal inte är lika med det angivna värdet. |
| är större än | Returnerar dimensionsobjekt vars unika antal är större än det angivna värdet. |
| är mindre än | Returnerar dimensionsobjekt vars unika antal är mindre än det angivna värdet. |
| är större än eller lika med | Returnerar dimensionsobjekt vars unika antal är större än eller lika med det angivna värdet. |
| är mindre än eller lika med | Returnerar dimensionsobjekt vars unika antal är mindre än eller lika med det angivna värdet. |