---
title: Customer Journey Analytics Connections overview
description: Lär dig mer om anslutningar i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Anslutningar - översikt

Med anslutningar kan Customer Journey Analytics-produktadministratörer upprätta anslutningar med olika [!DNL Adobe Experience Platform]-datakällor, som till exempel händelseuppsättningar, uppslag och profildatamängder. Dessa anslutningar möjliggör integrering av data från en anslutning till en datavy som är en härledd datavy. Anslutningar är grunden för CJA och skapas från [!DNL Experience Platform] källdatauppsättningar. Med åtkomst till anslutningar kan du även visa anslutningshanteraren, där du kan visa de underliggande datauppsättningarna som anslutningen består av samt göra viktiga redigerings- och konfigurationsval.

Vi rekommenderade att åtkomsten till anslutningshantering begränsas till en kärnhanteringsgrupp. Konfigurationer på anslutningsnivå har avtalsmässiga konsekvenser för volymtilldelningar för data som hämtas till Customer Journey Analytics.

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

## Nödvändiga behörigheter

Om du vill skapa en anslutning till Customer Journey Analytics behöver du följande behörigheter. Mer information om behörigheter finns i dokumentationen för [Adobe Admin Console](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) och [Adobe Experience Platform Permissions](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

### Inom Adobe Admin Console:

* Customer Journey Analytics: Produktadministratör
* Adobe Experience Platform: Tillagd i produktprofilen med namnet *AEP-Default-All-Users*

### Inom Adobe Experience Platform behörigheter:

* Datamodellering: Visa scheman, Hantera scheman
* Datahantering: Visa datauppsättningar, Hantera datauppsättningar
* Inmatning av data: Hantera källor
* Identity Management: Visa identitetsnamnutrymmen
* Sandlådor: Sandlådor som används i relaterade Customer Journey Analytics-anslutningar

>[!IMPORTANT]
>
>Du kan kombinera flera [!DNL Experience Platform]-datauppsättningar till en enda anslutning.
