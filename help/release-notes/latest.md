---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 835be84fd5f1398b88e265a21fe6f9665c758dce
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (augusti 2024)

**Senast uppdaterad**: 14 augusti 2024

Versionsanteckningarna gäller den 14 augusti till september 2024. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Datakällor på sammanfattningsnivå** | Gör att du kan hämta in tidsseriedata som inte har något person-ID. Dessa tidsseriedata kan användas för att stödja olika användningsfall, som:<ul><li>Presentera högnivåindikatorer som en del av eller bredvid data på händelsenivå. Det kan vara något så enkelt som ett datum och ett enda mätvärde eller innehålla flera dimensioner och mätvärden, som annonsvisningar, öppning av e-post, reklamkostnader, kostnad för sålda produkter med mera.</li><li>Överför mål per timme eller dag och positionera sedan dessa mål mot händelsenivåstatistik. Detta hjälper till att visualisera hur mätvärden trendar mot organisatoriska mål eller mål.</li></ul><p>Mer information finns i [Sammanfattningsdata](/help/data-views/summary-data.md)</p> |  | 13 augusti 2024 |
| **Publiker publiceras i ett nytt&quot;Publiker&quot;-avsnitt i Experience Platform** | Publikationer som publiceras från Customer Journey Analytics är nu tillgängliga i det nya avsnittet&quot;Publiker&quot; i Adobe Experience Platform.<p>Tidigare fanns målgrupper som publicerades från Customer Journey Analytics tillgängliga i Experience Platform under segmentavsnittet.</p><p>Den här förbättringen ger följande fördelar:</p><ul><li>Publiken har inte längre en timmes fördröjning innan de visas i Experience Platform; de är tillgängliga sekunder efter att de har publicerats.</li><li>Publiker kan sorteras i Experience Platform med hjälp av kolumnen &quot;Ursprung&quot;, som visar det program som målgruppen ursprungligen publicerades från.</li><li>Med filtrerings- och sorteringsalternativen i Experience Platform kan du hitta rätt målgrupper snabbare.</li></ul> <p>Mer information finns i [Använda Customer Journey Analytics-målgrupper i Experience Platform](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform) i artikeln [Skapa och publicera målgrupper](/help/components/audiences/publish.md).</p> | 14 augusti 2024 | 22 augusti 2024 |
| **Intelligenta aviseringar** | Med intelligenta aviseringar i Customer Journey Analytics kan ni meddelas omedelbart när onormala händelser inträffar i era data.<p>Du kan ange att aviseringar ska utlösas baserat på avvikelsetrösklar, ändrade procentsatser eller specifika datapunkter. Varningar ger detaljerade kontroller som kan integreras med avvikelseidentifiering och aktiveras när du behöver dem som mest.</p><p>Processen att använda intelligenta aviseringar i Customer Journey Analytics är nästan identisk med att använda intelligenta aviseringar i Adobe Analytics. En viktig skillnad är att det inte finns timaviseringar i Customer Journey Analytics. Den här skillnaden beror på att datainmatningen för de olika typer av händelsedata som kan importeras är slutförd först efter en fördröjning, vanligtvis från 3 till 9 timmar efter datahändelsetiden.</p><p>(Uppdaterade dokumentationslänkar att följa)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | TBD |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-354359; AN-351646; AN-346873; AN-352504; AN-353755; AN-354199; AN-354268; AN-4 354791; AN-354598; AN-354462; AN-354547;

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation om tilläggsprogrammet för direktuppspelad mediasamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
