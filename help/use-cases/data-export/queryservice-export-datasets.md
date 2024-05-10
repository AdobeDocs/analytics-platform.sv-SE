---
title: Experience Platform Query Service (Data Distiller) och Export datasets
description: Beskriver hur du använder frågetjänsten (Data Distiller) och datauppsättningsexporten för att exportera data.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '2471'
ht-degree: 0%

---

# Query Service (Data Distiller) och Export datasets

I den här artikeln beskrivs hur en kombination av Experience Platform Query Service (Data Distiller) och Datauppsättningsexport kan användas för att implementera följande [användningsfall vid dataexport](overview.md):

- Dataverifiering
- Data Lake, Data Warehouse av BI-verktyg
- Beredskap för Artificial Intelligent and Machine Learning.


Adobe Analytics kan implementera dessa användningsområden med hjälp av [Dataflöden](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) funktionalitet. Dataflöden är ett kraftfullt sätt att få ut rådata från Adobe Analytics. I den här artikeln beskrivs hur du hämtar liknande typer av rådata från Experience Platform, så att du kan implementera de ovan nämnda användningsområdena. I tillämpliga fall jämförs de funktioner som beskrivs i den här artikeln med Adobe Analytics Data Feeds för att klargöra skillnader i data och processer.

## Introduktion

Exportera data med hjälp av frågetjänsten (Data Distiller) och datauppsättningsexporten består av:

- definiera en **schemalagd fråga** som genererar data för din datafeed som en utdatauppsättning ![utdatamängd](../assets/output-dataset.svg), använda **Frågetjänst**.
- definiera en **schemalagd datauppsättningsexport** som exporterar utdata till ett molnlagringsmål, med **Datauppsättningsexport**.

![Datafeed](../assets/queryservice-export-datasets.svg)


## Förutsättningar

Kontrollera att du uppfyller alla följande krav innan du använder de funktioner som beskrivs i det här fallet:

- En fungerande implementering som samlar in data i Experience Platform datarö.
- Tillgång till tillägget Data Distiller för att säkerställa att du har rätt att köra gruppfrågor. Se [Paket för frågetjänst](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging) för mer information.
- Tillgång till funktionen Exportera datauppsättningar, som är tillgänglig när du har köpt Real-Time CDP Prime- eller Ultimate-paketet, Adobe Journey Optimizer eller Customer Journey Analytics. Se [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) för mer information.
- En eller flera konfigurerade mål (till exempel Amazon S3, Google Cloud-lagring) till den plats där du kan exportera rådata från din datafeed.


## Frågetjänst

Med Experience Platform Query Service kan du söka efter och ansluta till alla datauppsättningar i Experience Platform Data Lake som om det vore en databastabell. Sedan kan du samla in resultaten som en ny datauppsättning och använda den för vidare rapportering eller för export.

Du kan använda frågetjänsten [användargränssnitt](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview), a [klienten ansluten via protokollet PostgresQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview), eller [RESTful API:er](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) för att skapa och schemalägga frågor som samlar in data för din datafeed.

### Skapa fråga

Du kan använda all funktionalitet som finns i ANSI SQL för SELECT-satser och andra begränsade kommandon för att skapa och köra frågor som genererar data för din datafeed. Se [SQL-syntax](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax) för mer information. Utöver denna SQL-syntax stöder Adobe:

- fördefinierad [Adobe-definierade funktioner (ADF)](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) som hjälper till att utföra vanliga affärsrelaterade uppgifter på händelsedata som lagras i Experience Platform, inklusive funktioner för [Yrkesställning](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) och [Attribut](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview),
- inbyggda [Spark SQL-funktioner](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions),
- [metadata PostgreSQL-kommandon](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata),
- [förberedda programsatser](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements).

#### Datautmatningskolumner

Vilka XDM-fält du kan använda i frågan beror på schemadefinitionen som datamängderna baseras på. Se till att du förstår schemat som ligger till grund för datauppsättningen. Mer information finns i [Användargränssnittshandbok för datauppsättningar](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide).

Information om hur du definierar mappningen mellan kolumnerna för dataflöde och XDM-fälten finns i [Mappning av analysfält](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Se även [Översikt över schemaanvändargränssnittet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields) för mer information om hur du hanterar XDM-resurser, inklusive scheman, klasser, fältgrupper och datatyper.

Om du till exempel vill använda *sidnamn* som en del av ditt dataflöde:

- I Adobe Analytics Data Feed&#39;s UI väljer du **[!UICONTROL pagename]** som den kolumn som ska läggas till i dataflödesdefinitionen.
- I frågetjänsten inkluderar du `web.webPageDetails.name` från `sample_event_dataset_for_website_global_v1_1` datauppsättning (baserat på **Exempel på händelseschema för webbplats (Global v1.1)** händelseschema) i din fråga. Se [Schemafältgrupp för webbinformation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details) för mer information.


#### Identiteter

I Experience Platform finns olika identiteter. När du skapar dina frågor måste du kontrollera att du frågar identiteter korrekt.


Du hittar ofta identiteter i en separat fältgrupp. I en implementering av ECID (`ecid`) kan definieras som en del av en fältgrupp med en `core` -objekt, som i sin tur är en del av ett `identification` -objekt (till exempel: `_sampleorg.identification.core.ecid`). ECID:n kan ordnas på olika sätt i dina scheman.

Du kan också använda `identityMap` för att fråga efter identiteter. The `identityMap` är av typen `Map` och använder [kapslad datastruktur](#nested-data-structure).

Se [Definiera identitetsfält i användargränssnittet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) om du vill ha mer information om hur du definierar identitetsfält i Experience Platform.

Se [Primära identifierare i analysdata](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) för att förstå hur Adobe Analytics-identiteter mappas till Experience Platform-identiteter när du använder Analytics-källkopplingen. Den här mappningen kan fungera som vägledning när du skapar dina identiteter, även när du inte använder Analytics-källkopplingen.


#### Data och identifiering på träffnivå

Baserat på implementeringen lagras data på träffnivå som traditionellt samlats in i Adobe Analytics som tidsstämplade händelsedata i Experience Platform. Följande tabell extraheras från [Mappning av analysfält](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) och visar exempel på hur du mappar träffnivåspecifika Adobe Analytics Data Feed-kolumner med motsvarande XDM-fält i dina frågor. Tabellen visar också exempel på hur träffar, besök och besökare identifieras med hjälp av XDM-fält.

| Datafeedkolumn | XDM-fält | Typ | Beskrivning |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | En unik identifierare som identifierar en träff. |
| `hitid_low` | `_id` | string | Används med `hitid_high` för att identifiera en träff unikt. |
| `hitid_high` | `_id` | string | Används med `hitid_high` för att identifiera en träff unikt. |
| `hit_time_gmt` | `receivedTimestamp` | string | Tidsstämpeln för träffen, baserad på UNIX®-tid. |
| `cust_hit_time_gmt` | `timestamp` | string | Den här tidsstämpeln används bara i tidsstämpelaktiverade datauppsättningar. Tidsstämpeln skickas med träffen, baserat på UNIX®-tid. |
| `visid_high` + `visid_low` | `identityMap` | object | En unik identifierare för ett besök. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | En unik identifierare för ett besök. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | boolesk | Används med `visid_low` för att unikt identifiera ett besök. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | Används med `visid_low` för att unikt identifiera ett besök. |
| `visid_low` | `identityMap` | object | Används med `visid_high` för att unikt identifiera ett besök. |
| `cust_visid` | `identityMap` | object | Kundens besökar-ID. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | object | Kundens besökar-ID. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | boolesk | Kundbesökarens ID-namnområdeskod. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | Används med `visid_low` för att identifiera kundbesöks-ID unikt. |
| `geo\_*` | `placeContext.geo.* ` | sträng, tal | Geolokaliseringsdata, som land, region, stad och andra |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ..., `_experience.analytics.event901_1000.*` | string | Standardhandel och anpassade händelser som utlöses vid träffen. |
| `page_event` | `web.webInteraction.type` | string | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, slutlänk eller anpassad länk som klickats). |
| `page_event` | `web.webInteraction.linkClicks.value` | tal | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, slutlänk eller anpassad länk som klickats). |
| `page_event_var_1` | `web.webInteraction.URL` | string | En variabel som bara används för bildbegäran för länkspårning. Den här variabeln innehåller URL:en för den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickat på. |
| `page_event_var_2` | `web.webInteraction.name` | string | En variabel som bara används för bildbegäran för länkspårning. Här visas länkens egna namn, om det har angetts. |
| `paid_search` | `search.isPaid` | boolesk | En flagga som anges om träffen matchar betalsökningsidentifiering. |
| `ref_type` | `web.webReferrertype` | string | Ett numeriskt ID som representerar typen av referens för träffen. |

#### Bokför kolumner

Adobe Analytics Data Feeds använder begreppet kolumner med en `post_` -prefix, som är kolumner som innehåller data efter bearbetning. Se [Vanliga frågor om dataflöden](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post) för mer information.

Data som samlas in via datauppsättningar via Experience Platform (Web SDK, Mobile SDK, Server API) har inget koncept `post_` fält. Detta resulterar i `post_` prefix och *ej*-`post_` kolumner för prefix-datafeed mappas till samma XDM-fält. Till exempel båda `page_url` och `post_page_url` dataflödeskolumner mappas till samma `web.webPageDetails.URL` XDM-fält.

Se [Jämför databehandling i Adobe Analytics och Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) för en översikt över skillnaden i databehandling.

The `post_` när data samlas in i dataljön med prefix kräver det dock avancerade omformningar innan de kan användas i ett dataflöde. När du utför dessa avancerade omformningar i dina frågor måste du använda [Funktioner som definieras av Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) för sessioner, attribuering och deduplicering. Se [Exempel](#examples) om hur du använder dessa funktioner.

#### Uppslag

Om du vill söka efter data från andra datauppsättningar använder du standardfunktionen för SQL (`WHERE` -sats, `INNER JOIN`, `OUTER JOIN`, med flera).

#### Beräkningar

Om du vill utföra beräkningar i fält (kolumner) använder du SQL-standardfunktionerna (till exempel `COUNT(*)`) eller [matematiska och statistiska operatorer och funktioner](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math) ingår i Spark SQL. Dessutom [fönsterfunktioner](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) har stöd för att uppdatera aggregeringar och returnera enstaka objekt för varje rad i en ordnad delmängd. Se [Exempel](#examples) om hur du använder dessa funktioner.

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

Du kan använda [`explode()` eller andra arrayfunktioner](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays) från Spark SQL för att komma till data i en kapslad datastruktur, till exempel:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Du kan också referera till enskilda element med punktnotation. Exempel:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Se [Arbeta med kapslade datastrukturer i frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures) för mer information.


#### Exempel

För frågor:

- som använder data från datauppsättningar i datasjön Experience Platform,
- utnyttjar de extra funktionerna i Adobe Defined Function och/eller Spark SQL, och
- som skulle ge liknande resultat som ett motsvarande dataflöde från Adobe Analytics,

se:

- [övergiven surfning](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [attribueringsanalys](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [startsfiltrering](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- och andra [användningsexempel som stöds i guiden för frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview).


### Schemaläggningsfråga

Du schemalägger frågan för att se till att den körs och att resultaten genereras enligt det önskade intervallet.

#### Använda Frågeredigeraren

Du kan schemalägga en fråga med Frågeredigeraren. När du schemalägger frågan definierar du en utdatamängd. Se [Frågescheman](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules) för mer information.


#### Använda API för frågetjänst

Du kan också använda RESTful API:er för att definiera en fråga och ett schema för frågan. Se [API-guide för frågetjänst](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) för mer information.
Se till att du definierar utdata som en del av det valfria `ctasParameters` egenskap när frågan skapas ([Skapa en fråga](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) eller när schemat skapas för en fråga ([Skapa en schemalagd fråga](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exportera datauppsättningar

När du har skapat och schemalagt din fråga och verifierat resultatet kan du sedan exportera rådatamängderna till molnlagringsmål. Den här exporten sker i Experience Platform Destinations-terminologi, som kallas för datauppsättningens exportdestinationer. Se [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) för en översikt.

Följande molnlagringsmål stöds:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Datallandningszon](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud-lagring](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### Experience Platform UI

Du kan exportera och schemalägga exporten av dina utdatauppsättningar via användargränssnittet i Experience Platform. I det här avsnittet beskrivs de steg som ingår.

#### Välj mål

När du har fastställt vilket molnlagringsmål du vill exportera utdatamängden till, [välj mål](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). När du ännu inte har konfigurerat ett mål för ditt rekommenderade molnlagringsutrymme måste du [skapa en ny målanslutning](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Som en del av konfigurationen av ett mål kan du

- Definiera filtypen (JSON eller Parquet).
- huruvida den resulterande filen ska komprimeras eller inte, och
- om en manifestfil ska inkluderas eller inte.


#### Välj datauppsättning

När du har valt målet, i nästa **[!UICONTROL Select datasets]** måste du välja din utdatauppsättning i listan med datauppsättningar. Om du har skapat flera schemalagda frågor och vill att utdatamängderna ska skickas till samma molnlagringsmål, kan du välja motsvarande utdatamängder. Se [Välj datauppsättningar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) för mer information.

#### Schemalägg datauppsättningsexport

Slutligen vill du schemalägga datauppsättningsexporten som en del av **[!UICONTROL Scheduling]** steg. I det steget kan du definiera schemat och om exporten av utdatauppsättningen ska vara inkrementell eller inte. Se [Schemalägg datauppsättningsexport](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) för mer information.


#### Slutliga steg

[Granska](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) ditt val och, när det är korrekt, börja exportera din utdatauppsättning till molnlagringsmålet.

Du måste [verifiera](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) en lyckad dataexport. När du exporterar datauppsättningar skapas en eller flera i Experience Platform `.json` eller `.parquet` filer på den lagringsplats som är definierad i målet. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.

### API för flödestjänst

Du kan också exportera och schemalägga export av utdatamängder med API:er. Stegen beskrivs i [Exportera datauppsättningar med API:t för Flow Service](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Kom igång

Om du vill exportera datauppsättningar måste du ha [nödvändiga behörigheter](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Verifiera också att målet dit du vill skicka din utdatauppsättning har stöd för export av datauppsättningar. Då måste du [samla in värden för obligatoriska och valfria rubriker](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) som du använder i API-anropen. Du måste också [identifiera anslutningsspecifikation och flödesspec-ID för destinationen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) du tänker exportera datauppsättningar till.

#### Hämta giltiga datauppsättningar

Du kan [hämta en lista över kvalificerade datauppsättningar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) för export och verifiera om din utdatamängd är en del av den listan med [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Skapa källanslutning

Nästa steg [skapa en källanslutning](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) för den utdatamängd, med dess unika ID, som du vill exportera till molnlagringsmålet. Du använder [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Autentisera till mål (skapa basanslutning)

Du måste [skapa en basanslutning](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) för att autentisera och lagra autentiseringsuppgifterna på ett säkert sätt på molnlagringsmålet med [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Ange exportparametrar

Nästa steg är att [skapa ytterligare en målanslutning som lagrar exportparametrarna](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) för dina utdata med [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Dessa exportparametrar inkluderar plats, filformat, komprimering med mera.

#### Ställ in dataflöde

Äntligen får du [konfigurera dataflödet](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) för att se till att din utdatauppsättning exporteras till ditt molnlagringsmål med [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. I det här steget kan du definiera exportschemat med hjälp av `scheduleParams` parameter.

#### Validera dataflöde

Till [kontrollera slutförda körningar av dataflödet](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), använder du [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, ange dataflödes-ID som frågeparameter. Detta dataflödes-ID är en identifierare som returneras när du ställer in dataflödet.

[Verifiera](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) en lyckad dataexport. När du exporterar datauppsättningar skapas en eller flera i Experience Platform `.json` eller `.parquet` filer på den lagringsplats som är definierad i målet. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.

## Slutsats

För att emulera Adobe Analytics Data Feed-funktionaliteten innebär det kort och gott att ställa in schemalagda frågor med hjälp av frågetjänsten och att använda resultaten av dessa frågor vid schemalagd datauppsättningsexport.

>[!IMPORTANT]
>
>Två schemaläggare är inblandade i det här användningsfallet. För att garantera att de emulerade dataflödesuppgifterna fungerar korrekt ska du se till att de scheman som konfigureras i frågetjänsten och dataexporter inte stör.
