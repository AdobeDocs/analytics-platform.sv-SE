---
description: Lär dig lägga till komponenter i ett projekt i Analysis Workspace
title: Använda komponenter i Analysis Workspace
feature: Components
role: User
source-git-commit: b02a3954e7b531caabfbea1f7df4e322eb4af741
workflow-type: tm+mt
source-wordcount: '962'
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

   Du kan till exempel dra ett filter till filtersläppzonen i en panelrubrik.

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

Så här lägger du till ett filter i ett projekt i Analysis Workspace:

1. Börja lägga till ett filter i ditt projekt i Analysis Workspace, enligt beskrivningen i [Börja lägga till komponenter i ett projekt](#begin-adding-components-to-a-project).

1. Välj en av följande metoder för att börja filtrera panelen:

   * Dra ett enskilt filter från den vänstra listen till filterdroppområdet.

     ![släppa ett filter i släppzonen](assets/filter-dropzone.png)

   * Håll ned Skift eller Ctrl om du vill markera flera filter i den vänstra listen och håll sedan ned Skift när du släpper dem i filtersläppningsområdet.

     ![släppa flera filter i släppzonen](assets/filter-dropzone-multiple.png)

     Då skapas en nedrullningsbar meny där användarna på panelen kan välja vilket filter de vill använda. Den nedrullningsbara menyn innehåller en [!UICONTROL **Inget filter**] som användare kan markera, vilket lämnar panelen ofiltrerad.

     Du kan välja (x) för att ta bort ett alternativ från listrutan. Om du tar bort [!UICONTROL **Inget filter**] måste du ange ett filter.

   * Skapa ad hoc-filter genom att dra icke-filterkomponenter till släppzonen. Detta kan spara tid och arbete när du går till filterverktyget. Filter som skapas på det här sättet definieras automatiskt som träffnivåfilter. Du kan ändra den här definitionen genom att klicka på informationsikonen (i) bredvid filtret, sedan den pennformade redigeringsikonen och redigera den i Filterverktyget.

     Ad hoc-filter är en typ av snabbfilter och är lokala för projektet. De visas inte i den vänstra listen om du inte gör dem offentliga.

     Mer information finns i [Snabbfilter](/help/components/filters/quick-filters.md).

Mer information om hur du kan använda filtersläppzonen på en panel för att filtrera panelen finns i [Släppzon](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Paneler - översikt](/help/analysis-workspace/c-panels/panels.md).

## Lägga till datumintervall i ett projekt

[Datumintervall](/help/components/date-ranges/custom-date-ranges.md) fastställa tidsramen för rapporteringen i Analysis Workspace och kan tillämpas på en eller flera paneler i ett projekt.

Varje panel innehåller som standard ett datumintervall. Det finns flera sätt att uppdatera ett datumintervall för en panel. Ett sätt att uppdatera ett datumintervall för en panel i Analysis Workspace är att dra en datumintervallkomponent från den vänstra listen:

1. Börja lägga till ett datumintervall i ditt projekt i Analysis Workspace, enligt beskrivningen i [Börja lägga till komponenter i ett projekt](#begin-adding-components-to-a-project).

1. Dra ett datumintervall från den vänstra listen till det aktuella datumintervallet i panelens övre högra del.

   ![släppa ett datumintervall](assets/daterange-drop.png)

Mer information om hur du använder kalendrar och datumintervall i Analysis Workspace finns i [Översikt över kalender- och datumintervall](/help/components/date-ranges/custom-date-ranges.md).
