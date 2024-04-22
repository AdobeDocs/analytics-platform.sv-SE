---
title: Planera användarintroduktion vid migrering till Customer Journey Analytics
description: Planera användarintroduktion vid migrering till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 90a4aed62ec64f4e58e982a65bfce45789b5cdbb
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# Steg 6: Planera användarintroduktion vid migrering till Customer Journey Analytics

+++Informationen på den här sidan är en del av en större migreringsprocess. Expandera det här avsnittet för att se var informationen passar in i migreringsprocessen. </br></br>Du måste slutföra alla tidigare migreringssteg innan du kan fortsätta med informationen på den här sidan.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 6, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsmetod](/help/getting-started/cja-migration/cja-migration-method.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken migreringsmetod du väljer i steg 1. |
| **Steg 4: [Planera datamappning till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta flyttningsmetoder kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p> |
| **Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| <span class="preview">**Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)**</span> | <span class="preview">Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics.</span> |
| **Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)** | Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics. |
| **Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics. |
| **Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)** | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Det finns några viktiga skillnader mellan Customer Journey Analytics och Adobe Analytics som användare måste vara medvetna om.

Precis som i Adobe Analytics är Analysis Workspace det viktigaste användarvänliga verktyget i Customer Journey Analytics. Men det finns vissa viktiga skillnader mellan Analysis Workspace i Customer Journey Analytics som användare måste vara medvetna om.

Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics.

Mer information om några av de viktigaste skillnaderna mellan Adobe Analytics och Customer Journey Analytics finns i [Användarhandbok för Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

## Därefter anger du API-användningen för rapportering

Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md) från Adobe Analytics rapporterings-API:t till Customer Journey Analytics.