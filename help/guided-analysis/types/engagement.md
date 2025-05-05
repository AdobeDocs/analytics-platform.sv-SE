---
title: Förlovningsanalys
description: Förstå bredden och djupet av engagemanget.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---

# [!UICONTROL Engagement]-analys {#engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_engagement_button"
>title="Engagemang"
>abstract="Förstå bredden och djupet av engagemanget."

<!-- markdownlint-enable MD034 -->


Analysen ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) **[!UICONTROL Engagement]** ger dig insikt i hur ofta en funktion används jämfört med hur många som använder den. Den här analysen fungerar bäst när flera funktioner jämförs. Det hjälper er att fatta investeringsbeslut genom att förstå vad era kärnfunktioner, er kraft, engångsfunktioner och tvivelaktiga funktioner är.

Funktioner som pekar mot toppen av den här visualiseringen visar att de ofta används av engagerade användare. Funktioner som pekar åt höger om den här visualiseringen visar att de används av många av dina aktiva användare. Medianvärdet för hur många gånger en funktion används dividerar diagrammet vågrätt. Procentandelen aktiva användare delar diagrammet lodrätt. Medianer beräknas baserat på händelser som valts i frågan, inte alla data.

* Funktionerna i det övre vänstra hörnet av matrisen är dina **kraftfulla**-funktioner. De används inte särskilt mycket, men används ofta av engagerade användare.
* Funktionerna i matrisens övre högra hörn är dina **högkvalitativa**-funktioner. De används både ofta och i stor omfattning.
* Funktionerna längst ned till vänster i matrisen har **låg effekt** och används inte särskilt mycket.
* Funktionerna längst ned till höger i matrisen är dina **engångs**-funktioner. De används ofta, men inte ofta.

>[!VIDEO](https://video.tv.adobe.com/v/3447471?captions=swe)


## Användningsexempel

Användningsexempel för den här analysen är:

* **Engagemang efter funktion**: Du kan upprätta en direkt korrelation mellan engagemang och användning av en viss funktion. Att förstå vilka funktioner som används mest kan hjälpa till att avgöra vilka funktioner som ska investeras ytterligare.
* **Upptäck underanvända funktioner**: Funktioner med låga aktiva användare men hög användning kan visa på en kraftfull funktion, en som är värdefull men inte upptäcks eller används av den bredare befolkningen. Överväg att förbättra upptäckten av dessa funktioner så att fler användare utnyttjar dem.
* **Förbättra populära funktioner**: Funktioner med högaktiva användare, men låg användning kan tyda på att en funktion är efterfrågad men underanvänd. Dessa situationer ger möjligheter att lära sig mer av användarna om vilka förbättringar som skulle göra funktionen mer värdefull för dem.
* **Skapa funktionsbaserade segment**: Visar funktionsanvändning på det här sättet för att få fler analysmöjligheter. Skapa ett segment för vilken punkt som helst i diagrammet för att dyka ytterligare in i användargruppen och tillämpa dessa inlärningar på er strategi för användarengagemang.
* **A/B-testning**: Jämför användningen av flera funktioner i olika användargrupper. Lägg till segment i frågespelaren för att avgöra skillnaden i funktionsanvändning mellan nyckelanvändargrupper.

## Gränssnitt

I [Gränssnitt](../overview.md#interface) finns en översikt över gränssnittet för guidad analys. Följande inställningar är specifika för den här analysen:

### Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Events]**: De händelser som du vill mäta. Varje händelse representerar användningen av en viss funktion och visas som en punkt i matrisen. Du kan inkludera upp till tio händelser. Medianvärdet beräknas baserat på de händelser som valts.
* **[!UICONTROL Counted as]**: Utmed x-axeln kan du mäta den genomsnittliga procentandelen aktiva användare per dag, vecka, månad eller kvartal. Y-axeln justerar automatiskt genomsnittstiden per användare baserat på x-axelns markering.
* **[!UICONTROL Segments]**: Segmenten som du vill mäta. Varje markerat segment dubblerar antalet plottade punkter i diagrammet och raderna i tabellen. Du kan inkludera upp till tre segment.

>[!TIP]
>
>Om flera händelser representerar användning av en enda funktion kan du skapa en ny händelse som representerar funktionen i datavyer.

### Diagraminställningar

Analysen av [!UICONTROL Engagement] innehåller följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **[!UICONTROL Medians]**: Avgör var medianinjerna visas och hur de plottade punkterna relaterar till medianerna.
   * **[!UICONTROL Standard]**: Visa det absoluta värdet av användning och engagemang.
   * **[!UICONTROL Normalized]**: Visa relativa ändringar från varje median.
* **[!UICONTROL Top events overlay]**: Se hur dina händelser fungerar jämfört med de 20 vanligaste händelserna, baserat på företagets och användarens senaste och relevanta händelser (samma algoritm som tillämpas på händelseväljaren i frågespelaren).

### Tidsjämförelse

{{apply-time-comparison}}

### Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa trenddata efter. Den här analysen behandlar [!UICONTROL Interval] på ungefär samma sätt som [!UICONTROL Counted as] i frågerinjen. Timvis aktiva användare stöds inte.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
