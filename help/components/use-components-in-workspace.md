---
description: Lär dig använda komponenter i ett projekt i Analysis Workspace
title: Använda komponenter i Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 0%

---

# Använda komponenter i ett projekt

Komponenterna utgör själva data i alla projekt i Analysis Workspace. Komponenterna består av mått, mått, segment och datumintervall. Du kan lägga till komponenter i ett projekt genom att dra dem till visualiseringar eller paneler.

Mer information om vilka typer av komponenter du kan lägga till finns i [komponentöversikten](/help/components/overview.md).

>[!TIP]
>
>Använd ![InfoOutline](/help/assets/icons/InfoOutline.svg) om du vill ha information om varje komponent. Mer information finns i [Komponentinformation](#component-info)

## Lägga till komponenter i ett projekt

1. [Skapa ett projekt i Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Lägg till en panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel) eller [lägg till en visualisering](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) i projektet i Analysis Workspace. Om du lägger till en komponent i ett tomt projekt skapas redan en frihandsritabellvisualisering åt dig.

1. Välj ![Kurva](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** på knapppanelen. Alla tillgängliga komponenter visas på den vänstra panelen. Mer information finns i [Gränssnitt](/help/analysis-workspace/home.md#interface).

1. Bläddra till eller sök efter komponenten som du vill lägga till och dra den sedan till en panel eller visualisering i projektet.

1. Du kan också dra en komponent till segmentets släppzon i ett panelhuvud. Den här dra-och-släpp-funktionen definierar komponenten som ett segment och tillämpar segmentet på allt innehåll på panelen.
Mer information om hur du kan använda segmentsläppzonen på en panel för att segmentera panelen finns i [Släppzon](/help/analysis-workspace/c-panels/panels.md#drop-zone) i [Panelöversikt](/help/analysis-workspace/c-panels/panels.md).

1. Mer detaljerad information finns i följande avsnitt:

   * [Lägga till dimensioner i ett projekt](#add-dimensions-to-a-project)

   * [Lägga till mätvärden i ett projekt](#add-metrics-to-a-project)

   * [Lägga till segment i ett projekt](#add-segments-to-a-project)

   * [Lägga till datumintervall i ett projekt](#add-date-ranges-to-a-project)

### Lägga till dimensioner i ett projekt

[Dimensioner](/help/components/dimensions/overview.md) är variabler i Customer Journey Analytics som vanligtvis innehåller strängvärden. [Mått](/help/components/calc-metrics/calc-metr-overview.md) innehåller däremot numeriska värden som är kopplade till en dimension. En grundläggande rapport visar rader med strängvärden (dimension) mot en kolumn med numeriska värden (metrisk).

1. Börja lägga till en dimension i ditt projekt i Analysis Workspace, enligt beskrivningen i [Lägg till komponenter i ett projekt](#add-components-to-a-project).

1. Välj en av följande metoder för att lägga till dimensioner och bestämma vilken typ av data du vill analysera:

   ![Lägg till en dimension](/help/components/assets/add-dimension.gif)

   * Dra en dimension till en visualisering (till exempel en frihandstabell) i Analysis Workspace.

   * Dra en eller flera dimensioner från den vänstra panelen till segmentets släppzon för att skapa ett snabbsegment, enligt beskrivningen i [Lägg till segment i ett projekt](#add-filters-to-a-project).

1. Du kan även dela upp dimensioner och dimensionsobjekt i Analysis Workspace med andra komponenter. Mer information finns i [Dela upp dimensioner i Workspace](/help/components/dimensions/t-breakdown-fa.md).

Mer information om hur du använder dimensioner i Analysis Workspace finns i [Förhandsvisa dimensioner](/help/components/dimensions/view-dimensions.md), [Dela upp dimensioner](/help/components/dimensions/t-breakdown-fa.md) och [Tidsdelningsdimensioner](/help/components/dimensions/time-parting-dimensions.md).

### Lägga till mätvärden i ett projekt

Med mätvärden kan du kvantifiera datapunkter i Analysis Workspace. De används oftast som kolumner i en visualisering och är knutna till dimensioner.

Så här lägger du till en mätmetod i ett projekt i Analysis Workspace:

1. Börja lägga till ett mått i ditt projekt i Analysis Workspace, enligt beskrivningen i [Lägg till komponenter i ett projekt](#add-components-to-a-project).



1. Välj en av följande metoder för att lägga till ett mått i Analysis Workspace:

   ![Lägger till ett mått](/help/components/assets/add-metric.gif)

   * Dra ett mätvärde till släppzonen för mätvärden i en tom Freeform-tabell om du vill se mätningen under projektets datumperiod.

   * Dra ett mått när det finns en dimension för att se måttet för varje dimensionsobjekt.

   * Dra ett mätresultat över ett befintligt måtthuvud om du vill ersätta det.

   * Lägg till det nya måttet genom att dra ett mätvärde till vänster om den högra sidan av en befintlig metrisk rubrik.

   * Dra ett mätresultat ovanför eller under en befintlig måttrubrik om du vill skapa en metrisk överlappning.


Mer information om mått finns i [Metrisk](/help/components/apply-create-metrics.md).

### Lägga till segment i ett projekt

Med [segment](/help/components/segments/seg-overview.md) kan du identifiera deluppsättningar av personer, sessioner eller händelser baserat på egenskaper eller specifika interaktioner.

Du kan använda segment i Analysis Workspace på något av följande sätt:

* Lägga till segment i en panel
När du lägger till segment på en panel används segmenten på allt innehåll på panelen.
Mer information om hur du kan använda segmentsläppzonen på en panel för att segmentera panelen finns i [Släppzon](/help/analysis-workspace/c-panels/panels.md#drop-zone) i [Panelöversikt](/help/analysis-workspace/c-panels/panels.md).

* Lägga till segment i en visualisering
När du lägger till segment i en kolumn i en frihandstabell används segmenten på allt innehåll i tabellkolumnen. Du kan också lägga till segment som en del av en utfallsvisualisering.

* Använda segment i komponenter
När du definierar komponenter som [beräknade mätvärden](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [anteckningar](/help/components/annotations/create-annotations.md#annotation-builder) eller till och med [segment](/help/components/segments/seg-builder.md) kan du använda segment som en del av definitionen.


### Lägga till datumintervall i ett projekt

[Datumintervall](/help/components/date-ranges/overview.md) bestämmer tidsramen för rapportering i Analysis Workspace, och kan tillämpas på en eller flera paneler i ett projekt och även på vissa visualiseringar (till exempel frihandstabellen).

Varje panel innehåller som standard ett datumintervall. Det finns flera sätt att uppdatera ett datumintervall för en panel. Ett sätt att uppdatera ett datumintervall för en panel i Analysis Workspace är att dra en datumintervallkomponent från den vänstra panelen:

1. Du kan också lägga till ett datumintervall i ditt projekt i Analysis Workspace, enligt beskrivningen i [Lägg till komponenter i ett projekt](#add-components-to-a-project).

1. Dra och släpp ett datumintervall från den vänstra panelen till:

   * Det aktuella datumintervallet för att ändra datumintervallet för panelen.

     ![Släpp ett datumintervall](assets/add-date-range.gif)

   * Ett mått eller en dimension i en visualisering av frihandsregister. Mer information finns i [Använd datumintervall](/help/components/date-ranges/overview.md#use-date-ranges).

Mer information om hur du använder och hanterar datumintervall i Analysis Workspace finns i [Översikt över datumintervall](/help/components/date-ranges/overview.md).

## Komponentinformation

Du kan hovra över valfri komponent om du vill visa ![mer information](/help/assets/icons/InfoOutline.svg). När det här alternativet är markerat visas ett popup-fönster med ytterligare information om komponenten.

![Komponentinformation](assets/component-info.png)

Baserat på din åtkomstkontroll kan du:

* Få åtkomst till definitionen ![Bokmärke](/help/assets/icons/Bookmark.svg) [!UICONTROL Data dictionary] för komponenten.
* Få åtkomst till komponentbyggaren ![Redigera](/help/assets/icons/Edit.svg) eller datavyn där komponenten är definierad.
