---
title: Customer Journey Analytics snabbstartsguide för B2B
description: Snabbstartsguide för B2B-versionen av Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B-utgåva"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: d7ee16c64761440989f2850d72b8159799bb8479
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Snabbstartsguide för B2B Edition

{{draft-b2b}}

Om du vill implementera Customer Journey Analytics B2B Edition måste du först se till att du förstår de B2B-specifika koncepten och funktionerna. Du bör också vara bekant med det traditionella arbetsflödet för att implementera Customer Journey Analytics.

Det här dokumentet fokuserar på det arbetsflöde som är specifikt för implementeringen av Customer Journey Analytics.

## Förutsättningar

Följande förutsättningar gäller för att implementera Customer Journey Analytics B2B Edition:

* Du har den åtkomstkontroll och de behörigheter [&#128279;](/help/technotes/access-control.md) som krävs för att tillhandahålla administrationsåtgärder i Customer Journey Analytics.
* Du har köpt Customer Journey Analytics B2B edition-tilläggspaketet.


## Arbetsflöde

| Uppgift | Detaljer |
| --- | --- |
| **Steg 1: Hämta B2B-data till Experience Platform** | Det här steget, som utförs i Experience Platform, omfattar flera understeg:<ul><li>**Steg 1a: Förbered ditt dataschema**: Använd [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) för att standardisera B2B-data och [definiera scheman](https://experienceleague.adobe.com/sv/docs/experience-platform/rtcdp/schemas/b2b) för dina B2B-data.</li><li>**Steg 1b: Skapa en datauppsättning baserat på schemat**: Data i Platform består av datauppsättningar, till exempel kontodata, affärsmöjlighetsdata, inköpsgruppsdata, kampanjdata, marknadsföringslistdata, e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar med mera. Varje datauppsättning består av ett schema och batchar med data. Du kan [skapa en datauppsättning i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=sv-SE).</li><li>**Steg 1c: Importera data till Experience Platform**: Du har [flera alternativ](https://experienceleague.adobe.com/sv/docs/experience-platform/ingestion/home).</li></ul> |
| **Steg 2: Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics** | Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om Experience Platform datauppsättningar måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Workspace. Det finns ytterligare alternativ när du konfigurerar en anslutning till B2B edition. <br>Se [Skapa eller redigera en anslutning](/help/connections/create-connection.md). |
| **Steg 3: Skapa datavyer** | En datavy är en *filtrerad* vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering med mera. Du kan skapa flera datavyer för en enda datamängd. Du har ytterligare alternativ när du konfigurerar en datavy när du har B2B-utgåvan.<br>Mer information finns i [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 4: Rapportera om dina flerkanalsdata i Workspace** | När du har skapat anslutningar och datavyer kan du analysera de B2B-data som du har hämtat in med hjälp av kraften och flexibiliteten i Analysis Workspace.<br>Se [Utföra grundläggande analys](/help/analysis-workspace/perform-basic-analysis.md) och [Utföra avancerad analys](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->