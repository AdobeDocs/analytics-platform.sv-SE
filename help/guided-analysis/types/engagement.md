---
title: Åtagandevy
description: Förstå bredden och djupet av engagemanget.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: 670443a8caf6b71f49fc63a23b5328609864a9be
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# [!UICONTROL Engagement] visa

The **[!UICONTROL Engagement]** ger insikt i hur ofta en funktion används jämfört med hur många som använder den. Den här analysen fungerar bäst när flera funktioner jämförs. Det hjälper er att fatta investeringsbeslut genom att förstå vad era kärnfunktioner, er kraft, engångsfunktioner och tvivelaktiga funktioner är.

Funktioner som pekar mot toppen av den här visualiseringen visar att de ofta används av engagerade användare. Funktioner som pekar åt höger om den här visualiseringen visar att de används av många av dina aktiva användare. Medianvärdet för hur många gånger en funktion används dividerar diagrammet vågrätt. Procentandelen aktiva användare delar diagrammet lodrätt. Medianer beräknas baserat på händelser som valts i frågan, inte alla data.

* Funktionerna längst upp till vänster i matrisen är **effekt** funktioner, som inte används i någon större utsträckning, men ofta används av engagerade användare.
* Funktionerna i matrisens övre högra hörn är **hög effekt** funktioner; de är både allmänt använda och ofta använda.
* Funktionerna längst ned till vänster i matrisen är **låg effekt** funktioner; de används inte i någon större utsträckning eller ofta.
* Funktionerna längst ned till höger i matrisen är **en gång** funktioner; de är vida spridda, men används inte ofta.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)

## Användningsexempel

Exempel:

* **Engagemang efter funktion**: Du kan fastställa ett direkt samband mellan engagemang och användning av en viss funktion. Att förstå vilka funktioner som används mest kan hjälpa till att avgöra vilka funktioner som ska investeras ytterligare.
* **Upptäck underanvända funktioner**: Funktioner med användare med låg aktivitet men hög användning kan tyda på en kraftfull funktion, en som är värdefull men inte upptäcks eller används av en större befolkning. Överväg att förbättra upptäckten av dessa funktioner så att fler användare utnyttjar dem.
* **Förbättra populära funktioner**: Funktioner med aktiva användare men låg användning kan tyda på att en funktion är efterfrågad men underanvänd. Dessa situationer ger möjligheter att lära sig mer av användarna om vilka förbättringar som skulle göra funktionen mer värdefull för dem.
* **Skapa funktionsbaserade segment**: Visa funktionsanvändning på det här sättet för att få fler analysmöjligheter. Skapa ett segment för vilken punkt som helst i diagrammet för att dyka ytterligare in i användargruppen och tillämpa dessa inlärningar på er strategi för användarengagemang.
* **A/B-testning av nya funktioner**: Jämför användningen av flera funktioner för olika användargrupper. Lägg till segment i frågespelaren för att avgöra skillnaden i funktionsanvändning mellan nyckelanvändargrupper.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Events]**: De händelser som du vill mäta. Varje händelse representerar användningen av en viss funktion och visas som en punkt i matrisen. Du kan inkludera upp till tio händelser. Medianvärdet beräknas baserat på de händelser som valts.
* **[!UICONTROL Counted as]**: Längs x-axeln kan du mäta den genomsnittliga procentandelen aktiva användare varje dag, vecka, månad eller kvartal. Y-axeln justerar automatiskt genomsnittstiden per användare baserat på x-axelns markering.
* **[!UICONTROL Segments]**: De segment som du vill mäta. Varje markerat segment dubblerar antalet plottade punkter i diagrammet och raderna i tabellen. Du kan inkludera upp till tre segment.

>[!TIP]
>
>Om flera händelser representerar användning av en enda funktion kan du skapa en ny händelse som representerar funktionen i datavyer.

## Diagraminställningar

The [!UICONTROL Engagement] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Medians]**: Avgör var medianinjerna visas och hur de plottade punkterna relaterar till medianerna.
   * **[!UICONTROL Standard]**: Visa det absoluta värdet av användning och engagemang.
   * **[!UICONTROL Normalized]**: Visa relativa ändringar från varje median.
* **[!UICONTROL Top events overlay]**: Se hur dina händelser fungerar jämfört med de 20 vanligaste händelserna, baserat på företagets och användarens senaste aktivitet och relevans (samma algoritm som används för händelseväljaren i frågespelaren).

## Tidsjämförelse

{{apply-time-comparison}}

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa trenddata efter. Den här vytypen behandlar [!UICONTROL Interval] liknar [!UICONTROL Counted as] i frågefältet. Timvis aktiva användare stöds inte.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
