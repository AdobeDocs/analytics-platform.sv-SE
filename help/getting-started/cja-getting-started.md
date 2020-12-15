---
title: Komma igång med Customer Journey Analytics
description: Förstå de förutsättningar och det arbetsflöde som krävs för att implementera Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 8067bb355934f8f6f1d54776f44abfd853aee231
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 0%

---


# Komma igång med Customer Journey Analytics

Om du vill implementera Customer Journey Analytics måste du följa det här arbetsflödet. Vissa initiala åtgärder utförs i Adobe Experience Platform och andra i Customer Journey Analytics.

## Förutsättningar

Customer Journey Analytics är tillgängligt för kunder som

* Är Adobe Analytics [Select-, Prime- eller Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html)-kunder och
* har etablerats för [Adobe Experience Platform](https://www.adobe.com/experience-platform.html) och
* Har köpt SKU:n för Customer Journey Analytics

## Arbetsflöde

| Uppgift | Detaljer |
|---|---|
| **Steg 1: Hämta data till Adobe Experience Platform** | Det här steget, som utförs i Adobe Experience Platform, omfattar flera delsteg:<ul><li>**Steg 1a: Förbered ditt dataschema**: Använd  [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) för att standardisera kundupplevelsedata och  [definiera ](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) scheman för kundupplevelsehantering.</li><li>**Steg 1b: Skapa en datauppsättning baserad på schemat**: Data in Platform består av datauppsättningar som e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datauppsättningar osv. Varje datauppsättning består av ett schema och grupper med data. Du kan skapa en datauppsättning [i Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).</li><li>**Steg 1c: Infoga data i Experience Platform**: Använd den färdiga Adobe Analytics Platform Connector för att överföra traditionella Adobe Analytics-data till plattformen. Du kan skapa en källanslutning per rapportserie. Se [Skapa en källanslutning med Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) i Adobe Experience Platform-dokumentationen. När anslutningen har skapats skapas ett målschema och en datauppsättning automatiskt som innehåller inkommande data. Dessutom sker datainfyllning och inmatning av historiska data i upp till 13 månader. När det första intaget är klart kan du fortsätta med `Step 2` för att skapa en anslutning mellan den här Analytics-datauppsättningen och Customer Journey Analytics. Du kan också importera andra datatyper via [Gruppförtäring](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md),[Direktuppspelningsupphämtning](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) eller via [andra källanslutningar](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md).</li></ul> |
| **Steg 2: Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om datauppsättningar från Experience Platform måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Workspace.<br>Se  [Skapa en anslutning](/help/connections/create-connection.md). |
| **Steg 3: Skapa datavyer** | En datavy är en&quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering osv. Du kan skapa flera datavyer för en enskild datauppsättning.<br>Se  [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 4: Rapportera om dina flerkanalsdata i Workspace** | När du har skapat anslutningar och datavyer kan du analysera de data du har tagit med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se  [Utföra grundläggande ](/help/analysis-workspace/perform-basic-analysis.md) analyser och  [Utför avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |
