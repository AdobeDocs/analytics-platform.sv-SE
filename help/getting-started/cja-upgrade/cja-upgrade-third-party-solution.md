---
title: Uppgradera från en analyslösning från tredje part till Customer Journey Analytics
description: Lär dig hur du uppgraderar från en analyslösning från tredje part till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 87df2fb92f238ce051ac5f6cc90e218737279471
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 1%

---

# Uppgradera från en analyslösning från tredje part till Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="En analysprodukt från tredje part"
>abstract="En implementering som samlar in data för en analysprodukt från tredje part, som Google Analytics. Om du väljer det här alternativet inaktiveras flera alternativ i enkäten som inte gäller när du uppgraderar till Customer Journey Analytics från en analysprodukt från tredje part."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i [checklistan för uppgradering av Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Den rekommenderade processen att uppgradera från en analyslösning från tredje part till Customer Journey Analytics är en ny implementering av Experience Platform Web SDK, som är den bästa datainsamlingsmetoden för Customer Journey Analytics. I samverkan med Web SDK rekommenderar Adobe också att man hämtar in historiska data från tredjepartslösningen till Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Använd följande process när du går över till Customer Journey Analytics från en analyslösning från tredje part, som Google Analytics:

1. ...


Kontakta Adobe om du behöver mer specifik rådgivning, vägledning eller support.

| Befintlig analyslösning | Beskrivning | Tillgängliga uppgraderingssökvägar |
|---------|----------|----------|
| AppMeasurement | AppMeasurement för JavaScript har tidigare varit ett vanligt sätt att implementera Adobe Analytics.<p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med AppMeasurement för JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för kontinuerlig datainsamling; Analytics Source Connector för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrera Adobe Analytics till Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Adobe Analytics-tillägg (taggar) | <p>Taggar i Adobe Experience Platform är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Adobe erbjuder integreringar med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.</p><p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Analytics-tillägget](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för kontinuerlig datainsamling; Analytics Source Connector för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrera Adobe Analytics till Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK är Adobe nuvarande rekommenderade metod för implementering av Adobe Analytics. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. <p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för kontinuerlig datainsamling; Analytics Source Connector för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li></ul> |
| Experience Platform Web SDK-tillägg (taggar) | Experience Platform Web SDK är Adobe nuvarande rekommenderade metod för att implementera Adobe Analytics för webbdata. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. <p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för kontinuerlig datainsamling; Analytics Source Connector för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li></ul> |
| Mobilt SDK för Experience Platform | Experience Platform Mobile SDK är Adobe nuvarande rekommenderade metod för att implementera Adobe Analytics för mobildata. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats.<p>Adobe Experience Platform Mobile SDK hjälper er att driva Adobe Experience Cloud lösningar och tjänster i era mobilappar. </p><p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för kontinuerlig datainsamling; Analytics Source Connector för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li></ul> |
| API för insättning av data i bulk | BDIA (Bulk Data Insertion API) är en Adobe Analytics-funktion som gör att du kan överföra serveranropsdata i grupper av filer i stället för att använda klientbibliotek som AppMeasurement. </p><p>Mer information om den här implementeringstypen finns i [API för gruppdatainfogning](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för kontinuerlig datainsamling; Analytics Source Connector för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server API och Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
