---
title: Attributionspanel
description: Lär dig använda och tolka attribueringspanelen i Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 8%

---

# Attributionspanelen {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Tillskrivning"
>abstract="Jämför och visualisera snabbt valfritt antal attribueringsmodeller med framgångsmått, kanal- och uppslagsfönster."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panelen Attribution IQ"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Attributionspanelen"
>abstract="Jämför och visualisera snabbt valfritt antal attribueringsmodeller för ett framgångsmått. Markera kanalen (dimensionen), modellerna som ska inkluderas och uppslagsfönstret."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panelen Attribution IQ"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Den här artikeln dokumenterar panelen Attribution i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Se [Attribution panel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/attribution) för_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]

Panelen **[!UICONTROL Attribution]** är ett enkelt sätt att skapa en analys som jämför olika attribueringsmodeller. Panelen innehåller en dedikerad arbetsyta för att använda och jämföra attribueringsmodeller.

Customer Journey Analytics förbättrar attribueringen genom att du kan:

* Definiera attribuering bortom betalda medier: Alla dimensioner, mätvärden, kanaler eller händelser kan tillämpas på modeller (till exempel intern sökning), inte bara marknadsföringskampanjer.
* Använd obegränsad jämförelse av attribueringsmodell: jämför dynamiskt så många modeller du vill.
* Undvik implementeringsändringar: Med rapporttidsbearbetning och sammanhangsberoende sessioner kan kundens reskontext byggas in och tillämpas vid körning.
* Skapa den session som bäst matchar attribueringsscenariot.
* Dela upp attribuering efter segment: Jämför enkelt resultatet i era marknadsföringskanaler i alla viktiga segment (till exempel nya kontra upprepade kunder, produkt X jämfört med produkt Y, lojalitetsnivå eller CLV).
* Granska analyser av kontaktytor och kanalbyten: använd venndiagram och histogram samt trendattribuering.
* Analysera viktiga marknadsföringssekvenser visuellt: utforska vägar som leder till konvertering visuellt med flernodsflöde och bortfallsvisualisering.
* Skapa beräknade värden: använd valfria metoder för attribueringstilldelning.

## Använd

Så här använder du en **[!UICONTROL Attribution]**-panel:

1. Skapa en **[!UICONTROL Attribution]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.

### Panelindata

Du kan konfigurera panelen Attribution med följande indatainställningar:

1. Lägg till en **[!UICONTROL Success metric]** och en dimension från **[!UICONTROL Channel]** som du vill attributera mot. Exempel är marknadskanaler eller anpassade dimensioner, som interna kampanjer.

   ![Panelfönstret Attribution visar flera valda dimensioner och mått.](assets/attribution-panel.png)

1. Välj en eller flera [attribueringsmodeller](#attribution-models) från **[!UICONTROL Included models]** och ett [uppslagsfönster](#lookback-window) från **[!UICONTROL Lookback window]** som du vill använda för jämförelse.

1. Välj **[!UICONTROL Build]** om du vill skapa visualiseringar i panelen.

### Panelutdata

Panelen **[!UICONTROL Attribution]** returnerar en mängd data och visualiseringar som jämför attribuering för den valda dimensionen och måttet.

![Visualiseringar av panelen Attribution som jämför valda mått och mått.](assets/attr_panel_vizs.png)

### Attributvisualiseringar

Följande visualisering är en del av panelutdata.

* **Totalt mått**: Det totala antalet konverteringar som inträffade under rapporttidsperioden och som är kopplade till den dimension som du valde.
* **Attribution Comparison Bar**: Jämför de tilldelade konverteringarna visuellt för alla dimensionsobjekt från den valda dimensionen. Varje stapelfärg representerar en distinkt attribueringsmodell.
* **Attributjämförelsetabell**: Visar samma data som stapeldiagrammet, representerat som en tabell. Om du markerar olika kolumner eller rader i den här tabellen segmenteras stapeldiagrammet och flera av de andra visualiseringarna på panelen. Den här tabellen fungerar på ungefär samma sätt som andra frihandstabeller i Workspace, vilket gör att du kan lägga till komponenter som mått, segment och uppdelningar.
* **Överlappningsdiagram**: En Vennvisualisering som visar de tre viktigaste dimensionsobjekten och hur ofta de deltar tillsammans i en konvertering. Storleken på bubbelöverlappningen anger till exempel hur ofta konverteringar inträffade när en person exponerades för båda dimensionsobjekten. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Prestandainformation**: En spridningsvisualisering för att jämföra upp till tre attribueringsmodeller visuellt.
* **Trended Performance**: Visar trenden för konverteringar av attribut för den översta dimensionsobjektet. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Flöde**: Gör att du kan se vilka kanaler som interagerar mest och i vilken ordning de interagerar under en persons resa.

## Attributionsmodeller

{{attribution-models-details}}

## Behållare

{{attribution-container}}

## Fönstret Lookback

{{attribution-lookback-window}}

## Exempel

{{attribution-example}}

>[!MORELIKETHIS]
>
> [Skapa en panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
