---
description: Lär dig hur du visar avvikelser i en tabell eller i ett linjediagram.
title: Så här visar du avvikelser i Analysis Workspace
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: 16f1a732260ace8393d7303134fc351740fd1661
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 1%

---

# Visa avvikelser i Analysis Workspace

Du kan visa avvikelser i en tabell eller i ett linjediagram.

## Visa avvikelser i en tabell {#table}

Du kan visa avvikelser i en friformstabell i en tidsserie.

1. Markera ikonen för kolumninställningar i kolumnrubriken och kontrollera sedan att [!UICONTROL **Anomalier**] är markerat i listan med alternativ. Mer information finns i [Kolumninställningar](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Klicka utanför inställningsmenyn för att visa den uppdaterade tabellen.

   ![Ett avvikelsedetekteringsmeddelande som anger 15 % lägre än förväntat.](assets/anomaly_detected.png)

1. Anomalier visas i tabellen enligt följande:

   A **mörkgrå triangel** visas i det övre högra hörnet av varje rad där en dataavvikelse upptäcks.

   Den färgade **lodrät linje** på varje rad anger det förväntade värdet. Den färgade **skuggat område** på varje rad anger det verkliga värdet. Hur raden (förväntat värde) jämförs med det skuggade området (faktiskt värde) avgör om det finns någon avvikelse. (En observation anses vara onormal på grundval av de avancerade statistiska tekniker som beskrivs i [Statistiska tekniker som används för avvikelseidentifiering](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Markera den grå triangeln i det övre högra hörnet av en rad för att visa detaljer om avvikelsen. Detta visar i vilken utsträckning (i procent) det faktiska värdet avviker antingen över eller under det förväntade värdet.

## Visa avvikelser i ett linjediagram {#line-chart}

Ett linjediagram är den enda visualisering som gör att du kan visa avvikelser.

Så här visar du avvikelser i ett linjediagram:

1. Välj inställningsikonen i visualiseringshuvudet och kontrollera sedan att [!UICONTROL **Visa avvikelser**] är markerat i listan med alternativ. Mer information finns i [Linje](/help/analysis-workspace/visualizations/line.md).

1. (Valfritt) Om du vill att konfidensintervallet ska kunna skalförändra diagrammet väljer du inställningsikonen i visualiseringshuvudet och väljer sedan alternativet **[!UICONTROL Allow anomalies to Scale Y-axis]**.

   Det här alternativet är inte markerat som standard eftersom det ibland kan göra diagrammet mindre läsbart.

1. Klicka utanför inställningsmenyn för att visa det uppdaterade linjediagrammet.

   ![Ett linjediagram med ett felaktigt meddelande som anger 15 % högre än förväntat.](assets/anomaly_linechart.png)

   Anomalier visas i linjediagrammet enligt följande:

   A **vit punkt** visas på raden där en dataavvikelse upptäcks. (En observation anses vara onormal på grundval av de avancerade statistiska tekniker som beskrivs i [Statistiska tekniker som används för avvikelseidentifiering](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

   The **ljusskuggat område** är konfidensintervallet, eller förväntat intervall, där värden ska förekomma. Alla värden som ligger utanför det förväntade intervallet är en avvikelse.

   Om du har flera mätvärden i linjediagrammet visas bara avvikelserna, och du måste hålla muspekaren över varje avvikelse för att se konfidensintervallet för det måttet.

   The **prickad linje** är det exakta förväntade värdet.

1. Klicka på en avvikelse (vit punkt) om du vill visa följande information:

   * Datumet då avvikelsen inträffade

   * avvikelsens råvärde

   * Procentvärdet över eller under det förväntade värdet, som representeras av den helgröna linjen.

