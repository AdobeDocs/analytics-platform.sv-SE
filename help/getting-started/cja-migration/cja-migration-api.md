---
title: Portar för API-användning för rapportering vid migrering till Customer Journey Analytics
description: Lär dig portera API-användning från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 0%

---

# Steg 7: Porten för API-användningen för rapportering vid migrering till Customer Journey Analytics

+++Informationen på den här sidan är en del av en större migreringsprocess. Expandera det här avsnittet för att se var informationen passar in i migreringsprocessen. </br></br>Du måste slutföra alla tidigare migreringssteg innan du kan fortsätta med informationen på den här sidan.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 7, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsmetod](/help/getting-started/cja-migration/cja-migration-method.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken migreringsmetod du väljer i steg 1. |
| **Steg 4: [Planera datamappning till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta flyttningsmetoder kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p> |
| **Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics. |
| <span class="preview">**Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)**</span> | <span class="preview">Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics.</span> |
| **Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics. |
| **Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)** | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics.

Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt.

## Ersätt sedan datafeeds och Data Warehouse

Bestäm hur exportalternativen i Customer Journey Analytics ska användas för att [ersätta funktionerna för dataflöden och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md) du använde i Adobe Analytics.