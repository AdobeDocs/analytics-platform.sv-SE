---
title: Frihandstabell
description: Läs mer om frihandsritningar och frihandsritningstabeller
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 1%

---


# Frihandstabell

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

I Analysis Workspace är en frihandstabell inte bara en datatabell, utan även en interaktiv visualisering. Du kan dra och släppa en kombination av [komponenter](/help/components/overview.md) i rader och kolumner för att skapa en anpassad tabell för analysen. När varje komponent släpps uppdateras tabellen omedelbart så att du kan göra en snabb analys.

Du kan anpassa tabellen på flera olika sätt:

* **Rader**
   * Varje dimensionsrad kan visa upp till 400 rader, innan sidnumreringen görs. Du kan anpassa fler rader till en enda skärm genom att justera projektets [visningsdensitet](/help/analysis-workspace/build-workspace-project/view-density.md).
   * Rader kan delas upp efter ytterligare komponenter. Om du vill dela upp flera rader samtidigt markerar du bara flera rader och drar sedan nästa komponent över de markerade raderna. Läs mer om [uppdelningar](/help/components/dimensions/t-breakdown-fa.md).
   * Rader kan [filtreras](/help/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md) för att visa en reducerad uppsättning med objekt. Ytterligare inställningar finns under [Radinställningar](/help/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md).

* **Kolumner**
   * Komponenter kan staplas i kolumner för att skapa segmenterade mätvärden, tabbanalyser med mera.
   * Vyn för varje kolumn kan justeras under [kolumninställningarna](/help/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md).
   * Flera åtgärder är tillgängliga via [högerklicksmenyn](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). Menyn innehåller olika åtgärder beroende på om du klickar på tabellhuvudet, raderna eller kolumnerna.

## Bygg frihandstabell

Om du föredrar att lägga till flera komponenter i tabellen först och sedan återge data, kan du aktivera Frihand tabellverktyg. Med verktyget aktiverat kan du dra och släppa i många dimensioner, uppdelningar, mätvärden och segment för att skapa tabeller som besvarar mer komplexa frågor. Data uppdateras inte direkt, utan uppdateras när du klickar **[!UICONTROL Build]**.

Table Builder är ett tidsbesparande alternativ när du har en komplex fråga om data och du har en uppfattning om tabellen som du vill konstruera för att besvara din fråga. Andra fördelar med tabellbyggaren är möjligheten att:

* Ordna tabellen i det format du behöver, utan att behöva vänta på att varje åtgärd ska återges.
* Utför snabbt upp till fyra nivåer av uppdelningar.
* Definiera rad- och brytningsinställningarna för varje tabellrad och dimensionskolumn.
* **[!UICONTROL Breakdown by Position]** för alla nivåer i tabellen som standard (i traditionella frihandstabeller är standardvärdet **[!UICONTROL Breakdown by Item]**.)
* Ordna statiska rader manuellt i tabellen. Om du till exempel vill att måttrader ska visas i en viss ordning.
* Förhandsgranska tabellformatet innan du återger verkliga data.

Se hur Frihand tabellbyggaren fungerar [här](https://youtu.be/GUMWiJAmMGI).

## Exportera frihandstabelldata

Data i en friformstabell kan kopieras från Analysis Workspace på några sätt:

* Högerklicka på tabellrubriken och välj **[!UICONTROL Copy to Clipboard]**. Den fullständiga (synliga) tabellen exporteras.
* Markera specifika celler i tabellen, högerklicka och markera **[!UICONTROL Copy to Clipboard]** eller använd snabbtangenten Ctrl + C.
* **[!UICONTROL Project > Download CSV]**. Då exporteras alla synliga tabeller i projektet som en CSV-fil.
