---
title: Jämför Analytics Source Connector-data med Adobe Analytics
description: Förstå skillnader i data när du tittar på liknande rapporter i Adobe Analytics och Customer Journey Analytics.
role: Developer, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: frågetjänst;frågetjänst;sql-syntax
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# Jämför Analytics Source Connector-data med Adobe Analytics

När er organisation använder Customer Journey Analytics kan ni se att det finns vissa skillnader i data mellan Adobe Analytics och Customer Journey Analytics. Dessa skillnader är normala och kan inträffa av flera orsaker. Customer Journey Analytics är utformat för att du ska kunna förbättra vissa begränsningar av dina data i Adobe Analytics. Denna flexibilitet kan orsaka vissa skillnader i hur Customer Journey Analytics tolkar data. Läs den här artikeln om du vill veta mer om eventuella skillnader i hur Customer Journey Analytics och Adobe Analytics hanterar dina data.

På den här sidan förutsätts att du importerar Adobe Analytics-data till Adobe Experience Platform med [Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE), och sedan skapar en [anslutning](/help/connections/overview.md) och [datavy](/help/data-views/data-views.md) i Customer Journey Analytics.

![Dataflödet från Adobe Analytics via dataanslutningen till Adobe Experience Platform och till kundreseanalys via CJA-anslutningar.](assets/compare.png)

Tänk på följande möjliga orsaker till varför data kan skilja sig åt mellan olika rapporteringsplattformar:

* **Olika datauppsättningar eller rapportsviter**: Se till att rapportsviten i Adobe Analytics och rapportsviten som Source Connector hämtar data från är desamma.
* **Kalenderinställningar**: Rapportsviter i Adobe Analytics innehåller en tidszon och andra kalenderinställningar som du kan konfigurera. På samma sätt har datavyer i Customer Journey Analytics en separat inställning som du kan styra. Kontrollera att de här inställningarna matchar mellan produkterna om paritet önskas.
* **Ytterligare datauppsättningar**: Customer Journey Analytics ger möjlighet att inkludera flera datauppsättningar i en enda anslutning. Dessa skillnader omfattar ytterligare händelsedatamängder, profildatamängder eller uppslagsdatamängder. Detta är en viktig skillnad mellan Adobe Analytics och Customer Journey Analytics och ger insikt i flerkanalsdata.
* **Stitched datasets**: Adobe ger möjlighet att analysera person-ID:n mellan två datauppsättningar, vilket resulterar i en ny datauppsättning som innehåller sammanfogade ID:n. Dessa [sammanslagna datauppsättningar](/help/stitching/overview.md) innehåller ytterligare data utöver vad en Adobe Analytics-rapportserie erbjuder.
* **Datakällor**: Customer Journey Analytics innehåller inte någon typ av [Datakällor](https://experienceleague.adobe.com/sv/docs/analytics/import/data-sources/overview) som har överförts till en Adobe Analytics-rapportserie, inklusive sammanfattningsdatakällor eller transaktions-ID-datakällor.
* **Dimension- och måttinställningar**: I en datavy innehåller alla dimensioner och mått egna inställningar som din organisation kan ändra. Dessa ändringar gäller när rapporten körs och tillämpas därför retroaktivt. Dimension och mätinställningarna i Adobe Analytics förändrar hur data samlas in, så att ändringarna tillämpas från och med den tidpunkten. Om du har ändrat komponentinställningarna i någon av produkterna kan de skapa rapporteringsskillnader. Om du fokuserar på en viss dimension måste du se till att inställningarna för attribuering och beständighet stämmer överens mellan Adobe Analytics och Customer Journey Analytics.

  >[!TIP]
  >
  >Adobe rekommenderar att dimensioner i Adobe Analytics använder en allokering av [!UICONTROL Most recent (last)]. Den här allokeringsinställningen ger mycket större attribueringsflexibilitet i Customer Journey Analytics.

* **Besök definitionen**: Förutom individuella mått- och måttinställningar innehåller själva datavyn inställningar som i grunden förändrar hur visningsdata tolkas. Du kan till exempel tillämpa ett segment på en hel datavy (som liknar en [virtuell rapportsvit](https://experienceleague.adobe.com/sv/docs/analytics/components/virtual-report-suites/vrs-about) i Adobe Analytics). Du kan också ändra definitionen av en besökslängd eller automatiskt starta ett nytt besök vid önskad händelse. Alla dessa inställningar kan ha en betydande inverkan på rapporteringen av skillnader mellan Customer Journey Analytics och Adobe Analytics.

## Kontrollerar antal poster mellan produkter

Om alla ovanstående inställningar ser likadana ut och du vill validera minst antalet poster mellan produkterna kan du göra på följande sätt:

1. Kör följande fråga om totalt antal poster per tidsstämpel i Adobe Experience Platform [Query Services](https://experienceleague.adobe.com/sv/docs/experience-platform/query/home):

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. Generera feed-filer för det önskade datumintervallet i Adobe Analytics [Dataflöden](https://experienceleague.adobe.com/sv/docs/analytics/export/analytics-data-feed/data-feed-overview). Räkna antalet rader i varje fil och identifiera och exkludera följande rader:

   * `exclude_hit` är inte `0` (data har uteslutits från Analysis Workspace i båda produkterna)
   * `hit_source` är `0`, `3`, `5`, `7`, `8`, `9` eller `10` (datakällor och andra ej träffdata)
   * `page_event` är `53` eller `63` (direktuppspelningsmediets keep-alive-träffar)

   Rader som matchar något av ovanstående villkor exkluderas från arbetsflödet för att ta emot data i Analytics Source Connector, och bör därför också exkluderas när du räknar datarader.

1. Det totala antalet poster i frågetjänsterna ska matcha antalet rader i en datafeed för samma tidsperiod.
