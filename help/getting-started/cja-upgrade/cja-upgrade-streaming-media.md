---
title: Ställ in Streaming Media Collection för Customer Journey Analytics
description: Lär dig hur du konfigurerar Streaming Media Collection för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 380ed5c9ee0c21ea9855a41728afec040637ce65
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Ställ in Streaming Media Collection för Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Konfigurera och implementera Media Edge"
>abstract="Om du tänker använda Streaming Media Collection med Customer Journey Analytics måste du göra vissa val under vissa steg i uppgraderingsprocessen. Du måste till exempel lägga till fältgruppen MediaAnalytics Interactions Details i ditt schema, aktivera Media Analytics i datastream med mera."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Precis som i Adobe Analytics kan Streaming Media Collection användas för att samla in strömmande mediedata för användning i Customer Journey Analytics. Om du använder Streaming Media Collection tillsammans med Adobe Analytics bör du inkludera det i uppgraderingsplanerna för Customer Journey Analytics.

När du går igenom stegen för att uppgradera från Adobe Analytics till Customer Journey Analytics gör du följande val för att ta hänsyn till Streaming Media Collection-data:

* Inkludera fältgruppen `MediaAnalytics Interaction Details` när du skapar schemat för Customer Journey Analytics.

  Mer information om hur du lägger till den här fältgruppen finns i [Konfigurera schemat i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) i guiden för direktuppspelning av mediasamling.

  Mer information om hur du skapar schemat finns i [Skapa ett anpassat schema som ska användas med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Aktivera Media Analytics när du konfigurerar dataströmmen för Customer Journey Analytics.

  Mer information om hur du aktiverar det här alternativet finns i [Konfigurera ett dataflöde i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) i guiden för direktuppspelning av mediasamling.

  Mer information om hur du skapar datastream finns i [Skapa ett datastream som ska användas med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

  >[!NOTE]
  >
  >Om Adobe Analytics-implementeringen redan använder Experience Platform Web SDK behöver du inte utföra det här steget.

* När du skapar en datavy för Customer Journey Analytics ska du ta med de schemafält som krävs för den direktuppspelade mediesamlingen.

  Se till att mappa dessa schemafält till rätt värden i XDM-objektet.

  Mer information om de obligatoriska fälten finns i [Skapa en datavy i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) i guiden för direktuppspelning av media.

  Mer information om hur du skapar datavyn finns i [Skapa en datavy i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
