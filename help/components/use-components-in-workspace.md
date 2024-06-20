---
description: Lär dig lägga till komponenter i ett projekt i Analysis Workspace
title: Använda komponenter i Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 0%

---

# Använda komponenter i Analysis Workspace

Komponenterna utgör själva data i alla projekt i Analysis Workspace. Komponenterna består av mått, mått, filter och datumintervall. Du kan lägga till komponenter i ett projekt genom att dra dem till visualiseringar eller paneler.

Mer information om de typer av komponenter du kan lägga till finns i [Komponenter - översikt](/help/components/overview.md).

>[!TIP]
>
>Om du vill ha information om de olika komponenterna väljer du ikonen Info bredvid en komponents namn i den vänstra listen i Analysis Workspace.

## Börja lägga till komponenter i ett projekt

1. [Skapa ett projekt i Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) om du inte redan gjort det.

1. [Lägga till en panel](/help/analysis-workspace/c-panels/panels.md) eller [lägga till en visualisering](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) till Analysis Workspace.

   Om du lägger till en komponent i ett tomt projekt skapas en frihandsritabellvisualisering automatiskt.

1. Välj **[!UICONTROL Components]** ikonen i den vänstra listen.

   ![](assets/build-components.png)

1. Bläddra till eller sök efter komponenten som du vill lägga till och dra den sedan till en panel eller visualisering i projektet.

1. (Valfritt) Dra en komponent till filtersläppzonen i en panelrubrik.

   Filter gäller för allt innehåll på panelen.

   Mer information om hur du kan använda filtersläppzonen på en panel för att filtrera panelen finns i [Släppzon](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Paneler - översikt](/help/analysis-workspace/c-panels/panels.md).

   ![släppa ett filter i släppzonen](assets/filter-dropzone.png)

1. Mer detaljerad information finns i följande avsnitt, beroende på vilken komponenttyp du lägger till:

   * [Lägga till dimensioner i ett projekt](#add-dimensions-to-a-project)

   * [Lägga till mätvärden i ett projekt](#add-metrics-to-a-project)

   * [Lägga till filter i ett projekt](#add-filters-to-a-project)

   * [Lägga till datumintervall i ett projekt](#add-date-ranges-to-a-project)

## Lägga till dimensioner i ett projekt

[Dimensioner](/help/components/dimensions/overview.md) är variabler i Adobe Analytics som vanligtvis innehåller strängvärden. I motsats till [mått](/help/components/calc-metrics/calc-metr-overview.md) innehåller numeriska värden som är kopplade till en dimension. En grundläggande rapport visar rader med strängvärden (dimension) mot en kolumn med numeriska värden (metrisk).

1. Börja lägga till en dimension i ditt projekt i Analysis Workspace, enligt beskrivningen i [Börja lägga till komponenter i ett projekt](#begin-adding-components-to-a-project).

1. Välj en av följande metoder för att lägga till dimensioner och bestämma vilken typ av data du vill analysera:

   * Dra en dimension till en visualisering (till exempel en frihandstabell) i Analysis Workspace.

     ![Lägga till dimensioner i ett projekt](assets/add-dimensions.png)

   * Dra en eller flera dimensioner från den vänstra listen till filterdroppzonen för att skapa ett ad hoc-filter enligt beskrivningen i [Lägga till filter i ett projekt](#add-filters-to-a-project).

1. (Valfritt) Du kan dela upp dimensioner och dimensionsobjekt i Analysis Workspace med andra komponenter.

   Mer information finns i [Dela upp dimensioner i arbetsytan](/help/components/dimensions/t-breakdown-fa.md).

Mer information om hur du använder dimensioner i Analysis Workspace finns i [Förhandsvisa dimensioner](/help/components/dimensions/view-dimensions.md), [Dela upp dimensioner](/help/components/dimensions/t-breakdown-fa.md)och [Tidsdelningsdimensioner](/help/components/dimensions/time-parting-dimensions.md).

## Lägga till mätvärden i ett projekt

Med mätvärden kan du kvantifiera datapunkter i Analysis Workspace. De används oftast som kolumner i en visualisering och är knutna till dimensioner.

Så här lägger du till en mätmetod i ett projekt i Analysis Workspace:

1. Börja lägga till en mätmetod i ditt projekt i Analysis Workspace, enligt beskrivningen i [Börja lägga till komponenter i ett projekt](#begin-adding-components-to-a-project).

1. Välj en av följande metoder för att lägga till ett mått i Analysis Workspace:

   * Dra ett mätvärde till släppzonen för mätvärden i en tom Freeform-tabell om du vill se mätningen under projektets datumperiod.

     ![Lägga till ett mått i ett projekt](assets/add-metrics.png)

   * Dra ett mätvärde när det finns en dimension för att se mätvärdet jämfört med varje dimensionsobjekt.

   * Dra ett mätresultat över ett befintligt måtthuvud om du vill ersätta det.

   * Dra ett mätvärde bredvid ett huvud om du vill visa båda mätvärdena sida vid sida.

Mer information om mätvärden finns i [Översikt över beräknade mätvärden](/help/components/calc-metrics/calc-metr-overview.md).

## Lägga till filter i ett projekt

[Filter](/help/components/filters/filters-overview.md) gör att du kan identifiera undergrupper av besökare baserat på egenskaper eller specifika interaktioner.

Du kan använda filter i Analysis Workspace på något av följande sätt:

### Lägga till filter på en panel

När du lägger till filter på en panel tillämpas filtren på allt innehåll på panelen.

Mer information om hur du kan använda filtersläppzonen på en panel för att filtrera panelen finns i [Släppzon](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Paneler - översikt](/help/analysis-workspace/c-panels/panels.md).

### Lägga till filter i en kolumn i en frihandstabell

När du lägger till filter i en kolumn i en frihandstabell tillämpas filtren på allt innehåll i tabellkolumnen.

### Använd filter när du skapar beräknade värden

I verktyget Beräknade mätvärden kan du använda filter i måttdefinitionen.

Mer information finns i [Filtrerade mätvärden](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md).

## Lägga till datumintervall i ett projekt

[Datumintervall](/help/components/date-ranges/custom-date-ranges.md) fastställa tidsramen för rapporteringen i Analysis Workspace och kan tillämpas på en eller flera paneler i ett projekt.

Varje panel innehåller som standard ett datumintervall. Det finns flera sätt att uppdatera ett datumintervall för en panel. Ett sätt att uppdatera ett datumintervall för en panel i Analysis Workspace är att dra en datumintervallkomponent från den vänstra listen:

1. Börja lägga till ett datumintervall i ditt projekt i Analysis Workspace, enligt beskrivningen i [Börja lägga till komponenter i ett projekt](#begin-adding-components-to-a-project).

1. Dra ett datumintervall från den vänstra listen till det aktuella datumintervallet i panelens övre högra del.

   ![släppa ett datumintervall](assets/daterange-drop.png)

Mer information om hur du använder kalendrar och datumintervall i Analysis Workspace finns i [Översikt över kalender- och datumintervall](/help/components/date-ranges/custom-date-ranges.md).
