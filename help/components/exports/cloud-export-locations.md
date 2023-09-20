---
description: Konfigurera den molnexportplats där Customer Journey Analytics data kan skickas
keywords: Analysis Workspace
title: Konfigurera platser för molnexport
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 1%

---

# Konfigurera platser för molnexport

{{select-package}}

Innan du kan exportera Customer Journey Analytics-data till ett molnmål enligt beskrivningen i [Exportera data från Customer Journey Analytics till molnet](/help/analysis-workspace/export/export-cloud.md)måste du lägga till och konfigurera platsen dit du vill att data ska skickas.

Den här processen består av att lägga till och konfigurera kontot (som Amazon S3, Google Cloud Platform o.s.v.) enligt beskrivningen i [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md)och sedan lägga till och konfigurera platsen inom det kontot (till exempel en mapp inom kontot) enligt beskrivningen i den här artikeln.

Mer information om hur du hanterar befintliga platser, inklusive visning, redigering och borttagning av platser, finns i [Hantera platser och konton för molnexport](/help/components/exports/manage-export-locations.md).

Så här konfigurerar du en plats för molnexport:

1. Du måste lägga till ett konto innan du kan lägga till en plats. Om du inte redan har det lägger du till ett konto enligt beskrivningen i [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md).
1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].
1. På [!UICONTROL Exports] väljer du [!UICONTROL **Platser**] -fliken.
1. Välj [!UICONTROL **Lägg till plats**].

   ![lägg till platsknapp](assets/location-add.png)

   Dialogrutan Plats visas.

1. Ange följande information: |Fält | Funktion | |—|—| | [!UICONTROL **Namn**] | Namnet på platsen.  | | [!UICONTROL **Beskrivning**] | Ange en kort beskrivning av kontot så att det kan särskiljas från andra konton av samma kontotyp. | | [!UICONTROL **Platskonto**] | Välj det platskonto som du skapade i [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md). |

1. I [!UICONTROL **Platsegenskaper**] anger du information som är specifik för kontotypen för ditt platskonto.

   För konfigurationsinstruktioner expanderar du det avsnitt nedan som motsvarar kontotypen som du valde i dialogrutan [!UICONTROL **Platskonton**] fält.

   +++Amazon S3 Roll ARN

   Ange följande information för att konfigurera en ARN-plats för en Amazon S3-roll:

   <!-- still need to update; can't create S3 role ARN account -->

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Den bucket på ditt Amazon S3-konto där du vill att Adobe Analytics-data ska skickas. Se till att användar-ARN som tillhandahålls av Adobe har åtkomst till att överföra filer till den här bucket. |
   | [!UICONTROL **Prefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Till exempel folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Ange följande information för att konfigurera en plats för Google Cloud-plattformen:

   <!-- still need to update; can't create GCP account -->

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Den bucket på ditt GCP-konto där du vill att Customer Journey Analytics data ska skickas. Se till att du har gett Adobe tillåtelse att överföra filer till denna bucket till säkerhetsobjektet. (Huvudkontot tillhandahålls när [konfigurera Google Cloud Platform-kontot](/help/components/exports/cloud-export-accounts.md).) Mer information om att bevilja behörigheter finns i [Lägga till ett huvudnamn i en princip på paketnivå](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) i Google Cloud-dokumentationen. |
   | [!UICONTROL **Prefix**] | Mappen inom hakparentesen där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Till exempel folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Ange följande information för att konfigurera en Azure SAS-plats:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Behållarnamn**] | Behållaren i det konto du angav där du vill att Customer Journey Analytics data ska skickas. |
   | [!UICONTROL **Prefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Ange följande information för att konfigurera en Azure RBAC-plats:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Behållare**] | Behållaren i det konto du angav där du vill att Adobe Analytics-data ska skickas. Se till att du ger behörighet att överföra filer till Azure-programmet som du skapade tidigare. |
   | [!UICONTROL **Prefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel, `folder_name/` |
   | [!UICONTROL **Konto**] | Azure-lagringskontot. |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Ange följande information för att konfigurera en Snowflake-plats:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **DB**] | Standarddatabasen som ska användas när den är ansluten, eller anger en tom sträng. Den angivna databasen ska vara en befintlig databas som den angivna standardrollen har behörighet för. <p>Mer information finns i [Referenssida för JDBC-drivrutinens anslutningsparameter i Snowflake-dokumentationen](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Schema**] | Standardschemat som ska användas för den angivna databasen när den har anslutits, eller anger en tom sträng. Det angivna schemat ska vara ett befintligt schema som den angivna standardrollen har privilegier för. <p>Mer information finns i [Referenssida för JDBC-drivrutinens anslutningsparameter i Snowflake-dokumentationen](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Scennamn**] | Namnet på den plats där datafiler lagras i Snowflake. <p>Mer information finns i [Välja en intern scen för sidan Lokala filer i Snowflake-dokumentationen](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Scenbana**] | Sökvägen till den plats där datafiler lagras i Snowflake. <p>Mer information finns i [Välja en intern scen för sidan Lokala filer i Snowflake-dokumentationen](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

+++

   +++Adobe Experience Platform

   Ange följande information för att konfigurera en Adobe Experience Platform-plats:

   <!-- still need to update; can't create AEP account -->

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **IMS-organisations-ID**] | IMS-organisationsnumret tillhandahålls av Adobe. Klicka på ikonen Kopiera bredvid [!UICONTROL **IMS-organisations-ID**] om du vill kopiera innehållet i fältet och sedan använda ID:t i Adobe Experience Platform-kontot. |
   | [!UICONTROL **Prefix**] | Mappen i behållaren där du vill placera data. Ange ett mappnamn och lägg sedan till ett omvänt snedstreck efter namnet för att skapa mappen. Exempel, `folder_name/` |

+++

1. Välj [!UICONTROL **Spara**].

1. Nu kan du exportera data från Analysis Workspace till det konto och den plats som du konfigurerade. Mer information om hur du exporterar data till molnet finns i [Exportera projektdata till molnet](/help/analysis-workspace/export/export-cloud.md).