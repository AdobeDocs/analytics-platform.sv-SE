---
title: Kundhanterade nycklar
description: Lär dig hur du konfigurerar kundhanterade nycklar för Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: cdc8d889a05c55d2f4765d0837023d007a5a230d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Kundhanterade nycklar

Adobe Customer Journey Analytics ger kunder som har [Sköld för hälso- och sjukvård](https://www.adobe.com/trust/compliance/hipaa-ready.html) och skölden för sekretess och säkerhet möjlighet att använda kundhanterade nycklar (CMK) för Customer Journey Analytics-data. Observera att den här processen är skild från [Adobe Experience Platform CMK-inställningen](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). Kundhanterade nycklar är bara tillgängliga för organisationer som har köpt tilläggserbjudandet [Healthcare Shield eller Privacy &amp; Security Shield](https://experienceleague.adobe.com/sv/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield) .

## Konfigurera kundhanterade nycklar för Customer Journey Analytics på Azure

Följ de här stegen för att konfigurera CMK för Customer Journey Analytics som körs på Azure:

1. Se till att du är berättigad till Adobe Customer Journey Analytics CMK och att din organisation använder Adobe Experience Platform som körs på Azure. Kontakta Adobe Account Team för att kontrollera berättigandena.
1. Se till att du i Azure är administratör med en privilegierad roll som programadministratör, molnprogramadministratör eller global administratör. Mer information finns i [Inbyggda roller i Microsoft Entra](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference).
1. Skapa ett nytt Azure Key Vault som endast ska användas med Customer Journey Analytics. Mer information finns i [dokumentationen för Microsoft Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/).
1. Ge Adobe Azure App åtkomst till din nyckel i nyckelvalvet. Du kan göra det på något av följande sätt:
   * Bevilja behörigheter via godkännande via följande URL: [https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&client_id=251e3919-1940-4296-bb8b-6b9a5e8a4805&redirect_uri=https://experience.adobe.com&scope=user.read](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&client_id=251e3919-1940-4296-bb8b-6b9a5e8a4805&redirect_uri=https://experience.adobe.com&scope=user.read)

   * Följ instruktionerna i [Konfigurera kundhanterade nycklar för ett befintligt konto](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault). Adobe program-ID:

     **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Skapa en kundtjänstbiljett från Adobe som begär CMK-konfiguration. Inkludera Azure URI i din biljett. URI:n finns i fältet **Nyckelidentifierare** i din Azure-nyckel:

   ![Nyckelidentifierarfält som visar URI för https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. Adobe kundtjänst bekräftar att CMK-programmet har slutförts på dina Customer Journey Analytics-data.

Alla data som används av Platform krypteras under överföring och i vila för att skydda dina data, med eller utan kundhanterade nycklar. Mer information om Adobe Experience Platform-kryptering finns i [Datakryptering i Adobe Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/governance-privacy-security/encryption).

## Konfigurera kundhanterade nycklar för Customer Journey Analytics på Amazon Web Services

>[!AVAILABILITY]
>
>Detta avsnitt gäller implementeringar av Experience Platform som körs på Amazon Web Services (AWS). Experience Platform som körs på AWS är för närvarande tillgängligt för ett begränsat antal kunder. Mer information om den Experience Platform-infrastruktur som stöds finns i [Experience Platform översikt över flera moln](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/multi-cloud).

Om din organisation använder Adobe Experience Platform som körs på Amazon Web Services är CMK redan konfigurerat för dig. Ingen ytterligare konfiguration behövs.
