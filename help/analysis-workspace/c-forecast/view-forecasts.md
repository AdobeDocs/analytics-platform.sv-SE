---
description: Lär dig hur du visar prognoser i en tabell eller i ett linjediagram.
title: Så här visar du prognoser i Analysis Workspace
feature: Visualizations
role: User
source-git-commit: e52cee369be75785a99798d5acfa9cfc5aba2986
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Visa prognoser i Analysis Workspace

Du kan visa prognoser i en frihandstabell eller i ett linjediagram.

## Visa prognoser i en tabell

Du kan visa prognoser i en friformstabell i tidsserier. När Visa prognos är aktiverat för frihandsregister i [användarinställningar](../user-preferences.md), visas prognoser automatiskt för den första måttkolumnen som läggs till i tabellen. För ytterligare kolumner:

1. Markera ikonen för kolumninställningar ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) i kolumnrubriken kontrollerar du att **[!UICONTROL Show forecast]** är markerat i listan med alternativ. Mer information finns i [Kolumninställningar](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Klicka utanför **[!UICONTROL Column settings]** för att spara inställningen och visa den uppdaterade tabellen.

I tabellen visas prognoser enligt följande:

![Visa prognos i register](assets/show-forecast-table.png)

* Prognosvärdet och procentandelen för varje cell visas i **mörkgrå**.
* En prognossymbol anger ett prognosvärde <img src="./assets/forecast.svg" alt="Prognossymbol" width="20" /> visas i cellens övre högra hörn.


## Visa prognoser i ett linjediagram

Ett linjediagram är den enda visualisering som gör att du kan visa prognoser.

1. Välj inställningsikonen ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) i visualiseringshuvudet kontrollerar du att **[!UICONTROL Show forecast]** är markerat i listan med alternativ.

1. (valfritt) Välj **[!UICONTROL Allow forecast to scale Y-axis]**. Det här alternativet är inte markerat som standard eftersom det ibland kan återge ett mindre läsbart diagram.

1. Klicka utanför **[!UICONTROL Settings]** för att visa det uppdaterade linjediagrammet.

Prognoser visas i linjediagrammet enligt följande:

![Visa prognos i linjediagram](assets/show-forecast-linechart.png)

* De aktuella värdena för måtten i linjediagrammet anges med ett lodrätt streck. Om du för muspekaren över den lodräta raden visas en popup med det senaste aktuella datumet.
* Prognosvärden för ett eller flera mätvärden visas direkt från det lodräta strecket med prickade linjer. Du kan hovra över valfri datapunkt för ett mätresultat. Då visas ett popup-fönster med:
   * prognosdatum
   * prognostiserat värde för måttet
   * övre gräns för prognostiserat värde för mätvärdet
   * nedre gräns för prognostiserat värde för mätvärdet
* det skuggade området visar prognosens konfidensintervall.

