---
title: Customer Journey Analytics Connections overview
description: Lär dig mer om anslutningar i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: dc3a109f162adfe48f621ba3ece95fedead3c6e1
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 1%

---

# Anslutningar - översikt

Tack vare anslutningar kan Customer Journey Analytics-produktadministratörer upprätta anslutningar med olika [!DNL Adobe Experience Platform] datakällor, till exempel händelsedata, uppslag och profildatamängder. Dessa anslutningar möjliggör integrering av data från en anslutning till en datavy som är en härledd datavy. Anslutningar är grunden för CJA och skapas från [!DNL Experience Platform] källdatamängder. Med åtkomst till anslutningar kan du även visa anslutningshanteraren, där du kan visa de underliggande datauppsättningarna som anslutningen består av samt göra viktiga redigerings- och konfigurationsval.

Vi rekommenderade att åtkomsten till anslutningshantering begränsas till en kärnhanteringsgrupp. Konfigurationer på anslutningsnivå har avtalsmässiga konsekvenser för volymtilldelningar för data som hämtas till Customer Journey Analytics.

Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Nödvändiga behörigheter

Om du vill skapa en anslutning till Customer Journey Analytics behöver du följande behörigheter i [Adobe Admin Console](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html):

Adobe Experience Platform:
* Datamodellering: Visa scheman, Hantera scheman
* Datahantering: Visa datauppsättningar, Hantera datauppsättningar
* Inmatning av data: Hantera källor
* Visa identitetsnamnutrymmen

Customer Journey Analytics
* Produktadministratörsåtkomst

>[!IMPORTANT]
>
>Du kan kombinera flera [!DNL Experience Platform] datauppsättningar till en enda anslutning.
