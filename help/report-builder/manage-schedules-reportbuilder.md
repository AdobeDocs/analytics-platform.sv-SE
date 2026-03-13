---
title: Hantera schemalagda arbetsböcker i Report Builder
description: Lär dig hantera schemalagda arbetsböcker i Report Builder.
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 0a0427d9-223e-410b-a8ef-8601390d88aa
source-git-commit: 9d5c895672e422a82ef68b0af6cd85359c9b11ea
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# Hantera schemalagda arbetsböcker

Du kan schemalägga en arbetsbok för delning via e-post eller genom att exportera den till ett molnmål, vilket beskrivs i följande artiklar:

* [Schemalägg arbetsböcker genom delning via e-post](/help/report-builder/schedule-reportbuilder.md)

* [Schemalägg arbetsböcker för export till molnmål](/help/report-builder/report-builder-export.md)

I följande avsnitt beskrivs hur du hanterar arbetsböcker efter att de har schemalagts:

## Visa och hantera schemalagda arbetsböcker

Du kan visa och hantera alla schemalagda arbetsböcker på fliken **[!UICONTROL Workbooks]**.

1. Välj **[!UICONTROL Schedule]** i Report Builder-hubben

1. Välj fliken **[!UICONTROL Workbooks]**. Du ser en lista över alla schemalagda arbetsböcker. (Du kan också välja fliken **[!UICONTROL Legacy]** om du vill visa en lista över äldre arbetsböcker som behöver migreras till den nya Report Builder.)

   ![Schemalagd arbetsbok](assets/scheduled-workbooks.png){zoomable="yes"}

1. Gör något av följande:

   * Håll muspekaren över ikonen om du vill visa statusen för en schemalagd arbetsbok.

   * Sök efter specifika schemalagda arbetsböcker i sökfältet ![Sök](/help/assets/icons/Search.svg).

   * Välj kolumnikonen ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att definiera vilka kolumner som ska visas.

   * Markera filterikonen ![Filterikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) och välj sedan [!UICONTROL **Visa alla**] för att visa alla schemalagda arbetsböcker för en viss organisation.

1. Markera en eller flera arbetsböcker.

   ![Schemalägg arbetsböcker har valts](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   Följande alternativ är tillgängliga:

   | Alternativ | Beskrivning |
   |---|---|
   | ![Redigera](/help/assets/icons/Edit.svg) | Redigera schemat för en vald arbetsbok. |
   | ![Historik](/help/assets/icons/History.svg) | Visa historiken för valda arbetsböcker. |
   | ![Paus](/help/assets/icons/Pause.svg) | Pausa schemat för markerade arbetsböcker. |
   | ![Spela upp](/help/assets/icons/Play.svg) | Återuppta schemat för valda arbetsböcker. |
   | ![Hämta](/help/assets/icons/Download.svg) | Hämta den markerade arbetsboken till en ny arbetsbok. |
   | ![Ta bort](/help/assets/icons/Delete.svg) | Ta bort schemat för valda arbetsböcker. |


## Historik och status för schemalagda arbetsböcker

Du kan visa historik och status för schemalagda arbetsböcker på fliken **[!UICONTROL History]**.

1. Välj **[!UICONTROL Schedule]** i Report Builder-navet.

1. Välj fliken **[!UICONTROL History]**. Du ser en lista över alla schemalagda arbetsböcker.

   ![Schemalagd historik](assets/scheduled-workbooks-history.png){zoomable="yes"}

   Använd ![Sök](/help/assets/icons/Search.svg) om du vill söka efter specifika arbetsböcker i listan.
Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att definiera vilka kolumner som ska visas.

   På fliken **[!UICONTROL History]** kan du granska statusen för varje schemalagd aktivitet. En separat rad visar statusändringen för varje schemalagd aktivitet.

   * En ![CheckCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg) anger att arbetsboken har skickats.
   * Ett ![AlertRed](/help/assets/icons/AlertRed.svg) indikerar att ett fel har inträffat.

Du kan också välja ![Historik](/help/assets/icons/History.svg) för en eller flera markerade arbetsböcker på fliken **[!UICONTROL Workbooks]**. Den här åtgärden visar fliken **[!UICONTROL History]** med en lista filtrerad efter din markering. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort ett filter.
