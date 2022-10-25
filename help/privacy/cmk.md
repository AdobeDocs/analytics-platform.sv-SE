---
title: Kundhanterade nycklar
description: Lär dig hur du konfigurerar kundhanterade nycklar för CJA.
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '0'
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

Så här konfigurerar du CMK för CJA:

1. Kontrollera att du har rätt till CMK genom att kontakta ditt Adobe-kontoteam.
1. Skapa ett nytt Azure Key Vault som endast ska användas med CJA.
1. Koppla ditt Azure-nyckelvärde till Azure CJA CMK-appen (länk som ska följas).
1. Skapa en kundtjänstbiljett från Adobe som begär CMK-konfiguration. Inkludera Azure URI i din biljett.
1. Adobe kundtjänst bekräftar att CMK-programmet har slutförts på dina CJA-data.
