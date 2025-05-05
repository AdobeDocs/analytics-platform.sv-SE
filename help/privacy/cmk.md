---
title: Kundhanterade nycklar
description: Lär dig hur du ställer in kundhanterade nycklar för Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Kundhanterade nycklar

Adobe Customer Journey Analytics ger kunderna möjlighet att använda kundhanterade nycklar (CMK) för data från Customer Journey Analytics för [Vårdsköld](https://www.adobe.com/trust/compliance/hipaa-ready.html) och Privacy &amp; Security Shield. Observera att den här processen är skild från [Adobe Experience Platform CMK-inställningen](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). Kundhanterade nycklar är bara tillgängliga för organisationer som har köpt tilläggserbjudandet [Healthcare Shield eller Privacy &amp; Security Shield](https://experienceleague.adobe.com/sv/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield) .

## Ställ in kundhanterade nycklar för Customer Journey Analytics på Azure

Följ de här stegen för att konfigurera CMK för Customer Journey Analytics som körs på Azure:

1. Se till att du är berättigad till Adobe Customer Journey Analytics CMK och att din organisation använder Adobe Experience Platform som körs på Azure. Du kan kontrollera berättigandena genom att kontakta ditt kontoteam på Adobe.
1. Se till att du i Azure är administratör med en privilegierad roll som programadministratör, molnprogramadministratör eller global administratör. Mer information finns i [Inbyggda roller i Microsoft Entra](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference).
1. Skapa ett nytt Azure Key Vault som endast ska användas med Customer Journey Analytics. Mer information finns i [dokumentationen för Microsoft Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/).
1. Ge Adobe Azure App åtkomst till din nyckel i nyckelvalvet. Mer information finns i [Konfigurera kundhanterade nycklar för ett befintligt konto](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault). Program-ID för Adobe är:

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Skapa en kundtjänstbiljett från Adobe som begär CMK-konfiguration. Inkludera Azure URI i din biljett. URI:n finns i fältet **Nyckelidentifierare** i din Azure-nyckel:

   ![Nyckelidentifierarfält som visar URI för https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. Adobe kundtjänst bekräftar att CMK-programmet har slutförts på dina Customer Journey Analytics-data.

Alla data som används av Platform krypteras under överföring och i vila för att skydda dina data, med eller utan kundhanterade nycklar. Mer information om Adobe Experience Platform-kryptering finns i [Datakryptering i Adobe Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/governance-privacy-security/encryption).

## Ställ in kundhanterade nycklar för Customer Journey Analytics på Amazon Web Services

>[!AVAILABILITY]
>
>Detta avsnitt gäller för implementeringar av Experience Platform som körs på Amazon Web Services (AWS). Experience Platform som körs på AWS är för närvarande tillgängligt för ett begränsat antal kunder. Mer information om den Experience Platform-infrastruktur som stöds finns i [Översikt över flera moln i Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/multi-cloud).

Om din organisation använder Adobe Experience Platform som körs på Amazon Web Services är CMK redan konfigurerat för dig. Ingen ytterligare konfiguration behövs.
