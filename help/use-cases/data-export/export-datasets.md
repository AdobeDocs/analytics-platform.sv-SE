---
title: Customer Journey Analytics Export datasets
description: Beskriver hur du använder Exportera datauppsättningar för att säkerhetskopiera dina data.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 0%

---


# Exportera datauppsättningar

I den här artikeln beskrivs hur [!DNL Customer Journey Analytics Export datasets] kan användas för att implementera följande [användningsfall vid dataexport](overview.md):

- Säkerhetskopiering av data

## Introduktion

Exportera data med [!DNL Experience Platform Export datasets] Med kan du exportera data från datavyer i Customer Journey Analytics till valfritt molnlagringsmål.

![BI-tillägg](../assets/export-datasets.svg)

## Mer information

Du kan exportera rådatauppsättningar, från datasjön i Experience Platform, till molnlagringsmål. Den här exporten sker i Experience Platform Destinations-terminologi, som kallas för datauppsättningens exportdestinationer. Se [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) för en översikt.

Följande molnlagringsmål stöds:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Datallandningszon](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud-lagring](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### Experience Platform UI

Du kan exportera och schemalägga exporten av dina datauppsättningar via användargränssnittet i Experience Platform. I det här avsnittet beskrivs de steg som ingår.

#### Välj mål

När du har fastställt molnlagringsmålet till den plats där du vill exportera datauppsättningen till [välj mål](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). När du ännu inte har konfigurerat ett mål för ditt rekommenderade molnlagringsutrymme måste du [skapa en ny målanslutning](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Som en del av konfigurationen av ett mål kan du definiera:

- filtypen (JSON eller Parquet),
- huruvida den resulterande filen ska komprimeras eller inte, och
- om en manifestfil ska inkluderas eller inte.


#### Välj datauppsättning

När du har valt målet, i nästa **[!UICONTROL Select datasets]** måste du välja datauppsättningen i listan med datauppsättningar. Om du har skapat flera schemalagda frågor och vill att datauppsättningarna ska skickas till samma molnlagringsmål, kan du välja motsvarande datauppsättningar. Se [Välj datauppsättningar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) för mer information.

#### Schemalägg datauppsättningsexport

Slutligen vill du schemalägga datauppsättningsexporten som en del av **[!UICONTROL Scheduling]** steg. I det steget kan du definiera schemat och om datauppsättningsexporten ska vara inkrementell eller inte. Se [Schemalägg datauppsättningsexport](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) för mer information.


#### Slutliga steg

[Granska](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) ditt val och, när det är korrekt, börja exportera datauppsättningen till molnlagringsmålet.

Först måste du [verifiera](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) en lyckad dataexport. När du exporterar datauppsättningar skapas en eller flera i Experience Platform `.json` eller `.parquet` filer på den lagringsplats som är definierad i målet. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.

### API för flödestjänst

Du kan också exportera och schemalägga export av datauppsättningar med API:er. Stegen beskrivs i [Exportera datauppsättningar med API:t för Flow Service](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Kom igång

Om du vill exportera datauppsättningar måste du ha [nödvändiga behörigheter](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Verifiera också att målet dit du vill skicka datauppsättningen har stöd för export av datauppsättningar. Då måste du [samla in värden för obligatoriska och valfria rubriker](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) som du använder i API-anropen. Du måste också [identifiera anslutningsspecifikation och flödesspec-ID för destinationen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) du tänker exportera datauppsättningar till.

#### Hämta giltiga datauppsättningar

Du kan [hämta en lista över kvalificerade datauppsättningar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) för export och verifiera om datauppsättningen ingår i den listan med [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Skapa källanslutning

Nästa steg är att [skapa en källanslutning](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) för datauppsättningen, med hjälp av dess unika ID, som du vill exportera till molnlagringsmålet. Du använder [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Autentisera till mål (skapa basanslutning)

Du måste [skapa en basanslutning](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) för att autentisera och lagra autentiseringsuppgifterna på ett säkert sätt på molnlagringsmålet med [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Ange exportparametrar

Nästa steg är att [skapa ytterligare en målanslutning som lagrar exportparametrarna](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) för datauppsättningen med [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Dessa exportparametrar inkluderar plats, filformat, komprimering med mera.

#### Ställ in dataflöde

Äntligen får du [konfigurera dataflödet](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) för att säkerställa att datauppsättningen exporteras till molnlagringsmålet med hjälp av [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. I det här steget kan du definiera exportschemat med hjälp av `scheduleParams` parameter.

#### Validera dataflöde

Till [kontrollera slutförda körningar av dataflödet](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), använder du [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, ange dataflödes-ID som frågeparameter. Detta dataflödes-ID är en identifierare som returneras när du ställer in dataflödet.

[Verifiera](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) en lyckad dataexport. När du exporterar datauppsättningar skapas en eller flera i Experience Platform `.json` eller `.parquet` filer på den lagringsplats som är definierad i målet. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.
