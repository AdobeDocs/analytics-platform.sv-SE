---
title: Översikt över kohortabellen
description: Lär dig använda en kohorttabell för kohortanalys i Analysis Workspace
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 353993c14103906553d87738ed3f7fc0926e123c
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 0%

---

# Översikt över kohortabellen {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Kohortabell"
>abstract="Skapa en kohortvisualisering för att gruppera användare baserat på slutförandet av en händelse och analysera det pågående engagemanget och bortfallet över tid."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Kohortabell"
>abstract="Gruppera användarna efter att ha slutfört en händelse, analysera sedan deras pågående engagemang och kraschar över tid.<br/><br/>**Parametrar **<br/>**Inkluderingskriterier**: De komponenter som används för att definiera den inledande besökarkohorten.<br/>**Returvillkor**: Komponenterna som används för att avgöra om en besökare har returnerat."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*I den här artikeln beskrivs kohorttabellen i **Customer Journey Analytics**.<br/>Se [Kohorttabell](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis) för **Adobe Analytics**-versionen av den här artikeln.*

>[!ENDSHADEBOX]


En *kohort* är en grupp personer som delar gemensamma egenskaper under en angiven period. En ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Cohort table]**-visualisering är till exempel användbar när du vill veta hur en kohort interagerar med ett varumärke. Du kan enkelt upptäcka ändringar i trender och sedan svara på dem. (Förklaringar av [!UICONTROL Cohort Analysis] finns på webben, till exempel [Kohortanalys 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

När du har skapat en kohortrapport kan du strukturera komponenterna (specifika dimensioner, mätvärden och filter) och sedan dela kohortrapporten med vem som helst. Se [Kuratera och dela](/help/analysis-workspace/curate-share/curate.md).

Exempel på vad du kan göra med en [!UICONTROL Cohort table]:

* Lansera kampanjer som är utformade för att ge önskat resultat.
* Byt marknadsföringsbudget vid exakt rätt tidpunkt i kundlivscykeln.
* Identifiera när en testversion eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer för A/B-testning inom områden som priser, uppgraderingsalternativ osv.

[!UICONTROL Cohort table] är tillgängligt för alla Customer Journey Analytics-kunder med åtkomstbehörighet till [!UICONTROL Analysis Workspace].

+++ Visa en videodemonstration av kohorttabellen.

>[!VIDEO](https://video.tv.adobe.com/v/23990/?quality=12)

{{videoaa}}

+++

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] stöder inte icke-filterbara mått (inklusive beräknade värden), icke-heltalsmått (till exempel Intäkter) eller förekomster. Endast mätvärden som kan användas i filter kan användas i [!UICONTROL Cohort Analysis], och de kan bara ökas med 1 åt gången.

Kohorttabeller i Customer Journey Analytics stöder dubbelbaserade (eller numeriska) mätvärden. Exempel: Purchase.Value (en dubbel) kan användas som Inkluderings-/returmått. Dessutom fördubblas också alla mätvärden som skickas till Adobe Experience Platform via Analytics Source Connector.

## Cohort table capabilities

I följande avsnitt beskrivs kohortanalysfunktioner som gör det möjligt att finjustera kontrollen över kohorterna som du bygger.

Mer information om hur du skapar en kohort och kör en [!UICONTROL Cohort Analysis]-rapport finns i [Konfigurera en kohorttabell](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention]-tabell

En [!UICONTROL Retention]-kohorttabell returnerar personer: varje datacell visar det råa antalet och procentandelen personer i kohorten som utförde åtgärden under den tidsperioden. Du kan ta med upp till 3 mätvärden och upp till 10 filter.

![En återgivningskohortrapport som visar enheter och procent av personerna i kohorten.](assets/retention-report.png)

### [!UICONTROL Churn]-tabell

En [!UICONTROL Churn]-kohorttabell är omvänd till en kvarhållningstabell och visar de personer som inte uppfyller eller aldrig uppfyller returkriterierna för din kohort över tiden. Du kan ta med upp till 3 mätvärden och upp till 10 filter.

![En Churn-tabell som visar enheter och procentandel av personer som inte uppfyller returkriterierna för en kohort.](assets/churn-report.png)

### [!UICONTROL Rolling Calculation]

Du kan beräkna kvarhållning eller bortfall baserat på föregående kolumn, inte den inkluderade kolumnen, som kallas rullande beräkning.

![En CSS-kvarhållningsrapport som visar beräkningar baserade på en tidigare datakolumn.](assets/retention-report-rolling.png)

### [!UICONTROL Latency]-tabell

En latenstabell mäter den tid som har gått före och efter det att inkluderingshändelsen inträffade. Mätning av fördröjning är ett utmärkt verktyg för för- och efteranalys. Kolumnen **[!UICONTROL Included]** finns i mitten av tabellen och tidsperioder före och efter inkluderingshändelsen visas på båda sidor.

![En kohortrapport som visar förfluten tid före och efter en händelse.](assets/retention-report-latency.png)

### [!UICONTROL Custom dimension]-kohort

Du kan skapa kohorter baserat på en vald dimension och inte på tidsbaserade kohorter (som är standard). Använd dimensioner som [!UICONTROL City geo], [!UICONTROL Marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region] eller någon annan dimension för att visa hur kvarhållandet ändras. Baserat på de olika värdena för de här dimensionerna.

![En kohortrapport som visar en anpassad rapport med valda dimensioner är inte standardtidsbaserad kohort.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Konfigurera en kohorttabell](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

