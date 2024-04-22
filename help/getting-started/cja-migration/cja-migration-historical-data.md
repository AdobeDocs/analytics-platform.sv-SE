---
title: Behåll historiska data vid migrering till Customer Journey Analytics
description: Lär dig hur du behåller historiska data när du migrerar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Steg 5: Behåll historiska data när du migrerar till Customer Journey Analytics

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större migreringsprocessen. Kontrollera att alla tidigare migreringssteg är slutförda.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 5, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsmetod](/help/getting-started/cja-migration/cja-migration-method.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken migreringsmetod du väljer i steg 1. |
| **Steg 4: [Mappa data till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta flyttningsmetoder kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p> |
| <span class="preview">**Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)**</span> | <span class="preview">De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta.</span> |
| **Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics. |
| **Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)** | Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics. |
| **Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics. |
| **Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)** | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Välj något av följande alternativ för att behålla historiska data när du flyttar från Adobe Analytics till Customer Journey Analytics:

## Använd Analytics Source Connector

Du kan använda [Källanslutning för analyser](/help/data-ingestion/analytics.md) att bevara historiska data. Oavsett vilken migreringsmetod du väljer (även om du migrerar med Web SDK) kan du använda Analytics Source Connector för att behålla historiska data från din Adobe Analytics-miljö.

Du kan använda Analytics Source Connector för att behålla historiska data på följande sätt:

* Lägg in historiska data på sin egen dedikerade plats, skilt från era aktuella data.

* Mappa historiska data på ett sätt som gör att du kan koppla dem till nya data. <!-- Possible? Explain -->

## Underhåll din befintliga Adobe Analytics-implementering

Du kan behålla din befintliga Adobe Analytics-implementering tillsammans med din nya Customer Journey Analytics-implementering under en viss tidsperiod (till exempel ett år). När du väljer det här alternativet måste du planera för att avbryta Adobe Analytics-implementeringen när du har tillräckligt med data i Customer Journey Analytics.

Kontakta din kontorepresentant på Adobe för att fastställa priser för det här alternativet.

## Nästa: Planera användarintroduktion

[Planera användarintroduktion på Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-onboarding.md). Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics.
