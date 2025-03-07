---
title: Skapa ett anpassat schema för Analytics-källkopplingen
description: Lär dig hur du skapar ett anpassat schema för Analytics-källkopplingen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: ac3ec479938acf509bbd26be282b75e75dd49c33
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---

# Skapa ett anpassat schema för Analytics-källkopplingen {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Skapa ett schema för Analytics-källkopplingen"
>abstract="Det här schemat är en kombination av fältgruppen Adobe Analytics ExperienceEvent med alla fältgrupper som utgör organisationens anpassade schema. Det gör att du kan mappa de fält som används av Analytics-källkopplingen till organisationens schema, och det används bara för historiska data.<br><br>Under tiden som det är tekniskt tekniskt nyttigt kan schemat skapas på några timmar, kanske snabbare om du vet exakt vilka fältgrupper som utgör organisationens anpassade schema."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="Skapa Analytics-källkopplingen för historiska data"
>abstract="Du kan använda Analytics-källkopplingen för att hämta data från Adobe Analytics rapportsvit till Adobe Experience Platform. Dessa data kan sedan användas som historiska data i Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Förstå hur Analytics-källkopplingen kan överföra historiska data till Customer Journey Analytics

Du kan använda Analytics-källkopplingen för att hämta data från Adobe Analytics rapportsvit till Adobe Experience Platform. Dessa data kan sedan användas som historiska data i Customer Journey Analytics.

I den här processen förutsätts att du vill [skapa ett anpassat schema som ska användas med Customer Journey Analytics Web SDK-implementeringen](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) eftersom du vill ha ett anpassat schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder.

Om du vill använda Analytics-källkopplingen för att hämta historiska data till Customer Journey Analytics måste du:

1. Skapa ett anpassat schema för Analytics-källkopplingen enligt beskrivningen nedan.

1. Om du inte redan har en Analytics-källkoppling [skapar du Analytics-källkopplingen och mappar fälten till det anpassade schemat](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   eller

   Om du redan har en Analytics-källkoppling mappar [fält från källkopplingen till ditt XDM-schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Skapa ett anpassat schema för Analytics-källkopplingen

Du bör redan ha [skapat ett nytt anpassat schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) för din Experience Platform Web SDK-implementering som ska användas med Customer Journey Analytics. Det här schemat ska innehålla alla fältgrupper för fält som du planerar att samla in data om.

Nu måste du använda samma fältgrupper från ditt Web SDK-schema och lägga till dem i ett nytt schema som du kan använda med Analytics-källkopplingen.

Det här schemat för Analytics-källkopplingen måste innehålla:

* Alla fältgrupper (inklusive eventuella egna fältgrupper som du har skapat) som ingår i ditt anpassade schema som du har skapat för din Web SDK-implementering. (Alla anpassade fält som inte är en del av en standardfältgrupp ska ha lagts till i ditt Web SDK-schema som en del av en anpassad fältgrupp.)

* Fältgruppen Adobe Analytics ExperienceEvent-mall

Så här skapar du det anpassade schema som ska användas med Analytics-källkopplingen:

1. Börja skapa ett nytt anpassat schema enligt beskrivningen i [Skapa ett anpassat schema som ska användas med Customer Journey Analytics Web SDK-implementeringen](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) i Adobe Experience Platform.

1. Lägg till alla fältgrupper (inklusive anpassade fältgrupper) som ingår i det schema som du skapade för Web SDK-implementeringen.

1. När du har lagt till de här fältgrupperna lägger du till fältgruppen Adobe Analytics ExperienceEvent:

   I avsnittet **[!UICONTROL Field groups]** väljer du **[!UICONTROL Add]** om du vill lägga till ytterligare en fältgrupp.

   ![Lägg till fältgrupp i schema](assets/schema-add-field-group.png)

1. Sök efter och markera fältgruppen **[!UICONTROL Adobe Analytics ExperienceEvent Template]**.

   ![Lägg till fältgruppen Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Välj **[!UICONTROL Add field groups]**.

1. Välj **[!UICONTROL Save]** om du vill spara ditt schema.

{{upgrade-final-step}}
