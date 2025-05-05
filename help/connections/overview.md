---
title: Customer Journey Analytics Connections overview
description: Läs mer om anslutningar i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 836c793ae74185728af03636b0ba3e838f46f05d
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# Anslutningar - översikt

Med anslutningar kan Customer Journey Analytics-produktadministratörer upprätta anslutningar med olika [!DNL &#x200B; Experience Platform]-datakällor, till exempel händelseuppsättningar, sökningar, profiler och sammanfattningsdatauppsättningar. De här anslutningarna gör det möjligt att integrera data från en anslutning till en variabel datavy. Anslutningar är grunden för Customer Journey Analytics och skapas från [!DNL Experience Platform] källdatauppsättningar.

>[!IMPORTANT]
>
>Du kan kombinera flera [!DNL Experience Platform]-datauppsättningar till en enda anslutning.


## Arbetsflöde för anslutningar

![Anslutningsarbetsflöde](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

På en hög nivå ger anslutningsarbetsflödet dig möjlighet att:

| Gränssnitt | Beskrivning |
|:---:|---|
| ➊ | [Hantera dina anslutningar och den övergripande användningen](manage-connections.md) av Customer Journey Analytics från Anslutningshanteraren. |
| ➋ | [Granska informationen för en anslutning](manage-connections.md#connection-details), som datauppsättningsposter som har importerats, hoppats över eller tagits bort. |
| ➌ | [Skapa eller redigera konfigurationen för en anslutning](create-connection.md#create-or-edit-a-connection), till exempel ett rullande datafönster, den sandlåda som ska användas, vilka datauppsättningar som är en del av anslutningen, med mera. |
| ○ | [Lägg till datauppsättningar i en anslutning](create-connection.md#add-datasets). Anslutningen bör ha minst en händelse- eller sammanfattningsdatauppsättning men kan innehålla en mängd olika datauppsättningar för händelse, profil, sökning och sammanfattning. |
| ○ | [Konfigurera inställningarna](create-connection.md#dataset-settings) för datauppsättningar som du lägger till. Du kan bestämma hur olika datauppsättningar ska länkas baserat på en vanlig personbaserad eller [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} kontobaserad identifierare. |
| ➏ | [Redigera inställningarna för en befintlig datamängd](create-connection.md#edit-a-dataset). Du kan alltid gå tillbaka till datauppsättningsinställningarna i ett senare skede. |



## Åtkomstkontroll

Åtkomst till anslutningshantering bör begränsas till en kärnhanteringsgrupp. Anslutningskonfigurationer har avtalsmässiga konsekvenser för volymtilldelningar för data som hämtas till Customer Journey Analytics.

>[!MORELIKETHIS]
>
>[Åtkomstkontroll](/help/technotes/access-control.md).

