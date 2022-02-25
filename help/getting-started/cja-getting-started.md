---
title: Komma igång med Customer Journey Analytics
description: Förstå de förutsättningar och det arbetsflöde som krävs för att implementera Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 04ceeb9e9a048a224ea957ad42bc54cbd4b3f249
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Komma igång med Customer Journey Analytics

Om du vill implementera Customer Journey Analytics måste du följa det här arbetsflödet. Vissa initiala åtgärder utförs i Adobe Experience Platform och andra i Customer Journey Analytics.

## Förutsättningar

Customer Journey Analytics är tillgängligt för kunder som

* Är Adobe Analytics [Select, Prime eller Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) kunder och
* Har etablerats för [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)och
* Har köpt SKU:n för Customer Journey Analytics

## Arbetsflöde

| Uppgift | Detaljer |
| --- | --- |
| **Steg 1: Hämta data till Adobe Experience Platform** | Det här steget, som utförs i Adobe Experience Platform, omfattar flera delsteg:<ul><li>**Steg 1a: Förbered ditt dataschema**: Använd [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) standardisera kundupplevelsedata och [definiera scheman](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en) för kundupplevelsehantering.</li><li>**Steg 1b: Skapa en datauppsättning baserad på schemat**: Data in Platform består av datauppsättningar som e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datauppsättningar osv. Varje datauppsättning består av ett schema och grupper med data. Du kan [skapa en datauppsättning i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html%3Flang%3Dnl).</li><li>**Steg 1c: Infoga data i Experience Platform**: Använd den färdiga Adobe Analytics Platform Connector för att överföra traditionella Adobe Analytics-data till plattformen. Du kan skapa en källanslutning per rapportserie. Se [Skapa en källanslutning med Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) i Adobe Experience Platform-dokumentationen. När anslutningen har skapats skapas ett målschema och en datauppsättning automatiskt som innehåller inkommande data. Dessutom sker datainfyllning och inmatning av historiska data i upp till 13 månader. När det första intaget är klart kan du fortsätta med `Step 2` för att skapa en anslutning mellan den här Analytics-datauppsättningen och Customer Journey Analytics. Du kan även importera andra datatyper via [Batchförtäring](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en),[Direktinmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en)eller via [andra källkopplingar](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en).</li></ul> |
| **Steg 2: Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om datauppsättningar från Experience Platform måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Workspace.<br>Se [Skapa en anslutning](/help/connections/create-connection.md). |
| **Steg 3: Skapa datavyer** | En datavy är en&quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering osv. Du kan skapa flera datavyer för en enskild datauppsättning.<br>Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 4: Rapportera om dina flerkanalsdata i Workspace** | När du har skapat anslutningar och datavyer kan du analysera de data du har tagit med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se [Utför grundläggande analys](/help/analysis-workspace/perform-basic-analysis.md) och [Avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |
