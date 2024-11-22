---
title: Skapa ett XDM-schema för Analytics-källkopplingen
description: Lär dig hur du skapar ett XDM-schema för Analytics-källkopplingen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Skapa ett XDM-schema för Analytics-källkopplingen

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

## Förstå hur Analytics-källkopplingen kan överföra historiska data till Customer Journey Analytics

Du kan använda Analytics-källkopplingen för att hämta data från Adobe Analytics rapportsvit till Adobe Experience Platform. Dessa data kan sedan användas som historiska data i Customer Journey Analytics.

Den här processen förutsätter att du vill [skapa ett XDM-schema när du uppgraderar till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), eftersom du vill ha ett anpassat schema som passar behoven i din organisation och de plattformsspecifika program som du använder.

Om du vill använda Analytics-källkopplingen för att hämta historiska data till Customer Journey Analytics måste du:

1. Skapa ett XDM-schema för Analytics-källkopplingen enligt beskrivningen nedan.

1. Om du inte redan har en Analytics-källkoppling [skapar du Analytics-källkopplingen och mappar fält till XDM-schemat](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   eller

   Om du redan har en Analytics-källkoppling mappar [fält från källkopplingen till ditt XDM-schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Skapa ett XDM-schema för Analytics-källkopplingen

Du bör redan ha [skapat ett nytt XDM-schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) för Experience Platform Web SDK-implementeringen som ska användas med Customer Journey Analytics. Det här schemat ska innehålla alla fältgrupper för fält som du planerar att samla in data om.

Nu måste du använda samma fältgrupper från ditt Web SDK-schema och lägga till dem i ett nytt schema som du kan använda med Analytics-källkopplingen.

Det här schemat för Analytics-källkopplingen måste innehålla:

* Alla fältgrupper (inklusive eventuella egna fältgrupper som du har skapat) som ingår i ditt anpassade schema som du har skapat för Web SDK-implementeringen. (Alla anpassade fält som inte är en del av en standardfältgrupp bör ha lagts till i ditt Web SDK-schema som en del av en anpassad fältgrupp.)

* Fältgruppen Adobe Analytics ExperienceEvent-mall

Så här skapar du XDM-schemat som ska användas med Analytics-källkopplingen:

1. I Adobe Experience Platform börjar du skapa ett nytt XDM-schema enligt beskrivningen i [Skapa ett XDM-schema som ska användas med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Lägg till alla fältgrupper (inklusive anpassade fältgrupper) som ingår i det schema som du skapade för Web SDK-implementeringen.

1. När du har lagt till de här fältgrupperna lägger du till fältgruppen Adobe Analytics ExperienceEvent:

   I avsnittet **[!UICONTROL Field groups]** väljer du **[!UICONTROL Add]** om du vill lägga till ytterligare en fältgrupp.

   ![Lägg till fältgrupp i schema](assets/schema-add-field-group.png)

1. Sök efter och markera fältgruppen **[!UICONTROL Adobe Analytics ExperienceEvent Template]**.

   ![Lägg till fältgruppen Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Välj **[!UICONTROL Add field groups]**.

1. Välj **[!UICONTROL Save]** om du vill spara ditt schema.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
