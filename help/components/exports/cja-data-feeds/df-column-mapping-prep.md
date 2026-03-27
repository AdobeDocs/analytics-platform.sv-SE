---
description: Lär dig hur du förbereder mappning av dataflödeskolumner från Adobe Analytics till Customer Journey Analytics.
keywords: klickström;datafeed;datafeed;datafeed
title: Förbered för att mappa datautmatningskolumner från Adobe Analytics till Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
source-git-commit: 9403a4c6d0e0389de19aa4627d9d952f0c31f1a2
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 0%

---

# Förbered mappning av dataflödeskolumner från Adobe Analytics till Customer Journey Analytics

Customer Journey Analytics erbjuder en mer flexibel arkitektur än Adobe Analytics för att fastställa vilka kolumner som är tillgängliga för att inkluderas i en datafeed. De flesta organisationer bör förvänta sig att kunna exportera andra dataflödeskolumner från Customer Journey Analytics än de exporterar från Adobe Analytics. Dessa skillnader beror på följande faktorer:

* **[Schemaarkitektur](#schema-architecture)**: Adobe Analytics dataflödeskolumner härleds från Analytics-variabler, medan Customer Journey Analytics dataflödeskolumner härleds från datavyschemat.

* **[Databearbetning](#data-processing)**: Det finns grundläggande skillnader i databearbetning mellan Adobe Analytics och Customer Journey Analytics, särskilt förekomsten av både för- och efterbearbetade kolumner för många Adobe Analytics-kolumner.

* **[Oanvända kolumner](#unused-columns)**: Adobe Analytics innehåller fler än 1 100 kolumner för datafeed. De flesta organisationer använder inte data från alla kolumner som exporteras.

* **[Flerkanalskolumner](#cross-channel-columns)**: Customer Journey Analytics har stöd för flerkanalsdata (till exempel callcenter-data), som inte är tillgängliga i Adobe Analytics.

Innan du börjar mappa Adobe Analytics dataflödeskolumner till Customer Journey Analytics dataflödeskolumner ska du läsa igenom avsnitten nedan för att få en bättre förståelse för de nyckelfaktorer som påverkar mappningen.

När du har granskat informationen följer du mappningsinstruktionerna för varje dataflödeskolumn från Adobe Analytics som du vill behålla i Customer Journey Analytics, enligt beskrivningen i [Datakolumnreferens](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

## Schemaarkitektur

Customer Journey Analytics erbjuder en mer flexibel arkitektur än Adobe Analytics för att avgöra vilka kolumner som är tillgängliga för att inkluderas i en datafeed:

### Adobe Analytics-arkitektur

Det finns en fördefinierad, statisk lista med variabler som kan inkluderas som dataflödeskolumner.

Det är enkelt att ta med alla kolumner, och många kunder gör det, även när data i dessa kolumner inte används i hela organisationen.

### Customer Journey Analytics-arkitektur

Alla komponenter som ingår i datavyschemat kan inkluderas som dataflödeskolumner. Mer information om den här processen för varje potentiell Adobe Analytics-dataflödeskolumn finns i [Datakolumnreferens](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

Komponenter inkluderas i datavyschemat på något av de sätt som beskrivs i följande tabell:

| Metod för inkludering i datavyns schema | Ytterligare information |
|---------|----------|
| XDM-schemafält struktureras som komponenter i datavyn | Fält som finns i XDM-schemat blir en del av datavyschemat i Customer Journey Analytics när de har strukturerats som komponenter i datavyn. <p>Antalet fält som är tillgängliga som standard i ditt Customer Journey Analytics XDM-schema kan variera beroende på hur data samlas in för din Customer Journey Analytics-implementering, enligt följande:</p><ul><li>**Nya SDK-implementeringar för webben**: Om din Customer Journey Analytics-implementering använder ett anpassat schema finns förmodligen inte många kolumner i Adobe Analytics dataflöden i Customer Journey Analytics. På samma sätt kan Customer Journey Analytics innehålla fält som inte finns i Adobe Analytics dataflöden.<p>Kontakta om möjligt det team eller den person som skapade XDM-schemat för er organisations Customer Journey Analytics-implementering. Många av besluten om vilka Adobe Analytics-fält som behövdes i Customer Journey Analytics fattades när XDM-schemat skapades. Mer information finns i [Skapa ditt schema för användning med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).</p></li><li>**Analyserar Source Connector-implementeringar**: Det finns 1:1-fältmappningar som standard för många dataflödeskolumner eftersom Analytics Source Connector använder fältgruppen Analytics Experience Event i XDM-schemat. Information om vilka Adobe Analytics-fält som mappas till fält i den här fältgruppen finns i [Mappningar av analysfält](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) i Experience Platform-dokumentationen.</li></ul> |
| Komponenter skapas i datavyn med hjälp av härledda fält | Du kan skapa komponenter direkt i en datavy och på så sätt skapa dataflödeskolumner som inte är tillgängliga i XDM-schemat. |

## Databehandling

Skillnader i databehandling mellan Adobe Analytics och Customer Journey Analytics påverkar vilka dataflödeskolumner som är tillgängliga för export enligt följande:

* **Adobe Analytics**: Många datafeedfält exporteras som två separata kolumner: en som innehåller förbearbetade data och en annan som innehåller efterbearbetade data. (Efterbearbetade data inkluderar logik på serversidan, bearbetningsregler, VISTA-regler, regler för dimensionskonsistens och så vidare.)

  Eftersom Adobe Analytics exporterar data för vissa fält i två separata kolumner (en för förbearbetade data och en för efterbearbetade data) innehåller Adobe Analytics fler dataflödeskolumner än Customer Journey Analytics. Tänk på detta när du mappar fält.

* **Customer Journey Analytics**: Det finns fält tillgängliga för dataflöden när de har skapats i datavyn. Vanligtvis innehåller fält i datavyer i Customer Journey Analytics endast efterbearbetade data. Du kan emellertid vanligtvis approximera den förbearbetade Adobe Analytics-versionen av ett fält genom att skapa en andra version av fältet i Customer Journey Analytics datavy och konfigurera det så att det förfaller vid träffen.

## Oanvända kolumner

Det finns över 1 100 dataflödeskolumner som kan exporteras i Adobe Analytics. Av dessa kolumner kommer inte alla att användas i dina Customer Journey Analytics-dataflöden. Skillnaden är inte ett tecken på att dina Customer Journey Analytics-kolumner för dataflöden är otillräckliga.

Identifiera vilka av Adobe Analytics-kolumnerna för dataflöde som din organisation använder. Om du gör det informeras vilka kolumner som behövs i dina Customer Journey Analytics-dataflöden. Så här avgör du vilka kolumner som ska användas:

* **Identifiera fält som bara gäller för Adobe Analytics**: Vissa kolumner i Adobe Analytics dataflöden är specifika för Adobe Analytics databearbetningsmotor och gäller därför inte för Customer Journey Analytics. Exempel på sådana kolumner är `exclude_hit` och `hit_source`.

* **Identifiera fält som gäller för din organisation**: Även om inte alla Adobe Analytics-kunder exporterar alla tillgängliga kolumner exporterar många kunder mer än de faktiskt använder.

  Innan du börjar exportera dataflöden från Customer Journey Analytics bör du först fastställa vilka Adobe Analytics-dataflödeskolumner din organisation använder för närvarande och sedan se till att dessa komponenter finns i Customer Journey Analytics datavyschema. Om du vill samla in den här informationen kontaktar du de team eller personer i organisationen som använder dataflödesinnehåll för Adobe Analytics.

## Flerkanalskolumner

Customer Journey Analytics stöder flerkanalsdata (t.ex. callcenter-data) som inte är tillgängliga i Adobe Analytics. Dessa flerkanalsfält är exempel på nya kolumner som kan inkluderas i Customer Journey Analytics-dataflöden, som inte stöds i Adobe Analytics.

<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
