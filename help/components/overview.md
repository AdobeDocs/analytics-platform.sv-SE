---
title: Vad är komponenterna i Customer Journey Analytics?
description: Lär dig vilka komponenter CJA erbjuder och hur du kan använda dem vid rapportering.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: 83a725ac746629874162827d30d5bdf8be0fa6dc
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 9%

---

# Komponenter – översikt

Komponenter är funktioner i Customer Journey Analytics som kan användas i rapporter eller som komplement till rapporteringsfunktioner. Du kan hantera de här komponenterna på följande sätt:

1. Logga in på [analytics.adobe.com](https://analytics.adobe.com) med dina Adobe ID-inloggningsuppgifter.
2. Navigera till [!UICONTROL Components] > [!UICONTROL Components] i rubrikmenyn.

Du kan hantera följande komponenter:

* [**Anteckningar**](/help/components/annotations/overview.md): Kommunicera kontextuella datanunkter och insikter till organisationen. **Den här funktionen är för närvarande [begränsad testning](/help/release-notes/releases.md).**
* [**Filter**](filters/filters-overview.md): Uteslut delar av dina data för att fokusera på gemensamma dimensionsobjekt
* [**Beräknade mått**](calc-metrics/calc-metr-overview.md): Använd mätvärden och formler som nya komponenter för rapportering
* [**Datumintervall**](date-ranges/overview.md): Anpassa och förfina datumintervallen som Analysis Workspace erbjuder
* [**Projekt**](/help/analysis-workspace/home.md): Ordna och underhålla projekt i Analysis Workspace

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

## Behörigheter för komponentåtkomst

I Analysis Workspace kan administratörer [kuratera](/help/analysis-workspace/curate-share/curate.md) vilka komponenter som exponeras för användare vid rapportering.
