---
title: Customer Journey Analytics snabbstartsguide för B2B
description: Lathund för B2B edition i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
source-git-commit: 0e4e52cfd42db321c4a7a18a9b1473a67f87e785
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# B2B edition snabbstartsguide

{{draft-b2b}}

För att implementera Customer Journey Analytics B2B edition måste du först förstå de B2B-specifika begreppen och funktionerna. Du bör också känna till det traditionella arbetsflödet för att implementera Customer Journey Analytics.

Det här dokumentet fokuserar på arbetsflödet som är specifikt för implementeringen av Customer Journey Analytics.

## Förutsättningar

För att implementera Customer Journey Analytics B2B edition gäller följande krav:

* Du har den åtkomstkontroll och de behörigheter ](/help/technotes/access-control.md) som krävs för att tillhandahålla administrationsåtgärder i Customer Journey Analytics.[
* Du har köpt Customer Journey Analytics B2B edition-tilläggspaketet.


## Arbetsflöde

| Uppgift | Information |
| --- | --- |
| **Steg 1: Hämta B2B-data till Experience Platform** | Det här steget, som utförs i Experience Platform, omfattar flera delsteg:<ul><li>**Steg 1a: Förbered ditt dataschema**: Använd [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) för att standardisera B2B-data och [definiera scheman](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) för dina B2B-data.</li><li>**Steg 1b: Skapa en datauppsättning baserad på schemat**: Data i Platform består av datauppsättningar som kontodata, affärsmöjlighetsdata, köp av gruppdata, kampanjdata, marknadsföringslistdata, e-postdatamängder, CRM-datauppsättningar, POS-datauppsättningar med mera. Varje datauppsättning består av ett schema och grupper med data. Du kan [skapa en datauppsättning i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html).</li><li>**Steg 1c: Infoga data i Experience Platform**: Du har [flera alternativ](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home).</li></ul> |
| **Steg 2: Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om Experience Platform datauppsättningar måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Workspace. Det finns ytterligare alternativ när du konfigurerar en anslutning till B2B edition. <br>Se [Skapa eller redigera en anslutning](/help/connections/create-connection.md). |
| **Steg 3: Skapa datavyer** | En datavy är en *filtrerad* vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering med mera. Du kan skapa flera datavyer för en enskild datauppsättning. Du har ytterligare alternativ när du konfigurerar en datavy när du har B2B edition.<br>Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 4: Rapport om dina data för olika kanaler i Workspace** | När du har skapat anslutningar och datavyer kan du analysera de B2B-data du har tagit med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se [Utför grundläggande analys](/help/analysis-workspace/perform-basic-analysis.md) och [Utför avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |

## Användningsfall

Dokumentet [B2B Use Case](../data-ingestion/data-ingestion.md) innehåller ett exempel på hur du implementerar Customer Journey Analytics B2B edition.
