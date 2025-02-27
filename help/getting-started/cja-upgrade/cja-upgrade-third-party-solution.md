---
title: Uppgradera från en analyslösning från tredje part till Customer Journey Analytics
description: Lär dig hur du uppgraderar från en analyslösning från tredje part till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---

# Uppgradera från en analyslösning från tredje part till Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="En produkt som inte är från Adobe Analytics"
>abstract="En implementering som samlar in data för en annan produkt än Adobe Analytics, till exempel Google Analytics. Om du väljer det här alternativet inaktiveras flera alternativ i enkäten som inte gäller när du uppgraderar till Customer Journey Analytics från en produkt som inte är från Adobe Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Den rekommenderade processen att uppgradera från en annan analyslösning än Adobe Analytics till Customer Journey Analytics är en ny implementering av Experience Platform Web SDK, vilket är den bästa datainsamlingsmetoden för Customer Journey Analytics. I samverkan med Web SDK rekommenderar Adobe också att man hämtar in historiska data från tredjepartslösningen till Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Använd följande process när du går över till Customer Journey Analytics från en analyslösning från tredje part, som Google Analytics:

1. Följ de [detaljerade rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   De här stegen är avsedda för organisationer som uppgraderar från Adobe Analytics. När du följer dessa steg ska du vara medveten om följande:

   * Du måste skapa en datastream.

   * Du kan inte migrera projekt och komponenter från en lösning som inte är från Adobe Analytics.

   * Beroende på din analyslösning kan det finnas en källanslutning för inhämtning av historiska data. Mer information finns i [Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics) i [Source Connectors overview](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) i Experience Platform-dokumentationen.


Kontakta Adobe om du behöver mer specifik rådgivning, vägledning eller support.

