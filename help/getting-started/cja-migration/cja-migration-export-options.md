---
title: Ersätt datafeeds och Data Warehouse vid migrering till Customer Journey Analytics
description: Planera din migrering från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# Steg 8: Ersätt datafeeds och Data Warehouse när du migrerar till Customer Journey Analytics

+++Informationen på den här sidan är en del av en större migreringsprocess. Expandera det här avsnittet för att se var informationen passar in i migreringsprocessen. </br></br>Du måste slutföra alla tidigare migreringssteg innan du kan fortsätta med informationen på den här sidan.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 8, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsmetod](/help/getting-started/cja-migration/cja-migration-method.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken migreringsmetod du väljer i steg 1. |
| **Steg 4: [Planera datamappning till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta flyttningsmetoder kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p> |
| **Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics. |
| **Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)** | Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics. |
| <span class="preview">**Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics.</span> |
| **Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)** | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Om du för närvarande använder dataflöden eller Data Warehouse i Adobe Analytics använder du följande tabell för att lära dig mer om de olika exportalternativen som är tillgängliga i Customer Journey Analytics:

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| Dataflöden | Utvärdera dina datafeeds användningsfall och använd sedan en kombination av alternativa exportmetoder som finns i Customer Journey Analytics: <ul><li>Om du vill exportera rådatauppsättningar [exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets). &#x200B;</li><li>Om du vill exportera på målgrupps- eller händelsenivå med hjälp av person-ID eller tidsstämpel använder du [Fullständig tabellexport](/help/analysis-workspace/export/export-cloud.md). &#x200B;</li><li>För direkt integrering med Power BI och Tableau använder du [Customer Journey Analytics BI-tillägg](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension). &#x200B;</li><li>Om du vill ha direkt SQL-åtkomst till data i Adobe Experience Platform använder du [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | Ändra export av Adobe Analytics-Data Warehouse till att använda [Fullständig tabellexport](/help/analysis-workspace/export/export-cloud.md) i Customer Journey Analytics.<p>Customer Journey Analytics Full Table Export är en utveckling av rapporter om Data Warehouse i Adobe Analytics, med många nya, ofta efterfrågade funktioner som inte är tillgängliga i Data Warehouse idag.</p> |

{style="table-layout:auto"}

## Migrera sedan projekt och komponenter

Använd komponentmigreringsområdet i Adobe Analytics för att [migrera projekt och tillhörande komponenter](/help/getting-started/cja-migration/cja-migration-projects.md) från Adobe Analytics till Customer Journey Analytics.
