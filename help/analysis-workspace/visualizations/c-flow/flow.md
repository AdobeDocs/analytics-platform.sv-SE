---
description: Lär dig hur du använder flödesvisualisering i Analysis Workspace.
title: Flödesöversikt
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Flödesöversikt {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Flöde"
>abstract="Skapa en visualisering för att visa flödet av människor från en kontrollpunkt till nästa."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Flöde"
>abstract="Analysera besöksflödet eller besökarna från en kontaktyta till nästa. Ange en komponent (mått, dimension eller artikel) att börja med, att sluta med. Om du vill kan du definiera avancerade inställningar för att ytterligare konfigurera visualiseringen."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Den här artikeln dokumenterar Flow-visualiseringen i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Se [Flow](https://experienceleague.adobe.com/sv/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) för_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]


Visualiseringen ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]** visar kundsökvägar via dina webbplatser och appar.

Med visualiseringen kan du

* Visualisera kundresan via er webbplats eller tillämpning.
* Analysera vart kunderna ska gå före och efter angivna kontrollpunkter, till exempel inmatning, en viss dimension eller avslutning.
* Skapa segment genom att definiera en viss punkt i en vald bana.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Skapa en flödesvisualisering](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

{{videoaa}}

>[!ENDSHADEBOX]


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
