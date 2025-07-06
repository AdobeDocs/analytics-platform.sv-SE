---
description: Lär dig hur du visar prognoser i en tabell eller i ett linjediagram.
title: Visa prognoser
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# Visa prognoser

Du kan visa prognoser i en frihandstabell eller i ett linjediagram.

## Visa prognoser i en tabell

Du kan visa prognoser i en friformstabell i tidsserier. När [!UICONTROL Show forecast] är aktiverat för friformstabellen i [användarinställningarna](../user-preferences.md) visas prognoser automatiskt för den första måttkolumnen som läggs till i tabellen. För ytterligare kolumner:

1. Markera ikonen för kolumninställningar ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) i kolumnrubriken och kontrollera sedan att **[!UICONTROL Show forecast]** är markerat i listan med alternativ. Mer information finns i [Kolumninställningar](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Klicka utanför menyn **[!UICONTROL Column settings]** om du vill spara inställningen och visa den uppdaterade tabellen.

I tabellen visas prognoser enligt följande:

![Visa prognos i tabell](assets/show-forecast-table.png)

* Prognosvärdet och procentandelen för varje cell visas i **mörkgrått**.
* Om du vill ange ett prognosvärde visas prognossymbolen ![ForecastAnalytics](/help/assets/icons/ForecastAnalytics.svg) i cellens övre högra hörn.


## Visa prognoser i ett linjediagram

Ett linjediagram är den enda visualisering som gör att du kan visa prognoser.

1. Välj inställningsikonen ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) i visualiseringshuvudet och kontrollera sedan att **[!UICONTROL Show forecast]** är markerat i listan med alternativ.

1. (valfritt) Välj **[!UICONTROL Allow forecast to scale Y-axis]** om du vill tillåta att prognoserna skalar diagrammet korrekt. Det här alternativet är inte markerat som standard eftersom det ibland kan återge ett mindre läsbart diagram.

1. Klicka utanför menyn **[!UICONTROL Settings]** om du vill visa det uppdaterade linjediagrammet.

Prognoser visas i linjediagrammet enligt följande:

![Visa prognos i linjediagram](assets/show-forecast-linechart.png)

* De aktuella värdena för måtten i linjediagrammet anges med ett lodrätt streck. Om du för muspekaren över den lodräta raden visas en popup med det senaste aktuella datumet.
* Prognosvärden för ett eller flera mätvärden visas direkt från det lodräta strecket med prickade linjer. Du kan hovra över valfri datapunkt för ett mätresultat. Då visas ett popup-fönster med:
   * prognosdatum
   * prognostiserat värde för måttet
   * övre gräns för prognostiserat värde för mätvärdet
   * nedre gräns för prognostiserat värde för mätvärdet
* I det skuggade området visas prognosens konfidensintervall.
