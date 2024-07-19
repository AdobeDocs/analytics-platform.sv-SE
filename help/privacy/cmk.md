---
title: Kundhanterade nycklar
description: Lär dig hur du konfigurerar kundhanterade nycklar för Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# Kundhanterade nycklar

Adobe Customer Journey Analytics ger kunder som har [skölden för hälso- och sjukvård](https://www.adobe.com/trust/compliance/hipaa-ready.html) och skölden för sekretess och säkerhet möjlighet att använda en CMK-nyckel (Azure Customer Managed Key) som kan användas på dina Customer Journey Analytics-data.  Observera att den här processen är skild från [Adobe Experience Platform CMK-inställningen](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>Kundhanterade nycklar är för närvarande bara tillgängliga för organisationer som har köpt tilläggserbjudandet [Healthcare Shield eller Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html).

## Konfigurera CMK för Customer Journey Analytics

Så här konfigurerar du CMK för Customer Journey Analytics:

1. Se till att du har rätt till Adobe Customer Journey Analytics CMK genom att höra med ditt kontoteam på Adobe.
1. Se till att du i Azure är administratör med en privilegierad roll som programadministratör, molnprogramadministratör eller global administratör. [Läs mer från Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. Skapa ett nytt Azure Key Vault som endast ska användas med Customer Journey Analytics. [Läs mer från Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Ge Adobe Azure App åtkomst till din nyckel i nyckelvalvet. Detta är Adobe program-ID: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Läs mer från Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Skapa en kundtjänstbiljett från Adobe som begär CMK-konfiguration. Inkludera Azure URI i din biljett. URI:n finns i fältet **Nyckelidentifierare** i Azure-nyckeln.

   ![Nyckelidentifierarfält som visar URI för https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. Adobe kundtjänst bekräftar att CMK-programmet har slutförts på dina Customer Journey Analytics-data.

Alla data som används av Platform krypteras under överföring och i vila för att skydda data, med eller utan CMK. Mer information om Adobe Experience Platform-kryptering finns i [läs mer](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html).
