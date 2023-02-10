---
title: Komma igång med Customer Journey Analytics
description: Förstå de förutsättningar och det arbetsflöde som krävs för att implementera Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: ab4b65a8948d650615cdf9b99718cbc50499e9f5
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 4%

---

# Komma igång med Customer Journey Analytics

Om du vill implementera Customer Journey Analytics måste du följa det här arbetsflödet. Vissa initiala åtgärder utförs i Adobe Experience Platform och andra i Customer Journey Analytics.

## Förutsättningar

Customer Journey Analytics är tillgängligt för kunder som

* Har etablerats för [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)och
* Har köpt SKU:n för Customer Journey Analytics

## Arbetsflöde

| Uppgift | Detaljer |
| --- | --- |
| **Steg 1: Om du migrerar från Adobe Analytics till CJA ska du ta reda på vad du ska göra.** | Se [Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) och [Importera och använda data från traditionella Adobe Analytics](../data-ingestion/analytics.md). |
| **Steg 2: Hämta andra data till Adobe Experience Platform** | Det här steget, som utförs i Adobe Experience Platform, omfattar flera delsteg:<ul><li>**Steg 2a: Förbered ditt dataschema**: Använd [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) standardisera kundupplevelsedata och [definiera scheman](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) för kundupplevelsehantering.</li><li>**Steg 2b: Skapa en datauppsättning baserad på schemat**: Data in Platform består av datauppsättningar som e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datauppsättningar osv. Varje datauppsättning består av ett schema och grupper med data. Du kan [skapa en datauppsättning i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html).</li><li>**Steg 2c: Infoga data i Experience Platform**: Här har du flera alternativ.</li></ul> |
| **Steg 3: Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om datauppsättningar från Experience Platform måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Workspace.<br>Se [Skapa en anslutning](/help/connections/create-connection.md). |
| **Steg 4: Skapa datavyer** | En datavy är en&quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering osv. Du kan skapa flera datavyer för en enskild datauppsättning.<br>Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 5: Rapportera om dina flerkanalsdata i Workspace** | När du har skapat anslutningar och datavyer kan du analysera de data du har tagit med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se [Utför grundläggande analys](/help/analysis-workspace/perform-basic-analysis.md) och [Avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |

## Snabbstartguider

The [Intag av data](../data-ingestion/data-ingestion.md) innehåller snabbstartsguider för arbetsflödet ovan. Dessa snabbstartsguider visar hur man importerar data från olika källor (inklusive Adobe Analytics) i Adobe Experience Platform och sedan använder dessa data i Customer Journey Analytics.
