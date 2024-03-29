---
title: Komma igång med Customer Journey Analytics
description: Förstå de förutsättningar och det arbetsflöde som krävs för att implementera Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: bfaf76fa5f225e9aa3153fc4ee10c5be8f3164e7
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# Komma igång med Customer Journey Analytics

Om du vill implementera Customer Journey Analytics måste du följa det här arbetsflödet. Vissa initiala åtgärder utförs i Adobe Experience Platform och andra i Customer Journey Analytics.

## Förutsättningar

Customer Journey Analytics är tillgängligt för kunder som

* Har etablerats för [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)och
* Har köpt SKU:n för Customer Journey Analytics

## Arbetsflöde

| Uppgift | Information |
| --- | --- |
| **Steg 1: Om du migrerar från Adobe Analytics till Customer Journey Analytics ska du migrera dina data och replikera dina projekt.** | Mer information om hur du migrerar data från Adobe Analytics till Customer Journey Analytics finns i: <ul><li>[Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)</li><li>[Importera och använda data från traditionella Adobe Analytics](../data-ingestion/analytics.md)</li></ul><p>Mer information om hur du replikerar dina Adobe Analytics-projekt i Customer Journey Analytics, samt hur du mappar projektkomponenter från en Adobe Analytics-rapportsvit till datavyn för Customer Journey Analytics, finns i:</p><ul><li>[Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html)</li></ul> |
| **Steg 2: Hämta andra data till Adobe Experience Platform** | Det här steget, som utförs i Adobe Experience Platform, omfattar flera delsteg:<ul><li>**Steg 2a: Förbered ditt dataschema**: Använd [XDM (Adobe Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) standardisera kundupplevelsedata och [definiera scheman](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) för kundupplevelsehantering.</li><li>**Steg 2b: Skapa en datauppsättning baserad på schemat**: Data i Platform består av datauppsättningar, som e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datauppsättningar osv. Varje datauppsättning består av ett schema och grupper med data. Du kan [skapa en datauppsättning i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html).</li><li>**Steg 2c: Infoga data i Experience Platform**: Här har du flera alternativ.</li></ul> |
| **Steg 3: Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om datauppsättningar från Experience Platform måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Workspace.<br>Se [Skapa eller redigera en anslutning](/help/connections/create-connection.md). |
| **Steg 4: Skapa datavyer** | En datavy är en&quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering osv. Du kan skapa flera datavyer för en enskild datauppsättning.<br>Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 5: Rapportera om dina flerkanalsdata i arbetsytan** | När du har skapat anslutningar och datavyer kan du analysera de data du har tagit med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se [Utför grundläggande analys](/help/analysis-workspace/perform-basic-analysis.md) och [Avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |

## Snabbstartguider

The [Intag av data](../data-ingestion/data-ingestion.md) innehåller snabbstartsguider för arbetsflödet ovan. Dessa snabbstartsguider visar hur man importerar data från olika källor (inklusive Adobe Analytics) i Adobe Experience Platform och sedan använder dessa data i Customer Journey Analytics.
