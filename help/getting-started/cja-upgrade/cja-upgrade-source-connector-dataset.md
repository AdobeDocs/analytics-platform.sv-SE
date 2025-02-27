---
title: Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen
description: Lär dig hur du lägger till Analytics-källanslutningsdatauppsättningen i anslutningen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---

# Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen"
>abstract="Nu när historiska data från Analytics-rapportsviten finns i Adobe Experience Platform lägger du till den datauppsättningen i din befintliga anslutning som du skapade när du konfigurerade Customer Journey Analytics första gången. När det här steget är klart finns historiska data i Customer Journey Analytics tillgängliga.<br><br>Det är enkelt att lägga till en datauppsättning i en anslutning i Customer Journey Analytics, vilket tar bara några minuter."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Förstå hur Analytics-källkopplingen kan överföra historiska data till Customer Journey Analytics

Du kan använda Analytics-källkopplingen för att hämta data från Adobe Analytics rapportsvit till Adobe Experience Platform. Dessa data kan sedan användas som historiska data i Customer Journey Analytics.

Den här processen förutsätter att du vill [skapa ett XDM-schema när du uppgraderar till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), eftersom du vill ha ett anpassat schema som passar organisationens behov och de plattformsspecifika program som du använder.

Om du vill använda Analytics-källkopplingen för att hämta historiska data till Customer Journey Analytics måste du:

1. [Skapa ett XDM-schema för Analytics-källkopplingen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Om du inte redan har en Analytics-källkoppling [skapar du Analytics-källkopplingen och mappar fält till XDM-schemat](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   eller

   Om du redan har en Analytics-källkoppling mappar [fält från källkopplingen till ditt XDM-schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen, enligt beskrivningen nedan.

## Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen

När du [har skapat en Analytics-källkoppling för historiska data](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md) skapas en datauppsättning automatiskt för Analytics-data.

Du måste lägga till den här automatiskt skapade datauppsättningen i samma anslutning som du skapade för din Web SDK-implementering. När du gör det placeras Analytics-data i samma datavy i Customer Journey Analytics som era Web SDK-data.

Så här lägger du till den automatiskt skapade datauppsättningen i samma anslutning som du skapade för din Web SDK-implementering:

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

1. Ange den period som du vill att återfyllnaden av anslutningen ska omfatta i Customer Journey Analytics genom att ange start- och slutdatum eller genom att välja kalenderikonen ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).

   Var tydlig när du anger de datum du begär för bakåtfyllnad. Beroende på flera faktorer kan du göra något av följande:

   * Välj ett slutdatum som är samma datum som när du började samla in data med Web SDK-implementeringen.

   * Välj ett slutdatum som ligger kort efter det datum då du började samla in data med Web SDK-implementeringen och använd sedan datavysegment för att filtrera bort överlappande data.

   * Välj ett slutdatum som ger en större överlappning av data och använd sedan datavysegment för att filtrera bort överlappande data.

     **Obs!** Det här alternativet skulle leda till ökade kostnader eftersom det skulle finnas fler rader i anslutningen.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Välj **[!UICONTROL Queue backfill]**.

1. Välj **[!UICONTROL Add datasets]** och välj sedan **[!UICONTROL Save]** för att spara anslutningen.

1. (Villkorligt) Om du använder uppslagsdatauppsättningar måste du skapa uppslagsdatauppsättningen och lägga till den i anslutningen. Mer information finns i [Skapa uppslagsdatauppsättningar för att klassificera data i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

   Detta krävs bara om du inte redan gjorde det när du konfigurerade din Web SDK-implementering.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
