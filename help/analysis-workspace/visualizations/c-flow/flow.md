---
description: Läs mer om funktionen Flöde som visar kundvägar via era webbplatser och appar.
title: Flödesöversikt
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 0%

---

# Flöde {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Flöde"
>abstract="Skapa en visualisering för att visa flödet av människor från en kontrollpunkt till nästa."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Flöde"
>abstract="Analysera besöksflödet eller besökarna från en kontaktyta till nästa.<br/><br/>**Parametrar **<br/>**Börjar med**: Lägg till en dimension, dimensionsobjekt eller mätvärden för att se de högsta kontaktytorna efter förekomsten av den markerade komponenten.<br/>**Innehåller**: Lägg till en dimension eller ett dimensionsobjekt om du vill visa de övre kontaktytorna före och efter förekomsten av den markerade komponenten.<br/>**Slutar med**: Lägg till en dimension, dimensionsobjekt eller mätvärde för att se de övre kontaktytorna innan den valda komponenten finns.<br/>**Målningsdimension**: Lägg till en dimension som ska användas som vägleda till eller gå från den markerade komponenten."

<!-- markdownlint-enable MD034 -->



Visualiseringen ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]** visar kundsökvägar via dina webbplatser och appar.

Med visualiseringen kan du

* Visualisera kundresan via er webbplats eller tillämpning.
* Analysera vart kunderna ska gå före och efter angivna kontrollpunkter, till exempel inmatning, en viss dimension eller avslutning.
* Skapa filter genom att ange en specifik punkt i en vald bana

+++ Visa en videodemonstration av Flow-visualiseringen.

>[!VIDEO](https://video.tv.adobe.com/v/346063/?quality=12)

{{videoaa}}

+++

## Flerdimensionella flöden

Du kan visa [flödet mellan dimensioner](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Du kan till exempel kombinera sidor och avdelningar i ett diagram. I det här fallet kan ditt flöde gå från startsidan, till Men-sidan och sedan till Shoes-avdelningen.

Varje kolumn kan ha olika dimensioner. Dra en dimension och släpp den i en släppzon för att lägga till den dimensionen i diagrammet.

>[!MORELIKETHIS]
>
>[Konfigurera en flödesvisualisering](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Välj mellan visualiseringar av arbetsytan i Flöde, Utfall eller Resurs

Flödesvisualiseringen har likheter med [Utfallsvisualisering](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) och visualisering av arbetsytan på [Resurs](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), men med viktiga skillnader.

### Förstå skillnaderna

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### När ska Flow användas

Flödesvisualiseringar passar bäst för:

* Förberedande ad hoc-analys för nästa kontaktyta på banan. (Använd arbetsytan på resande fot med en fördefinierad sidsekvens, eller de som använder en slutlig bana.)

* Icke-linjära resor med flera ingångspunkter och sökvägar. (Använd arbetsytan Resa för resor med en fördefinierad sidsekvens.)

Använd [tabellen ovan](#understand-the-differences) för att förstå skillnaderna mellan arbetsytan för Flöde, Utfall och Resa.
