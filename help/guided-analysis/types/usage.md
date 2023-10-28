---
title: Användningsvy
description: Mät användarengagemanget över tid.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Guided Analysis
keywords: produktanalys
source-git-commit: 713d70a444b3dba81a94d4f472b3ca7e0b39d742
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# [!UICONTROL Usage] visa

The **[!UICONTROL Usage]** ger värdefull information om produktens prestanda eller hur användarna beter sig över tid. Den vågräta axeln i den här rapporten är ett tidsintervall, medan den lodräta axeln mäter dina önskade händelser.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Användningsexempel

Exempel:

* **Utvärdera produktens prestanda**: Trender gör att du kan utvärdera den övergripande prestandan för din produkt under en viss period. Genom att analysera mätvärden som användarengagemang, användning och konverteringsgrader kan ni identifiera om produktens prestanda förbättras, stagnerar eller försämras.
* **Antagande av nya funktioner**: Trender gör att du kan förstå hur användare antar nya funktioner eller uppdateringar som du släpper. Du kan avgöra vilka funktioner som är populära och vilka som behöver förbättras. Med den här informationen kan ni fatta datadrivna beslut om vilka funktioner ni ska prioritera utvecklingsarbetet kring.
* **Användarbeteende**: Trender kan ge insikt i användarbeteendet över tid. Genom att undersöka specifika åtgärder som användare utför kan du identifiera mönster där användare kan släppa av. Du kan kombinera insikter från den här vyn med [Funktion](friction.md) för ännu mer insikter om beteenden.
* **A/B-testning och -experiment**: Om du kör A/B-tester i produkten kan du använda Trends för att mäta vilka tester som är mest framgångsrika över tid.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Events]**: De händelser som du vill mäta. Varje markerad händelse representeras som en färgad linje eller en uppsättning staplar, beroende på diagramtyp. En rad som representerar händelsen trended läggs till i tabellen. Du kan inkludera upp till fem händelser.
* **[!UICONTROL People]**: De segment som du vill mäta. Varje markerat segment dubblerar antalet rader i diagrammet och raderna i tabellen. Du kan inkludera upp till fem segment.
* **[!UICONTROL Breakdown]**: Skapa en separat trendlinje per dimensionsobjekt. En enda uppdelningsdimension stöds.

## Diagraminställningar

The [!UICONTROL Usage] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Metric]**: Det mått som du vill mäta. Alternativen är Händelser, Sessioner, Användare, Händelser per session och Händelser per användare.
* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Du kan välja mellan Linje, Stapel, Staplad liggande och Staplad yta.

## Övertäckningar

Lägg till ytterligare data i diagrammet.

* **[!UICONTROL Show anomalies]**: Körningar [avvikelseidentifiering](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) på trendanalysen. Exponenter visas som punkter som du kan hovra över för mer information.
* **[!UICONTROL Trendline overlay]**: Lägger till en trendlinje i diagrammet, så att du kan se den övergripande riktning dina data tar inom den angivna tidsperioden.
   * [!UICONTROL Linear]: En linjär regressionsmodell. Rekommenderas för data som ökar eller minskar i en konstant hastighet.
   * [!UICONTROL Logarithmic]: En böjd linjeregressionsmodell. Rekommenderas för data som är utjämnade över tid.
   * [!UICONTROL Moving average]: En utjämnad linje som beräknar medelvärdet för föregående punkt från varje punkt. Rekommenderas för data som har regelbundna cykler. Vilka perioder som är tillgängliga beror på det valda datumintervallet.

## Använd tidsjämförelse

{{apply-time-comparison}}

![Jämför användningstid](../assets/usage-compare.png)

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
