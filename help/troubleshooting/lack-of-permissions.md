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

När du har skapat en [anslutning](../connections/overview.md) och [datavy](../data-views/data-views.md) kan du få följande felmeddelande i avsnittet [Komponenter](/help/data-views/create-dataview.md#components):


>[!BEGINSHADEBOX]

*[!UICONTROL Something went wrong retrieving DULE policies. Please verify account permissions, policies, or labels. Message: Forbidden.]*

>[!ENDSHADEBOX]


1. Kontrollera att du har rätt åtkomstkontroll:

   * Du måste ha system- eller produktadministratörsbehörighet för en organisation som har en Experience Platform-produkt. Mer information finns i [Översikt över åtkomstkontroll](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=sv-SE#platform-permissions).

   * Du måste vara användare i produktprofilen AEP-Default-All-Users. Fråga administratören om du inte har behörighet att lägga till dig själv i den här profilen. Mer information finns i [Åtkomstkontrollhierarki och arbetsflöde](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=sv-SE#access-control-hierarchy-and-workflow).


1. Navigera till användargränssnittet för Adobe Experience Platform.

1. Välj **[!UICONTROL Permissions]** i den vänstra listen.

1. Välj **[!UICONTROL Roles]**.

1. Navigera till den relevanta rollen.

1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** om du vill redigera rollen.

1. Kontrollera att **[!UICONTROL Manage Data Usage Policies]** och **[!UICONTROL View Data Usage Policies]** har lagts till i behållaren **[!UICONTROL Data Governance]**.

1. Välj **[!UICONTROL Save]** om du vill spara ändringarna.
