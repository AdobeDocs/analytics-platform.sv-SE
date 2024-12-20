---
title: Skapa Analytics-källkopplingen och kartfälten
description: Lär dig hur du skapar Analytics-källkopplingen och kartfälten
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 45f2097d2f0657f623b825acb8d06ec6972f757f
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 0%

---

# Skapa Analytics-källkopplingen och kartfälten

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

## Förstå hur Analytics-källkopplingen kan överföra historiska data till Customer Journey Analytics

Du kan använda Analytics-källkopplingen för att hämta data från Adobe Analytics rapportsvit till Adobe Experience Platform. Dessa data kan sedan användas som historiska data i Customer Journey Analytics.

I den här processen förutsätts att du vill [skapa ett anpassat schema som ska användas med Customer Journey Analytics Web SDK-implementeringen](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), eftersom du vill ha ett anpassat schema som är anpassat efter behoven i din organisation och de specifika plattformsprogram som du använder.

Om du vill använda Analytics-källkopplingen för att hämta historiska data till Customer Journey Analytics måste du:

1. [Skapa ett anpassat schema för Analytics-källkopplingen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Om du inte redan har en Analytics-källanslutning skapar du Analytics-källkopplingen och mappar fält till ditt anpassade Web SDK-schema, enligt beskrivningen nedan.

   eller

   Om du redan har en Analytics-källkoppling mappar [fält från källkopplingen till ditt anpassade Web SDK-schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Skapa Analytics-källkopplingen och kartfälten

När du har skapat ett anpassat schema måste du skapa Adobe Analytics-källkopplingen för att kunna använda för historiska data. (Mer utförliga allmänna riktlinjer om hur du skapar en källanslutning finns i [Skapa en Adobe Analytics-källanslutning i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).)

Så här skapar du en Adobe Analytics-källanslutning som ska användas för historiska data:

1. Välj **[!UICONTROL Sources]** i avsnittet **[!UICONTROL Connections]** till vänster i plattformsgränssnittet.

1. Välj **[!UICONTROL Adobe applications]** i listan med [!UICONTROL CATEGORIES].

1. Välj **[!UICONTROL Add data]** i rutan Adobe Analytics.

   ![Fönstret Adobe Experience Platform med Källor markerat tillsammans med Adobe-program och Lägg till data markerat.](./assets/sources-overview.png)

1. Välj **[!UICONTROL Report suite]** och välj sedan den rapportserie som innehåller historiska data som du vill använda i Customer Journey Analytics i listan över rapportsviter.

   ![Adobe Experience Platform-fönstret med rapportsvitslistan](./assets/report-suites.png)

1. Välj **[!UICONTROL Next]** i skärmens övre högra hörn.

1. Välj **[!UICONTROL Custom schema]** och välj sedan det schema som du skapade i [Skapa ett anpassat schema som innehåller Adobe Analytics-fältgruppen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md). <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Mappa varje Adobe Analytics-dimension till en anpassad schemadimension.

   1. Välj fliken **[!UICONTROL Custom]** i avsnittet **[!UICONTROL Map standard fields]**.

   1. Välj **[!UICONTROL Add new mapping]**.

   ![mappa schemafält](assets/schema-mapping.png)

   1. I **[!UICONTROL Source field]** väljer du ett Adobe Analytics-fält i fältgruppen Adobe Analytics ExperienceEvent-mall. I **[!UICONTROL Target field]** markerar du sedan det anpassade fältet i XDM-schemat som du vill mappa det till.

      Alla Adobe Analytics-fält har inte ett motsvarande fält i XDM på grund av de inbyggda arkitekturskillnaderna mellan AppMeasurement och XDM.

   1. Upprepa den här processen för varje fält i fältgruppen Adobe Analytics ExperienceEvent-mall som du använder för att samla in data i Adobe Analytics.

1. Välj **[!UICONTROL Next]** i skärmens övre högra hörn.

1. Namnge dataflödet och (eventuellt) ge en beskrivning.

   ![Adobe Experience Platform-fönstret markerar dataflödesdetaljavsnittet](./assets/dataflow-detail.png)

1. Välj **[!UICONTROL Next]** i skärmens övre högra hörn.

1. Granska anslutningen och välj sedan **[!UICONTROL Finish]**.

   ![Adobe Experience Platform-fönstret markerar avsnitten Connect och Data för granskning](./assets/review.png)

   När anslutningen har skapats skapas dataflödet automatiskt för att fylla i en datauppsättning med Adobe Analytics-data från rapportsviten. Dataflödet importerar upp till 13 månaders historiska data för produktionssandlådor. Bakåtfyllnaden i icke-produktionssandlådor är begränsad till tre månader.

   Om du använder Analytics-källkopplingen för att hämta historiska data till Customer Journey Analytics Web SDK-implementeringen måste du lägga till den automatiskt skapade datauppsättningen i anslutningen som du skapade för Web SDK-implementeringen.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
