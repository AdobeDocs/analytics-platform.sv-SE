---
description: Använd linjevisualisering för att avbilda trenddata (tidsbaserade)
title: Linjediagram
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 4f163e32787a732526511aeda5f6c1e32becb490
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 3%

---


# Linjediagram

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Radvisualiseringen representerar mätvärden som använder en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram kan bara användas när tid används som dimension.

![Radvisualisering](assets/line-viz.png)

>[!IMPORTANT]
>
>Vissa inställningar för linjevisualisering, till exempel [!UICONTROL Show trendline], är för närvarande i begränsad testning. [Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/landing/an-releases.html)

Klicka på kugghjulsikonen i det övre högra hörnet av linjevisualiseringen för att komma åt [**Visualiseringsinställningarna**](freeform-analysis-visualizations.md) tillgängliga. Inställningarna är indelade i:

* **Allmänt**: Inställningar som är gemensamma för olika visualiseringstyper
* **Axel**: Inställningar som påverkar x- eller y-axeln i linjens visualisering
* **Övertäckningar**: Alternativ för att lägga till ytterligare kontext till de serier som visas i din radvisualisering.

![Visualiseringsinställningar](assets/viz-settings-modal.png)

## Ändra granularitet

Med en listruta för granularitet i [visualiseringsinställningarna](freeform-analysis-visualizations.md) kan du ändra en anpassad visualisering (t.ex. rad, bar) från dag till vecka till månad, osv. Granulariteten uppdateras också i datakälltabellen.

## Visa min eller max

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show min/max]** kan du täcka över en etikett för minsta och högsta värde för att snabbt markera toppar och dalar i ett mätresultat. Obs! min/max-värdena härleds från de synliga datapunkterna i visualiseringen, inte från hela uppsättningen värden inom en dimension.

![Visa min/max](assets/min-max-labels.png)

## Visa trendlinjeövertäckning

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show trendline]** kan du välja att lägga till en regressionstrendlinje i radserien. Trendlinjer hjälper till att beskriva ett tydligare mönster i data.

![Linjär trendlinje](assets/show-linear-trendline.png)

Alla modeller passas in med vanliga minsta fyrkanter:

| Modell | Beskrivning |
| --- | --- |
| Linjär | Skapar en rät linje som passar bäst för enkla linjära datauppsättningar och är användbar när data ökar eller minskar med en konstant hastighet. Ekvation: `y = a + b * x` |
| Logaritmisk | Skapar en kurvformad linje som passar bäst och är användbar när ändringshastigheten i data snabbt ökar eller minskar och sedan Nivåer ut. En logaritmisk trendlinje kan använda negativa och positiva värden. Ekvation: `y = a + b * log(x)` |
| Exponentiell | Skapar en böjd linje och är användbar när data ökar eller minskar med konstant ökande hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: `y = a + e^(b * x)` |
| Strömförsörjning | Skapar en böjd linje och är användbar för datauppsättningar som jämför mått som ökar med en viss hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: `y = a * x^b` |
| Kvadratisk | Söker efter den bästa passningen för en datauppsättning som är formad som en parabola (konkav uppåt eller nedåt). Ekvation: `y = a + b * x + c * x^2` |
