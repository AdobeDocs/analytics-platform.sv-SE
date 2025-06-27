---
description: Lär dig hur du använder ett histogram, som liknar ett stapeldiagram, men grupperar nummer i intervall (intervall).
title: Histogram
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 2%

---

# Histogram {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histogram"
>abstract="Skapa en histogramvisualisering som representerar fördelningen av numeriska data i grupper av intervall."


>[!BEGINSHADEBOX]

_I den här artikeln dokumenteras histogramvisualiseringen i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Se [Histogram](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/histogram) för_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]


Visualiseringen av ![histogrammet](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogram]** liknar en [!UICONTROL Bar]-visualisering, men grupperar nummer i intervall (bucket). Analytics automatiserar&quot;paketeringen&quot; av tal i intervall, men du kan ändra inställningarna i [Avancerade inställningar](#advanced-settings).

## Använd

Skapa ett histogram:

1. Lägg till en ![histogram](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogram]**-visualisering. Se [Lägga till en visualisering på en panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Dra ett mätvärde från komponentlistan **[!UICONTROL Metrics]** eller välj ett mätvärde i listrutan [!UICONTROL *Lägg till ett mätvärde*] .
1. (valfritt) Välj **[!UICONTROL Show advanced settings]**. Se [Avancerade inställningar](#advanced-settings).
1. Välj **[!UICONTROL Build]**.

>[!NOTE]
>
>Histogram stöder endast standardvärden, inte beräknade värden.

I exemplet nedan används ett histogram för att bucket-sessioner för antalet personer. Histogrammet visar att de flesta personer har mellan 16 och 21 sessioner för det valda datumintervallet.

![Histogram](assets/histogram.png)

## Avancerade inställningar

Som en del av visualiseringen är specifika histograminställningar tillgängliga.

| Histograminställningar | Beskrivning |
|---|---|
| **[!UICONTROL Starting bucket]** | Anger vilken bucket histogrammet börjar med. &quot;1&quot; är standardvärdet. Du kan ange startnummer från 0 till oändlighet (inga negativa tal). |
| **[!UICONTROL Metric buckets]** | Gör att du kan öka/minska antalet dataintervall (bucket). Det högsta antalet bucklor är 50. |
| **[!UICONTROL Metric bucket size]** | Gör att du kan ange storleken för varje bucket. Du kan till exempel ändra bucketstorleken från en sidvy till två sidvyer. |
| **[!UICONTROL Counting method]** | Välj mellan **[!UICONTROL Global Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Buying Group]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Person]**, **[!UICONTROL Session]** eller **[!UICONTROL Event]**. Till exempel sidvisningar per konto [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, sidvisningar per session eller sidvisningar per person eller sidvisningar per händelse. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exempel**:

| Startar bucket | Måttbucklar | Storlek på måttpyts | Resultat |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogram, med startintervall 1, metriska bucket 5, metrisk bucketstorlek 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogram, med startintervall 0, metriska intervall 3, metrisk bucket 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Lägg till en visualisering på en panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Visualiseringsinställningar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Snabbmenyn Visualisering ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>&#x200B;>[Identifiera oväntade datavärden med histogram ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

