---
title: Customer Journey Analytics Connections Overview
description: Läs mer om anslutningar i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---

# Anslutningar - översikt

Med anslutningar kan Customer Journey Analytics produktadministratörer definiera vilka [!DNL &#x200B; Experience Platform]-datakällor, till exempel händelser, sökning, profil och sammanfattningsdatauppsättningar, som är inkapslade. Anslutningar utgör grunden för Customer Journey Analytics och avgör tillgängligheten för data (fält) som du kan definiera i en [datavy](/help/data-views/data-views.md) som mått eller mätvärden.

>[!IMPORTANT]
>
>Du kan kombinera flera [!DNL Experience Platform]-datauppsättningar till en enda anslutning.


## Arbetsflöde för anslutningar

![Anslutningsarbetsflöde](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Ansluta till datakällor](https://experienceleague.adobe.com/sv/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

På en hög nivå ger anslutningsarbetsflödet dig möjlighet att:

| Gränssnitt | Beskrivning |
|:---:|---|
| ➊ | [Hantera dina anslutningar och den övergripande användningen](manage-connections.md) av Customer Journey Analytics från Anslutningshanteraren. |
| ➋ | [Granska informationen för en anslutning](manage-connections.md#connection-details), som datauppsättningsposter som har importerats, hoppats över eller tagits bort. |
| ➌ | [Skapa eller redigera konfigurationen för en anslutning](create-connection.md#create-or-edit-a-connection), till exempel ett rullande datafönster, den sandlåda som ska användas, vilka datauppsättningar som är en del av anslutningen, med mera. |
| ➍ | [Lägg till datauppsättningar i en anslutning](create-connection.md#add-datasets). Anslutningen bör ha minst en händelse- eller sammanfattningsdatauppsättning men kan innehålla en mängd olika datauppsättningar för händelse, profil, sökning och sammanfattning. |
| ➎ | [Konfigurera inställningarna](create-connection.md#dataset-settings) för datauppsättningar som du lägger till. Du kan bestämma hur olika datauppsättningar ska länkas baserat på en vanlig personbaserad eller [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} kontobaserad identifierare. |
| ➏ | [Redigera inställningarna för en befintlig datamängd](create-connection.md#edit-a-dataset). Du kan alltid gå tillbaka till datauppsättningsinställningarna i ett senare skede. |



## Åtkomstkontroll

Åtkomst till anslutningshantering bör begränsas till en kärnhanteringsgrupp. Anslutningskonfigurationer har avtalsmässiga konsekvenser för volymtilldelningar för data som hämtas till Customer Journey Analytics.

>[!MORELIKETHIS]
>
>[Åtkomstkontroll](/help/technotes/access-control.md).

