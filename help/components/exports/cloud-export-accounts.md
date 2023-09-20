---
description: Konfigurera molnexportkontot där Customer Journey Analytics data kan skickas
keywords: Analysis Workspace
title: Konfigurera molnexportkonton
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 0%

---

# Konfigurera molnexportkonton

{{select-package}}

Innan du kan exportera Customer Journey Analytics-data till ett molnmål enligt beskrivningen i [Exportera data från Customer Journey Analytics till molnet](/help/analysis-workspace/export/export-cloud.md)måste du lägga till och konfigurera platsen dit du vill att data ska skickas.

Den här processen består av att lägga till och konfigurera kontot (t.ex. Amazon S3, Google Cloud Platform o.s.v.) enligt beskrivningen i den här artikeln, och sedan lägga till och konfigurera platsen inom det kontot (t.ex. en mapp inom kontot) enligt beskrivningen i [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).

Mer information om hur du hanterar befintliga konton, inklusive visning, redigering och borttagning av konton, finns i [Hantera platser och konton för molnexport](/help/components/exports/manage-export-locations.md).

Du måste konfigurera Customer Journey Analytics med den information som krävs för att komma åt ditt molndestinationskonto.

Så här konfigurerar du ett molnexportkonto:

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].
1. På [!UICONTROL Exports] väljer du [!UICONTROL **Platskonton**] -fliken.
1. Välj [!UICONTROL **Lägg till konto**].

   ![Lägg till konto](assets/account-add.png)

   Dialogrutan Lägg till konto visas.
1. Ange följande information: |Fält | Funktion | |—|—| | [!UICONTROL **Platskontonamn**] | Namnet på platskontot. Det här namnet visas när du skapar en plats | | [!UICONTROL **Beskrivning av platskonto**] | Ange en kort beskrivning av kontot så att det kan särskiljas från andra konton av samma kontotyp. | | [!UICONTROL **Kontotyp**] | Välj vilken typ av molnkonto du exporterar till. De tillgängliga kontotyperna är Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake och Adobe Experience Platform. |
1. I [!UICONTROL **Kontoegenskaper**] anger du information som är specifik för den kontotyp som du har valt.

   Utöka det avsnitt nedan som motsvarar [!UICONTROL **Kontotyp**] som du valde.

   +++Amazon S3 Roll ARN

   Ange följande information för att konfigurera ett Amazon S3 Role ARN-konto:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Roll-ARN**] | Du måste ange en roll-ARN (Amazon Resource Name) som Adobe kan använda för att få åtkomst till Amazon S3-kontot. För att göra detta skapar du en IAM-behörighetsprincip för källkontot, kopplar principen till en användare och skapar sedan en roll för målkontot. Mer information finns i [den här AWS-dokumentationen](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **Användar-ARN**] | Användar-ARN (Amazon Resource Name) tillhandahålls av Adobe. Du måste koppla den här användaren till den princip du skapade. |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Ange följande information för att konfigurera ett Google Cloud Platform-konto:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Projekt-ID**] | Ditt projekt-ID för Google Cloud som du kopierar från ditt Google Cloud-konto. Se [Google Cloud-dokumentation om hur du får ett projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
   | [!UICONTROL **kapitalbelopp**] | Huvudmannen tillhandahålls av Adobe. Klicka på [!UICONTROL **Kopiera**] -ikonen bredvid [!UICONTROL **kapitalbelopp**] om du vill kopiera innehållet i fältet måste du först ge säkerhetsobjektet behörighet att överföra filer till det här bucket i Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this --> |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Ange följande information för att konfigurera ett Azure SAS-konto:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI för nyckelvalv**] | <p>Sökvägen till SAS-token i Azure Key Vault.  Om du vill konfigurera Azure SAS måste du lagra en SAS-token som en hemlighet med Azure Key Vault. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>När nyckelvalvs-URI:n har skapats lägger du till en åtkomstprincip på nyckelvalvet för att ge behörighet till det Azure-program som du skapade. Mer information finns i [Microsoft Azure-dokumentation om hur du tilldelar en åtkomstprincip för nyckelvalv](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nyckelvalvets hemliga namn**] | Det hemliga namn du skapade när du lade till hemligheten i Azure Key Vault. I Microsoft Azure finns den här informationen i nyckelvalvet som du skapade på **Key Vault** inställningssidor. Mer information finns i [Microsoft Azure-dokumentation om hur du ställer in och hämtar en hemlighet från Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Hemlighet för platskonto**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Ange följande information för att konfigurera ett Azure RBAC-konto:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Program-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Klient-ID**] | Kopiera det här ID:t från det Azure-program som du skapade. I Microsoft Azure finns den här informationen på **Ökning** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Hemlighet för platskonto**] | Kopiera hemligheten från Azure-programmet som du skapade. I Microsoft Azure finns den här informationen på **Certifikat och hemligheter** -fliken i programmet. Mer information finns i [Microsoft Azure-dokumentation om hur du registrerar ett program med Microsoft identitetsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Ange följande information för att konfigurera ett Snowflake-konto:

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **Kontoidentifierare**] | Identifierar unikt ett Snowflake-konto inom er organisation, liksom i hela det globala nätverket av molnplattformar och molnregioner som stöds av Snowflake. <p>Mer information finns i [Sidan Kontoidentifierare i Snowflake-dokumentationen](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Användare**] | Anger inloggningsnamnet för användaren för anslutningen. Detta är en användare som kommer att användas särskilt för Adobe. Du kan skapa användaren i Snowflake efter att du har angett användarnamnet här. <p>Mer information finns i [Referenssida för JDBC-drivrutinens anslutningsparameter i Snowflake-dokumentationen](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Roll**] | Den standardroll för åtkomstkontroll som ska användas i den Snowflake-session som initieras av drivrutinen. Du bör skapa en roll som är specifik för Adobe som har läs- och skrivåtkomst.<p>Mer information finns i [Referenssida för JDBC-drivrutinens anslutningsparameter i Snowflake-dokumentationen](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Offentlig nyckel**] | Den offentliga nyckeln tillhandahålls av Adobe. Välj ikonen Kopiera bredvid ikonen [!UICONTROL **Offentlig nyckel**] om du vill kopiera innehållet i fältet och sedan använda den offentliga nyckeln i ditt Snowflake-konto. Mer information finns i [Key Pair Authentication &amp; Key Pair Rotation page in the Snowflake documentation](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

+++

   +++Adobe Experience Platform

   Alla Adobe Experience Platform-kunder kan exportera data till AEP Landing Zone.

   Ange följande information för att konfigurera ett Adobe Experience Platform-konto.

   | Fält |  -funktion |
   |---------|----------|
   | [!UICONTROL **IMS-organisations-ID**] | IMS-organisationsnumret tillhandahålls av Adobe. Klicka på ikonen Kopiera bredvid [!UICONTROL **IMS-organisations-ID**] om du vill kopiera innehållet i fältet och sedan använda ID:t i Adobe Experience Platform-kontot. |

+++

1. Välj [!UICONTROL **Spara**].

1. Fortsätt med [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md).

