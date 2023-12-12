---
title: Emulera funktioner för datafeed
description: Förstå hur ni kan emulera dataflöden från Adobe Analytics med data i Experience Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: d5719dddfb4cefda761370951973d55b3904032f
workflow-type: tm+mt
source-wordcount: '2103'
ht-degree: 0%

---

# Emulera funktioner för datafeed

Adobe Analytics dataflöden är ett kraftfullt sätt att få ut rådata från Adobe Analytics. I det här användningsexemplet beskrivs hur du hämtar liknande typer av rådata från Experience Platform, för användning på andra plattformar utanför Adobe och efter din organisations gottfinnande.

## Förutsättningar

Kontrollera att du uppfyller alla följande krav innan du använder de funktioner som beskrivs i det här fallet:

* En fungerande implementering som skickar online- och offlinedata till Experience Platform Data Lake.
* Tillgång till Query Service, som paketeras som en del av plattformsbaserade program eller Data Distiller-tillägget. Se [Paket för frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) för mer information.
* Tillgång till funktionen Exportera datauppsättningar, som är tillgänglig för kunder som har köpt Real-Time CDP Prime- eller Ultimate-paketet, Adobe Journey Optimizer eller Customer Journey Analytics. Se [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en) för mer information.
* En eller flera destinationer (till exempel Amazon S3, Google Cloud-lagring) som konfigurerats för att exportera rådata från din datafeed.

## Introduktion

Emulering av en datafeed från Adobe Analytics innefattar:

* definiera en **schemalagd fråga** som genererar data för din datafeed som en utdatauppsättning, med **Frågetjänst**.
* definiera en **schemalagd datauppsättningsexport** som exporterar utdata till ett molnlagringsmål, med **Datauppsättningsexport**.


![Datafeed](assets/data-feed.svg)


## Frågetjänst

Med Experience Platform Query Service kan du söka efter och ansluta till alla datauppsättningar i Experience Platform Data Lake som om det vore en databastabell. Sedan kan du samla in resultaten som en ny datauppsättning och använda den för vidare rapportering eller för export.

Du använder tjänsten Query Service [användargränssnitt](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [klient ansluten via protokollet PostgresSQL](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en), eller [RESTful API:er](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) för att skapa och schemalägga frågor som samlar in data för din datafeed.

### Skapa fråga

Du kan använda alla funktioner i ANSI SQL-standard för SELECT-satser och andra begränsade kommandon för att skapa och köra frågor som genererar data för din datafeed. Se [SQL-syntax](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) för mer information. Utöver denna SQL-syntax stöder Adobe:

* fördefinierad [Adobe-definierade funktioner (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) som kan utföra vanliga affärsrelaterade uppgifter på händelsedata som lagras i Experience Platform Data Lake, inklusive funktioner för [Yrkesställning](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=en) och [Attribut](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en),
* inbyggda [Spark SQL-funktioner](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [metadata PostgreSQL-kommandon](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [förberedda programsatser](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Exempel

Några exempel på frågor som samlar in data för dina dataflöden visas nedan. De här exemplen använder `demo_system_event_dataset_for_website_global_v1_1` som exempelupplevelsehändelsedatamängd som innehåller data som samlats in från kunder som interagerar med webbplatsen.

+++De fem viktigaste produkterna

*Vilka är de fem främsta produkterna på webbplatsen?*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++Produktinteraktionstru

*Vilka är de olika produktinteraktionerna på webbplatsen?*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++Vad gör människor?

*Vad gör folk på webbplatsen innan de kommer till sidan&quot;Avbryt tjänst&quot; som den tredje sidan i en session?*

Den här frågan använder de Adobe-definierade funktionerna `SESS_TIMEOUT` och `NEXT`.

* The `SESS_TIMEOUT()` återger de besöksgrupperingar som hittats med Adobe Analytics. Den utför en liknande tidsbaserad gruppering, men med anpassningsbara parametrar.
* `NEXT()` och `PREVIOUS()` hjälper er att förstå hur kunderna navigerar på er webbplats.

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++Hur mycket tid

*Hur lång tid har du innan en besökare ringer callcentret efter att ha besökt sidan Avbryt tjänst?*

Om du vill svara på den här typen av frågor använder du `TIME_BETWEEN_NEXT_MATCH()` Funktion som definieras av Adobe. Tiden mellan föregående och nästa matchningsfunktioner ger en ny dimension som mäter den tid som har gått sedan en viss incident.

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++Vad är resultatet?

*Vad händer om kunderna ringer callcentret?*

För den här frågan `demo_system_event_dataset_for_website_global_v1_1` datauppsättningen med ett exempel `demo_system_event_dataset_for_call_center_global_v1_1` datauppsättning som innehåller kundtjänstinteraktioner.

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++Marketing Channel Engagement (Adobe Analytics-data)

*Vad är engagemanget i alla marknadsföringskanaler för italiensk webbtrafik?*

I det här exemplet används den datauppsättning som skapas automatiskt av Adobe Analytics-källkopplingen, till exempel `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

Fler (avancerade) exempelfrågor finns på [övergiven surfning](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), [attribueringsanalys](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), [startsfiltrering](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)och andra exempel i Query Service Guide.


#### Identiteter

I Experience Platform finns olika identiteter. Kontrollera att du frågar identiteter korrekt. I exemplen ovan definieras ECID som en del av ett huvudobjekt, som i sin tur är en del av ett identifieringsobjekt, som båda läggs till i schemat med hjälp av en Experience Event Core-fältgrupp (till exempel: `_sampleorg.identification.core.ecid`). ECID:n kan ordnas på olika sätt i dina scheman.

Du kan också använda `identityMap` för att fråga efter identiteter. Det här objektet är av typen `Map` och använder [kapslad datastruktur](#nested-data-structure).

För data som har importerats med Adobe Analytics källanslutning kan det finnas flera tillgängliga identiteter. Den primära identifieraren beror på om det finns ett ECID eller AAID. Se [Primära identifierare i Adobe Analytics-data](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) och [AAID, ECID, AACUSTOMID och Analytics-källkopplingen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) för mer information

#### Datautmatningskolumner

Vilka fält (kolumner) du kan använda i frågan beror på schemadefinitionen som datamängderna baseras på. Se till att du förstår schemat som ligger till grund för datauppsättningen.

I en del av [exempelfrågor](#examples) du frågade efter *sidnamn*.

* I Adobe Analytics Data Feed&#39;s UI väljer du **[!UICONTROL pagename]** som den kolumn som ska läggas till i dataflödesdefinitionen.
* I frågetjänsten inkluderar du `web.webPageDetails.name` från `demo_system_event_dataset_for_website_global_v1_1` datauppsättning (baserat på **Demo System - händelseschema för webbplats (Gobal v1.1)** händelseschema) i din fråga. Se [Schemafältgrupp för webbinformation](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) för mer information.

Mer information om mappningen mellan tidigare Adobe Analytics-datakolumner och XDM-fält i händelsedatamängden och det underliggande schemat finns i [Mappning av analysfält](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en) och [Schemafältgruppen Adobe Analytics ExperienceEvent Full Extension](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) för mer information.

Dessutom kan den information som automatiskt samlas in av Experience Platform Web SDK (utanför rutan) också vara relevant för att identifiera kolumner för din fråga. Se [Automatiskt insamlad information](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) för mer information.


#### Uppslag

Om du vill söka efter data från andra datauppsättningar använder du SQL-standardfunktioner (WHERE-satsen, INNER JOIN, OUTER JOIN med flera). Se [Vad är resultatet?](#examples) -frågan i exemplen.

#### Beräkningar

Om du vill utföra beräkningar i fält (kolumner) använder du bara SQL-standardfunktionerna (till exempel `COUNT(*)` i [Produktinteraktionstru](#examples) i exemplen) eller [matematiska och statistiska operatorer och funktioner](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) ingår i Spark SQL.

#### Kapslad datastruktur

Scheman som datauppsättningarna baseras på innehåller ofta komplexa datatyper, inklusive kapslade datastrukturer. Tidigare nämnda `identityMap` är ett exempel på en kapslad datastruktur. Nedan finns ett exempel på `identityMap` data.

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

Du kan använda [`explode()` eller andra arrayfunktioner](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) från Spark SQL för att komma till data i en kapslad datastruktur.

Exempel:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Du kan också referera till enskilda element med punktnotation. Exempel:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Se [Arbeta med kapslade datastrukturer i frågetjänsten](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) för mer information.

### Schemaläggningsfråga

Du schemalägger frågan för att se till att den körs och att resultaten genereras enligt det önskade intervallet. När du schemalägger frågan definierar du en utdatamängd.

#### Använda Frågeredigeraren

Du kan schemalägga en fråga med Frågeredigeraren. När du definierar ett schema för en fråga kan du definiera utdatamängden. Se [Frågescheman](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) för mer information.


#### Använda API för frågetjänst

Du kan också använda RESTful API:er för att definiera en fråga och ett schema för frågan. Se [API-guide för frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) för mer information.
Se till att du definierar utdata som en del av det valfria `ctasParameters` egenskap när frågan skapas ([Skapa en fråga](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) eller när schemat skapas för en fråga ([Skapa en schemalagd fråga](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Datauppsättningsexport

När du har skapat och schemalagt din fråga och verifierat att resultatet i utdatamängderna är i linje med dina krav, kan du sedan exportera rådatamängderna till molnlagringsmål. Den här exporten sker i Experience Platform Destinations-terminologi, som kallas för datauppsättningens exportdestinationer. Se [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en) för en översikt.

Följande molnlagringsmål stöds:

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [Datallandningszon](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Google Cloud-lagring](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### Experience Platform UI

Du kan exportera och schemalägga exporten av dina utdatauppsättningar via användargränssnittet i Experience Platform. I det här avsnittet beskrivs de steg som ingår.

#### Välj mål

När du har bestämt till vilket molnlagringsmål du vill exportera utdatamängden, [välj mål](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). När du ännu inte har konfigurerat ett mål för ditt rekommenderade molnlagringsutrymme måste du [skapa en ny målanslutning](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en).

När du konfigurerar ett mål kan du definiera filtypen (JSON eller Parquet), om den resulterande filen ska komprimeras eller inte och om en manifestfil ska inkluderas eller inte.


#### Välj datauppsättning

När du har valt målet, i nästa **[!UICONTROL Select datasets]** måste du välja din utdatauppsättning i listan med datauppsättningar. Om du har skapat flera schemalagda frågor och vill att utdatamängderna ska skickas till samma molnlagringsmål, kan du välja motsvarande utdatamängder. Se [Välj datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) för mer information.

#### Schemalägg datauppsättningsexport

Slutligen vill du schemalägga datauppsättningsexporten som en del av **[!UICONTROL Scheduling]** steg. I det steget kan du definiera schemat och om exporten av utdatauppsättningen ska vara inkrementell eller inte. Se [Schemalägg datauppsättningsexport](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) för mer information.


#### Slutliga steg

[Granska](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) ditt val och när det är korrekt, börja exportera din utdatauppsättning till molnlagringsmålet.

Du måste [verifiera](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) en lyckad dataexport. När du exporterar datauppsättningar skapas en eller flera i Experience Platform `.json` eller `.parquet` filer på den lagringsplats som är definierad i målet. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.

### API för flödestjänst

Du kan också exportera och schemalägga export av utdatamängder med API:er. Stegen beskrivs i [Exportera datauppsättningar med API:t för Flow Service](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### Kom igång

Se till att du har [nödvändiga behörigheter](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) för att exportera datauppsättningar och att målet dit du vill skicka din utdatauppsättning har stöd för export av datauppsättningar. Då måste du [samla in värden för obligatoriska och valfria rubriker](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) du använder i API-anropen, samt [identifiera anslutningsspecifikation och flödesspec-ID för destinationen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) du tänker exportera datauppsättningar till.

#### Hämta giltiga datauppsättningar

Du kan [hämta en lista över kvalificerade datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) för export och verifiera om din utdatamängd är en del av den listan med [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Skapa källanslutning

Nästa steg [skapa en källanslutning](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) för den utdatamängd, med dess unika ID, som du vill exportera till molnlagringsmålet. Du använder [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Autentisera till mål (skapa basanslutning)

Du måste [skapa en basanslutning](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) för att autentisera och lagra inloggningsuppgifterna på ett säkert sätt på molnlagringsmålet med [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Ange exportparametrar

Nästa steg är att [skapa ytterligare en målanslutning som lagrar exportparametrarna](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) för dina utdata med [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Dessa exportparametrar inkluderar plats, filformat, komprimering med mera.

#### Ställ in dataflöde

Äntligen får du [konfigurera dataflödet](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) för att se till att din utdatauppsättning exporteras till ditt molnlagringsmål med [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. I det här steget kan du definiera exportschemat med hjälp av `scheduleParams` parameter.

#### Validera dataflöde

Till [kontrollera slutförda körningar av dataflödet](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs), använder du [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, ange dataflödes-ID som frågeparameter. Detta dataflödes-ID är en identifierare som returneras när du ställer in dataflödet.

[Verifiera](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) en lyckad dataexport. När du exporterar datauppsättningar skapas en eller flera i Experience Platform `.json` eller `.parquet` filer på den lagringsplats som är definierad i målet. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.

## Slutsats

För att emulera Adobe Analytics Data Feed-funktionaliteten innebär det kort och gott att du måste ställa in schemalagda frågor med hjälp av frågetjänsten och använda resultaten av dessa frågor vid schemalagd datauppsättningsexport.

>[!IMPORTANT]
>
>Två schemaläggare är inblandade i det här användningsfallet. För att garantera att de emulerade dataflödesuppgifterna fungerar korrekt ska du se till att de scheman som konfigureras i frågetjänsten och dataexporter inte stör.

