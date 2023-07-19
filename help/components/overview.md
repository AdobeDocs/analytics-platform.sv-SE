---
title: Vad är komponenterna i Customer Journey Analytics?
description: Lär dig vilka komponenter Customer Journey Analytics erbjuder och hur du kan använda dem vid rapportering.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: 202a726dc68853f55a24e566c656c92785e3b3f0
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 5%

---

# Komponenter – översikt

Komponenter är funktioner i Customer Journey Analytics som kan användas i rapporter eller som komplement till rapporteringsfunktioner. Du kan hantera de här komponenterna på följande sätt:

1. Logga in på [analytics.adobe.com](https://analytics.adobe.com) med dina Adobe ID-inloggningsuppgifter.
2. Navigera till [!UICONTROL Components] > [!UICONTROL Components] i rubrikmenyn.

Du kan hantera följande komponenter:

* [**Anteckningar**](/help/components/annotations/overview.md): Kommunicera kontextuella datanunkter och insikter till organisationen.
* [**Målgrupper**](/help/components/audiences/audiences-overview.md): Skapa och publicera målgrupper som upptäcks i Customer Journey Analytics till [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCDP) i Adobe Experience Platform för kundanpassning och personalisering.
* [**Filter**](filters/filters-overview.md): Skapa, hantera, dela och lägg på kraftfulla filter för riktade målgrupper i era rapporter. Med filter kan du identifiera delmängder av personer baserat på egenskaper eller interaktioner.
* [**Beräknade mått**](calc-metrics/calc-metr-overview.md): Använd mätvärden och formler som nya komponenter för rapportering
* [**Dataordlista**](/help/components/data-dictionary/data-dictionary-overview.md): Hjälper både användare och administratörer att hålla reda på och förstå komponenterna i sin Analytics-miljö bättre.
* [**Datumintervall**](date-ranges/create.md): Anpassa och förfina datumintervallen som Analysis Workspace erbjuder.
* [**Dimensioner**](/help/components/dimensions/view-dimensions.md): Dimensioner är variabler som vanligtvis innehåller strängvärden. Vanliga dimensioner är Page och Reference domain.
* [**Mått**](/help/components/apply-create-metrics.md): Gör att du kan kvantifiera datapunkter i Analysis Workspace.
* [**Projekt**](/help/analysis-workspace/home.md): Ordna och underhåll dina projekt i Analysis Workspace.

## Analysis Workspace-komponenter

Komponenterna i Analysis Workspace består av mätvärden, dimensioner, filter och tidsdetaljer som du kan dra och släppa i ett projekt. Anpassade komponenter som du skapar läggs till i dessa paneler, till exempel anpassade datumintervall.

Du öppnar panelen Komponenter genom att klicka på **[!UICONTROL Components]** ikonen i den vänstra listen. Du kan växla mellan paneler (panelen Tom, [Frihandspanelen](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Snabba insikter](/help/analysis-workspace/c-panels/quickinsight.md), eller [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) panel), [Visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)och komponenter som använder ikonerna för den vänstra listen eller med [snabbtangenter](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

Se [Skapa ett projekt](/help/analysis-workspace/home.md) om du vill ha information om hur du använder komponenter i ett projekt.

## Komponentåtgärder

Du kan hantera komponenter (individuellt eller genom att markera flera) på flera olika sätt. Högerklicka på en komponent eller klicka **[!UICONTROL Actions]** längst upp i komponentlistan.

>[!NOTE]
>
>Dessa åtgärder gäller inte för tidskomponenter.

| Komponentåtgärd | Beskrivning |
| --- | --- |
| Tagg | Ordna eller hantera komponenter genom att lägga till taggar i dem. Sedan visas den i respektive komponenthanterare, som [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Filters], eller [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects] |
| Favorit | Lägg till komponenten i listan med favoriter. Sedan visas den i respektive komponenthanterare, som [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL filters], eller [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects]. |
| Godkänn | Godkänn komponenten för att göra den kanonisk. Sedan visas den i respektive komponenthanterare, som [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Filters], eller  [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects] |
| Dela | Gäller endast filter. |
| Ta bort | Gäller endast filter. |

Se videon Creating Metrics, Filters, and Dates:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Hantera komponenter {#actions}

Du kan hantera komponenter direkt i den vänstra listen.

1. Högerklicka på en komponent.

   eller

   Markera en komponent och markera sedan **Åtgärd** (3 punkter) längst upp i komponentlistan.

   >[!TIP]
   >
   >   Du kan markera flera komponenter genom att hålla ned Skift, eller genom att hålla ned Kommando (Mac) eller Ctrl (Windows).


   ![](assets/component-actions.png)

   | Komponentåtgärd | Beskrivning |
   |--- |--- |
   | [!UICONTROL **Tagg**] | Ordna eller hantera komponenter genom att lägga till taggar i dem. Du kan sedan söka efter tagg i den vänstra listen genom att klicka på filtret eller skriva #. Taggar fungerar också som filter i komponenthanterarna. |
   | [!UICONTROL **Favorit**] | Lägg till komponenten i listan med favoriter. Precis som med taggar kan du söka efter Favoriter i den vänstra listen och filtrera efter dem i komponenthanterarna. |
   | [!UICONTROL **Godkänn**] | Markera komponenter som godkända för att signalera till användarna att komponenten är godkänd för organisationen. Precis som med taggar kan du söka efter Godkänd i den vänstra listen och filtrera efter dem i komponenthanterarna. |
   | [!UICONTROL **Dela**] | Dela komponenter med användare i organisationen. Det här alternativet är endast tillgängligt för anpassade komponenter, till exempel filter eller beräknade värden. |
   | [!UICONTROL **Ta bort**] | Ta bort komponenter som du inte längre behöver. Det här alternativet är endast tillgängligt för anpassade komponenter, till exempel filter eller beräknade värden. |

Anpassade komponenter kan också hanteras med respektive komponenthanterare. Till exempel [Hantera filter](/help/components/filters/manage-filters.md).

## Söka, filtrera och sortera komponentlistan

Du kan söka efter, filtrera och sortera komponentlistan i den vänstra listen i Analysis Workspace för att snabbt hitta en viss komponent.

### Sök i komponentlistan

1. Välj **Komponenter** icon ![Ikon för komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) till vänster.

2. I sökfältet börjar du skriva namnet på komponenten som du vill använda i ditt projekt.

   Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension, ikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) är orange, **Filter** ![Filterikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) är blå, **Datumintervall** ![Ikon för datumintervall](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) är lila, och **Mått** ![Mätningsikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) är gröna. Ikonen Adobe ![Adobe, ikon](assets/default-calc-metric-icon.png) anger antingen en mall för beräknade mätvärden eller en filtermall och räkningsikonen ![Beräkningsikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) har angett ett beräknat mått som har skapats av en Analytics-administratör i organisationen.

3. Markera komponenten när den visas i listrutan.

### Filtrera komponentlistan

1. Välj **Komponenter** icon ![Ikon för komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) till vänster.

2. Välj **Filter** icon ![Ikon för dataordlistefilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)).

   eller

   Skriv nummertecknet (#) i sökfältet.

3. Välj något av följande filteralternativ för att filtrera komponentlistan:

   | Alternativ |  -funktion |
   |---------|----------|
   | [!UICONTROL **Godkänd**] | Visa endast komponenter som har markerats som Godkänd av en administratör. |
   | [!UICONTROL **Favoriter**] | Visa endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Hantera komponenter](#manage-components). |
   | [!UICONTROL **Dimensioner**] | Visa endast komponenter som är Dimensioner. |
   | [!UICONTROL **Mätvärden**] | Visa endast komponenter som är mätvärden. |
   | [!UICONTROL **Filter**] | Visa endast komponenter som är filter. |
   | [!UICONTROL **Datumintervall**] | Visa endast komponenter som är datumintervall. |
   | [!UICONTROL **Visa alla**] | Visa alla komponenter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Ej godkänt**] | Visa endast komponenter som ännu inte har markerats som Godkända av en administratör. Som administratör är detta användbart när du identifierar komponenter som kräver granskning och godkännande. Det här alternativet är endast tillgängligt för administratörer. |

4. (Valfritt) Om du vill finjustera listan ytterligare kan du sortera komponentlistan enligt beskrivningen i [Sortera komponentlistan](#sort-the-component-list).

### Sortera komponentlistan

{{release-limited-testing-section}}

1. (Valfritt) Tillämpa eventuella filter på komponentlistan enligt beskrivningen i [Filtrera komponentlistan](#filter-the-component-list).

2. Välj **Komponenter** icon ![Ikon för komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) till vänster.

3. Välj **Sortera** icon ![Ikon för att sortera komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)väljer du sedan något av följande filteralternativ för att sortera komponentlistan:

   {{components-sort-options}}

## Behörigheter för komponentåtkomst

I Analysis Workspace kan administratörer [kuratera](/help/analysis-workspace/curate-share/curate.md) vilka komponenter som exponeras för användare vid rapportering.
