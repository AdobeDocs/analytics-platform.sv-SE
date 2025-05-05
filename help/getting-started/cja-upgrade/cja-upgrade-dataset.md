---
title: Skapa ett schema för Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Skapa en datauppsättning som ska användas med Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Skapa en datauppsättning i Adobe Experience Platform"
>abstract="En datauppsättning är en plats där insamlade data finns. Skapa den här platsen i Adobe Experience Platform.<br><br>Det tar bara några minuter att skapa en datauppsättning med ett schema i åtanke."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

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

   Mer information om hur du visar, förhandsgranskar, skapar och tar bort en datauppsättning finns i [Användargränssnittshandbok för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=sv-SE). Du kan även lära dig hur du aktiverar en datauppsättning för kundprofil i realtid.

{{upgrade-final-step}}
