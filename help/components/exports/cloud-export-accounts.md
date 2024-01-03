---
description: Konfigurera molnexportkontot där Customer Journey Analytics data kan skickas
keywords: Analysis Workspace
title: Konfigurera molnexportkonton
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
role: User, Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1719'
ht-degree: 0%

---

# Konfigurera molnexportkonton

Innan du kan exportera Customer Journey Analytics-rapporter till ett molnmål enligt beskrivningen i [Exportera Customer Journey Analytics-rapporter till molnet](/help/analysis-workspace/export/export-cloud.md)måste du lägga till och konfigurera målet dit du vill att data ska skickas.

Den här processen består av att lägga till och konfigurera kontot (t.ex. Amazon S3, Google Cloud Platform o.s.v.) enligt beskrivningen i den här artikeln, och sedan lägga till och konfigurera platsen inom det kontot (t.ex. en mapp inom kontot) enligt beskrivningen i [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).

Mer information om hur du hanterar befintliga konton, inklusive visning, redigering och borttagning av konton, finns i [Hantera platser och konton för molnexport](/help/components/exports/manage-export-locations.md).

## Börja skapa ett molnexportkonto

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].
1. På [!UICONTROL Exports] väljer du [!UICONTROL **Platskonton**] -fliken.
1. Välj [!UICONTROL **Lägg till konto**].

   ![Exporterar sidalternativ som visar Lägg till ett annat konto](assets/account-add.png)

   Dialogrutan Lägg till konto visas.

1. I [!UICONTROL **Platskontonamn**] anger du ett namn för platskontot. Det här namnet visas när du skapar en plats.

1. I [!UICONTROL **Beskrivning av platskonto**] ska du ange en kort beskrivning av kontot så att det kan särskiljas från andra konton av samma kontotyp.

1. I [!UICONTROL **Kontotyp**] väljer du vilken typ av molnkonto du exporterar till. De tillgängliga kontotyperna är Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake och AEP Data Landing Zone.

1. Fortsätt med det avsnitt nedan som motsvarar [!UICONTROL **Kontotyp**] du markerade.

   * [AEP Data Landing Zone](#aep-data-landing-zone)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### AEP Data Landing Zone

>[!IMPORTANT]
>
>När du exporterar rapporter från Customer Journey Analytics till Adobe Experience Platform Data Landing Zone ska du se till att du hämtar data inom 7 dagar och sedan ta bort dem från AEP Data Landing Zone. Efter 7 dagar tas data automatiskt bort från AEP Data Landing Zone.

1. [Börja skapa ett molnexportkonto](#begin-creating-a-cloud-export-account), enligt beskrivningen ovan.

1. Välj [!UICONTROL **Spara**].

   The [!UICONTROL **Exportera konto har skapats**] visas.

   ![Exportera kontodialogruta AEP Data Landing Zone](assets/export-account-aep.png)

1. Kopiera innehållet i [!UICONTROL **SAS-URI**] till Urklipp. Du använder den här SAS-URI:n för att komma åt data som exporteras från Analysis Workspace från AEP Data Landing Zone.

   Om det här fältet är tomt måste du ha behörighet att komma åt Adobe Experience Platform.

1. Konfigurera din Data Landing Zone-behållare i Adobe Experience Platform så att den använder den SAS URI som du kopierade.

   >[!NOTE]
   >
   >Eftersom AEP Data Landing Zone-kontot baseras på Azure är det enklaste sättet att komma åt rapporter som du exporterar till AEP Data Landing Zone genom att använda Azure Storage Explorer. I följande steg används den här metoden.

   1. Om du inte redan har det hämtar du [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Följ stegen i Adobe Experience Platform-dokumentationen [Anslut Data Landing Zone-behållaren till Azure Storage Explorer](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en#connect-your-data-landing-zone-container-to-azure-storage-explorer).

      Du kan hoppa över de uppgifter som beskrivs i avsnitten [Hämta autentiseringsuppgifterna för din Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en#retrieve-dlz-credentials) och [Uppdatera autentiseringsuppgifter för Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en#update-dlz-credentials), eftersom den URI som du kopierade innehåller dessa autentiseringsuppgifter.

   1. När du följer Adobe Experience Platform dokumentation kommer du till [!UICONTROL **SAS-URL för blobbbehållare**] klistra in den SAS-URI som du kopierade i steg 3.

      >[!NOTE]
      >
      >Du måste utföra den här åtgärden var 7:e dag eftersom SAS-URI:n går ut 7 dagar efter att den har skapats. Du kan skapa ett skript för att automatisera den här processen.


      ![Fönstret Anslutningsinformation med fältet SAS-URL](assets/blob-container-sas-uri.png)

   1. Välj [!UICONTROL **Nästa**] > [!UICONTROL **Anslut**].

1. I Customer Journey Analytics, på [!UICONTROL **Exportera konto har skapats**] dialogruta, välja [!UICONTROL **OK**].

   ![Exportera kontodialogruta AEP Data Landing Zone](assets/export-account-aep.png)

1. Fortsätt med [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. [Börja skapa ett molnexportkonto](#begin-creating-a-cloud-export-account), enligt beskrivningen ovan.

1. I [!UICONTROL **Kontoegenskaper**] i [!UICONTROL **Lägg till konto**] anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Roll-ARN**] | Du måste ange en roll-ARN (Amazon Resource Name) som Adobe kan använda för att få åtkomst till Amazon S3-kontot. För att göra detta skapar du en IAM-behörighetsprincip för källkontot, kopplar principen till en användare och skapar sedan en roll för målkontot. Mer information finns i [den här AWS-dokumentationen](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Spara**].

   The [!UICONTROL **Exportera konto har skapats**] visas.

   ![Dialogrutan Amazon S3 Roll ARN för exportkonto har skapats](assets/export-account-amazons3.png)

1. Kopiera innehållet i [!UICONTROL **Användar-ARN**] till Urklipp. Användar-ARN (Amazon Resource Name) tillhandahålls av Adobe. Du måste koppla den här användaren till den princip du skapade i Amazon S3 Role ARN.

1. Välj [!UICONTROL **OK**].

1. Fortsätt med [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. [Börja skapa ett molnexportkonto](#begin-creating-a-cloud-export-account), enligt beskrivningen ovan.

1. I [!UICONTROL **Kontoegenskaper**] i [!UICONTROL **Lägg till konto**] anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Projekt-ID**] | Ditt projekt-ID för Google Cloud som du kopierar från ditt Google Cloud-konto. Se [Google Cloud-dokumentation om hur du får ett projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Spara**].

   The [!UICONTROL **Exportera konto har skapats**] visas.

   ![Dialogrutan Exportera konto har skapats](assets/export-account-gcp.png)

1. Kopiera innehållet i [!UICONTROL **kapitalbelopp**] till Urklipp och kontrollera sedan att du ger huvudpersonen behörighet att överföra filer till den här bucket i Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this -->

1. Välj [!UICONTROL **OK**].

1. Fortsätt med [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. [Börja skapa ett molnexportkonto](#begin-creating-a-cloud-export-account), enligt beskrivningen ovan.

1. I [!UICONTROL **Kontoegenskaper**] i [!UICONTROL **Lägg till konto**] anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI för nyckelvalv**] | <p>Sökvägen till SAS URI i Azure Key Vault.  Om du vill konfigurera Azure SAS måste du lagra en SAS URI som en hemlighet med Azure Key Vault. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>När nyckelvalvs-URI:n har skapats lägger du till en åtkomstprincip på nyckelvalvet för att ge behörighet till det Azure-program som du skapade. Mer information finns i [Microsoft Azure-dokumentation om hur du tilldelar en åtkomstprincip för nyckelvalv](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nyckelvalvets hemliga namn**] | Det hemliga namn du skapade när du lade till hemligheten i Azure Key Vault. I Microsoft Azure finns den här informationen i nyckelvalvet som du skapade på **Key Vault** inställningssidor. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Hemlighet för platskonto**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Spara**].

   The [!UICONTROL **Exportera konto har skapats**] visas.

   ![Dialogrutan Exportera konto har skapats](assets/export-account-azure.png)

1. Om du inte redan gjort det kontrollerar du att du beviljar behörigheter till bucket i Azure SAS. <!-- add link to Google Cloud docs on how to do this -->

1. Välj [!UICONTROL **OK**].

1. Fortsätt med [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. [Börja skapa ett molnexportkonto](#begin-creating-a-cloud-export-account), enligt beskrivningen ovan.

1. I [!UICONTROL **Kontoegenskaper**] i [!UICONTROL **Lägg till konto**] anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Hemlighet för platskonto**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Spara**].

   The [!UICONTROL **Exportera konto har skapats**] visas.

   ![Dialogrutan Exportera konto har skapats](assets/export-account-azure.png)

1. Om du inte redan gjort det kontrollerar du att du har gett behörighet till bucket i Azure RBAC. <!-- add link to Google Cloud docs on how to do this -->

1. Välj [!UICONTROL **OK**].

1. Fortsätt med [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. [Börja skapa ett molnexportkonto](#begin-creating-a-cloud-export-account), enligt beskrivningen ovan.

1. I [!UICONTROL **Kontoegenskaper**] i [!UICONTROL **Lägg till konto**] anger du följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Kontoidentifierare**] | Identifierar unikt ett Snowflake-konto inom er organisation, liksom i hela det globala nätverket av molnplattformar och molnregioner som stöds av Snowflake. <p>Du måste hämta kontoidentifieraren från ditt Snowflake-konto och sedan klistra in informationen här.</p><p>Om du vill veta var du kan få den här informationen kan du läsa [Sidan Kontoidentifierare i Snowflake-dokumentationen](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Användare**] | Inloggningsnamnet för den användare som ska användas för anslutningen. Vi rekommenderar att du skapar en ny användare som ska användas specifikt för Adobe. Ange namnet här och skapa sedan en användare i Snowflake med samma namn. Du kan skapa en användare i Snowflake med `CREATE USER` -kommando.  <p>Mer information finns i [Kommandon för användare, roll och behörighet](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **Roll**] | Den roll som ska tilldelas användaren. Vi rekommenderar att du skapar en ny roll som ska användas särskilt för Adobe. Ange rollen här, skapa sedan en roll i Snowflake med samma namn och tilldela rollen till användaren. Du kan skapa en roll i Snowflake med `CREATE ROLE` -kommando. <p>Mer information finns i [Kommandon för användare, roll och behörighet](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Spara**].

   The [!UICONTROL **Exportera konto har skapats**] visas.

   ![Dialogrutan Exportera konto har skapats](assets/export-account-snowflake.png)

1. Kopiera innehållet i [!UICONTROL **Offentlig nyckel**] till Urklipp. Den offentliga nyckeln tillhandahålls av Adobe.

   Använd den offentliga nyckeln i Snowflake för att ansluta till ditt Snowflake-konto. Du måste associera användaren som du skapade med den här offentliga nyckeln.

   I Snowflake anger du till exempel följande kommando:

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   Mer information finns i [Key Pair Authentication &amp; Key Pair Rotation page in the Snowflake documentation](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. Välj [!UICONTROL **OK**].

1. Fortsätt med [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).
