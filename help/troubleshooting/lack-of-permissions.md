---
title: Brist på behörigheter
description: Lär dig hur du felsöker problem som beror på bristande behörighet
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 1905e37b76843a7622af4e874a2d74aceff55384
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# Brist på behörigheter

Customer Journey Analytics fungerar inte korrekt när vissa Adobe Experience Platform-behörigheter saknas.

Efter att du skapat en [Anslutning](../connections/overview.md) och [Datavy](../data-views/data-views.md)kan följande felmeddelande visas i [Komponenter](/help/data-views/create-dataview.md#components) avsnitt:


>[!BEGINSHADEBOX]

*[!UICONTROL Something went wrong and we couldn't load schema fields. Please try again.]*

>[!ENDSHADEBOX]


För att åtgärda det här felet måste du ha system- eller produktadministratörsbehörighet för en organisation som har en Experience Platform-produkt. Se [Översikt över åtkomstkontroll](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) för mer information.

1. Navigera till användargränssnittet för Adobe Experience Platform.

1. Välj **[!UICONTROL Permissions]** från den vänstra listen.

1. Välj **[!UICONTROL Roles]**.

1. Navigera till den relevanta rollen.

1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** för att redigera rollen.

1. Säkerställ **[!UICONTROL Manage Data Usage Policies]** och **[!UICONTROL View Data Usage Policies]** läggs till i **[!UICONTROL Data Governance]** behållare.

1. Välj **[!UICONTROL Save]** för att spara ändringarna.


