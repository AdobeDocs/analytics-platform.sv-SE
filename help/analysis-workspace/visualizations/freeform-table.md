---
title: Frihandstabell
description: Läs mer om Freeform-tabeller och Freeform-tabellbyggare
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 1%

---


# Frihandstabell

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

I Analysis Workspace är en Freeform-tabell inte bara en datatabell utan också en interaktiv visualisering. Du kan dra och släppa en kombination av [komponenter](/help/components/overview.md) i raderna och kolumnerna för att skapa en anpassad tabell för analysen. När varje komponent tas bort uppdateras tabellen omedelbart så att du kan göra en snabb analys.

Du kan anpassa tabellen på flera olika sätt:

* **Rader**
   * Varje dimensionsrad kan visa upp till 400 rader innan sidnumrering sker. Du kan anpassa fler rader till en enda skärm genom att justera projektets [vytäthet](/help/analysis-workspace/build-workspace-project/view-density.md).
   * Raderna kan delas upp efter ytterligare komponenter. Om du vill dela upp många rader samtidigt markerar du bara flera rader och drar sedan nästa komponent ovanpå de markerade raderna. Läs mer om [uppdelning](/help/components/dimensions/t-breakdown-fa.md).
   * Rader kan [filtrerad](/help/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md) för att visa en reducerad uppsättning artiklar. Ytterligare inställningar finns under [Radinställningar](/help/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md).

* **Kolumner**
   * Komponenter kan staplas i kolumner för att skapa segmenterade mått, korstabbanalys med mera.
   * Varje kolumnvy kan justeras under [kolumninställningar](/help/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md).
   * Flera åtgärder finns tillgängliga genom [högerklicksmeny](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). Menyn innehåller olika åtgärder beroende på om du klickar på tabellhuvud, rader eller kolumner.

## Freeform Table Builder

Om du vill lägga till flera komponenter i tabellen först och sedan återge data kan du aktivera Freeform Table Builder. Med verktyget aktiverat kan du dra &amp; släppa i många dimensioner, uppdelningar, mått och segment för att skapa tabeller som besvarar mer komplexa frågor. Data kommer inte att uppdateras på flyget, utan uppdateras när du klickar på **[!UICONTROL Build]**.

Tabellbyggaren är ett tidsbesparande alternativ när du har en komplex fråga att ställa om data och du har en uppfattning om tabellen som du vill skapa för att besvara din fråga. Andra fördelar med tabellbyggaren är bland annat möjligheten att:

* Ordna tabellen i det format du behöver, utan att vänta på att varje åtgärd ska återge.
* Utför snabbt upp till 4 nivåer med uppdelning.
* Här definierar du inställningarna för rad och uppdelning för varje tabellrad och dimensionskolumn.
* **[!UICONTROL Breakdown by Position]** för varje tabellnivå som standard (i traditionella frihandstabeller är standardvärdet **[!UICONTROL Breakdown by Item]**.
* Ordna statiska rader manuellt i tabellen. Om du till exempel vill att metriska rader ska visas i en viss ordning.
* Förhandsgranska tabellformatet innan du återger verkliga data.

Se åtgärden Freeform Table Builder i [här](https://youtu.be/GUMWiJAmMGI).

## Exportera frihandstabelldata

Data i en frihandstabell kan kopieras från Analysis Workspace på några sätt:

* Högerklicka på tabellrubriken och välj **[!UICONTROL Copy to Clipboard]**. Då exporteras hela (synliga) tabellen.
* Markera specifika celler i tabellen, högerklicka och markera **[!UICONTROL Copy to Clipboard]** eller använd snabbtangenten Ctrl + C.
* **[!UICONTROL Project > Download CSV]**. Då exporteras alla synliga tabeller i projektet som CSV.
