---
title: Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen
description: Lär dig hur du lägger till Analytics-källanslutningsdatauppsättningen i anslutningen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

## Förstå hur Analytics-källkopplingen kan överföra historiska data till Customer Journey Analytics

Du kan använda Analytics-källkopplingen för att hämta data från Adobe Analytics rapportsvit till Adobe Experience Platform. Dessa data kan sedan användas som historiska data i Customer Journey Analytics.

Den här processen förutsätter att du vill [skapa ett XDM-schema när du uppgraderar till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), eftersom du vill ha ett anpassat schema som passar behoven i din organisation och de plattformsspecifika program som du använder.

Om du vill använda Analytics-källkopplingen för att hämta historiska data till Customer Journey Analytics måste du:

1. [Skapa ett XDM-schema för Analytics-källkopplingen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. [Skapa Analytics-källkopplingen och kartfälten](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)

1. Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen, enligt beskrivningen nedan.

## Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen

När du [har skapat en Analytics-källkoppling för historiska data](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md) skapas en datauppsättning automatiskt för Analytics-data.

Du måste lägga till den här automatiskt skapade datauppsättningen i samma anslutning som du skapade för Web SDK-implementeringen. Om du gör det placeras Analytics-data i samma datavy i Customer Journey Analytics som dina Web SDK-data.

Så här lägger du till den automatiskt skapade datauppsättningen i samma anslutning som du skapade för Web SDK-implementeringen:

1. I Customer Journey Analytics väljer du fliken **[!UICONTROL Connections]**.

1. Välj anslutningen som du [skapade för din Web SDK-implementering](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Välj **[!UICONTROL Edit]**.

   ![Redigera anslutning](assets/connection-add-dataset.png)

1. Välj **[!UICONTROL Add datasets]** i det övre högra hörnet.

   ![Redigera anslutning](assets/connection-add-dateset2.png)

1. Bläddra till eller sök efter den datauppsättning som skapades automatiskt när du skapade Analytics-källkopplingen.

   Namnet på den här datauppsättningen är namnet på din rapportserie, följt av `midValues`. Till exempel: `My report suite midValues`

1. Markera kryssrutan bredvid datauppsättningsnamnet och välj sedan **[!UICONTROL Next]**.

   ![Redigera anslutning](assets/connection-add-dataset3.png)

1. Ange följande information:

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Endast tillgängligt för händelse- och profildatauppsättningar. Välj ett person-ID i listrutan med tillgängliga identiteter. Dessa identiteter definierades i datauppsättningsschemat i Experience Platform. Nedan finns information om hur du använder identitetskartan som ett person-ID.<p>Om det inte finns några person-ID:n att välja mellan, innebär det att ett eller flera person-ID:n inte har definierats i schemat. Mer information finns i [Definiera identitetsfält i användargränssnittet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity). <p>Värdet för det valda person-ID:t anses vara skiftlägeskänsligt. `abc123` och `ABC123` är till exempel två olika värden. |
   | **[!UICONTROL Timestamp]** | Endast för händelse- och sammanfattningsdatauppsättningar anges den här inställningen automatiskt till standardfältet för tidsstämpling från händelsebaserade scheman i Experience Platform. |
   | **[!UICONTROL Timezone]** | Endast tillgängligt för sammanfattningsdata. Välj lämplig tidszon för tidsseriens sammanfattningsdata. |
   | **[!UICONTROL Data source type]** | Välj en typ av datakälla. <br/>Typer av datakällor omfattar: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>Det här fältet används för att undersöka vilka typer av datakällor som används. |

   {style="table-layout:auto"}

1. Låt alternativet **[!UICONTROL Import all new data]** vara inaktiverat i avsnittet **[!UICONTROL Import new data]**.

   Eftersom du använder Analytics-källanslutningsdatauppsättningen för historiska data vill du inte ta över framtida data som samlas in i den här datauppsättningen.

1. Välj **[!UICONTROL Request backfill]** i avsnittet **[!UICONTROL Dataset backfill]**.

1. Definiera perioden som du vill att bakåtfyllnaden ska omfatta genom att ange start- och slutdatum eller genom att välja kalenderikonen ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).

   Källkopplingen för Analytics importerar 13 månaders data (oavsett storlek) för produktionssandlådor. Bakgrundsfyllningen i icke-produktionssandlådor är tre månader.

   >[!IMPORTANT]
   >
   >Var tydlig när du anger de datum du begär för bakåtfyllnad. Slutdatumet bör vara det datum då du först började samla in data med Web SDK-implementeringen.
   >
   >Du kan också välja ett datum kort efter det datum då du först började samla in data med Web SDK-implementeringen och sedan använda segment för att filtrera bort överlappande data.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Välj **[!UICONTROL Queue backfill]**.

1. Välj **[!UICONTROL Add datasets]** och välj sedan **[!UICONTROL Save]** för att spara anslutningen.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
