---
title: Customer Journey Analytics Quick Start Guide
description: Förstå de förutsättningar och det arbetsflöde som krävs för att implementera Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7b824c914187854e9779ebdc51c5f5d6e77f6b16
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 1%

---

# Snabbstartsguide

För att implementera Customer Journey Analytics måste du följa det här arbetsflödet. Vissa initiala åtgärder utförs i Adobe Experience Platform och andra i Customer Journey Analytics.

## Förutsättningar

Customer Journey Analytics finns för kunder som

* har etablerats för [Adobe Experience Platform](https://www.adobe.com/experience-platform.html) och
* Har köpt Customer Journey Analytics SKU

## Arbetsflöde

| Uppgift | Information |
| --- | --- |
| **Steg 1: Om du uppgraderar från Adobe Analytics till Customer Journey Analytics: välj en uppgraderingsväg och skicka data till Adobe Experience Platform** | Det finns olika alternativ när du uppgraderar från Adobe Analytics till Customer Journey Analytics. Varje uppgraderingsväg har sina egna fördelar och nackdelar, och en väg som passar en organisation kanske inte passar en annan. <p>Gör något av följande för att börja uppgradera från Adobe Analytics till Customer Journey Analytics:</p><ul><li>Följ uppgraderingsanvisningarna från Adobe. Mer information finns i [Rekommenderad sökväg vid uppgradering från Adobe Analytics till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</li><li>Läs mer om alla tillgängliga uppgraderingsalternativ och välj den väg som passar er organisation bäst. Mer information finns i [Kom igång med uppgraderingen till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md).</li></ul> |
| **Steg 2: Hämta andra data till Adobe Experience Platform** | Det här steget, som utförs i Adobe Experience Platform, omfattar flera delsteg:<ul><li>**Steg 2a: Förbered ditt dataschema**: Använd [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) för att standardisera kundupplevelsedata och [definiera scheman](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE) för kundupplevelsehantering.</li><li>**Steg 2b: Skapa en datauppsättning baserad på schemat**: Data i Platform består av datauppsättningar, till exempel e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datauppsättningar osv. Varje datauppsättning består av ett schema och grupper med data. Du kan [skapa en datauppsättning i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=sv-SE).</li><li>**Steg 2c: Infoga data i Experience Platform**: Här finns flera alternativ.</li></ul> |
| **Steg 3: Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om Experience Platform datauppsättningar måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Workspace.<br>Se [Skapa eller redigera en anslutning](/help/connections/create-connection.md). |
| **Steg 4: Skapa datavyer** | En datavy är en&quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering osv. Du kan skapa flera datavyer för en enskild datauppsättning.<br>Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 5: Porten för API-användningen för rapportering**</br> Gäller endast vid migrering från Adobe Analytics | Customer Journey Analytics rapporterings-API har samma format, men använder en annan slutpunkt. Anmäl API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics API. |
| **Steg 6: Konto för datafeeds och Data Warehouse-användningsfall**</br> Gäller endast vid migrering från Adobe Analytics | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att på bästa sätt replikera de dataflöden och Data Warehouse-funktioner som du använde i Adobe Analytics. <!-- link to docs Rob is creating --> |
| **Steg 7: Migrera projekt och komponenter**</br> Gäller endast när du migrerar från Adobe Analytics | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics.<p>Migreringsprocessen omfattar:</p><ul><li>Återskapa Adobe Analytics-projekt i Customer Journey Analytics.</li><li>Mappa mått och mätvärden från Adobe Analytics rapporteringsprogram till mått och mätvärden i Customer Journey Analytics datavyer.</li></ul><p>Innan du påbörjar migreringen [Förbered dig för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=sv-SE).</p><p>När du har gjort alla förberedelser du behöver kan du [Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=sv-SE).</p> |
| **Steg 8: Planera användarintroduktion** | Precis som i Adobe Analytics är Analysis Workspace det viktigaste användarvänliga verktyget i Customer Journey Analytics. Det finns dock vissa viktiga skillnader när det gäller att använda Analysis Workspace i Customer Journey Analytics som användare måste vara medvetna om.<p>Du bör ge dina användare god tid (3-6 månader) att bekanta sig med de viktigaste skillnaderna mellan Analysis Workspace i Customer Journey Analytics.</p><p>Mer information om några av de viktigaste skillnaderna mellan Adobe Analytics och Customer Journey Analytics finns i [Användarhandbok för Adobe Analytics-användare](/help/getting-started/aa-to-cja-user.md).</p> |
| **Steg 9: Rapport om dina data för olika kanaler i Workspace** | När du har skapat anslutningar och datavyer kan du analysera de data du har tagit med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se [Utför grundläggande analys](/help/analysis-workspace/perform-basic-analysis.md) och [Utför avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |

## Snabbstartguider

Avsnittet [Datainförsel](../data-ingestion/data-ingestion.md) innehåller snabbstartguider för arbetsflödet ovan. Dessa snabbstartsguider visar hur man importerar data från olika källor (inklusive Adobe Analytics) i Adobe Experience Platform och sedan använder dessa data i Customer Journey Analytics.
