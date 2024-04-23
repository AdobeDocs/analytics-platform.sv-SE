---
title: Skicka data till Adobe Experience Platform vid migrering till Customer Journey Analytics
description: Skicka data till Adobe Experience Platform vid migrering till Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 0%

---

# Steg 3: Skicka data till Adobe Experience Platform när du migrerar till Customer Journey Analytics

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större migreringsprocessen. Kontrollera att alla tidigare migreringssteg är slutförda.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 3, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsmetod](/help/getting-started/cja-migration/cja-migration-method.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| <span class="preview">**Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken migreringsmetod du väljer i steg 1.</span> |
| **Steg 4: [Mappa data till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta flyttningsmetoder kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p> |
| **Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics. |
| **Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)** | Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics. |
| **Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics. |
| **Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)** | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics. |

{style="table-layout:auto"}

+++


Efter dig [välj migreringsmetod](#step-2-choose-your-customer-journey-analytics-migration-method) som är bäst för er organisation kan ni börja skicka data till Adobe Experience Platform för att göra dem tillgängliga i Customer Journey Analytics.

Processen för att skicka data till Experience Platform för varje migreringsmetod visas nedan. Följ länkarna i tabellen nedan för mer detaljerad information.

| Migreringsmetod | Process för att skicka data till plattformen |
|---------|----------|
| Ny implementering av Web SDK | Eftersom det här är en ny implementering av Web SDK måste du följa alla steg som beskrivs i [Importera data via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md). |
| Migrera din Adobe Analytics-implementering till Web SDK | Stegen för migrering till Adobe Analytics Web SDK skiljer sig åt beroende på om din nuvarande implementering är Analytics-tillägget eller AppMeasurementet. <p>Om du använder taggtillägget Analytics: [Migrera från Adobe Analytics-taggtillägget till Web SDK-taggtillägget](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</p><p>eller</p><p>Om du använder AppMeasurement: [Migrera från AppMeasurement till Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| Konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till Customer Journey Analytics | Eftersom Adobe Analytics-implementeringen redan använder Web SDK behöver du bara [konfigurera ett datastream](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream). Du kan ignorera det andra avsnittet i [Importera data via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk). |
| Källanslutning för analyser | [Importera och använda data från traditionella Adobe Analytics](/help/data-ingestion/analytics.md) |

## Mappa sedan data till XDM-schemat

När du har skickat data till Experience Platform genom att följa länkarna i tabellen ovan kan du behöva [mappa data till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md), beroende på vilken implementeringsmetod du väljer.

Följande implementeringsmetoder kräver att du mappar data till XDM-schemat:

* Migrera från Adobe Analytics-taggtillägget till Web SDK-taggtillägget

* Konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till Customer Journey Analytics

Om du väljer att göra en ny implementering av Web SDK krävs ingen mappning eftersom du redan [konfigurera ett nytt XDM-schema](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) som en del av den nya implementeringen.

Om du väljer att använda Analytics Source Connector för din migrering behövs ingen mappning eftersom Analytics Source Connector använder ditt befintliga Adobe Analytics-schema i stället för XDM-schemat.
