---
title: Customer Journey Analytics Export datasets
description: Beskriver hur du använder Exportera datauppsättningar för att säkerhetskopiera dina data.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 0%

---

# Exportera datauppsättningar

I den här artikeln beskrivs hur [!DNL Customer Journey Analytics Export datasets] kan användas för att implementera följande [användningsfall för dataexport](overview.md):

- Säkerhetskopiering av data

## Introduktion

Genom att exportera data med [!DNL Experience Platform Export datasets] kan du exportera data från datavyer i Customer Journey Analytics till valfritt molnlagringsmål.

![BI-tillägg](../assets/export-datasets.svg)

## Mer information

Du kan exportera rådatauppsättningar, från datasjön i Experience Platform, till molnlagringsmål. Den här exporten sker i Experience Platform Destinations-terminologi, som kallas för datauppsättningens exportdestinationer. Se [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets) för en översikt.

Följande molnlagringsmål stöds:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Datalandningszon](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud-lagring](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure-blob](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### Experience Platform UI

Du kan exportera och schemalägga exporten av dina datauppsättningar via användargränssnittet i Experience Platform. I det här avsnittet beskrivs de steg som ingår.

#### Välj mål

När du har fastställt molnlagringsmålet till den plats där du vill exportera datauppsättningen till [väljer du målet](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Om du ännu inte har konfigurerat ett mål för ditt rekommenderade molnlagringsutrymme måste du [skapa en ny målanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/connect-destination).

Som en del av konfigurationen av ett mål kan du definiera:

- filtypen (JSON eller Parquet),
- huruvida den resulterande filen ska komprimeras eller inte, och
- om en manifestfil ska inkluderas eller inte.


#### Välj datauppsättning

När du har valt målet måste du i nästa **[!UICONTROL Select datasets]**-steg välja din datauppsättning från listan med datauppsättningar. Om du har skapat flera schemalagda frågor och vill att datauppsättningarna ska skickas till samma molnlagringsmål, kan du välja motsvarande datauppsättningar. Mer information finns i [Välj datauppsättningar](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets).

#### Schemalägg datauppsättningsexport

Slutligen vill du schemalägga datauppsättningsexporten som en del av **[!UICONTROL Scheduling]**-steget. I det steget kan du definiera schemat och om datauppsättningsexporten ska vara inkrementell eller inte. Mer information finns i [Schemalägg datauppsättningsexport](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling).


#### Slutliga steg

[Granska](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#review) ditt val och börja exportera datauppsättningen till molnlagringsmålet när det är korrekt.

Först måste du [verifiera](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#verify) för att dataexporten ska lyckas. När du exporterar datauppsättningar skapar Experience Platform en eller flera `.json`- eller `.parquet`-filer på den lagringsplats som är definierad i ditt mål. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.

### API för flödestjänst

Du kan också exportera och schemalägga export av datauppsättningar med API:er. Stegen som ingår beskrivs i [Exportera datauppsättningar med API:t för Flow Service &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets).

#### Kom igång

Om du vill exportera datauppsättningar måste du ha de [nödvändiga behörigheterna](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#permissions). Verifiera också att målet dit du vill skicka datauppsättningen har stöd för export av datauppsättningar. Du måste sedan [samla in värdena för obligatoriska och valfria rubriker](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) som du använder i API-anropen. Du måste också [identifiera anslutningsspec- och flödesspec-ID:n för målet &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) som du tänker exportera datamängder till.

#### Hämta giltiga datauppsättningar

Du kan [hämta en lista över kvalificerade datauppsättningar](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) för export och verifiera om din datauppsättning är en del av den listan med API:t för [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets).


#### Skapa källanslutning

Därefter måste du [skapa en källanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#create-source-connection) för datauppsättningen, med hjälp av dess unika ID, som du vill exportera till molnlagringsmålet. Du använder API:t [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection).

#### Autentisera till mål (skapa basanslutning)

Du måste nu [skapa en basanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#create-base-connection) för att autentisera och lagra autentiseringsuppgifterna på ett säkert sätt på molnlagringsmålet med API:t [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection).


#### Ange exportparametrar

Därefter måste du [skapa ytterligare en målanslutning som lagrar exportparametrarna &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#create-target-connection) för datauppsättningen med [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API:t. Dessa exportparametrar inkluderar plats, filformat, komprimering med mera.

#### Ställ in dataflöde

Slutligen [konfigurerar du dataflödet](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#create-dataflow) för att se till att datauppsättningen exporteras till molnlagringsmålet med API:t [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow). I det här steget kan du definiera exportschemat med hjälp av parametern `scheduleParams`.

#### Validera dataflöde

Om du vill [kontrollera slutförda körningar av dataflödet](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs) använder du [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns)-API:t och anger dataflödes-ID:t som frågeparameter. Detta dataflödes-ID är en identifierare som returneras när du ställer in dataflödet.

[Verifiera](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets#verify) en dataexport. När du exporterar datauppsättningar skapar Experience Platform en eller flera `.json`- eller `.parquet`-filer på den lagringsplats som är definierad i ditt mål. Förvänta dig att nya filer ska placeras på din lagringsplats enligt det exportschema som du ställer in. Experience Platform skapar en mappstruktur på den lagringsplats som du angav som en del av det valda målet, där de exporterade filerna placeras. En ny mapp skapas för varje exporttid enligt mönstret: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Standardfilnamnet genereras slumpmässigt och säkerställer att de exporterade filnamnen är unika.
