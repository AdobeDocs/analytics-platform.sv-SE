---
title: Komponenter – översikt
description: Lär dig vilka komponenter CJA erbjuder och hur du kan använda dem vid rapportering.
translation-type: tm+mt
source-git-commit: c1699c4319b3b840d8420f3ffa1a4bd1c1d9a4d4
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 17%

---


# Komponenter – översikt

Komponenter är funktioner i Customer Journey Analytics som kan användas i rapporter eller komplettera rapporteringsfunktioner. Du kan hantera de här komponenterna på följande sätt:

1. Logga in på [analytics.adobe.com](https://analytics.adobe.com) med dina Adobe ID-inloggningsuppgifter.
2. Navigera till [!UICONTROL Components] > [!UICONTROL Components] i rubrikmenyn.

Du kan hantera följande komponenter:

* [**Filter**](filters/filters-overview.md): Uteslut delar av dina data för att fokusera på gemensamma dimensionsobjekt
* [**Beräknade mått**](calc-metrics/calc-metr-overview.md): Använd mätvärden och formler som nya komponenter för rapportering
* [**Datumintervall**](date-ranges/overview.md): Anpassa och förfina datumintervallen som Analysis Workspace erbjuder
* [**Projekt**](/help/analysis-workspace/home.md): Ordna och underhålla projekt i Analysis Workspace

## Analysis Workspace-komponenter

Komponenterna i Analysis Workspace består av mått, dimensioner, segment och tidsdetaljer som du kan dra och släppa i ett projekt. Anpassade komponenter som du skapar läggs till i dessa paneler, till exempel anpassade datumintervall.

Du öppnar panelen Komponenter genom att klicka på ikonen **[!UICONTROL Components]** i den vänstra listen. Du kan växla mellan paneler (Tom panel, [Frihandspanel](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Snabbinsikter](/help/analysis-workspace/c-panels/quickinsight.md) eller [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) panel), [Visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) och Komponenter med ikonerna för vänster spår eller genom att använda [snabbtangenter](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

Mer information om hur du använder komponenter i ett projekt finns i [Skapa ett projekt](/help/analysis-workspace/home.md).

## Komponentåtgärder

Du kan hantera komponenter (individuellt eller genom att markera flera) på flera olika sätt. Högerklicka på en komponent eller klicka på **[!UICONTROL Actions]** högst upp i komponentlistan.

>[!NOTE]
>
>Dessa åtgärder gäller inte för tidskomponenter.

| Komponentåtgärd | Beskrivning |
|--- |--- |
| Tagg | Ordna eller hantera komponenter genom att lägga till taggar i dem. Sedan visas de i respektive komponenthanterare, som Analytics > Komponenter > Segment eller Analytics > Komponenter > Projekt. |
| Favorit | Lägg till komponenten i listan med favoriter. Sedan visas de i respektive komponenthanterare, som Analytics > Komponenter > Segment eller Analytics > Komponenter > Projekt. |
| Godkänn | Godkänn komponenten för att göra den kanonisk. Sedan visas de i respektive komponenthanterare, som Analytics > Komponenter > Segment eller Analytics > Komponenter > Projekt. |
| Dela | Gäller endast segment. |
| Ta bort | Gäller endast segment. |

Se videon Creating Metrics, Segments, and Dates:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Behörigheter för komponentåtkomst

Administratörer kan styra (via [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products)) vilka komponenter som exponeras för användare vid rapportering. I följande tabell visas hur de här åtkomstbehörigheterna för komponenter fungerar:

| Kurvtyp | Administratören kan se | Projektägaren (eller redigeringsrollen) som inte är administratör kan se | Duplicerad roll som inte är administratör |
| --- | --- | --- | --- |
| **Komponenter&quot;dolda&quot; från en datavy** | Alla datavykomponenter som är tillgängliga för rapportering (dolda komponenter kräver att du klickar på Visa alla) | Ej tillgängligt för rapportering | Ej tillgängligt för rapportering |
| **Komponenter som har lagts till eller tagits bort från en datavy** | Endast komponenter som har lagts till i datavyn (dolda eller inte dolda). Administratörer kan inte rapportera fält eller komponenter som inte har definierats i datavyn. | Endast komponenter som har lagts till i datavyn, eller komponenter som ägs eller delas med användaren. Dolda komponenter är inte tillgängliga (som VRS-kurering). | Endast komponenter som lagts till i DV-filen är inte dolda och har inkluderats i projektkurationen. |
| **Kuraterade komponenter i ett projekt** | Alla datavykomponenter som är tillgängliga för rapportering (dolda komponenter kräver att du klickar på Visa alla) | Alla icke-dolda datavykomponenter (kräver att du klickar på Visa alla) | Endast förvaltade komponenter, plus eventuella komponenter som ägs eller delas med användaren |
| **Kuraterat projekt med en datavy med dolda komponenter** | Alla datakomponenter som är tillgängliga för rapportering (dolda och icke-förvaltade komponenter kräver att du klickar på Visa alla) | Alla icke-förvaltade projektkomponenter, alla icke-dolda datavykomponenter och alla komponenter som ägs eller delas med användaren | Endast förvaltade komponenter, plus alla komponenter som ägs eller delas med användaren |

