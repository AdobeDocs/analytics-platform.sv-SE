---
title: Komma igång med Customer Journey Analytics
description: Förstå de förutsättningar och det arbetsflöde som krävs för att implementera Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: a0b282feed28c24565c5f7cc87c7fefab3e00057
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

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
| **Steg 1: Läs migreringsguiden om du migrerar från Adobe Analytics till CJA.** | [Migreringshandbok för Adobe Analytics till Customer Journey Analytics](/help/getting-started/aa-to-cja.md) |
| **Steg 2: Hämta data till Adobe Experience Platform** | Det här steget, som utförs i Adobe Experience Platform, omfattar flera delsteg:<ul><li>**Steg 2a: Förbered ditt dataschema**: Använd [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) standardisera kundupplevelsedata och [definiera scheman](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en) för kundupplevelsehantering.</li><li>**Steg 2b: Skapa en datauppsättning baserad på schemat**: Data in Platform består av datauppsättningar som e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datauppsättningar osv. Varje datauppsättning består av ett schema och grupper med data. Du kan [skapa en datauppsättning i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html%3Flang%3Dnl).</li><li>**Steg 2c: Infoga data i Experience Platform**: Här har du flera alternativ. Visa [användningsfall för dataöverföring](/help/use-cases/data-ingestion.md) för mer information. |
| **Steg 2: Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om datauppsättningar från Experience Platform måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Workspace.<br>Se [Skapa en anslutning](/help/connections/create-connection.md). |
| **Steg 3: Skapa datavyer** | En datavy är en&quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering osv. Du kan skapa flera datavyer för en enskild datauppsättning.<br>Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 4: Rapportera om dina flerkanalsdata i Workspace** | När du har skapat anslutningar och datavyer kan du analysera de data du har tagit med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se [Utför grundläggande analys](/help/analysis-workspace/perform-basic-analysis.md) och [Avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |
