---
description: Använd radvisualisering för att visa trenderade (tidsbaserade) datauppsättningar
title: Linjediagram
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: afe5b341ea1b442c23561299fbffce59dae45930
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 3%

---


# Linjediagram

Visualiseringen av linjen representerar mått med hjälp av en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram kan bara användas när tiden används som dimension.

![Radvisualisering](assets/line-viz.png)

>[!IMPORTANT]
>
>Vissa inställningar för visualisering av linjer, t.ex. [!UICONTROL Show trendline], för närvarande testas i begränsad omfattning. [Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/landing/an-releases.html)

Klicka på redskapsikonen högst upp till höger om linjens visualisering för att komma åt [**Visualiseringsinställningar**](freeform-analysis-visualizations.md) tillgänglig. Inställningarna kategoriseras i:

* **Allmänt**: Inställningar som är gemensamma för visualiseringstyper
* **Axel**: Inställningar som påverkar x- eller y-axeln för linjens visualisering
* **Överlägg**: Alternativ för att lägga till ytterligare kontext till serien som visas i radvisualiseringen.

![Visualiseringsinställningar](assets/viz-settings-modal.png)

## Ändra granularitet

En granularitetslistruta i [visualiseringsinställningar](freeform-analysis-visualizations.md) Med kan du ändra en trenderad visualisering (t.ex. linje, streck) från dag till vecka, till månad osv. Granulariteten uppdateras också i datakälltabellen.

## Visa min eller max

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show min/max]** kan du täcka över en minimi- och maximivärdesetikett för att snabbt markera topparna och dalarna i ett mått.

![Visa min/max](assets/min-max-labels.png)

## Visa trendlinjeövertäckning

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show trendline]** kan du välja att lägga till en regressionstrendlinje i radserien. Trendlinjer kan användas för att beskriva ett tydligare mönster i data.

![Linjärt trendlinje](assets/show-linear-trendline.png)

Alla modeller passar med vanliga fyrkanter:

| Modell | Beskrivning |
|---|---|
| Linjär | Skapar en rät linje som passar bäst för enkla linjära datauppsättningar och är användbar när data ökar eller minskar i jämn takt. Ekvation: `y = a + b * x` |
| Logarithmic | Skapar en kurvlinje som passar bäst och är användbar när ändringshastigheten i data ökar eller minskar snabbt och sedan överför. En logaritmisk trendlinje kan använda negativa och positiva värden. Ekvation: `y = a + b * log(x)` |
| Exponentiell | Skapar en böjd linje och är användbar när data ökar eller minskar med konstant ökande hastighet. Det här alternativet ska inte användas om data innehåller noll eller negativa värden. Ekvation: `y = a + e^(b * x)` |
| Ström | Skapar en kurvrad och är användbar för datauppsättningar som jämför mätningar som ökar med en viss hastighet. Det här alternativet ska inte användas om data innehåller noll eller negativa värden. Ekvation: `y = a * x^b` |
| Kvadratisk | Söker efter den bästa passningen för en datauppsättning som formas som en parabola (konkav upp eller ned). Ekvation: `y = a + b * x + c * x^2` |
