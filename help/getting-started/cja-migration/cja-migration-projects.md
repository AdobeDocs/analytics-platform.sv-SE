---
title: Migrera projekt och komponenter till Customer Journey Analytics
description: Lär dig mer om komponentmigrering för att migrera projekt och komponenter till Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 6e5c3ecf-6eba-4dfa-8bf2-e43d56cfc65f
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---

# Steg 9: Migrera projekt och komponenter till Customer Journey Analytics

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större migreringsprocessen. Kontrollera att alla tidigare migreringssteg är slutförda.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 9, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsväg](/help/getting-started/cja-migration/cja-migration-path.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Mappa data till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta migreringssökvägar kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p> |
| **Steg 4: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform varierar beroende på vilken migreringsväg du väljer i steg 2. |
| **Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics. |
| **Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)** | Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics. |
| **Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics. |
| <span class="preview">**Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)**</span> | <span class="preview">Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics.</span> |
| **Steg 10: [Utföra uppgifter efter migrering](/help/getting-started/cja-getting-started.md)** | När du är klar med migreringen måste du utföra olika uppgifter, till exempel att hämta andra data till Experience Platform, skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics, skapa datavyer och lära dig hur du rapporterar data över flera kanaler i Analysis Workspace. |

{style="table-layout:auto"}

+++

Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics.

Migreringsprocessen omfattar:

* Återskapande av Adobe Analytics-projekt i Customer Journey Analytics.

* Mappa mått och mätvärden från Adobe Analytics rapporteringsprogram till mått och mätvärden i datavyer i Customer Journey Analytics.

Innan du påbörjar migreringen måste du [Förbereda för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html).

När du har gjort alla förberedelser du behöver kan du [Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html).

## Utför sedan uppgifter efter migrering

Efter dig [Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html)måste du utföra olika uppgifter för att slutföra konfigurationen av Customer Journey Analytics-miljön. Dessa uppgifter innefattar att föra in andra data i Experience Platform, skapa kopplingar mellan plattformsdatauppsättningar och Customer Journey Analytics, skapa datavyer och lära sig hur man rapporterar om flerkanalsdata i Analysis Workspace.

Läs mer om migreringsuppgifterna i [Komma igång med Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
