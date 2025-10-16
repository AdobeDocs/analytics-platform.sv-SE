---
title: Importera och använda Experience Platform-målgrupper
description: Beskriver hur man importerar och använder Experience Platform målgrupper till Customer Journey Analytics för vidare analys.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: fc62e87c3a69302c4084bf8c0f6c16520e65d60d
workflow-type: tm+mt
source-wordcount: '1437'
ht-degree: 0%

---

# Importera och använda Experience Platform-målgrupper

I det här fallet utforskas en tillfällig lösning för att få in Experience Platform-målgrupper i Customer Journey Analytics. Dessa målgrupper kan ha skapats i Experience Platform Segment Builder, Adobe Audience Manager eller andra verktyg och lagras i kundprofilen i realtid. Målgrupperna består av en uppsättning profil-ID:n, tillsammans med tillämpliga attribut, händelser med mera. Ni vill överföra målgruppsdata till Customer Journey Analytics för ytterligare analys.

## Förutsättningar

* Åtkomst till [Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/access-control/home), särskilt kundprofil i realtid.
* Åtkomst för att skapa och hantera Experience Platform [scheman](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/home) och [datauppsättningar](https://experienceleague.adobe.com/sv/docs/experience-platform/catalog/datasets/overview).
* Åtkomst till [Experience Platform Query Service](https://experienceleague.adobe.com/sv/docs/experience-platform/query/home) (och möjlighet att skriva SQL).
* Tillgång till ett verktyg som kan utföra vissa omformningar av data.
* Tillgång till Customer Journey Analytics. Du måste vara [Customer Journey Analytics produktadministratör](/help/technotes/access-control.md) för att kunna skapa och ändra Customer Journey Analytics-anslutningar och datavyer.
* [Autentisera och få åtkomst till Experience Platform API:er (katalogtjänstens API och segmenteringstjänstens API)](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/platform-apis/api-authentication). Du måste skapa ett projekt i utvecklarkonsolen för organisationen och sandlådan och se till att du har den information som krävs för att kunna skicka API-anrop.

## Steg

Den tillfälliga lösningen omfattar följande steg:

1. [Välj målgrupper (Experience Platform-gränssnitt)](#select-audiences).
1. [Skapa en profilaktiverad datauppsättning (Experience Platform API)](#create-a-profile-enabled-dataset).
1. [Exportera målgrupper (Experience Platform API)](#export-audiences).
1. [Omforma utdata (Experience Platform-gränssnitt med mera)](#transform-the-output).
1. [Skapa ett schema och en datauppsättning (Experience Platform-gränssnitt)](#create-a-schema-and-dataset).
1. [Lägg till eller redigera en anslutning (Customer Journey Analytics-gränssnitt)](#add-or-edit-a-connection).
1. [Konfigurera en datavy (Customer Journey Analytics UI)](#configure-a-data-view).
1. [Rapportera och analysera (Customer Journey Analytics-gränssnitt)](#report-and-analyze).


### Välj målgrupper

Lösningen börjar med att identifiera de målgrupper ni vill importera i Customer Journey Analytics.

+++ Identifiera målgrupper

I Experience Platform-gränssnittet:

1. Välj **[!UICONTROL Customer]** > ![SegmentAudience](/help/assets/icons2/SegmentAudience.svg) **[!UICONTROL Audiences]**.
1. Välj **[!UICONTROL Browse]** och sök efter de målgrupper som du vill importera och använda i Customer Journey Analytics. Observera **[!UICONTROL Audience Id]** för var och en av målgrupperna för senare bruk.

   ![Publiker](assets/audiences.png)

+++

### Skapa en profilaktiverad datauppsättning

Du måste skapa en datauppsättning baserad på det kärnbaserade **[!UICONTROL XDM Individual Profile]**-schemat. Du kan inte välja den kärnbaserade enskilda XDM-profilen som schema när du skapar en datauppsättning i Experience Platform-gränssnittet. Använd i stället [katalogtjänstens API för att skapa en datauppsättning &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/catalog/datasets/create#create-a-dataset) baserat på `_xdm.context.profile__union`-schemat.

+++ Skapa datauppsättningsbegäran

#### Begäran

```shell
curl -X POST \
  'https://platform.adobe.io/data/foundation/catalog/dataSets?requestDataSource=true' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
   "name": "{DATASET_NAME}",
   "schemaRef": {
      "id": "_xdm.context.profile__union",
      "contentType": "application/vnd.adobe.xed+json;version=1"
   },
   "fileDescription": {
      "persistet": true,
      "containerFormat": "parquet",
      "format": "parquet"
   }
}'
```

Var:

* `DATASET_NAME` är datauppsättningens egna namn. Exempel: `Segment Export Job Dataset for CJA`.

#### Svar

```json
["@/dataSets/{DATASET_ID}"]
```

Var:

* `DATASET_ID` är datauppsättningens identifierare för den skapade datauppsättningen.

+++

### Exportera målgrupper

Exportera de valda målgrupperna till den datauppsättning du just skapade. Använd [Segmenteringstjänstens API för att skapa ett exportjobb](https://experienceleague.adobe.com/sv/docs/experience-platform/segmentation/api/export-jobs#create) som skickar målgrupperna till datauppsättningen.

+++ Exportera jobbförfrågan

```shell
curl -X POST https://platform.adobe.io/data/core/ups/export/jobs \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'Content-Type: application/json' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}' \
 -d '{
    "fields": "{COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES}",
    "filter": {
        "segments": [
            {
                "segmentId": "{AUDIENCE_ID_1}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_2}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_3}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ]             
             }
        ]
    },
    "destination":{
        "datasetId": "{DATASET_ID}",
        "segmentPerBatch": false
    },
    "schema":{
        "name": "_xdm.context.profile"
    }
}'
```

Plats

* `COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES` kan vara något som `_demoemea.identification.core.ecid, _demoemea.identification.core.email, _demoemea.identification.core.phoneNumber, person.gender, person.name.firstName, person.name.lastName`. Se till att du inkluderar åtminstone relevanta fält (som det person-ID (e-post)) som du vill använda i kundreseanalysen.
* `AUDIENCE_ID_x` är målgruppsidentifierare för de målgrupper som du vill exportera.
* `DATASET_ID` är datauppsättningen som du skapade.


### Svar

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
}
```

Plats

* `EXPORT_JOB_ID` är identifieraren för exportjobbet.


+++

Använd [Segmenteringstjänstens API för att kontrollera exportjobbets status &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/segmentation/api/export-jobs#get).

+++ Hämta en specifik begäran om exportjobb

#### Begäran

```shell
curl -X GET https://platform.adobe.io/data/core/ups/export/jobs/{EXPORT_JOB_ID} \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}'
```

#### Svar

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
  "status": "SUCCEEDED",
  "..."
}
```

+++

När exportjobbet har slutförts kontrollerar du om datauppsättningen innehåller inkapslade batchar.

+++ Kontrollera inmatningsstatus

I Experience Platform-gränssnittet:

1. Välj **[!UICONTROL Data Management]** > ![Data](/help/assets/icons2/Data.svg) **[!UICONTROL Datasets]**.
1. Välj den datauppsättning som du skapade, till exempel: **[!UICONTROL Segment Export Job Dataset for CJA]**.

   ![Datauppsättningsaktivitet](assets/dataset-activity.png)

1. Verifiera inkapslade batchar. Om datauppsättningen innehåller misslyckade batchar använder du **[!UICONTROL Data Management]** > ![Övervakning](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Monitoring]** för att se vad som orsakar felet. Du använde till exempel ett fältnamn som inte finns i schemat.
1. Kopiera **[!UICONTROL Table name]** för datauppsättningen. Till exempel: **[!UICONTROL segment_export_job_dataset_for_cja]**.  Du använder det namnet i nästa steg.

+++


### Omforma utdata

Data i datauppsättningen har inte rätt format för Customer Journey Analytics. Använd Experience Platform Query Service för att hämta data när du vill omvandla dessa data.

+++ SQL för att hämta exporterade målgruppsdata

Använd en PSQL-klient som ansluter till Experience Platform Query Service.

I Experience Platform-gränssnittet:

1. Välj **[!UICONTROL Data Management]** > ![DataSearch](/help/assets/icons2/DataSearch.svg) **[!UICONTROL Queries]**.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Credentials]**.

Använd autentiseringsuppgifterna för att konfigurera PSQL-klienten för att ansluta till Customer Journey Analytics Query Service.

#### Fråga

```sql
SELECT ROW_NUMBER() OVER (ORDER BY key)::text as _id, personID, key as audienceMembershipId
FROM (
   SELECT {IDENTITY_TO_USE_AS_PERSON_ID} AS personID, explode(segmentMembership.ups)
   FROM {DATASET_TABLE_NAME}
)
WHERE value.status = 'realized' AND (key = '{AUDIENCE_ID_1}' OR key = 'AUDIENCE_ID_2' OR key = 'AUDIENCE_ID_3')
```

Var:

* `IDENTITY_TO_USE_AS_PERSON_ID` är ett av fälten som du definierade som en del av exportjobbet. Till exempel: `_demoemea.identification.core.email`.
* `AUDIENCE_ID_x` är de målgrupper som du har definierat som en del av exportjobbet. Du måste ange dessa målgrupper en gång till eftersom specifikationen i exportjobbet är ett radnivåfilter. Det radnivåfiltret returnerar profiler för de angivna segmenten med alla segmentmedlemskap för varje profil.


#### Resultat

Resultatet av frågan, i JSON-format, ska se ut så här:

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   },
   {
      "_id": "2",
      "personID": "PERSON_ID_y",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   }

]
```

Var:

* `PERSON_ID_x` är identifierarvärdena för den identifierare som du vill använda som person-ID. Till exempel `john.doe@gmail.com` när du använder e-post.
* `AUDIENCE_ID_x` är målgruppsidentifierare.

+++

Du måste omvandla dessa JSON-data för att lägga till innehavarnamnet för miljön och för att ge målgruppen ett användarvänligt namn.

+++ Omforma JSON

Den slutliga JSON ska se ut så här:

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_x}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_x}"
      }
  },
  {
      "_id": "2",
      "personID": "{PERSON_ID_y}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_y}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_y}"
      }
    }
  }

]
```

Var:

* `TENANT_NAME` är innehavarens namn. Till exempel: `_demoemea`.
* `PERSON_ID_x` är identifierarvärdena för den identifierare som du vill använda som person-ID. Till exempel `john.doe@gmail.com` när du använder e-post.
* `AUDIENCE_ID_x` är målgruppsidentifierare.
* `AUDIENCE_FRIENDLY_NAME_x` är egna målgruppsnamn för målgrupps-ID:n. Till exempel: `Luma - Blue+ Members`.

Använd ditt favoritverktyg för att omvandla den ursprungliga JSON-filen till det här formatet.

+++


### Skapa ett schema och en datauppsättning

Om du vill använda den omformade JSON-versionen som exporterade målgruppsdata i Customer Journey Analytics måste du skapa ett dedikerat schema.

+++ Skapa schema

Så här skapar du schemat:

I Experience Platform-gränssnittet:

1. Välj **[!UICONTROL Data Management]** > ![Schema](/help/assets/icons2/Schema.svg) **[!UICONTROL Schemas]**.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create schema]**. Välj **[!UICONTROL Standard]** i listrutan.
1. Välj **[!UICONTROL Manual]** i dialogrutan **[!UICONTROL Create a schema]** och använd **[!UICONTROL Select]** för att fortsätta.
1. I guiden **[!UICONTROL Create schema]** i steget **[!UICONTROL Select a class]**:
   1. Välj **[!UICONTROL Individual Profile]**.
   1. Välj **[!UICONTROL Next]**.
1. I guiden **[!UICONTROL Create schema]** i steget **[!UICONTROL Name and review]**:
   1. Ange **[!UICONTROL Schema display name]**. Till exempel: `Audience Export for CJA Schema`.
   1. (valfritt) Ange **[!UICONTROL Description]**.
   1. Välj **[!UICONTROL Finish]**.
1. Konfigurera schemat så att det innehåller en anpassad fältgrupp (till exempel **[!UICONTROL Audience Membership]**) som innehåller två fält med namnen **[!UICONTROL audienceMembershipId]** och **[!UICONTROL audienceMembershipName]**.
1. Kontrollera att fältet **[!UICONTROL personID]** är ett **[!UICONTROL Identity]**, **[!UICONTROL Primary Identity]** och har **[!UICONTROL Email]** som I&#x200B;**[!UICONTROL dentity namespace]**.

   ![Segment för export](assets/segment-for-export.png)

1. **[!UICONTROL Apply]** alla ändringar. Välj **[!UICONTROL Save]** om du vill spara schemat.

+++

Skapa en datauppsättning och använd den datauppsättningen för att importera omformade JSON-data.

+++ Skapa datauppsättning och importera data

I Experience Platform-gränssnittet:

1. Välj **[!UICONTROL Data Management]** > ![Schema](/help/assets/icons2/Schema.svg) **[!UICONTROL Datasets]**.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create dataset]**.
1. Välj **[!UICONTROL Create dataset from schema]**.
1. I guiden **[!UICONTROL Create dataset from schema]** i steget **[!UICONTROL Select schema]**:
   1. Välj det schema som du nyss skapade. Till exempel: **[!UICONTROL Audience Export for CJA Schema]**.
   1. Välj **[!UICONTROL Next]**.
1. I guiden **[!UICONTROL Create dataset from schema]** i steget **[!UICONTROL Configure dataset]**:
   1. Ange **[!UICONTROL Name]** som datamängd.
   1. (valfritt) Ange **[!UICONTROL Description]** som datamängd.
   1. Välj **[!UICONTROL Finish]**.
1. Dra den omformade JSON-datafilen i **[!UICONTROL Datasets]** > **[!UICONTROL _namnet på datauppsättningen_]** och släpp filen på **[!UICONTROL Drag and drop files]**. Den här åtgärden startar inmatningen av exporterade JSON-data i datauppsättningen.
1. Verifiera inkapslade batchar. Om datauppsättningen innehåller misslyckade batchar använder du **[!UICONTROL Data Management]** > ![Övervakning](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Monitoring]** för att se vad som orsakar felet. Du har till exempel definierat ett fältnamn i JSON som inte finns i schemat.


+++

### Lägga till eller redigera en anslutning

När de omformade JSON-data som innehåller målgruppsdata från Experience Platform har importerats kan du lägga till datauppsättningen i en ny eller befintlig anslutning i Customer Journey Analytics.

+++ Lägg till datauppsättning i anslutning

I Customer Journey Analytics-gränssnittet:

1. Välj **[!UICONTROL Data Management]** > **[!UICONTROL Connections]**.
1. Skapa en ny anslutning/Definiera **[!UICONTROL Connection settings]** och **[!UICONTROL Data settings]**. Du kan också markera en befintlig anslutning och använda ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit Connection]** för att redigera anslutningen.
1. Välj ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Add datasets]**.
1. Markera den datauppsättning som du skapade och i vilken du importerade omformade JSON-data.
1. Konfigurera datauppsättningen. Exempel:

   ![Anslutning - datauppsättning med exporterade målgruppsdata](assets/connection-add-dataset.png)

1. **[!UICONTROL Save]** anslutningen.

+++

### Konfigurera en datavy

Konfigurera en datavy för anslutningen som du nyss skapade eller redigerade.

+++ Definiera publikkomponenter

1. Välj **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.
1. Redigera en befintlig datavy eller skapa en ny datavy.
1. Kontrollera att **[!UICONTROL Components]** och **[!UICONTROL Audience Membership Id]** har lagts till som dimensionskomponenter på fliken **[!UICONTROL Audience Membership Name]** i datavyn.

   ![Datavykomponenter](assets/dataview-components.png)

1. Välj **[!UICONTROL Save and Continue]** om du vill spara datavyn.

+++

### Rapportera och analysera

Använd slutligen Analysis Workspace för att rapportera om Experience Platform målgruppsdata i en eller flera paneler som använder datavyn med målgruppskomponenterna som `audienceMembershipId`, `audienceMembershipIdName` och `personID`.



<!--

## Step 1: Select audiences in Real-time Customer Profile {#audience}

Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv-SE) lets you see a holistic view of each individual customer by combining data from multiple channels, including online, offline, CRM, and third party. 

You likely already have audiences in RTCP that may have come from various sources. Select one or more audiences to ingest into Customer Journey Analytics. For example, WKND Fly Platinum and Gold Fly Club Members.




## Step 2: Create a Profile Union dataset for the export

In order to export the audience to a dataset that you can ingest in Customer Journey Analytics as profiles, create a dataset whose schema is a Profile [Union schema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=sv-SE#understanding-union-schemas).

Union schemas are composed of multiple schemas that share the same class and have been enabled for Profile. The union schema enables you to see an amalgamation of all of the fields contained within schemas sharing the same class. Real-time Customer Profile uses the union schema to create a holistic view of each individual customer.

## Step 3: Export an audience to the Profile Union dataset via API call {#export}

Before you can bring an audience into Customer Journey Analytics, you need to export it to an Adobe Experience Platform dataset. This can only be done using the Segmentation API, and specifically the [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=sv-SE). 

You can create an export job using the audience ID of your choice, and put the results in the Profile Union Adobe Experience Platform dataset you created in Step 2. Although you can export various attributes/events for the audience, you only need to export the specific profile ID field that matches the person ID field used in the Customer Journey Analytics connection you will be leveraging (see below in Step 5).

## Step 4: Edit the export output 

The results of the export job need to be transformed into a separate Profile dataset in order to be ingested into Customer Journey Analytics.  This transformation can be done with [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv-SE), or another transformation tool of your choice. We only need the Profile ID (that will match the Person ID in Customer Journey Analytics) and one or more audience ID(s) to do the reporting in Customer Journey Analytics.

The standard export job, however, contains more data and so we need to edit this output to remove extraneous data, as well as move some things around.  Also, you need to create a schema/dataset first before you add the transformed data to it.

Here is an example of the export output in the Profile union dataset, **before** any editing:

![Unedited output](../assets/export-unedited.png)

Note the following:

* The audience ID is contained under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* The status has to be "realized", or "entered", but not "exited".

This is the format of the Profile dataset that you can send into Customer Journey Analytics.

![Edited output](../assets/export-edited.png)

Here are the data elements that need to be present:

* `_aresprodvalidation` string field: Refers to your Organization ID. Yours will be different.
* `personID` string field: This is the standard XDM schema field on Profile datasets to identity the person. Use the Profile ID from the export.
* `audienceMembershipId` string field: The audience ID from the export.  NOTE: This field can be named whatever you want (from your own schema).
* Add a friendly name for the audience (`audienceMembershipIdName`), such as

   ![Friendly audience name](../assets/audience-name.png)
   
* Add other audience metadata if you desire.

## Step 5: Add this Profile dataset to an existing connection in Customer Journey Analytics

You could [create a new connection](/help/connections/create-connection.md), but most customers will want to add the Profile dataset to an existing connection. The audience IDs "enrich" the existing data in Customer Journey Analytics.

## Step 6: Modify existing (or create new) Customer Journey Analytics data view

Add `audienceMembershipId`, `audienceMembershipIdName` and `personID` to the data view.

## Step 7: Report in Workspace

You can now report on `audienceMembershipId`, `audienceMembershipIdName` and `personID` in Workspace.

-->


## Ytterligare information

* Du bör utföra den här processen regelbundet så att målgruppsdata uppdateras kontinuerligt i Customer Journey Analytics.
* Du kan importera flera målgrupper i en enda Customer Journey Analytics-anslutning. Detta gör processen ännu mer komplicerad, men det är möjligt. För att detta ska fungera måste du göra några ändringar i ovanstående process:
   1. Utför den här processen för varje målgrupp i målgruppssamlingen inom RTCP.
   1. Customer Journey Analytics har stöd för arrayer/objektarrayer i profildatamängder. Det bästa alternativet är att använda en [objektmatris &#x200B;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=sv-SE) för `audienceMembershipId` eller `audienceMembershipIdName`.
   1. I datavyn skapar du en ny dimension med delsträngsomformningen i fältet `audienceMembershipId` för att konvertera den kommaavgränsade värdesträngen till en array. Obs! Det finns för närvarande en gräns på 10 värden i arrayen.
   1. Du kan nu rapportera om den nya dimensionen `audienceMembershipIds` i Customer Journey Analytics Workspace.
