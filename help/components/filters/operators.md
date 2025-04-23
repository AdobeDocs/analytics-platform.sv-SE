---
title: Operatorer
description: Bestäm hur en komponent interagerar med ett värde inom ett segment.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: 85a22d1e57925f0512ce0cc658cfba1008339d91
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# Operatorer

Med segmentverktyget kan du jämföra och begränsa värden för komponenter med hjälp av valda operatorer. Det finns två kategorier av operatorer: [[!UICONTROL Standard]](#standard-operators) och [[!UICONTROL Distinct Count]](#distinct-count-operators).

## Standardoperatorer

| Operator | Beskrivning |
| --- | --- |
| **[!UICONTROL equals]** | Returnerar objekt som matchar exakt för ett numeriskt värde eller strängvärde. Om du använder jokertecken använder du operatorn match. |
| **[!UICONTROL does not equal]** | Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet.  Om du använder jokertecken ska du använda operatorn matchar inte. |
| **[!UICONTROL equals any of]** | Returnerar alla objekt som innehåller matchningen av de angivna delsträngsvärdena, avgränsade med kommatecken. |
| **[!UICONTROL contains]** | Returnerar objekt som jämför med delsträngarna för de angivna värdena. Om värdet för sidnamnsdimensionen till exempel innehåller `Search` matchar den här operatorn alla sidor som har delsträngen `Search` i sitt namn, inklusive `Search Results`, `Search` och `Searching`. Operatorn är skiftlägeskänslig. |
| **[!UICONTROL does not contain]** | Alla objekt som matchar det angivna värdet tas inte med i resultatet. Om värdet för en sidnamnsdimension till exempel inte innehåller `Search`, utesluter operatorn alla sidor som har delsträngen `Search` i sitt namn, inklusive `Search Results`, `Search` och `Searching`. |
| **[!UICONTROL contains all of]** | Returnerar objekt som innehåller alla delsträngar (avgränsade med blanksteg) i valfri ordning. Om du till exempel anger `Search Results` som värde för den här operatorn skulle det matcha `Search Results` och `Results of Search`, men inte `Search` eller `Results` separat. Den här operatorn stöder upp till 100 ord avgränsade med blanksteg. |
| **[!UICONTROL does not contain all of]** | Alla objekt som matchar alla angivna värden tas inte med i resultatet. Om du till exempel anger `Search Results` som värde för den här operatorn skulle det exkludera `Search Results` och `Results of Search`, men inte `Search` eller `Results`. Den här operatorn stöder upp till 100 ord avgränsade med blanksteg. |
| **[!UICONTROL contains any of]** | Returnerar objekt som innehåller någon av de angivna delsträngarna. Om du till exempel anger `Search Results` som värde för den här operatorn matchar `Search Results`, `Results of Search`, `Search` och `Results`. Den här operatorn stöder upp till 100 ord avgränsade med blanksteg. |
| **[!UICONTROL does not contain any of]** | Alla objekt som matchar en delsträng tas inte med i resultatet. Om du till exempel anger `Search Results` som värde för den här operatorn kommer `Search Results`, `Results of Search`, `Search` och `Results` att exkluderas. Den här operatorn stöder upp till 100 ord avgränsade med blanksteg. |
| **[!UICONTROL starts with]** | Returnerar objekt som börjar med det eller de tecken som har det angivna värdet. |
| **[!UICONTROL does not start with]** | Returnerar alla objekt som inte börjar med det angivna värdets tecken eller strängar. |
| **[!UICONTROL ends with]** | Returnerar objekt som slutar med det angivna tecknet eller de angivna strängarna. |
| **[!UICONTROL does not end with]** | Returnerar alla objekt som inte slutar med de angivna tecknen eller strängarna för värdet. |
| **[!UICONTROL matches]** | Returnerar objekt som matchar objekt exakt baserat på ett givet numeriskt värde eller strängvärde. Stöder jokertecken med en asterisk (`*`). Operatorn är skiftlägeskänslig. Exempel:<ul><li>`a*e` matchar `ae`, `abcde`, `adobe` och `a whole sentence`.</li><li>`adob*` matchar `adobe`, `adobe analytics` och `adobo recipe`</li><li>`*dobe` matchar `dobe`, `adobe` och `cute little dobe`.</li></ul> |
| **[!UICONTROL does not match]** | Alla objekt som matchar strängen exkluderas. Stöder jokertecken med en asterisk (`*`). |
| **[!UICONTROL exists]** | Returnerar objekt om värdet inte är null. |
| **[!UICONTROL does not exist]** | Returnerar objekt om värdet är null. |

## Distinkta räkningsoperatorer

Du kan segmentera ett visst antal artiklar i en dimension. Du kan till exempel skapa segment för personer som har tittat på mer än fem olika produkter eller besök där mer än fem olika sidor har visats.

| Operator | Beskrivning |
| --- | --- |
| **[!UICONTROL equals]** | Returnerar dimensionsobjekt vars unika antal är lika med det angivna värdet. |
| **[!UICONTROL does not equal]** | Returnerar dimensionsobjekt vars unika antal inte motsvarar det angivna värdet. |
| **[!UICONTROL is greater than]** | Returnerar dimensionsobjekt vars unika antal är större än det angivna värdet. |
| **[!UICONTROL is less than]** | Returnerar dimensionsobjekt vars unika antal är mindre än det angivna värdet. |
| **[!UICONTROL is greater than or equal to]** | Returnerar dimensionsobjekt vars unika antal är större än eller lika med det angivna värdet. |
| **[!UICONTROL is less than or equal to]** | Returnerar dimensionsobjekt vars unika antal är mindre än eller lika med det angivna värdet. |
