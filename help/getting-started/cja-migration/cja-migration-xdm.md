---
title: Mappa data till XDM-schemat vid migrering till Customer Journey Analytics
description: Lär dig mappa data till XDM-schemat när du migrerar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 0%

---

# Steg 4: Mappa data till XDM-schemat vid migrering till Customer Journey Analytics

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större migreringsprocessen. Kontrollera att alla tidigare migreringssteg är slutförda.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 4, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsmetod](/help/getting-started/cja-migration/cja-migration-method.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken migreringsmetod du väljer i steg 1. |
| <span class="preview">**Steg 4: [Mappa data till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta flyttningsmetoder kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p></span> |
| **Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics. |
| **Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)** | Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics. |
| **Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics. |
| **Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)** | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Alla flyttningsmetoder kräver inte att du mappar dina Adobe Analytics-data till XDM-schemat. Tabellen nedan visar vilka implementeringsmetoder som kräver XDM-schemamappning:


| Migreringsmetod | XDM-mappning krävs? | Mer information |
|---------|----------|---------|
| **Ny implementering av Web SDK**<p>De grundläggande stegen är:</p><ol><li>Skapa ett XDM-schema för din organisation</li><li>Implementera Web SDK</li><li>Skicka data till plattformen</li></ol> | Nej | Du behöver inte mappa eftersom du redan [konfigurera ett nytt XDM-schema](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) som en del av den nya implementeringen. |
| **Migrera din Adobe Analytics-implementering till Web SDK**<p>De grundläggande stegen är:</p><ol><li>Flytta din befintliga Adobe Analytics-implementering till Web SDK och validera att allt fungerar där.</li><li>Skapa ett XDM-schema för din organisation när du har tid.</li><li>Använd dataströmsmappning för att mappa alla fält i dataobjektet till ditt XDM-schema.</li><li>Skicka data till plattformen</li></ol> | Ja | Identifiera er organisations idealiska schemadesign för Customer Journey Analytics i samarbete med datagruppen och fastställ sedan hur ni ska mappa eVars och Props till XDM.</br>[Använd Data Prep för att mappa alla fält i dataobjektet till ditt XDM-schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till Customer Journey Analytics**<p>De grundläggande stegen är:</p><ol><li>Börja skicka data till Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Valfritt) Skapa ett XDM-schema för din organisation när du har tid.</li><li>Använd dataströmsmappning för att mappa alla fält i dataobjektet till ditt XDM-schema.</li></ol> | Ja | Identifiera er organisations idealiska schemadesign för Customer Journey Analytics i samarbete med datagruppen och fastställ sedan hur ni ska mappa eVars och Props till XDM.</br>[Använd Data Prep för att mappa alla fält i dataobjektet till ditt XDM-schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Källanslutning för analyser**</br> Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget kan du börja skicka data till en datavy i Customer Journey Analytics.<p>Detta är det enklaste sättet att få data till Customer Journey Analytics, men det är den minst användbara metoden på lång sikt.</p> | Nej | Ingen mappning krävs eftersom Analytics Source Connector använder ditt befintliga Adobe Analytics-schema i stället för XDM-schemat. |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## Behåll sedan historiska data

Välj sedan den metod du vill använda för [bevara historiska Adobe Analytics-data](/help/getting-started/cja-migration/cja-migration-historical-data.md).
