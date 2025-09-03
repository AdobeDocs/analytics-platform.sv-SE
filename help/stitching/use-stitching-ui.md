---
title: Använd stygn
description: Hur du använder stygn
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 4bca14492374939cd1ea6508c774720db61a6283
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Använd stygn

Du kan aktivera sammanfogning för en eller flera händelsedatamängder som du har konfigurerat som en del av anslutningen. Antalet händelsedatamängder som du kan aktivera för sammanfogning bestäms av det Customer Journey Analytics-paket som du har licensierat.

Du kan aktivera sammanfogning som en del av [datauppsättningsinställningarna](/help/connections/create-connection.md#dataset-settings) för en händelsedatauppsättning när du [skapar en anslutning](/help/connections/create-connection.md) eller när du [redigerar en anslutning](/help/connections/manage-connections.md#edit-a-connection).

Om du vill aktivera sammanfogning går du till händelsedatamängdsavsnittet i dialogrutan **[!UICONTROL Add datasets]** eller **[!UICONTROL Edit dataset]**:

![Alternativ för identitetssammanfogning när du aktiverar identitetssammanfogning](assets/identity-stitching-ui.png)

1. Välj **[!UICONTROL Enable identity stitching]**.

   Om du aktiverar sammanfogning för en befintlig händelsedatamängd visar dialogrutan **[!UICONTROL Change Person ID]** konsekvenserna av en ändring av person-ID på grund av användningen av sammanfogning. Välj **[!UICONTROL Continue]** om du vill fortsätta.

   Dialogrutan **[!UICONTROL Enable identity stitching]** sammanfattar konsekvenserna av att sy ihop identiteter. Välj **[!UICONTROL Continue]** om du vill fortsätta.

1. Välj ett beständigt ID i listrutan **[!UICONTROL Persistent ID]**.

   Om du väljer **[!UICONTROL Identity Map]** som beständigt ID måste du välja ett namnutrymme. Du har två alternativ:

   * Aktivera **[!UICONTROL Use primary identity namespace]** att använda det primära identitetsnamnområdet.
   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.

1. Välj ett person-ID i listrutan **[!UICONTROL Person ID]**.

   Om du väljer **[!UICONTROL Identity Map]** som person-ID måste du välja ett namnutrymme. Du har två alternativ:

   * Aktivera **[!UICONTROL Use primary identity namespace]** att använda det primära identitetsnamnområdet.
   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.

   Om du väljer **[!UICONTROL Identity Graph]** som person-ID måste du välja ett namnutrymme. Innan dess visas en **[!UICONTROL Change to identity graph]**-dialogruta för att kontrollera att du har slutfört konfigurationen av identitetsdiagrammet innan du använder identitetsdiagrammet för sammanfogning. Välj **[!UICONTROL Continue]** om du vill fortsätta.

   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.


1. Välj ett uppslagsfönster i listrutan **[!UICONTROL Lookback window]**. Alternativen är **[!UICONTROL 1 day]**, **[!UICONTROL 7 days]**, **[!UICONTROL 14 days]** eller **[!UICONTROL 30 days]**.
