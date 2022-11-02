---
title: Kundhanterade nycklar
description: Lär dig hur du konfigurerar kundhanterade nycklar för CJA.
source-git-commit: 903c1423c91b220524174fa900a9ec13cd2051c6
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Kundhanterade nycklar

>[!NOTE]
>
>Den här funktionen kommer att vara tillgänglig i november 2022.

Customer Journey Analytics (CJA) har alternativ för [Hälsovårdssköld](https://www.adobe.com/trust/compliance/hipaa-ready.html) och kunder med skölden för skydd och säkerhet för att använda en Azure Customer Managed Key (CMK) som kan användas på dina CJA-data.  Observera att den här processen är skild från [Adobe Experience Platform CMK-inställningar](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>Kundhanterade nycklar är för närvarande bara tillgängliga för organisationer som har köpt [Vårdsköld eller sköld för skydd av privatlivet och säkerheten](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) tilläggserbjudande.

## Konfigurera CMK för CJA

Så här konfigurerar du CMK för CJA:

1. Se till att du har rätt till Adobe CJA CMK genom att kontrollera med ditt Adobe-kontoteam.
1. Se till att du i Azure är administratör med en privilegierad roll som programadministratör, molnprogramadministratör eller global administratör. [Läs mer om Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. Skapa ett nytt Azure Key Vault som endast ska användas med CJA. [Läs mer om Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Ge Adobe Azure App åtkomst till din nyckel i nyckelvalvet. Detta är Adobe program-ID: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Läs mer från Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Skapa en kundtjänstbiljett från Adobe som begär CMK-konfiguration. Inkludera Azure URI i din biljett. URI:n finns i **Nyckelidentifierare** fältet för din Azure-nyckel.

   ![](assets/key-identifier.png)

1. Adobe kundtjänst bekräftar att CMK-programmet har slutförts på dina CJA-data.

Alla data som används av Platform krypteras under överföring och i vila för att skydda data, med eller utan CMK. Information om Adobe Experience Platform-kryptering finns här: [läs mer](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=en).