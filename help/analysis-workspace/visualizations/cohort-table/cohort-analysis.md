---
title: Vad är kohortanalys?
description: Läs om kohortanalys i Analysis Workspace
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 0%

---

# Vad är [!UICONTROL Cohort Analysis]?

En *`cohort`* är en grupp personer som delar gemensamma egenskaper under en angiven period. [!UICONTROL Cohort Analysis] är till exempel användbart när du vill veta hur en kohort interagerar med ett varumärke. Du kan enkelt upptäcka ändringar i trender och sedan svara på dem. (Förklaringar av [!UICONTROL Cohort Analysis] finns på webben, till exempel [Kohortanalys 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

När du har skapat en kohortrapport kan du strukturera komponenterna (specifika dimensioner, mätvärden och filter) och sedan dela kohortrapporten med vem som helst. Se [Kuratera och dela](/help/analysis-workspace/curate-share/curate.md).

Exempel på vad du kan göra med [!UICONTROL Cohort Analysis]:

* Lansera kampanjer som är utformade för att ge önskat resultat.
* Byt marknadsföringsbudget vid exakt rätt tidpunkt i kundlivscykeln.
* Identifiera när en testversion eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer för A/B-testning inom områden som priser, uppgraderingsalternativ osv.

[!UICONTROL Cohort Analysis] är tillgängligt för alla Customer Journey Analytics-kunder med åtkomstbehörighet till [!UICONTROL Analysis Workspace].

[Videosjälvstudie om kohortanalys](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] stöder inte icke-filterbara mått (inklusive beräknade värden), icke-heltalsmått (till exempel Intäkter) eller förekomster. Endast mätvärden som kan användas i filter kan användas i [!UICONTROL Cohort Analysis], och de kan bara ökas med 1 åt gången.

## Funktioner för kohortanalyser

Följande funktioner gör att du kan finjustera kontrollen över de kohorter du bygger:

### [!UICONTROL Retention]-tabell

En [!UICONTROL Retention]-kohortrapport returnerar personer: varje datacell visar det råa antalet och procentandelen personer i kohorten som utförde åtgärden under den tidsperioden. Du kan ta med upp till 3 mätvärden och upp till 10 filter.

![En återgivningskohortrapport som visar enheter och procent av personerna i kohorten.](assets/retention-report.png)

### [!UICONTROL Churn]-tabell

En [!UICONTROL Churn]-kohort är omvänd till en kvarhållningstabell och visar de personer som inte uppfyller eller aldrig uppfyller returkriterierna för din kohort över tiden. Du kan ta med upp till 3 mätvärden och upp till 10 filter.

![En Churn-tabell som visar enheter och procentandel av personer som inte uppfyller returkriterierna för en kohort.](assets/churn-report.png)

### [!UICONTROL Rolling Calculation]

Gör att du kan beräkna kvarhållning eller kurva baserat på föregående kolumn, inte den inkluderade kolumnen.

![En CSS-kvarhållningsrapport som visar beräkningar baserade på en tidigare datakolumn.](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency]-tabell

Mäter den tid som har gått före och efter det att inkluderingshändelsen inträffade. Detta är ett utmärkt verktyg för för-/efteranalys. Kolumnen **[!UICONTROL Included]** finns i mitten av tabellen och tidsperioder före och efter inkluderingshändelsen visas på båda sidor.

![En kohortrapport som visar förfluten tid före och efter en händelse.](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension]-kohort

Skapa kohorter baserat på en vald dimension, och inte tidsbaserade kohorter, som är standard. Använd dimensioner som [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region] eller någon annan dimension i Customer Journey Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för de här dimensionerna.

![En kohortrapport som visar en anpassad rapport med valda dimensioner är inte standardtidsbaserad kohort.](assets/cohort-customizable-cohort-row.png)

Instruktioner om hur du konfigurerar och kör en kohortrapport finns i [Konfigurera en kohortanalysrapport](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
