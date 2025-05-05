---
title: Förstå implementeringen av Adobe Analytics och hur den påverkar din uppgradering till Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 1%

---

# Förstå implementeringen av Adobe Analytics och hur den påverkar din uppgradering till Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (manuell JS-fil)"
>abstract="En JavaScript-implementering som läser in AppMeasurement.js på en sida och skickar data till Adobe med objektet s (till exempel s.eVar1)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics-tillägg (taggar)"
>abstract="En taggimplementering som läser in Adobe Experience Platform Data Collection (tidigare Launch). Taggen har tillägget Adobe Analytics installerat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK (alloy.js)"
>abstract="En JavaScript-implementering som läser in Web SDK-biblioteket (alloy.js) på en sida och skickar data till Adobe med en JSON-nyttolast."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Web SDK-tillägg (taggar)"
>abstract="En taggimplementering som läser in Adobe Experience Platform Data Collection (tidigare Launch). Taggen har Web SDK-tillägget installerat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="API för datainfogning"
>abstract="En implementering som använder API:t för infogning av data eller API:t för massdatainfogning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="En implementering som använder Adobe Experience Platform Mobile SDK."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-third-party"
>title="AppMeasurement med ett tagghanteringsverktyg från tredje part"
>abstract="En implementering som använder ett tagghanteringsverktyg från tredje part."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Okänd implementering"
>abstract="Om du inte är den person som hanterar implementeringen kan du tillfälligt välja det här alternativet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="Bestäm din befintliga implementeringstyp"
>abstract="Arbeta internt i organisationen för att avgöra vilken typ av implementering du använder för att skicka data till Adobe Analytics. När du uppgraderar till Customer Journey Analytics kan du samarbeta med den person eller det team som känner till informationen.<br><br>När du har fastställt vilken typ av implementering din organisation använder ändrar du svaret i Customer Journey Analytics Upgrade Guide."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Det finns olika sätt att implementera Adobe Analytics. När du uppgraderar till Customer Journey Analytics är inte alla uppgraderingsalternativ tillgängliga för alla Adobe Analytics-implementeringar. Den rekommenderade uppgraderingssökvägen är dock tillgänglig oavsett hur Adobe Analytics implementeras i din organisation.

Använd informationen nedan för att lära dig mer om hur Adobe Analytics implementeras och vilka uppgraderingsalternativ som finns tillgängliga för din organisation.

Kontakta Adobe om du behöver mer specifik rådgivning, vägledning eller support.

| Befintlig Adobe Analytics-implementering | Beskrivning | Tillgängliga uppgraderingssökvägar |
|---------|----------|----------|
| AppMeasurement | AppMeasurement för JavaScript har tidigare varit ett vanligt sätt att implementera Adobe Analytics.<p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med AppMeasurement för JavaScript](https://experienceleague.adobe.com/sv/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för pågående datainsamling; Analytics-källkopplingen för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrera Adobe Analytics till Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analysens källkoppling](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Adobe Analytics-tillägg (taggar) | <p>Taggar i Adobe Experience Platform är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Adobe erbjuder integreringar med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.</p><p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Analytics-tillägget](https://experienceleague.adobe.com/sv/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för pågående datainsamling; Analytics-källkopplingen för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrera Adobe Analytics till Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analysens källkoppling](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK är Adobe nuvarande rekommenderade metod för implementering av Adobe Analytics. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. <p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/sv/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för pågående datainsamling; Analytics-källkopplingen för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Web SDK-tillägg (taggar) | Experience Platform Web SDK är Adobe nuvarande rekommenderade metod för att implementera Adobe Analytics för webbdata. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. <p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/sv/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för pågående datainsamling; Analytics-källkopplingen för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Mobilt SDK för Experience Platform | Experience Platform Mobile SDK är Adobe nuvarande rekommenderade metod för att implementera Adobe Analytics för mobildata. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats.<p>Adobe Experience Platform Mobile SDK hjälper er att driva Adobe Experience Cloud lösningar och tjänster i era mobilappar. </p><p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/sv/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för pågående datainsamling; Analytics-källkopplingen för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| API för insättning av data i bulk | BDIA (Bulk Data Insertion API) är en Adobe Analytics-funktion som gör att du kan överföra serveranropsdata i grupper av filer i stället för att använda klientbibliotek som AppMeasurement. </p><p>Mer information om den här implementeringstypen finns i [API för gruppdatainfogning](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Rekommenderas) Ny implementering av Experience Platform Web SDK för pågående datainsamling; Analytics-källkopplingen för historiska data ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Ny implementering av Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server API och Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


