---
title: Skapa ett schema för Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Skapa en datauppsättning som ska användas med Customer Journey Analytics

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

En datauppsättning är den konstruktion som lagrar och hanterar data som du samlar in i Adobe Experience Platform.

Så här skapar du en datauppsättning:

1. I Adobe Experience Platform väljer du **[!UICONTROL Datasets]** i [!UICONTROL DATA MANAGEMENT] till vänster.

1. Välj **[!UICONTROL Create dataset]**.

   ![Skapa datauppsättning](assets/create-dataset.png)

1. Välj **[!UICONTROL Create dataset from schema]**.

   ![Skapa datauppsättning från schema](assets/create-dataset-from-schema.png)

1. Markera schemat som du skapade tidigare och välj **[!UICONTROL Next]**.

1. Ge datauppsättningen ett namn och (valfritt) ge en beskrivning.

   ![Namndatauppsättning](assets/name-your-datatest.png)

1. Välj **[!UICONTROL Finish]**.

1. Välj växeln **[!UICONTROL Profile]**.

   Du uppmanas att aktivera datauppsättningen för profilen. När datauppsättningen är aktiverad berikas kundprofiler i realtid med inkapslade data.

   >[!IMPORTANT]
   >
   >    Du kan bara aktivera en datauppsättning för profilen när schemat, som datauppsättningen följer, också är aktiverat för profilen.

   ![Aktivera schema för profilen](assets/aepwebsdk-dataset-profile.png)

   Mer information om hur du visar, förhandsgranskar, skapar och tar bort en datauppsättning finns i [Användargränssnittshandbok för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html). Du kan även lära dig hur du aktiverar en datauppsättning för kundprofil i realtid.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).

