---
title: Komma igång med kundresanalysen
description: Komma igång med kundresanalysen.
translation-type: tm+mt
source-git-commit: 16bca45f2576d3feef8129d558fad6f236852cb9
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---


# Komma igång med kundresanalysen

Du måste följa det här arbetsflödet för att kunna implementera kundressanalys. Vissa inledande uppgifter utförs i Adobe Experience Platform och vissa i Customer Journey Analytics.

## Förutsättningar

Kundresresestudier är tillgängliga för kunder som

* Är Adobe Analytics [Välj, Primär eller Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) kunder, och
* Etableras för [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)och
* Har köpt SKU för kundens Journey Analytics

## Arbetsflöde

| Uppgift | Information |
|---|---|
| **Steg 1: Hämta dina data till Adobe Experience Platform** | Det här steget, som utförs i Adobe Experience Platform, omfattar flera delsteg:<ul><li>**Steg 1a: Förbered ditt dataschema**: Använd [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) standardisera kundens erfarenhetsdata och [definiera scheman](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) för hantering av kundupplevelser.</li><li>**Steg 1b: Skapa en datauppsättning baserat på schemat**: Data i Platform består av datauppsättningar, t.ex. e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datamängd osv. Varje datamängd består av ett schema och datagrupper. Du kan skapa en datauppsättning [i Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).</li><li>**Steg 1c: Ingest-data från Experience Platform**: Använd Adobe Analytics Platform Connector som är klar att användas för att föra in traditionella Adobe Analytics-data i Platform. Du kan skapa en källanslutning per rapportsvit. Se [Skapa en källanslutning med Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) i dokumentationen för Adobe Experience Platform. När anslutningen har skapats skapas automatiskt ett målschema och en datamängd som innehåller inkommande data. Dessutom sker datautfyllning och insamling av upp till 13 månaders historiska data. När det första intaget är färdigt kan du fortsätta med `Step 2` för att skapa en anslutning mellan den här analytiska datamängden och kundens resvägsanalys. Du kan även infoga andra datatyper via [Batchintag](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md),[Direktuppspelning](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)eller via [Andra källkopplingar](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md).</li></ul> |
| **Steg 2: Skapa anslutningar mellan plattformsdatauppsättningar och kundressanalys** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i arbetsytan. För att kunna rapportera om uppsättningar av erfarenhetsplattformsdata måste du först upprätta en koppling mellan datauppsättningar i Experience Platform och Workspace.<br>Se [Skapa en anslutning](/help/connections/create-connection.md). |
| **Steg 3: Skapa datavyer** | En datavy är en &quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns, attribut osv. för besök. Du kan skapa flera datavyer för en enskild datamängd.<br>Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 4: Rapport om dina data över flera kanaler på arbetsytan** | När du har skapat anslutningar och datavyer analyserar du de data du har lagt in med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se [Utför grundläggande analys](/help/analysis-workspace/perform-basic-analysis.md) och [Utför avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |
