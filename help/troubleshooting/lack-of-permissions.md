---
title: Brist på behörigheter
description: Lär dig hur du felsöker problem som beror på bristande behörighet
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Brist på behörigheter

Customer Journey Analytics fungerar inte korrekt när vissa Adobe Experience Platform-behörigheter saknas.

Efter att du skapat en [Anslutning](../connections/overview.md) och [Datavy](../data-views/data-views.md)kan följande felmeddelande visas i [Komponenter](/help/data-views/create-dataview.md#components) avsnitt:


>[!BEGINSHADEBOX]

*[!UICONTROL Something went wrong retrieving DULE policies. Please verify account permissions, policies, or labels. Message: Forbidden.]*

>[!ENDSHADEBOX]


1. Kontrollera att du har rätt åtkomstkontroll:

   * Du måste ha system- eller produktadministratörsbehörighet för en organisation som har en Experience Platform-produkt. Se [Översikt över åtkomstkontroll](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions) för mer information.

   * Du måste vara användare i produktprofilen AEP-Default-All-Users. Fråga administratören om du inte har behörighet att lägga till dig själv i den här profilen. Se [Åtkomststyrningshierarki och arbetsflöde](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow) för mer information.


1. Navigera till användargränssnittet för Adobe Experience Platform.

1. Välj **[!UICONTROL Permissions]** från den vänstra listen.

1. Välj **[!UICONTROL Roles]**.

1. Navigera till den relevanta rollen.

1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** för att redigera rollen.

1. Säkerställ **[!UICONTROL Manage Data Usage Policies]** och **[!UICONTROL View Data Usage Policies]** läggs till i **[!UICONTROL Data Governance]** behållare.

1. Välj **[!UICONTROL Save]** för att spara ändringarna.
