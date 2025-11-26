---
title: Konfigurera systemspecifika lösningar för datalager
description: Lär dig hur du konfigurerar systemspecifika lösningar för datalager för Experience Platform Data Mirror för Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
source-git-commit: c9d7a4596a842ab7d949364e3469747d20ca15b4
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Konfigurera systemspecifika lösningar för datalager

{{release-limited-testing}}

För att stödja Experience Platform Data Mirror för Customer Journey Analytics måste de data som du vill använda från de tre datalagerbaserade lösningarna som stöds ([[!DNL Azure Databricks]](#azure-databricks), [[!DNL Google BigQuery]](#google-bigquery), [[!DNL Snowflake]](#snowflake)) aktiveras för registrering av ändringsdata.


## [!DNL Azure Databricks]

Aktivera **Ändra datafeed** i dina [!DNL Azure Databricks]-tabeller för att använda registrering av ändringsdata i din källanslutning.

Använd följande kommandon om du vill aktivera dataöverföring i tabeller:

**Ny tabell**

Om du vill använda datautmatning för ändring av en ny tabell måste du ange tabellegenskapen `delta.enableChangeDataFeed` till `TRUE` i kommandot `CREATE TABLE`.

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Befintlig tabell**

Om du vill använda datautmatning för ändring av en befintlig tabell måste du ange tabellegenskapen `delta.enableChangeDataFeed` till `TRUE` i kommandot `ALTER TABLE`.

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Alla nya tabeller**

Om du vill använda datafeed för ändring i alla nya tabeller måste du ange standardegenskaperna till `TRUE`.

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

Mer information finns i [[!DNL Azure Databricks] handboken om hur du aktiverar feed för ändringsdata](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed).

Läs följande dokumentation om hur du aktiverar registrering av ändringsdata för din [!DNL Azure Databricks]-källanslutning:

* [Skapa en [!DNL Azure Databricks] basanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/api-tutorials/create/databases/databricks).
* [Skapa en källanslutning för en databas](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Google BigQuery]

Om du vill använda registrering av ändringsdata i [!DNL Google BigQuery]-källanslutningen navigerar du till [!DNL Google BigQuery]-sidan i [!DNL Google Cloud]-konsolen och anger `enable_change_history` som `TRUE`. Den här egenskapen aktiverar ändringshistorik för datatabellen.

Mer information finns i handboken om [språksatser för datadefinitioner i  [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list).

Läs följande dokumentation om hur du aktiverar registrering av ändringsdata för din [!DNL Google BigQuery]-källanslutning:

* [Skapa en [!DNL Google BigQuery] basanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [Skapa en källanslutning för en databas](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

Aktivera **ändringsspårning** i [!DNL Snowflake]-tabellerna om du vill använda ändringsdatainhämtning i källanslutningarna.

Aktivera ändringsspårning i [!DNL Snowflake] genom att använda `ALTER TABLE` och ange `CHANGE_TRACKING` som `TRUE`.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

Mer information finns i [[!DNL Snowflake] handboken om hur du använder ändringssatsen](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes).

Läs följande dokumentation om hur du aktiverar registrering av ändringsdata för din [!DNL Snowflake]-källanslutning:

* [Skapa en [!DNL Snowflake] basanslutning](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [Skapa en källanslutning för en databas](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>[Data Mirror snabbstartsguide: Spegla och använda relationsdata](relational.md)
>
