---
title: Jämför dina AA-data med CJA-data
description: Lär dig hur du jämför dina Adobe Analytics-data med data i Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: 2088fd98510887e86cffb6bd957d32a35fcfc467
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# Jämför dina Adobe Analytics-data med CJA-data

När ni börjar använda CJA kan det finnas vissa skillnader i data mellan Adobe Analytics och CJA. Detta är normalt och kan inträffa av flera orsaker. CJA är utformat för att du ska kunna förbättra vissa begränsningar av dina data i AA. Oväntade/oavsiktliga avvikelser kan dock förekomma. Den här artikeln är utformad för att hjälpa dig att diagnostisera och lösa de skillnaderna så att du och ditt team kan använda CJA utan hinder av oron för dataintegritet.

Låt oss anta att du har inhämtat Adobe Analytics-data till AEP via [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)och skapade sedan en CJA-anslutning med den här datauppsättningen.

![dataflöde](assets/compare.png)

Därefter skapade du en datavy och när du senare rapporterade data på CJA märkte du avvikelser från rapportresultaten i Adobe Analytics.

Här följer några steg för att jämföra dina ursprungliga Adobe Analytics-data med Adobe Analytics-data som nu finns i Customer Journey Analytics.

## Förutsättningar

* Kontrollera att Analytics-datauppsättningen i AEP innehåller data för det datumintervall som du undersöker.

* Se till att rapportsviten som du valde i Analytics matchar rapportsviten som importerats till Adobe Experience Platform.

## Steg 1: Kör förekomstmåttet i Adobe Analytics

The [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html) mätvärdet visar antalet träffar där en given dimension angavs eller bestals.

1. I Analytics > [!UICONTROL Workspace]drar du datumintervallet som du vill rapportera som en dimension till en [!UICONTROL Freeform] tabell.

1. The [!UICONTROL Occurrences] mätvärden används automatiskt i det datumintervallet.

1. Spara projektet så att du kan använda det i jämförelsen.

## Steg 2: Jämför resultaten med [!UICONTROL Total records by timestamps] i CJA

Jämför nu [!UICONTROL Occurrences] i Analytics till totalt antal poster per tidsstämpel i Customer Journey Analytics.

Totalt antal poster efter tidsstämplar bör matcha med förekomster, förutsatt att inga poster har utelämnats av Analytics-källkopplingen - se avsnittet nedan.

>[!NOTE]
>
>Detta fungerar endast för vanliga datamängder med mellanvärden, inte sammanfogade datamängder (via [Flerkanalsanalys](/help/connections/cca/overview.md)). Observera att redovisning av det person-ID som används i CJA är avgörande för att jämförelsen ska fungera. Det är kanske inte alltid lätt att replikera i AA, särskilt om funktionen för kanalövergripande analys har aktiverats.

1. I Adobe Experience Platform [Frågetjänster](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html), kör följande [!UICONTROL Total Records by timestamps] fråga:

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. I [Dataflöden för analyser](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html)identifierar du utifrån rådata om några rader kan ha filtrerats bort av Analytics-källkopplingen.

   The [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) kan filtrera vissa rader under omvandlingen till XDM-schema. Det kan finnas flera orsaker till att hela raden inte kan omformas. Om något av följande Analytics-fält har dessa värden kommer hela raden att filtreras bort.

   | Analysfält | Värden som gör att en rad tas bort |
   | --- | --- |
   | Opt_ut | y, Y |
   | In_data_only | Inte 0 |
   | Exkludera_träff | Inte 0 |
   | Bot_id | Inte 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   Mer information om hit\_source finns i: [Referens för datakolumn](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en). Mer information om page\_event finns i: [Sökning efter sidhändelse](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=en).

1. Om kopplingens filtrerade rader är det bara att subtrahera de raderna från [!UICONTROL Occurrences] mätvärden. Det resulterande antalet ska matcha antalet händelser i Adobe Experience Platform datamängder.

## Varför poster kan filtreras eller hoppas över vid förtäring från AEP

CJA [Anslutningar](/help/connections/create-connection.md) gör att du kan samla ihop och sammanfoga flera datauppsättningar baserat på ett gemensamt person-ID för alla datauppsättningar. Vi använder borttagning av dubbletter: fullständig yttre koppling eller union av händelsedatamängder baserat på tidsstämplar, och sedan inre koppling på profil- och sökdatamängd, baserat på person-ID.

Här är några orsaker till varför poster kan hoppas över när data hämtas från AEP.

* **Tidsstämplar saknas** - Om tidsstämplar saknas i händelsedatamängder kommer dessa poster att ignoreras helt eller hoppas över under importen.

* **Person-ID saknas** - Saknade person-ID:n (från händelsedatamängden och/eller från profil-/sökdatamängden) gör att dessa poster ignoreras eller hoppas över. Orsaken är att det inte finns några vanliga ID:n eller matchande nycklar att koppla posterna till.

* **Ogiltigt eller stort person-ID** - Med ogiltiga ID:n kan systemet inte hitta ett giltigt gemensamt ID bland de datauppsättningar som ska kopplas. I vissa fall har kolumnen med person-ID ogiltiga person-ID:n, till exempel &quot;undefined&quot; eller &quot;000000&quot;. Ett person-ID (med valfri kombination av siffror och bokstäver) som förekommer i en händelse som är mer än 1 miljon gånger i månaden kan inte tilldelas en viss användare eller person. Den kategoriseras som ogiltig. Dessa poster kan inte importeras till systemet och resulterar i felbenägen inmatning och rapportering.
