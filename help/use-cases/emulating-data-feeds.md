---
title: Emulera funktioner för datafeed
description: Förstå hur ni kan emulera dataflöden från Adobe Analytics med data i Experience Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: b41adb3f3fa4abbfa7be491e5a1fbf81e1623598
workflow-type: tm+mt
source-wordcount: '2552'
ht-degree: 0%

---

# Emulera funktioner för datafeed

Adobe Analytics dataflöden är ett kraftfullt sätt att få ut rådata från Adobe Analytics. I det här användningsexemplet beskrivs hur du hämtar liknande typer av rådata från Experience Platform, så att du kan använda data på andra plattformar, verktyg utanför Adobe och efter din organisations gottfinnande.

## Introduktion

Emulering av en datafeed från Adobe Analytics innefattar:

* definiera en **schemalagd fråga** som genererar data för din datafeed som en utdatauppsättning ![utdatamängd](assets/output-dataset.svg), använda **Frågetjänst**.
* definiera en **schemalagd datauppsättningsexport** som exporterar utdata till ett molnlagringsmål, med **Datauppsättningsexport**.

![Datafeed](assets/data-feed.svg)


## Förutsättningar

Kontrollera att du uppfyller alla följande krav innan du använder de funktioner som beskrivs i det här fallet:

* En fungerande implementering som samlar in data i Experience Platform datarö.
* Tillgång till tillägget Data Distiller för att säkerställa att du har rätt att köra gruppfrågor. Se [Paket för frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) för mer information.
* Tillgång till funktionen Exportera datauppsättningar, som är tillgänglig när du har köpt Real-Time CDP Prime- eller Ultimate-paketet, Adobe Journey Optimizer eller Customer Journey Analytics. Se [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en) för mer information.
* En eller flera destinationer (till exempel Amazon S3, Google Cloud-lagring) som konfigurerats för att exportera rådata från din datafeed.


## Frågetjänst

Med Experience Platform Query Service kan du söka efter och ansluta till alla datauppsättningar i Experience Platform Data Lake som om det vore en databastabell. Sedan kan du samla in resultaten som en ny datauppsättning och använda den för vidare rapportering eller för export.

Du använder tjänsten Query Service [användargränssnitt](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [klienten ansluten via protokollet PostgresQL](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en), eller [RESTful API:er](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) för att skapa och schemalägga frågor som samlar in data för din datafeed.

### Skapa fråga

Du kan använda all funktionalitet som finns i ANSI SQL för SELECT-satser och andra begränsade kommandon för att skapa och köra frågor som genererar data för din datafeed. Se [SQL-syntax](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) för mer information. Utöver denna SQL-syntax stöder Adobe:

* fördefinierad [Adobe-definierade funktioner (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) som kan utföra vanliga affärsrelaterade uppgifter på händelsedata som lagras i Experience Platform, inklusive funktioner för [Yrkesställning](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=en) och [Attribut](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en),
* inbyggda [Spark SQL-funktioner](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [metadata PostgreSQL-kommandon](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [förberedda programsatser](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Identiteter

I Experience Platform finns olika identiteter. När du skapar dina frågor måste du kontrollera att du frågar identiteter korrekt.

Du hittar ofta identiteter i en separat fältgrupp. I en implementering av ECID (`ecid`) kan definieras som en del av en fältgrupp med en `core` -objekt, som i sin tur är en del av ett `identification` -objekt. (till exempel: `_sampleorg.identification.core.ecid`). ECID:n kan ordnas på olika sätt i dina scheman.

Du kan också använda `identityMap` för att fråga efter identiteter. Det här objektet är av typen `Map` och använder [kapslad datastruktur](#nested-data-structure).


#### Datautmatningskolumner

Vilka XDM-fält du kan använda i frågan beror på schemadefinitionen som datamängderna baseras på. Se till att du förstår schemat som ligger till grund för datauppsättningen.

För att underlätta mappningen mellan kolumnerna för dataflöde och XDM-fälten bör du överväga att ta med [Adobe Analytics ExperienceEvent-mall](https://github.com/adobe/xdm/blob/master/extensions/adobe/experience/analytics/experienceevent-all.schema.json) fältgrupp i ditt händelseschema för upplevelser. Se [Bästa tillvägagångssätt för datamodellering](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en) och mer specifikt [Schemafältgrupper för Adobe](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en#adobe-application-schema-field-groups).

Om du till exempel vill använda *sidnamn* som en del av ditt dataflöde:

* I Adobe Analytics Data Feed&#39;s UI väljer du **[!UICONTROL pagename]** som den kolumn som ska läggas till i dataflödesdefinitionen.
* I frågetjänsten inkluderar du `web.webPageDetails.name` från `sample_event_dataset_for_website_global_v1_1` datauppsättning (baserat på **Exempel på händelseschema för webbplats (Global v1.1)** händelseschema) i din fråga. Se [Schemafältgrupp för webbinformation](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) för mer information.

Mer information om mappningen mellan tidigare Adobe Analytics-dataflödeskolumner och XDM-fält i händelsedatamängden och det underliggande schemat finns i [Mappning av analysfält](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en) och [Schemafältgruppen Adobe Analytics ExperienceEvent Full Extension](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) för mer information.

Dessutom har [automatiskt insamlade uppgifter från Experience Platform Web SDK (utanför paketet)](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) kan vara relevant för att identifiera kolumner för din fråga.

#### Data och identifiering på träffnivå

Baserat på implementeringen lagras data på träffnivå som traditionellt samlats in i Adobe Analytics som tidsstämplade händelsedata i Experience Platform. Följande tabell extraheras från [Mappning av analysfält](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en#generated-mapping-fields) och visar exempel på hur du mappar träffnivåspecifika Adobe Analytics Data Feed-kolumner med motsvarande XDM-fält i dina frågor. Tabellen visar också exempel på hur träffar, besök och besökare identifieras med hjälp av XDM-fält.

| Datafeedkolumn | XDM-fält | Typ | Beskrivning |
|---|---|---|---|
| hitid_high + hitid_low | _id | string | En unik identifierare som identifierar en träff. |
| hitid_low | _id | string | Används tillsammans med hitid_high för att unikt identifiera en träff. |
| hitid_high | _id | string | Används tillsammans med hitid_high för att unikt identifiera en träff. |
| hit_time_gmt | receiveTimestamp | string | Tidsstämpeln för träffen, baserad på Unix-tid. |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | string | Tidsstämpel för besökarens första träff i Unix-tid. |
| cust_hit_time_gmt | tidsstämpel | string | Detta används endast i tidsstämpelaktiverade datauppsättningar. Det här är den tidsstämpel som skickas med den, baserat på Unix-tid. |
| visid_high + visid_low | identityMap | object | En unik identifierare för ett besök. |
| visid_high + visid_low | endUserID:n._experience.aaid.id | string | En unik identifierare för ett besök. |
| visid_high | endUserID:n._experience.aaid.primär | boolesk | Används tillsammans med visid_low för att unikt identifiera ett besök. |
| visid_high | endUserID:n._experience.aaid.namespace.code | string | Används tillsammans med visid_low för att unikt identifiera ett besök. |
| visid_low | identityMap | object | Används tillsammans med visid_high för att unikt identifiera ett besök. |
| cust_visid | identityMap | object | Kundbesökaren I.D |
| cust_visid | endUserID:n._experience.acustomid.id | object | Kundens besökar-ID. |
| cust_visid | endUserID:n._experience.acustomid.primär | boolesk | Kundbesökarens ID-namnområdeskod. |
| cust_visid | endUserID:n._experience.acustomid.namespace.code | string | Används tillsammans med visid_low för att unikt identifiera kundbesöks-ID. |
| geo\_* | placeContext.geo.* | sträng, tal | Geolokaliseringsdata, som land, region, stad och andra |
| besök_sidnummer | _experience.analytics.session.depth | tal | En variabel som används i dimensionen Träff. Värdet ökar med 1 för varje träff som användaren skapar och återställs efter varje besök. |
| event_list | commerce.purchasing, commerce.productViews, commerce.productListOpen, commerce.checkouts, commerce.productListAdds, commerce.productListRemovals, commerce.productListViews, \_experience.analytics.event101to200.*, ..., \_experience.analytics.event901_1000.\* | string | Standardhandel och anpassade händelser som utlöses vid träffen. |
| page_event | web.webInteraction.type | string | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, slutlänk eller anpassad länk som klickats). |
| page_event | web.webInteraction.linkClicks.value | tal | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, slutlänk eller anpassad länk som klickats). |
| page_event_var_1 | web.webInteraction.URL | string | En variabel som bara används för bildbegäran för länkspårning. Den här variabeln innehåller URL:en för den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickat på. |
| page_event_var_2 | web.webInteraction.name | string | En variabel som bara används för bildbegäran för länkspårning. Här visas länkens egna namn, om det har angetts. |
| first_hit_ref_type | _experience.analytics.endUser.firstWeb.webReferrer.type | string | Det numeriska ID:t som representerar referenstypen för besökarens allra första referent. |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | heltal | Tidsstämpel för besökarens första träff i Unix-tid. |
| paid_search | search.isPaid | boolesk | En flagga som anges om träffen matchar betalsökningsidentifiering. |
| ref_type | web.webReferrertype | string | Ett numeriskt ID som representerar typen av referens för träffen. |

#### Bokför kolumner

Adobe Analytics Data Feeds använder begreppet kolumner med en `post_` -prefix, som är kolumner som innehåller data efter bearbetning. Se [Vanliga frågor om dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html?lang=en#post) för mer information.

Data som samlas in i datauppsättningar via Experience Platform Edge Network (Web SDK, Mobile SDK, Server API) har inget koncept `post_` fält, vilket förklarar varför `post_` prefix och *ej* `post_` Kolumner för prefix-datafeed i analysfältet mappas till samma XDM-fält. Till exempel båda `page_url` och `post_page_url` dataflödeskolumner mappas till samma `web.webPageDetails.URL` XDM-fält.

Se [Jämför databehandling i Adobe Analytics och Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=en) för en översikt över skillnaden i databehandling.

The `post_` när data samlas in i dataljön med prefix kräver det dock avancerade omformningar innan de kan användas i ett dataflöde. När du utför dessa avancerade omformningar i dina frågor måste du använda [Funktioner som definieras av Adobe](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) för sessioner, attribuering och deduplicering. Se [Exempel](#examples) om hur du använder dessa funktioner.

#### Uppslag

Om du vill söka efter data från andra datauppsättningar använder du standardfunktionen för SQL (`WHERE` -sats, `INNER JOIN`, `OUTER JOIN`, med flera).

#### Beräkningar

Om du vill utföra beräkningar i fält (kolumner) använder du SQL-standardfunktionerna (till exempel `COUNT(*)` eller [matematiska och statistiska operatorer och funktioner](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) ingår i Spark SQL. Dessutom [fönsterfunktioner](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en#window-functions) har stöd för att uppdatera aggregeringar och returnera enstaka objekt för varje rad i en ordnad delmängd. Se [Exempel](#examples) om hur du använder dessa funktioner.

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

Du kan använda [`explode()` eller andra arrayfunktioner](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) från Spark SQL för att komma till data i en kapslad datastruktur, till exempel:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Du kan också referera till enskilda element med punktnotation. Exempel:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Se [Arbeta med kapslade datastrukturer i frågetjänsten](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) för mer information.


#### Exempel

Exempelfrågor som använder data från datauppsättningar i datavjön på Experience Platform, utnyttjar de extra funktionerna i Adobe Defined Function och/eller Spark SQL, och som skulle ge liknande resultat som en likvärdig Adobe Analytics datafeed, finns i

* [övergiven surfning](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en),
* [attribueringsanalys](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en),
* [startsfiltrering](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en),
* och andra exempel på hur du kan använda dem i guiden för frågetjänsten.


### Schemaläggningsfråga

Du schemalägger frågan för att se till att den körs och att resultaten genereras enligt det önskade intervallet.

#### Använda Frågeredigeraren

Du kan schemalägga en fråga med Frågeredigeraren. När du schemalägger frågan definierar du en utdatamängd. Se [Frågescheman](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) för mer information.


#### Använda API för frågetjänst

Du kan också använda RESTful API:er för att definiera en fråga och ett schema för frågan. Se [API-guide för frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) för mer information.
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

