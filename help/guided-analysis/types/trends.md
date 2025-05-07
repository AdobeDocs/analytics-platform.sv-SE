---
title: Trendanalys
description: Mät användarengagemanget över tid.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
role: User
source-git-commit: e42f04eaa06a761803e76b64a5a16674fb4af57d
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 0%

---

# [!UICONTROL Trends]-analys {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="Trender"
>abstract="Mät användarengagemanget över tid."

<!-- markdownlint-enable MD034 -->

Analysen ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Trends]** ger värdefull information om produktens prestanda eller användarnas beteende över tid. Den vågräta axeln i den här rapporten är ett tidsintervall, medan den lodräta axeln mäter dina önskade händelser.


>[!VIDEO](https://video.tv.adobe.com/v/3432438/?quality=12&learn=on&captions=swe)

## Användningsexempel

Användningsexempel för den här analysen är:

* **Utvärdera produktprestanda**: Med hjälp av trender kan du utvärdera produktens totala prestanda under en viss period. Genom att analysera mätvärden som användarengagemang, användning och konverteringsgrader kan ni identifiera om produktens prestanda förbättras, stagnerar eller försämras.
* **Funktionsinförande**: Med trender kan du förstå hur användare antar nya funktioner eller uppdateringar som du släpper. Du kan avgöra vilka funktioner som är populära och vilka som behöver förbättras. Med den här informationen kan ni fatta datadrivna beslut om vilka funktioner ni ska prioritera utvecklingsarbetet kring.
* **Användarbeteende**: Trender kan ge insikt i användarbeteendet över tid. Genom att undersöka specifika åtgärder som användare utför kan du identifiera mönster där användare kan släppa av. Du kan kombinera insikter från den här analysen med [Funnel](funnel.md) om du vill ha ännu mer information om beteendet.
* **A/B-testning och -experiment**: Om du kör A/B-tester i produkten kan du använda Trends för att mäta vilka tester som är mest framgångsrika över tid.

## Gränssnitt

I [Gränssnitt](../overview.md#interface) finns en översikt över gränssnittet för guidad analys. Följande inställningar är specifika för den här analysen:

### Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan den här analysen och [frekvens](frequency.md).
* **[!UICONTROL Events & Metrics]**: De händelser eller mått som du vill mäta. Varje markering representeras som en diagramserie och tabellrad. Det går inte att kombinera händelser och mätvärden i frågan. När du har gjort ditt första val måste de återstående frågevalen vara av samma typ. Du kan ta med upp till fem markeringar.
* **[!UICONTROL Counted as]**: Den beräkningsmetod som du vill använda för de markerade händelserna. <ul><li>**[!UICONTROL Options]** omfattar [!UICONTROL Users], [!UICONTROL Events], [!UICONTROL Sessions], [!UICONTROL Percentage of users], [!UICONTROL Events per session] och [!UICONTROL Events per user].</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} Additional **[!UICONTROL B2B options]** är tillgängligt för Customer Journey Analytics B2B edition: [!UICONTROL Global accounts], [!UICONTROL Accounts], [!UICONTROL Buying groups], [!UICONTROL Opportunities], [!UICONTROL Percentage of global accounts], [!UICONTROL Percentage of accounts], [!UICONTROL Percentage of buying groups], [!UICONTROL Percentage of opportunities], [!UICONTROL Events per global account], [!UICONTROL Events per account], [!UICONTROL Events per buying group] och [!UICONTROL Events per opportunity].</li></ul>Räknat som alternativ kan endast användas för händelsefrågor och tas bort för metriska frågor.
* **[!UICONTROL Segments]**: Segmenten som du vill mäta. Varje markerat segment dubblerar antalet diagramserier och tabellrader. Du kan inkludera upp till fem segment.
* **[!UICONTROL Breakdown property]**: Delar upp diagramserien och tabellraderna med värdena för den valda egenskapen. En enda uppdelningsegenskap stöds. De översta 20 värdena visas i tabellen och upp till tio värden kan visas i diagrammet. Du kan dölja eller visa en rad i diagrammet genom att växla ikonen ![Visa/dölj](../assets/hide-in-chart.png) .

### Diagraminställningar

Analysen av [!UICONTROL Trends] innehåller följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Du kan välja mellan Linje, Stapel, Staplad liggande och Staplad yta.

### Övertäckningar

Lägg till ytterligare data i diagrammet. När fler än en serie visas i diagrammet visas övertäckningarna endast vid hovring.

* **[!UICONTROL Anomaly detection]**: Kör [avvikelseidentifiering](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) i den trendanalys. Exponenter visas som punkter som du kan hovra över för mer information.
* **[!UICONTROL Trendline overlay]**: Lägger till en trendlinje i diagrammet som hjälper till att beskriva ett tydligare mönster i data.
   * [!UICONTROL Linear]: Skapar en rak regressionslinje. Bäst för enkla linjära data som ökar eller minskar med en konstant hastighet. Ekvation: `y = a + b * x`
   * [!UICONTROL Logarithmic]: Skapar en böjd regressionslinje. Bäst för data som snabbt ökar eller minskar, och sedan blir mer jämna. Ekvation: `y = a + b * log(x)`
   * [!UICONTROL Moving average]: Skapar en mjuk trendlinje baserad på en uppsättning medelvärden. Ett glidande medelvärde kallas även för ett glidande medelvärde och använder ett visst antal tidigare datapunkter (som bestäms av ditt val), jämför dem och använder medelvärdet som punkten på raden. Exempel är sju dagars glidande medelvärde eller fyra veckors glidande medelvärde. Vilka alternativ som är tillgängliga för glidande medelvärde beror på vilket intervall och datumintervall du har valt.

### Tidsjämförelse

{{apply-time-comparison}}


### Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->