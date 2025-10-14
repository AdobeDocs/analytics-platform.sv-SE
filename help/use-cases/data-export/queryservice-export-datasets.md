---
title: Experience Platform Query Service (Data Distiller) och Export datasets
description: Beskriver hur du använder frågetjänsten (Data Distiller) och datauppsättningsexporten för att exportera data.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 14a90758-91eb-4610-8802-1edfdb8b9689
source-git-commit: 3568aad27001b322da77f5d1fb762db5ba6d433d
workflow-type: tm+mt
source-wordcount: '2638'
ht-degree: 0%

---

# Query Service (Data Distiller) och Export datasets

I den här artikeln beskrivs hur en kombination av Experience Platform Query Service (Data Distiller) och Datauppsättningsexport kan användas för att implementera följande [dataexportanvändningsfall](overview.md):

- Dataverifiering
- Data Lake, Data Warehouse av BI-verktyg
- Beredskap för Artificial Intelligent and Machine Learning.


Adobe Analytics kan implementera de här användningsexemplen med hjälp av funktionen [Datafeeds](https://experienceleague.adobe.com/sv/docs/analytics/export/analytics-data-feed/data-feed-overview). Dataflöden är ett kraftfullt sätt att få ut rådata från Adobe Analytics. I den här artikeln beskrivs hur du hämtar liknande typer av rådata från Experience Platform, så att du kan implementera de ovan nämnda användningsområdena. I tillämpliga fall jämförs de funktioner som beskrivs i den här artikeln med Adobe Analytics Data Feeds för att klargöra skillnader i data och processer.

## Introduktion

Exportera data med hjälp av frågetjänsten (Data Distiller) och datauppsättningsexporten består av:

- definierar en **schemalagd fråga** som genererar data för din datafeed som en ![utdatamängd](../assets/output-dataset.svg) med **frågetjänst**.
- definiera en **schemalagd datauppsättningsexport** som exporterar utdatauppsättningen till ett molnlagringsmål med hjälp av **datauppsättningsexport**.

![Datafeed](../assets/queryservice-export-datasets.svg)


## Förutsättningar

Kontrollera att du uppfyller alla följande krav innan du använder de funktioner som beskrivs i det här fallet:

- En fungerande implementering som samlar in data i Experience Platform datarö.
- Tillgång till tillägget Data Distiller för att säkerställa att du har rätt att köra gruppfrågor. Mer information finns i [Paketering för frågetjänst](https://experienceleague.adobe.com/sv/docs/experience-platform/query/packaging).
- Tillgång till funktionen Exportera datauppsättningar, som är tillgänglig när du har köpt Real-Time CDP Prime- eller Ultimate-paketet, Adobe Journey Optimizer eller Customer Journey Analytics. Mer information finns i [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets).
- En eller flera konfigurerade mål (till exempel Amazon S3, Google Cloud-lagring) till den plats där du kan exportera rådata från din datafeed.


## Frågetjänst

Med Experience Platform Query Service kan du söka efter och ansluta till alla datauppsättningar i Experience Platform Data Lake som om det vore en databastabell. Sedan kan du samla in resultaten som en ny datauppsättning och använda den för vidare rapportering eller för export.

Du kan använda frågetjänstens [användargränssnitt](https://experienceleague.adobe.com/sv/docs/experience-platform/query/ui/overview), en [klient som är ansluten via protokollet PostgresQL](https://experienceleague.adobe.com/sv/docs/experience-platform/query/clients/overview) eller [RESTful API:er](https://experienceleague.adobe.com/sv/docs/experience-platform/query/api/getting-started) för att skapa och schemalägga frågor som samlar in data för din datafeed.

### Skapa fråga

Du kan använda all funktionalitet som finns i ANSI SQL för SELECT-satser och andra begränsade kommandon för att skapa och köra frågor som genererar data för din datafeed. Mer information finns i [SQL-syntax](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/syntax). Utöver denna SQL-syntax stöder Adobe:

- fördefinierade [Adobe-definierade funktioner (ADF)](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/adobe-defined-functions) som hjälper dig att utföra vanliga affärsrelaterade uppgifter på händelsedata som lagras i Experience Platform, inklusive funktioner för [Sessionalisering](https://experienceleague.adobe.com/sv/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) och [Attribution](https://experienceleague.adobe.com/sv/docs/analytics/analyze/analysis-workspace/attribution/overview),
- flera inbyggda [Spark SQL-funktioner](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/spark-sql-functions),
- [metadata PostgreSQL-kommandon](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/metadata),
- [förberedda programsatser](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/prepared-statements).

#### Datautmatningskolumner

Vilka XDM-fält du kan använda i frågan beror på schemadefinitionen som datamängderna baseras på. Se till att du förstår schemat som ligger till grund för datauppsättningen. Mer information finns i [Användargränssnittsguiden för datauppsättningar](https://experienceleague.adobe.com/sv/docs/experience-platform/catalog/datasets/user-guide).

Mer information om hur du definierar mappningen mellan kolumnerna för datafeed och XDM-fälten finns i [Mappning av analysfält](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Mer information om hur du hanterar XDM-resurser, inklusive scheman, klasser, fältgrupper och datatyper, finns i [Översikt över användargränssnittet för scheman](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/ui/overview#defining-xdm-fields).

Om du till exempel vill använda *sidnamn* som en del av din datafeed:

- I användargränssnittet för Adobe Analytics Data Feed väljer du **[!UICONTROL pagename]** som kolumn att lägga till i dataflödesdefinitionen.
- I frågetjänsten inkluderar du `web.webPageDetails.name` från datauppsättningen `sample_event_dataset_for_website_global_v1_1` (baserat på **exempelhändelseschemat för webbplatsen (händelseschemat för den globala upplevelsen v1.1)**) i din fråga. Mer information finns i schemafältgruppen [Webbinformation](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/field-groups/event/web-details).


#### Identiteter

I Experience Platform finns olika identiteter. När du skapar dina frågor måste du kontrollera att du frågar identiteter korrekt.


Du hittar ofta identiteter i en separat fältgrupp. I en implementering kan ECID (`ecid`) definieras som en del av en fältgrupp med ett `core` -objekt, som i sin tur är en del av ett `identification`-objekt (till exempel: `_sampleorg.identification.core.ecid`). ECID:n kan ordnas på olika sätt i dina scheman.

Du kan också använda `identityMap` för att fråga efter identiteter. `identityMap` är av typen `Map` och använder en [kapslad datastruktur](#nested-data-structure).

Mer information om hur du definierar identitetsfält i Experience Platform finns i [Definiera identitetsfält i användargränssnittet](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/ui/fields/identity).

Se [Primära identifierare i Analytics-data](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) för en förståelse för hur Adobe Analytics-identiteter mappas till Experience Platform-identiteter när du använder Analytics-källkopplingen. Den här mappningen kan fungera som vägledning när du skapar dina identiteter, även när du inte använder Analytics-källkopplingen.


#### Data och identifiering på träffnivå

Baserat på implementeringen lagras data på träffnivå som traditionellt samlats in i Adobe Analytics som tidsstämplade händelsedata i Experience Platform. Följande tabell extraheras från [Mappning av analysfält](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) och visar exempel på hur du mappar träffnivåspecifika Adobe Analytics Data Feed-kolumner med motsvarande XDM-fält i dina frågor. Tabellen visar också exempel på hur träffar, besök och besökare identifieras med hjälp av XDM-fält.

| Datafeedkolumn | XDM-fält | Typ | Beskrivning |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | En unik identifierare som identifierar en träff. |
| `hitid_low` | `_id` | string | Används med `hitid_high` för att identifiera en träff unikt. |
| `hitid_high` | `_id` | string | Används med `hitid_high` för att identifiera en träff unikt. |
| `hit_time_gmt` | `receivedTimestamp` | string | Tidsstämpeln för träffen, baserad på UNIX®-tid. |
| `cust_hit_time_gmt` | `timestamp` | string | Den här tidsstämpeln används bara i tidsstämpelaktiverade datauppsättningar. Tidsstämpeln skickas med träffen, baserat på UNIX®-tid. |
| `visid_high` + `visid_low` | `identityMap` | object | En unik identifierare för ett besök. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | En unik identifierare för ett besök. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | boolesk | Används med `visid_low` för att identifiera ett besök unikt. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | Används med `visid_low` för att identifiera ett besök unikt. |
| `visid_low` | `identityMap` | object | Används med `visid_high` för att identifiera ett besök unikt. |
| `cust_visid` | `identityMap` | object | Kundens besökar-ID. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | object | Kundens besökar-ID. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | boolesk | Kundbesökarens ID-namnområdeskod. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | Används med `visid_low` för att identifiera kundbesöks-ID unikt. |
| `geo\_*` | `placeContext.geo.* ` | sträng, tal | Geolokaliseringsdata, som land, region, stad och andra |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, `_experience.analytics.event901_1000.*` | string | Standardhandel och anpassade händelser som utlöses vid träffen. |
| `page_event` | `web.webInteraction.type` | string | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, slutlänk eller anpassad länk som klickats). |
| `page_event` | `web.webInteraction.linkClicks.value` | tal | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, slutlänk eller anpassad länk som klickats). |
| `page_event_var_1` | `web.webInteraction.URL` | string | En variabel som bara används för bildbegäran för länkspårning. Den här variabeln innehåller URL:en för den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickat på. |
| `page_event_var_2` | `web.webInteraction.name` | string | En variabel som bara används för bildbegäran för länkspårning. Här visas länkens egna namn, om det har angetts. |
| `paid_search` | `search.isPaid` | boolesk | En flagga som anges om träffen matchar betalsökningsidentifiering. |
| `ref_type` | `web.webReferrertype` | string | Ett numeriskt ID som representerar typen av referens för träffen. |

#### Bokför kolumner

Adobe Analytics Data Feeds använder begreppet kolumner med ett `post_`-prefix, som är kolumner som innehåller data efter bearbetning. Mer information finns i [Vanliga frågor om dataflöden](https://experienceleague.adobe.com/sv/docs/analytics/export/analytics-data-feed/df-faq#post).

Data som samlas in i datauppsättningar via Experience Platform (Web SDK, Mobile SDK, Server API) har inget koncept för `post_`-fält. Därför mappas dataflödeskolumner med `post_` som prefix och *som inte*-`post_` som prefix till samma XDM-fält. Både `page_url` och `post_page_url` dataflödeskolumner mappar till samma `web.webPageDetails.URL` XDM-fält.

Se [Jämför databearbetning i Adobe Analytics och Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) för en översikt över skillnaden i databehandling.

När datatypen för prefixkolumnen `post_` samlas in i datavjön på Experience Platform kräver det emellertid avancerade omformningar innan den kan användas i ett dataflöde. När du utför dessa avancerade omformningar i dina frågor används [Adobe-definierade funktioner](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/adobe-defined-functions) för sessioner, attribuering och deduplicering. Se [Exempel](#examples) om hur du använder dessa funktioner.

#### Uppslag

Om du vill söka efter data från andra datauppsättningar använder du standardSQL-funktioner (`WHERE` -sats, `INNER JOIN`, `OUTER JOIN` med flera).

#### Beräkningar

Om du vill utföra beräkningar i fält (kolumner) använder du SQL-standardfunktionerna (till exempel `COUNT(*)`), eller [&#x200B; math- och statistikoperatorerna och funktionerna &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/spark-sql-functions#math) i Spark SQL. Dessutom har [fönsterfunktioner](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) stöd för att uppdatera aggregeringar och returnera enstaka objekt för varje rad i en ordnad delmängd. Se [Exempel](#examples) om hur du använder dessa funktioner.

#### Kapslad datastruktur

Scheman som datauppsättningarna baseras på innehåller ofta komplexa datatyper, inklusive kapslade datastrukturer. Tidigare nämnd `identityMap` är ett exempel på en kapslad datastruktur. Nedan finns ett exempel på `identityMap`-data.

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

Du kan använda [`explode()` eller andra Arrays-funktioner &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/query/sql/spark-sql-functions#arrays) från Spark SQL för att komma till data i en kapslad datastruktur, till exempel:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Du kan också referera till enskilda element med punktnotation. Exempel:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Mer information finns i [Arbeta med kapslade datastrukturer i frågetjänsten](https://experienceleague.adobe.com/sv/docs/experience-platform/query/key-concepts/nested-data-structures).


#### Exempel

För frågor:

- som använder data från datauppsättningar i datasjön Experience Platform,
- utnyttjar de extra funktionerna i Adobe Defined Function och/eller Spark SQL, och
- som skulle ge liknande resultat som ett motsvarande dataflöde från Adobe Analytics,

se:

- [övergiven bläddring](https://experienceleague.adobe.com/sv/docs/experience-platform/query/use-cases/abandoned-browse)
- [attribueringsanalys](https://experienceleague.adobe.com/sv/docs/experience-platform/query/use-cases/attribution-analysis)
- [robotfiltrering](https://experienceleague.adobe.com/sv/docs/experience-platform/query/use-cases/bot-filtering)
- och andra [supportade användningsfall i frågetjänstguiden](https://experienceleague.adobe.com/sv/docs/experience-platform/query/use-cases/overview).

Nedan visas ett exempel på hur du korrekt kan använda attribuering i sessioner och som visar hur du

- använda de senaste 90 dagarna som uppslag,
- använda fönsterfunktioner som sessioner och/eller attribuering, och
- begränsa utdata baserat på `ingest_time`.

+++
Information

  För att göra detta måste du..

   - Använd en bearbetningsstatustabell, `checkpoint_log`, för att hålla reda på den aktuella kontra den senaste inmatningstiden. Mer information finns i [den här handboken](https://experienceleague.adobe.com/sv/docs/experience-platform/query/key-concepts/incremental-load).
   - inaktivera släppning av systemkolumner så att du kan använda `_acp_system_metadata.ingestTime`.
   - Använd en innersta `SELECT` för att ta tag i de fält som du vill använda och begränsa händelserna till din uppslagsperiod för sessions- och/eller attribueringsberäkningar. Till exempel 90 dagar.
   - Använd nästa nivå `SELECT` för att tillämpa funktioner för sessioner och/eller attribueringsfönster och andra beräkningar.
   - Använd `INSERT INTO` i utdatatabellen om du bara vill begränsa sökningen till händelser som har kommit sedan den senaste bearbetningstiden. Det gör du genom att filtrera på `_acp_system_metadata.ingestTime ` jämfört med den senaste tiden som lagrats i din bearbetningsstatustabell.

  **Exempel på funktioner i sessionsvyn**

  ```sql
  $$ BEGIN
     -- Disable dropping system columns
     set drop_system_columns=false; 
  
     -- Initialize variables
     SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
     -- Get the last processed batch ingestion time
     SET @from_batch_ingestion_time = SELECT coalesce(last_batch_ingestion_time, 'HEAD') 
        FROM checkpoint_log a 
        JOIN (
              SELECT MAX(process_timestamp) AS process_timestamp 
              FROM checkpoint_log
              WHERE process_name = 'data_feed' 
              AND process_status = 'SUCCESSFUL'
        ) b
        ON a.process_timestamp = b.process_timestamp;
  
     -- Get the last batch ingestion time
     SET @to_batch_ingestion_time = SELECT MAX(_acp_system_metadata.ingestTime) 
        FROM events_dataset;
  
     -- Sessionize the data and insert into data_feed.
     INSERT INTO data_feed
     SELECT *
     FROM (
        SELECT
              userIdentity,
              timestamp,
              SESS_TIMEOUT(timestamp, 60 * 30) OVER (
                 PARTITION BY userIdentity
                 ORDER BY timestamp
                 ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
              ) AS session_data,
              page_name,
              ingest_time
        FROM (
              SELECT
                 userIdentity,
                 timestamp,
                 web.webPageDetails.name AS page_name,
                 _acp_system_metadata.ingestTime AS ingest_time
              FROM events_dataset
              WHERE timestamp >= current_date - 90
        ) AS a
        ORDER BY userIdentity, timestamp ASC
     ) AS b
     WHERE b.ingest_time >= @from_batch_ingestion_time;
  
     -- Update the checkpoint_log table
     INSERT INTO checkpoint_log
     SELECT
        'data_feed' process_name,
        'SUCCESSFUL' process_status,
        cast(@to_batch_ingestion_time AS string) last_batch_ingestion_time,
        cast(@last_updated_timestamp AS TIMESTAMP) process_timestamp
  END
  $$;
  ```

  **Exempel på funktioner i fönstret Attribution**

  ```sql
  $$ BEGIN
   SET drop_system_columns=false;
  
  -- Initialize variables
   SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
  -- Get the last processed batch ingestion time 1718755872325
   SET @from_batch_ingestion_time =
       SELECT coalesce(last_snapshot_id, 'HEAD')
       FROM checkpoint_log a
       JOIN (
           SELECT MAX(process_timestamp) AS process_timestamp
           FROM checkpoint_log
           WHERE process_name = 'data_feed'
           AND process_status = 'SUCCESSFUL'
       ) b
       ON a.process_timestamp = b.process_timestamp;
  
   -- Get the last batch ingestion time 1718758687865
   SET @to_batch_ingestion_time =
       SELECT MAX(_acp_system_metadata.ingestTime)
       FROM demo_data_trey_mcintyre_midvalues;
  
   -- Sessionize the data and insert into new_sessionized_data
   INSERT INTO new_sessionized_data
   SELECT *
   FROM (
       SELECT
           _id,
           timestamp,
           struct(User_Identity,
           cast(SESS_TIMEOUT(timestamp, 60 * 30) OVER (
               PARTITION BY User_Identity
               ORDER BY timestamp
               ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
           ) as string) AS SessionData,
           to_timestamp(from_unixtime(ingest_time/1000, 'yyyy-MM-dd HH:mm:ss')) AS IngestTime,      
           PageName,
           first_url,
           first_channel_type
             ) as _demosystem5
       FROM (
           SELECT
               _id,
               ENDUSERIDS._EXPERIENCE.MCID.ID as User_Identity,
               timestamp,
               web.webPageDetails.name AS PageName,
              attribution_first_touch(timestamp, '', web.webReferrer.url) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_url,
              attribution_first_touch(timestamp, '',channel.typeAtSource) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_channel_type,
               _acp_system_metadata.ingestTime AS ingest_time
           FROM demo_data_trey_mcintyre_midvalues
           WHERE timestamp >= current_date - 90
       )
       ORDER BY User_Identity, timestamp ASC    
   )
   WHERE _demosystem5.IngestTime >= to_timestamp(from_unixtime(@from_batch_ingestion_time/1000, 'yyyy-MM-dd HH:mm:ss'));
  
  -- Update the checkpoint_log table
  INSERT INTO checkpoint_log
  SELECT
     'data_feed' as process_name,
     'SUCCESSFUL' as process_status,
     cast(@to_batch_ingestion_time AS string) as last_snapshot_id,
     cast(@last_updated_timestamp AS timestamp) as process_timestamp;
  
  END
  $$;
  ```

+++


### Schemaläggningsfråga

Du schemalägger frågan för att se till att den körs och att resultaten genereras enligt det önskade intervallet.

#### Använda Frågeredigeraren

Du kan schemalägga en fråga med Frågeredigeraren. När du schemalägger frågan definierar du en utdatamängd. Mer information finns i [Frågescheman](https://experienceleague.adobe.com/sv/docs/experience-platform/query/ui/query-schedules).


#### Använda API för frågetjänst

Du kan också använda RESTful API:er för att definiera en fråga och ett schema för frågan. Mer information finns i [API-handboken för frågetjänsten](https://experienceleague.adobe.com/sv/docs/experience-platform/query/api/getting-started).
Se till att du definierar utdatamängden som en del av den valfria egenskapen `ctasParameters` när du skapar frågan ([Skapa en fråga](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) eller när du skapar schemat för en fråga ([Skapa en schemalagd fråga](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exportera datauppsättningar

När du har skapat och schemalagt din fråga och verifierat resultatet kan du sedan exportera rådatamängderna till molnlagringsmål. Den här exporten sker i Experience Platform Destinations-terminologi, som kallas för datauppsättningens exportdestinationer. Se [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets) för en översikt.

Följande molnlagringsmål stöds:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Datalandningszon](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud-lagring](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure-blob](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### Experience Platform UI

Du kan exportera och schemalägga exporten av dina utdatauppsättningar via användargränssnittet i Experience Platform. I det här avsnittet beskrivs de steg som ingår.

#### Välj mål

När du har fastställt vilket molnlagringsmål du vill exportera utdatamängden till [väljer du målet](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Om du ännu inte har konfigurerat ett mål för ditt rekommenderade molnlagringsutrymme måste du [skapa en ny målanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/connect-destination).

Som en del av konfigurationen av ett mål kan du

- Definiera filtypen (JSON eller Parquet).
- huruvida den resulterande filen ska komprimeras eller inte, och
- om en manifestfil ska inkluderas eller inte.


#### Välj datauppsättning

När du har valt målet måste du i nästa **[!UICONTROL Select datasets]**-steg välja din utdatauppsättning från listan med datauppsättningar. Om du har skapat flera schemalagda frågor och vill att utdatamängderna ska skickas till samma molnlagringsmål, kan du välja motsvarande utdatamängder. Mer information finns i [Välj datauppsättningar](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets).

#### Schemalägg datauppsättningsexport

Slutligen vill du schemalägga datauppsättningsexporten som en del av **[!UICONTROL Scheduling]**-steget. I det steget kan du definiera schemat och om exporten av utdatauppsättningen ska vara inkrementell eller inte. Mer information finns i [Schemalägg datauppsättningsexport](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling).


#### Slutliga steg

[Granska](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#review) ditt val och, när det är korrekt, börja exportera din utdatauppsättning till molnlagringsmålet.

Du måste [verifiera](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#verify) för att dataexporten ska lyckas. När du exporterar datauppsättningar skapar Experience Platform en eller flera `.json`- eller `.parquet`-filer på den lagringsplats som är definierad i ditt mål. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.

### API för flödestjänst

Du kan också exportera och schemalägga export av utdatamängder med API:er. Stegen som ingår beskrivs i [Exportera datauppsättningar med API:t för Flow Service &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets).

#### Kom igång

Om du vill exportera datauppsättningar måste du ha de [nödvändiga behörigheterna](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#permissions). Verifiera också att målet dit du vill skicka din utdatauppsättning har stöd för export av datauppsättningar. Du måste sedan [samla in värdena för obligatoriska och valfria rubriker](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) som du använder i API-anropen. Du måste också [identifiera anslutningsspec- och flödesspec-ID:n för målet &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) som du tänker exportera datamängder till.

#### Hämta giltiga datauppsättningar

Du kan [hämta en lista över kvalificerade datauppsättningar](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) för export och verifiera om din utdatamängd är en del av den listan med API:t för [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets).


#### Skapa källanslutning

Därefter måste du [skapa en källanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#create-source-connection) för utdatauppsättningen, med hjälp av dess unika ID, som du vill exportera till molnlagringsmålet. Du använder API:t [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection).

#### Autentisera till mål (skapa basanslutning)

Du måste nu [skapa en basanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#create-base-connection) för att autentisera och lagra autentiseringsuppgifterna på ett säkert sätt på molnlagringsmålet med API:t [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection).


#### Ange exportparametrar

Därefter måste du [skapa ytterligare en målanslutning som lagrar exportparametrarna &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#create-target-connection) för din utdatauppsättning med [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API:t. Dessa exportparametrar inkluderar plats, filformat, komprimering med mera.

#### Ställ in dataflöde

Slutligen [konfigurerar du dataflödet](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#create-dataflow) för att se till att din utdatauppsättning exporteras till ditt molnlagringsmål med API:t [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow). I det här steget kan du definiera exportschemat med hjälp av parametern `scheduleParams`.

#### Validera dataflöde

Om du vill [kontrollera slutförda körningar av dataflödet](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs) använder du [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns)-API:t och anger dataflödes-ID:t som frågeparameter. Detta dataflödes-ID är en identifierare som returneras när du ställer in dataflödet.

[Verifiera](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#verify) en dataexport. När du exporterar datauppsättningar skapar Experience Platform en eller flera `.json`- eller `.parquet`-filer på den lagringsplats som är definierad i ditt mål. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.

## Slutsats

För att emulera Adobe Analytics Data Feed-funktionaliteten innebär det kort och gott att ställa in schemalagda frågor med hjälp av frågetjänsten och att använda resultaten av dessa frågor vid schemalagd datauppsättningsexport.

>[!IMPORTANT]
>
>Två schemaläggare är inblandade i det här användningsfallet. För att garantera att de emulerade dataflödesuppgifterna fungerar korrekt ska du se till att de scheman som konfigureras i frågetjänsten och dataexporter inte stör.
