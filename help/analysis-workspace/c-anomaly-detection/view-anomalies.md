---
description: Lär dig hur du visar avvikelser i en tabell eller i ett linjediagram.
title: Så här visar du avvikelser i Analysis Workspace
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Visa avvikelser i Analysis Workspace

Du kan visa avvikelser i en tabell eller i ett linjediagram.

## Visa avvikelser i en tabell {#table}

Du kan visa avvikelser i en friformstabell i en tidsserie.

1. Markera ikonen för kolumninställningar i kolumnrubriken och kontrollera sedan att alternativet [!UICONTROL **Anomalier**] är markerat i listan med alternativ. Mer information finns i [Kolumninställningar](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Klicka utanför inställningsmenyn för att visa den uppdaterade tabellen.

   ![Ett avvikelseidentifieringsmeddelande som anger 15 % under förväntat.](assets/anomaly_detected.png)

1. Anomalier visas i tabellen enligt följande:

   En **mörkgrå triangel** visas i det övre högra hörnet av varje rad där en dataavvikelse upptäcks.

   Den **lodräta raden** i varje rad anger det förväntade värdet. Det färgade **skuggade området** i varje rad anger det faktiska värdet. Hur raden (förväntat värde) jämförs med det skuggade området (faktiskt värde) avgör om det finns någon avvikelse. (En observation anses vara onormal baserat på de avancerade statistiska tekniker som beskrivs i [Statistiska tekniker som används vid avvikelseidentifiering](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Markera den grå triangeln i det övre högra hörnet av en rad för att visa detaljer om avvikelsen. Detta visar i vilken utsträckning (i procent) det faktiska värdet avviker antingen över eller under det förväntade värdet.

## Visa avvikelser i ett linjediagram {#line-chart}

Ett linjediagram är den enda visualisering som gör att du kan visa avvikelser.

Så här visar du avvikelser i ett linjediagram:

1. Välj inställningsikonen i visualiseringshuvudet och kontrollera sedan att alternativet [!UICONTROL **Visa avvikelser**] är markerat i listan med alternativ. Mer information finns i [Rad](/help/analysis-workspace/visualizations/line.md).

1. (Valfritt) Om du vill tillåta att konfidensintervallet skalförändrar diagrammet väljer du inställningsikonen i visualiseringshuvudet och väljer sedan alternativet **[!UICONTROL Allow anomalies to Scale Y-axis]**.

   Det här alternativet är inte markerat som standard eftersom det ibland kan göra diagrammet mindre läsbart.

1. Klicka utanför inställningsmenyn för att visa det uppdaterade linjediagrammet.

   ![Ett linjediagram med ett felaktigt identifierat meddelande som anger 15 % högre än förväntat.](assets/anomaly_linechart.png)

   Anomalier visas i linjediagrammet enligt följande:

   En **vit punkt** visas på raden där en dataavvikelse upptäcks. (En observation anses vara onormal baserat på de avancerade statistiska tekniker som beskrivs i [Statistiska tekniker som används vid avvikelseidentifiering](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   Det **ljusa skuggade området** är konfidensintervallet, eller det förväntade intervallet, där värden ska förekomma. Alla värden som ligger utanför det förväntade intervallet är en avvikelse.

   Om du har flera mätvärden i linjediagrammet visas bara avvikelserna, och du måste hålla muspekaren över varje avvikelse för att se konfidensintervallet för det måttet.

   Den **prickade linjen** är det exakta förväntade värdet.

1. Klicka på en avvikelse (vit punkt) om du vill visa följande information:

   * Datumet då avvikelsen inträffade

   * avvikelsens råvärde

   * Procentvärdet över eller under det förväntade värdet, som representeras av den helgröna linjen.

