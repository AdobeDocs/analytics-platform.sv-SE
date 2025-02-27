---
title: Ställ in Streaming Media Collection för Customer Journey Analytics
description: Lär dig hur du konfigurerar Streaming Media Collection för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 68ce73ddf805ec377fdb2c539683507f191c9249
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Ställ in Streaming Media Collection för Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Konfigurera och implementera Media Edge"
>abstract="Du kan konfigurera Adobe Streaming Media Collection så att Experience Platform Edge används för att göra data tillgängliga i Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Hur du implementerar Streaming Media Collection i Customer Journey Analytics skiljer sig åt beroende på hur implementeringen av Streaming Media Collection i Adobe Analytics ser ut.

Direktuppspelning av Media Collection kan implementeras i Adobe Analytics på något av följande sätt:

* [Edge Network implementeringar för Streaming Media Collection](#edge-network-implementations)

+++ Visa infografik

  ![Direktuppspelande media i Edge-implementering](assets/streaming-media-edge.png)

+++

* [Implementeringar endast för Adobe Analytics för Streaming Media Collection](#adobe-analytics-only-implementations)

+++ Visa infografik

  ![Implementering med enbart analys](assets/analytics-implementation.png)

+++

Mer information om skillnaderna mellan de här implementeringsmetoderna finns i [Implementera den direktuppspelande mediesamlingen](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) i guiden för direktuppspelande mediesamling.

## Edge Network implementeringar för Streaming Media Collection

Om Streaming Media Collection [implementeras med Edge Network i din Adobe Analytics-implementering](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods) innebär det att några steg som krävs för att uppgradera Streaming Media Collection till Customer Journey Analytics redan har slutförts som en del av din Adobe Analytics-implementering. Följande steg är slutförda:

* [Konfigurera schemat i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Skapa en datauppsättning i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Konfigurera en datastam i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

Följande steg måste utföras som en del av uppgraderingen till Customer Journey Analytics:

>[!NOTE]
>
>När du är klar med uppgraderingen av Customer Journey Analytics ska du kontrollera att du använder schema, datauppsättning och datastream från implementeringen av Streaming Media Collection i Adobe Analytics.

* [Skapa en anslutning i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Skapa en datavy i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Implementeringar endast för Adobe Analytics för Streaming Media Collection

Om Streaming Media Collection [implementeras med en Adobe Analytics-implementering i din Adobe Analytics-miljö](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods) innebär det att Streaming Media-data ännu inte kommer till Edge Network.

När du skapar schemat, datauppsättningen, datastream, anslutningen och datavyn som en del av uppgraderingen från Adobe Analytics till Customer Journey Analytics gör du följande val för att ta hänsyn till Streaming Media Collection-data:

* Inkludera fältgruppen `MediaAnalytics Interaction Details` när du skapar schemat för Customer Journey Analytics.

  Mer information om hur du lägger till den här fältgruppen finns i [Konfigurera schemat i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) i guiden för direktuppspelning av mediasamling.

  Mer information om hur du skapar schemat finns i [Skapa ett anpassat schema som ska användas med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Aktivera Media Analytics när du konfigurerar dataströmmen för Customer Journey Analytics.

  Mer information om hur du aktiverar det här alternativet finns i [Konfigurera ett dataflöde i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) i guiden för direktuppspelning av mediasamling.

  Mer information om hur du skapar datastream finns i [Skapa ett datastream som ska användas med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* När du skapar en datavy för Customer Journey Analytics ska du ta med de schemafält som krävs för den direktuppspelade mediesamlingen.

  Se till att mappa dessa schemafält till rätt värden i XDM-objektet.

  Mer information om de obligatoriska fälten finns i [Skapa en datavy i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) i guiden för direktuppspelning av media.

  Mer information om hur du skapar datavyn finns i [Skapa en datavy i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).


