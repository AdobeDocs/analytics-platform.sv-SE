---
title: Jämför med era Adobe Analytics-data
description: Lär dig hur du jämför dina Adobe Analytics-data med data i Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: frågetjänst;frågetjänst;sql-syntax
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 0%

---

# Jämför med era Adobe Analytics-data

När ni antar Customer Journey Analytics kan det finnas vissa skillnader i data mellan Adobe Analytics och Customer Journey Analytics. Detta är normalt och kan inträffa av flera orsaker. Customer Journey Analytics är utformat för att du ska kunna förbättra vissa begränsningar av dina data i AA. Oväntade och oavsiktliga avvikelser kan dock förekomma. Den här artikeln är utformad för att hjälpa dig att diagnostisera och lösa de skillnaderna så att du och ditt team kan använda Customer Journey Analytics utan hinder av dataintegritetsfrågor.

Låt oss anta att du importerade Adobe Analytics-data till Adobe Experience Platform via [Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE) och sedan skapade en Customer Journey Analytics-anslutning med den här datauppsättningen.

![Dataflödet från Adobe Analytics via dataanslutningen till Adobe Experience Platform och till kundreseanalys med CJA-anslutningar.](assets/compare.png)

Därefter skapade du en datavy och när du senare rapporterade data för Customer Journey Analytics upptäckte du att det fanns skillnader i rapportresultaten i Adobe Analytics.

Här följer några steg för att jämföra dina ursprungliga Adobe Analytics-data med Adobe Analytics-data som nu finns i Customer Journey Analytics.

## Förutsättningar

* Kontrollera att Analytics-datauppsättningen i Adobe Experience Platform innehåller data för det datumintervall som du undersöker.

* Se till att rapportsviten som du valde i Analytics matchar rapportsviten som importerats till Adobe Experience Platform.

## Steg 1: Kör förekomstmåttet i Adobe Analytics

Måttet [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=sv-SE) visar antalet träffar där en given dimension angavs eller beständig.

1. I Analytics > [!UICONTROL Workspace] drar du datumintervallet som du vill rapportera som en dimension till en [!UICONTROL Freeform]-tabell.

1. Måttet [!UICONTROL Occurrences] används automatiskt i det datumintervallet.

1. Spara projektet så att du kan använda det i jämförelsen.

## Steg 2: Jämför resultaten med [!UICONTROL Total records by timestamps] i Customer Journey Analytics

Jämför nu [!UICONTROL Occurrences] i Analytics med totalt antal poster med tidsstämplar i Customer Journey Analytics.

Totalt antal poster efter tidsstämplar bör matcha med förekomster, förutsatt att inga poster har utelämnats av Analytics Source Connector - se avsnittet nedan.

>[!NOTE]
>
>Detta fungerar endast för vanliga datamängder med mellanvärden, inte sammanfogade datamängder (via [Stitching](/help/stitching/overview.md)). Observera att redovisning av det person-ID som används i Customer Journey Analytics är avgörande för att jämförelsen ska fungera. Det är kanske inte alltid lätt att återskapa i Adobe Analytics, särskilt om du har aktiverat funktionen för att markera alternativet.

1. Kör följande [!UICONTROL Total Records by timestamps]-fråga i Adobe Experience Platform [Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=sv-SE):

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

1. I [Analysdatafeeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=sv-SE) kan du utifrån rådata identifiera om vissa rader kan ha filtrerats bort av Analytics Source-kopplingen.

   Source-kopplingen [Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE) kan filtrera vissa rader under omvandlingen till XDM-schemat. Det kan finnas flera orsaker till att hela raden inte kan omformas. Om något av följande Analytics-fält har dessa värden kommer hela raden att filtreras bort.

   | Analysfält | Värden som gör att en rad tas bort |
   | --- | --- |
   | Opt_ut | y, Y |
   | In_data_only | Inte 0 |
   | Exkludera_träff | Inte 0 |
   | Bot_id | Inte 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   Mer information om hit\_source finns i: [Datakolumnreferens](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=sv-SE). Mer information om page\_event finns i: [Sökning efter sidhändelser](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=sv-SE).

1. Om kopplingens filtrerade rader tar du bort de raderna från måttet [!UICONTROL Occurrences]. Resultatet ska matcha antalet händelser i Adobe Experience Platform datamängder.

## Varför poster kan filtreras eller hoppas över vid förtäring från Adobe Experience Platform

Med Customer Journey Analytics [Anslutningar](/help/connections/create-connection.md) kan du samla ihop och koppla ihop flera datauppsättningar baserat på ett gemensamt person-ID för alla datauppsättningar. På backend använder vi borttagning av dubbletter: fullständig yttre koppling eller union av händelsedatamängder baserat på tidsstämplar, och sedan inre koppling på profil- och sökdatamängd, baserat på person-ID.

Här är några anledningar till varför poster kan hoppas över när data hämtas från Adobe Experience Platform.

* **Tidsstämplar saknas** - Om tidsstämplar saknas i händelsedatamängder ignoreras dessa poster helt eller hoppas över under importen.

* **Saknade person-ID:n** - Person-ID:n som saknas (från händelsedatamängden och/eller från profil-/sökdatamängden) gör att dessa poster ignoreras eller hoppas över. Orsaken är att det inte finns några vanliga ID:n eller matchande nycklar att koppla posterna till.

* **Ogiltiga eller stora person-ID:n** - med ogiltiga ID:n kan systemet inte hitta ett giltigt gemensamt ID bland de datauppsättningar som ska kopplas. I vissa fall innehåller kolumnen med person-ID ogiltiga person-ID:n, till exempel &quot;undefined&quot; eller &quot;0000000&quot;. Ett person-ID (med valfri kombination av siffror och bokstäver) som förekommer i en händelse som är mer än 1 miljon gånger i månaden kan inte tilldelas en viss användare eller person. Den kategoriseras som ogiltig. Dessa poster kan inte importeras till systemet och resulterar i felbenägen inmatning och rapportering.
