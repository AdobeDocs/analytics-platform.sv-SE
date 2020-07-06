---
title: Vad är kohortanalys?
description: Läs om kohortanalys i Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---


# Vad är [!UICONTROL Cohort Analysis]?

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] är till exempel användbart när du vill veta hur en kohort interagerar med ett varumärke. Du kan enkelt upptäcka ändringar i trender och sedan svara på dem. (Förklaringar [!UICONTROL Cohort Analysis] finns på webben, t.ex. i [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

När du har skapat en kohortrapport kan du strukturera komponenterna (specifika dimensioner, mått och segment) och sedan dela kohortrapporten med vem som helst. Se [Kuratera och dela](/help/analysis-workspace/curate-share/curate.md).

Exempel på vad du kan göra med [!UICONTROL Cohort Analysis]:

* Lansera kampanjer som utformats för att ge önskat resultat.
* Byt marknadsföringsbudget vid exakt rätt tidpunkt i kundlivscykeln.
* Identifiera när en testversion eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer för A/B-testning inom områden som priser, uppgraderingsalternativ osv.
* Visa en [!UICONTROL Cohort Analysis] rapport i en rapport för guidad analys.

[!UICONTROL Cohort Analysis] är tillgängligt för alla Adobe Analytics-kunder med åtkomsträttigheter till [!UICONTROL Analysis Workspace].

[Kohortanalys på YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis]
>
>stöder inte icke-filterbara mått (inklusive beräknade värden), icke-heltalsmått (som Intäkter) eller förekomster. Endast mätvärden som kan användas i segment kan användas i
>[!UICONTROL Cohort Analysis]och de kan bara ökas med 1 i taget.

## Funktioner för kohortanalyser

Följande funktioner gör att du kan finjustera kontrollen över de kohorter du bygger:

### [!UICONTROL Retention] Tabell

En [!UICONTROL Retention] kohortrapport returnerar besökare: varje datacell visar det obearbetade antalet och den procentuella andelen besökare i kohorten som utförde åtgärden under den tidsperioden. Du kan ta med upp till 3 mätvärden och upp till 10 segment.

![](assets/retention-report.png)

### [!UICONTROL Churn] Tabell

En [!UICONTROL Churn] kohort är omvänd till ett kvarhållanderegister och visar de besökare som inte uppfyller eller aldrig uppfyller returkriterierna för din kohort över tiden. Du kan ta med upp till 3 mätvärden och upp till 10 segment.

![](assets/churn-report.png)

### [!UICONTROL Rolling Calculation]

Gör att du kan beräkna kvarhållning eller kurva baserat på föregående kolumn, inte den inkluderade kolumnen.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Tabell

Mäter den tid som har gått före och efter det att inkluderingshändelsen inträffade. Detta är ett utmärkt verktyg för för-/efteranalys. Kolumnen finns i mitten av tabellen och tidsperioder före och efter att inkluderingshändelsen visas på båda sidor. **[!UICONTROL Included]**

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Kohort

Skapa kohorter baserat på en vald dimension, och inte tidsbaserade kohorter, som är standard. Använd dimensioner som [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region]eller andra dimensioner i Adobe Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för dessa dimensioner.

![](assets/cohort-customizable-cohort-row.png)

Instruktioner om hur du konfigurerar och kör en kohortrapport finns i [Konfigurera en kohortanalysrapport](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

