---
title: Kundhanterade nycklar
description: Lär dig hur du konfigurerar kundhanterade nycklar för CJA.
source-git-commit: 4894519f618b79a5ca29952df48291c44915adae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Kundhanterade nycklar

>[!NOTE]
>
>Den här funktionen kommer att vara tillgänglig i november 2022.

Customer Journey Analytics (CJA) ger möjlighet för kunder inom hälso- och sjukvårdsskölden och skölden för sekretess och säkerhet att använda en CMK-nyckel (Azure Customer Managed Key) som ska användas på dina CJA-data.  Observera att den här processen är skild från Adobe Experience Platform CMK-inställningar (länk som följer).

>[!NOTE]
>
>Kundhanterade nycklar är för närvarande bara tillgängliga för organisationer som har köpt [Vårdsköld eller sköld för skydd av privatlivet och säkerheten](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) tilläggserbjudande.

Så här konfigurerar du CMK för CJA:

1. Kontrollera att du har rätt till CMK genom att kontakta ditt Adobe-kontoteam.
1. Skapa ett nytt Azure Key Vault som endast ska användas med CJA.
1. Koppla ditt Azure-nyckelvärde till Azure CJA CMK-appen (länk som ska följas).
1. Skapa en kundtjänstbiljett från Adobe som begär CMK-konfiguration. Inkludera Azure URI i din biljett.
1. Adobe kundtjänst bekräftar att CMK-programmet har slutförts på dina CJA-data.
