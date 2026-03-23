---
description: Lär dig hur du förbereder mappning av dataflödeskolumner från Adobe Analytics till Customer Journey Analytics.
keywords: klickström;datafeed;datafeed;datafeed
title: Förbered för att mappa datautmatningskolumner från Adobe Analytics till Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 5dada1744a479cd4736c9fb7f3c807471e8da226
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 0%

---

# Förbered mappning av dataflödeskolumner från Adobe Analytics till Customer Journey Analytics

När du övergår från Adobe Analytics dataflöden till Customer Journey Analytics dataflöden är det naturligt att du vill mappa alla Adobe Analytics dataflödeskolumner till en dataflödeskolumn i Customer Journey Analytics.

Att mappa dataflödeskolumner från Adobe Analytics till Customer Journey Analytics är dock sällan en-till-en-mappning. Detta beror på följande faktorer:

* **[Schemaarkitektur](#schema-architecture)**: Adobe Analytics dataflödeskolumner härleds från Analytics-variabler, medan Customer Journey Analytics dataflödeskolumner härleds från XDM-schemafält i Experience Platform och datavykomponenter i Customer Journey Analytics.

* **[Implementeringstyp](#implementation-type)**: Adobe Analytics och Customer Journey Analytics har stöd för flera implementeringskonfigurationer. Vilka steg som krävs för att mappa enskilda fält beror på dessa implementeringar.

* **[Databearbetning](#data-processing)**: Det finns skillnader i databearbetning mellan Adobe Analytics och Customer Journey Analytics.

* **[Oanvända kolumner](#unused-columns)**: Adobe Analytics innehåller fler än 1 100 kolumner för datafeed. Identifiera vilka av dessa kolumner som din organisation använder så att du bara kan mappa de kolumner som behövs.

Innan du börjar mappa Adobe Analytics dataflödeskolumner till Customer Journey Analytics dataflödeskolumner ska du läsa igenom avsnitten nedan för att få en bättre förståelse för de nyckelfaktorer som påverkar mappningen.

När du har granskat informationen följer du mappningsinstruktionerna för varje dataflödeskolumn från Adobe Analytics som du vill behålla i Customer Journey Analytics, enligt beskrivningen i [Datakolumnreferens](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

## Schemaarkitektur

XDM-schemat (Experience Data Model), tillsammans med datavyer som används i Customer Journey Analytics, är flexiblare än Adobe Analytics variabelbaserade modell. Därför innehåller organisationens XDM-schema förmodligen inga fält som översätts till en-till-en-kolumnmappningar.

Tänk på följande när det gäller schemaarkitekturen:

* Bristande 1:1-kolumnmappningar innebär inte att ditt Customer Journey Analytics XDM-schema är otillräckligt. Det innebär i stället att du först måste fastställa vilka Adobe Analytics-kolumner för dataflöden du använder och sedan endast mappa dessa kolumner till Customer Journey Analytics dataflöden.

* Customer Journey Analytics XDM-schemat har stöd för kanalövergripande data (t.ex. callcenter-data), som inte är tillgängliga i Adobe Analytics. Dessa flerkanalsfält är exempel på nya kolumner som kan inkluderas i Customer Journey Analytics-dataflöden som inte stöds i Adobe Analytics.

* Fält kan inkluderas i en datafeed från Customer Journey Analytics först när de har inkluderats i XDM-schemat i Experience Platform och sedan strukturerats för användning i datavyn i Customer Journey Analytics.

  Mer information om den här processen för varje potentiell Adobe Analytics-dataflödeskolumn finns i [Datakolumnreferens](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

>[!TIP]
>
>Kontakta om möjligt det team eller den person som skapade XDM-schemat för er organisations Customer Journey Analytics-implementering. Många av besluten om vilka Adobe Analytics-fält som behövdes i Customer Journey Analytics fattades när XDM-schemat skapades. Mer information finns i [Skapa ditt schema för användning med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

## Implementeringstyp

<!--  tons of different AA implementations + tons of different CJA schemas -->

Antalet fält som är tillgängliga att mappa till i ditt Customer Journey Analytics XDM-schema kan variera beroende på hur data samlas in för din Customer Journey Analytics-implementering, enligt följande:

* **Nya SDK-implementeringar för webben**: Om din Customer Journey Analytics-implementering använder ett anpassat schema finns förmodligen inte många kolumner i Adobe Analytics dataflöden i Customer Journey Analytics. På samma sätt kan Customer Journey Analytics innehålla fält som inte finns i Adobe Analytics dataflöden.

* **Analyserar Source Connector-implementeringar**: Det finns 1:1-fältmappningar som standard för många dataflödeskolumner eftersom Analytics Source Connector använder fältgruppen Analytics Experience Event i XDM-schemat. Information om vilka Adobe Analytics-fält som mappas till fält i den här fältgruppen finns i [Mappningar av analysfält](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) i dokumentationen för Experience Platform.

<!-- **Data layer**: ??? -->

## Databehandling

Databehandlingen skiljer sig mellan Adobe Analytics och Customer Journey Analytics enligt följande:

**Adobe Analytics**: Många datafeedfält exporteras som två separata kolumner: en som innehåller förbearbetade data och en annan som innehåller efterbearbetade data. (Efterbearbetade data inkluderar logik på serversidan, bearbetningsregler, VISTA-regler, regler för dimensionskonsistens och så vidare.)

Eftersom Adobe Analytics exporterar data för vissa fält i två separata kolumner (en för förbearbetade data och en för efterbearbetade data) innehåller Adobe Analytics fler dataflödeskolumner än Customer Journey Analytics. Tänk på detta när du mappar fält.

**Customer Journey Analytics**: Det finns fält tillgängliga för dataflöden när de har skapats i datavyn. Vanligtvis innehåller fält i datavyer i Customer Journey Analytics endast efterbearbetade data. Du kan emellertid vanligtvis approximera den förbearbetade Adobe Analytics-versionen av ett fält genom att skapa en andra version av fältet i Customer Journey Analytics datavy och konfigurera det så att det förfaller vid träffen.

## Oanvända kolumner

Det finns över 1 100 dataflödeskolumner som kan exporteras i Adobe Analytics. Av dessa kolumner kommer inte alla att användas i dina Customer Journey Analytics-dataflöden.

Så här avgör du vilka kolumner som ska användas:

* **Identifiera fält som bara gäller för Adobe Analytics**: Vissa kolumner i Adobe Analytics dataflöden är specifika för Adobe Analytics databearbetningsmotor och gäller därför inte för Customer Journey Analytics. Exempel på sådana kolumner är `exclude_hit` och `hit_source`.

* **Identifiera fält som gäller för din organisation**: Även om inte alla Adobe Analytics-kunder exporterar alla tillgängliga kolumner exporterar många kunder mer än de faktiskt använder.

  Innan du börjar mappa dataflödeskolumner måste du identifiera vilka fält som faktiskt används i hela organisationen. Om du vill samla in den här informationen kontaktar du de team eller personer som använder dataflödesinnehåll för Adobe Analytics.



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
