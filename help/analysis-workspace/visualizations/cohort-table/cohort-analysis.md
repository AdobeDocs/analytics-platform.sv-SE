---
title: Vad är Cohort Analysis?
description: Läs mer om kohortanalys i Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---


# Vad är det? [!UICONTROL Cohort Analysis]?

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

A *`cohort`* är en grupp personer som har gemensamma kännetecken under en viss period. [!UICONTROL Cohort Analysis] är till exempel användbart när du vill lära dig hur en kohort hanterar ett varumärke. Du kan enkelt upptäcka förändringar i trender och sedan svara på lämpligt sätt. (Förklaringar av [!UICONTROL Cohort Analysis] finns tillgängliga på webben, t.ex. på [Kohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).

När du har skapat en kohortrapport kan du kurvera dess komponenter (specifika dimensioner, mått och segment) och sedan dela kohortrapporten med vem som helst. Se [Kurva och dela](/help/analysis-workspace/curate-share/curate.md).

Exempel på vad du kan göra med [!UICONTROL Cohort Analysis]:

* Starta kampanjer som utformats för att sporra till önskad åtgärd.
* Flytta marknadsföringsbudgeten vid exakt rätt tidpunkt i kundens livscykel.
* Känn igen när en prövning eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer om A/B-testning på områden som prissättning, uppgraderingsväg osv.
* Visa en [!UICONTROL Cohort Analysis] rapportera inom en Guided Analysis-rapport.

[!UICONTROL Cohort Analysis] är tillgänglig för alla Adobe Analytics-kunder med åtkomsträttigheter till [!UICONTROL Analysis Workspace].

[Cohort Analysis on YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) 4:36)

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis]
>
>stöder inte icke-filterbara mått (inklusive beräknade mått), heltalsmått (t.ex. Intäkter) eller Händelser. Endast mått som kan användas i segment kan användas i
>[!UICONTROL Cohort Analysis]och de kan bara ökas med 1 i taget.

## Cohort Analysis-funktioner

Med följande funktioner kan du finjustera kontrollen över de kohorter du bygger:

### [!UICONTROL Retention] Tabell

A [!UICONTROL Retention] I kohortrapporten visas besökare: Varje datacell visar det råa antalet och procentandelen besökare i kohorten som utförde åtgärden under den perioden. Du kan inkludera upp till 3 mått och upp till 10 segment.

![](assets/retention-report.png)

### [!UICONTROL Churn] Tabell

A [!UICONTROL Churn] Kohort är omvänd till ett retentionstabell och visar de besökare som föll ut eller aldrig uppfyllde kriterierna för återresa för din kohort över tiden. Du kan inkludera upp till 3 mått och upp till 10 segment.

![](assets/churn-report.png)

### [!UICONTROL Rolling Calculation]

Gör att du kan beräkna kvarhållning eller kurva baserat på föregående kolumn, inte den inkluderade kolumnen.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Tabell

Mäter den tid som förflutit före och efter det att införandet skedde. Detta är ett utmärkt verktyg för förhands-/efterhandsanalys. De **[!UICONTROL Included]** kolumnen är i tabellens mittpunkt och tidsperioder före och efter inkluderingshändelsen visas på båda sidor.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Skapa kohorter baserat på en vald dimension, och inte tidsbaserade kohorter, som är standard. Använd dimensioner, t.ex. [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region]eller någon annan dimension i Adobe Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för dessa dimensioner.

![](assets/cohort-customizable-cohort-row.png)

Instruktioner om hur du konfigurerar och kör en kohortrapport finns i [Konfigurera en Cohort Analysis-rapport](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

