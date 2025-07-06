---
description: Lär dig hur du använder operatorerna i segmentbyggaren för att jämföra och begränsa värden.
title: Operatorer
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1053'
ht-degree: 0%

---

# Operatorer

Med segmentverktyget kan du jämföra och begränsa värden för komponenter med hjälp av valda operatorer. Det finns tre kategorier av operatorer: [Standard](#standard-operators), [Data Warehouse](#data-warehouse-operators) och [Distinkt antal](#distinct-count-operators).

Beroende på vilken operator du väljer:

* Du kan ange ett värde.
* Du kan ange en del av ett värde och välja från en nedrullningsbar meny (om den är tillgänglig).
* Välj omedelbart ett värde i listrutan (om tillgängligt).

När du skriver ett värde för en operator som validerar tillgängliga värden, som **[!UICONTROL equals]**, och värdet inte matchar de värden som är tillgängliga för komponenten, visas en ![ AlertRed](/help/assets/icons/AlertRed.svg) -ikon. Du kan antingen välja ett värde i listrutan eller trycka på **[!UICONTROL _Retur_]** för att ange värdet.

![Segment är lika med](assets/segment-operator-equals.png)

## Jokertecken

Asterisken `*` är det enda jokertecken som stöds för operatorer som stöder jokertecken. Om du behöver söka efter det specifika &#42;-tecknet kan du kringgå det med ett omvänt snedstreck, som `\*`.

Du har till exempel ett sidnamn som heter *Min coola produkt*.

* Segmentregeln **[!UICONTROL Page name]** **[!UICONTROL matches]** `* product` matchar sidnamnet ovan.
* Regeln **[!UICONTROL Page name]** **[!UICONTROL matches]** `My \* product` matchar bara sidnamnet *My * Product*.

## Standardoperatorer

| Operator | Den valda dimensionen, segmentet eller metriska händelsen... |
|--- |--- |
| **[!UICONTROL equals]** | Returnerar objekt som matchar exakt för ett numeriskt värde eller strängvärde. Obs! Använd operatorn **[!UICONTROL matches]** om du använder jokertecken. |
| **[!UICONTROL does not equal]** | Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet.  Obs! Använd operatorn **[!UICONTROL does not match]** om du använder jokertecken. |
| **[!UICONTROL equals any of]** | Returnerar objekt som matchar exakt för alla värden i indatafältet (upp till 500 objekt). Om du till exempel anger `Search Results, Homepage` för dimensionen **[!UICONTROL Page Name]** med den här operatorn matchar *sökresultaten* och *startsidan* och räknas som två objekt. Indatafältet för den här operatorn är kommaavgränsat. |
| **[!UICONTROL does not equal any of]** | Identifierar objekt som matchar exakt för alla värden i indatafältet (upp till 500 objekt) och returnerar sedan bara objekt utan dessa värden. Om du till exempel anger `Search Results, Homepage` med den här operatorn för dimensionen **[!UICONTROL Page Name]** identifieras *sökresultat* och *startsida* och sedan **exkluderar** dem från de returnerade objekten. Det här exemplet räknas som 2 objekt. Indatafältet för den här operatorn är kommaavgränsat. |
| **[!UICONTROL contains]** | Returnerar objekt som jämför med delsträngarna för de angivna värdena. Om regeln till exempel är **[!UICONTROL Page Name]** **[!UICONTROL contains]** `Search` matchar den här regeln alla sidor som innehåller delsträngen `Search`, inklusive *sökresultat*, *sökning* och *sökning*. Satsen&quot;contains&quot; är inte skiftlägeskänslig i Adobe Analytics, men den är skiftlägeskänslig i Customer Journey Analytics. |
| **[!UICONTROL does not contain]** | Returnerar inversen av **[!UICONTROL contains]**-regeln. I synnerhet kommer alla objekt som matchar det angivna värdet att exkluderas från de angivna värdena. Om regeln till exempel är **[!UICONTROL Page Name]** **[!UICONTROL does not contain]** `Search` kommer den inte att matcha någon sida som innehåller delsträngen `Search`, inklusive *sökresultat*, *sökning* och *sökning*. Dessa värden kommer att uteslutas från resultaten. |
| **[!UICONTROL contains all of]** | Returnerar objekt jämfört med delsträngarna, inklusive flera värden som sammanfogats. Om du till exempel anger `Search Results` med den här operatorn för dimensionen **[!UICONTROL Page Name]** matchar *sökresultaten* och *sökresultaten*, men inte *sökresultaten* eller *resultaten* individuellt. Regeln skulle matcha *Sök* OCH *Resultat* som hittades tillsammans. Indatafältet för den här operatorn är blankstegsavgränsat (100 ord). |
| **[!UICONTROL does not contain all of]** | Identifierar objekt jämfört med delsträngar, inklusive flera sammanfogade värden, och returnerar sedan bara objekt utan dessa värden. Om du till exempel anger `Search Results` med den här operatorn för dimensionen **[!UICONTROL Page Name]** skulle *sökresultat* och *sökresultat* identifieras (men inte *Sök* eller *Resultat* individuellt) och sedan utelämnas dessa objekt. Indatafältet för den här operatorn är blankstegsavgränsat (100 ord). |
| **[!UICONTROL contains any of]** | Returnerar objekt jämfört med delsträngarna, inklusive flera värden som är förenade med eller oberoende av varandra. Om du till exempel anger `Search Results` med den här operatorn skulle det matcha *sökresultat*, *sökresultat*, *sökresultat* och *resultat*. Det skulle matcha antingen *Sök* ELLER *Resultat* som hittades tillsammans eller oberoende av varandra. Indatafältet för den här operatorn är blankstegsavgränsat (100 ord). |
| **[!UICONTROL does not contain any of]** | Identifierar objekt baserat på delsträngar och returnerar sedan värden som inte innehåller dessa delsträngar. Den kan ha flera sammanfogade värden eller värden som identifieras separat. Om du till exempel anger `Search Results` för dimensionen **[!UICONTROL Page Name]** skulle det matcha *sökresultatet* s, *resultaten av sökningen*, *sökningen* och *resultaten* där antingen *sökningen* eller *resultatet* hittas tillsammans eller oberoende av varandra. Då exkluderas objekt som innehåller dessa delsträngar. Indatafältet för den här operatorn är blankstegsavgränsat (100 ord). |
| **[!UICONTROL starts with]** | Returnerar objekt som börjar med det angivna strängvärdet. |
| **[!UICONTROL does not start with]** | Returnerar alla objekt som inte börjar med det angivna strängvärdet. Det här är inversen till operatorn **[!UICONTROL starts with]**. |
| **[!UICONTROL ends with]** | Returnerar objekt som slutar med ett strängvärde angivet. |
| **[!UICONTROL does not end with]** | Returnerar alla objekt som inte slutar med det angivna strängvärdet. Det här är inversen till operatorn **[!UICONTROL ends with]**. |
| **[!UICONTROL matches]** | Returnerar objekt som matchar exakt baserat på ett givet numeriskt värde eller strängvärde. Satsen **[!UICONTROL matches]** är skiftlägeskänslig i Adobe Analytics och Customer Journey Analytics. **Obs!**: Använd den här operatorn när du använder [jokerteckenfunktioner](#wildcards) (globbing). Exempel på&quot;glöd&quot;:<ul><li>`a*e` matchar `ae`, `abcde`, `adobe` och `a whole sentence`</li><li>`adob*` matchar `adobe`, `adobe analytics` och `adobo recipe`</li><li>`*dobe` matchar `dobe`, `adobe` och `cute little dobe`</li></ul> |
| **[!UICONTROL does not match]** | Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet. Obs! Använd den här operatorn när du använder [jokerteckensfunktioner](#wildcards) (globbing). |
| **[!UICONTROL exists]** | Returnerar antalet objekt som finns. Om du till exempel utvärderar dimensionen **[!UICONTROL Pages Not Found]** med operatorn **[!UICONTROL exist]** returneras antalet felsidor som finns. |
| **[!UICONTROL does not exist]** | Returnerar alla objekt som inte finns. Om du till exempel utvärderar dimensionen **[!UICONTROL Pages Not Found]** med operatorn **[!UICONTROL does not exist]** returneras antalet sidor där den här felsidan inte fanns. |

## Data Warehouse operatorer

| Operator | Den valda dimensionen, segmentet eller metriska händelsen... |
| --- | --- |
| **[!UICONTROL is less than]** | Returnerar objekt vars numeriska antal är mindre än det angivna värdet. |
| **[!UICONTROL is less than or equal to]** | Returnerar objekt vars numeriska värde är mindre än eller lika med det angivna värdet. |
| **[!UICONTROL is greater than]** | Returnerar objekt vars numeriska antal är större än det angivna värdet. |
| **[!UICONTROL is greater than or equal to]** | Returnerar objekt vars numeriska värde är större än eller lika med det angivna värdet. |

## Distinkta räkningsoperatorer

Du kan segmentera ett visst antal artiklar i en dimension. Exempel: *Besökare som visade mer än fem olika produkter*, eller *Besök där fler än fem olika sidor sågs*.

| Operator | Den valda dimensionen, segmentet eller metriska händelsen... |
| --- | --- |
| **[!UICONTROL equals]** | Returnerar dimensionsobjekt vars unika antal är lika med det angivna värdet. |
| **[!UICONTROL does not equal]** | Returnerar dimensionsobjekt vars unika antal inte motsvarar det angivna värdet. |
| **[!UICONTROL is greater than]** | Returnerar dimensionsobjekt vars unika antal är större än det angivna värdet. |
| **[!UICONTROL is less than]** | Returnerar dimensionsobjekt vars unika antal är mindre än det angivna värdet. |
| **[!UICONTROL is greater than or equal to]** | Returnerar dimensionsobjekt vars unika antal är större än eller lika med det angivna värdet. |
| **[!UICONTROL is less than or equal to]** | Returnerar dimensionsobjekt vars unika antal är mindre än eller lika med det angivna värdet. |


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Distinkt dimensionsantal](https://video.tv.adobe.com/v/27257?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]
