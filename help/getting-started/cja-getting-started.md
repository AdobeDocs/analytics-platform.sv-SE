---
title: Komma igång med kundreseanalys
description: Customer Journey Analytics Getting Started.
translation-type: tm+mt
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# Komma igång med kundreseanalys

För att implementera kundreseanalys måste ni följa det här arbetsflödet. Vissa initiala uppgifter utförs i Adobe Experience Platform och andra i kundreseanalysen.

| Uppgift | Var utförd | Detaljer |
|---|---|---|
| **Steg 1: Hämta data till Adobe Experience Platform** | Adobe Experience Platform | Det finns flera sätt att inhämta data för både direktuppspelning och gruppanvändning, inklusive API:er och ett grafiskt gränssnitt för dataöverföring. Experience Platform kan hämta in data från exempelvis:<ul><li>S3-lagring</li><li>Azure Blob Storage</li><li>Kafka Streams</li><li>SFTP-överföringar</li><li>CSV-filöverföringar</li><li>JSON-filöverföringar</li></ul> |
| **Steg 2: Förbered ditt dataschema** | Adobe Experience Platform | Använd [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) för att standardisera kundupplevelsedata och definiera scheman för kundupplevelsehantering. |
| **Steg 3: Skapa en datauppsättning baserad på schemat** | Adobe Experience Platform | Data in Platform består av datauppsättningar, som e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datauppsättningen osv. Varje datauppsättning består av ett schema och grupper med data. Du kan skapa en datauppsättning [i Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Även om schemat för datauppsättningar som kan importeras till kundreseanalys är flexibelt, måste det följa vissa grundläggande regler. Det är bäst att se till att dina data uppfyller dessa krav innan du överför dem till plattformen. (Observera att schemat innehåller både mått och dimensioner.)<br>Det finns tre typer av data som är kompatibla med kundreseanalys:<ul><li>**Händelsedata**: Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsinformation osv.). Detta är typiska klickströmsdata, med ett kund-ID eller ett cookie-ID, och en tidsstämpel. Med händelsedata kan du använda vilket ID du vill.</li><li>**Uppslagsdata**: Dessa data används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn.</li><li>**Profildata**: Data som tillämpas på besökare, användare eller kunder i händelsedata. Du kan till exempel överföra CRM-data om dina kunder.</li></ul> |
| **Steg 4: Skapa anslutningar mellan plattformsdatauppsättningar och kundreseanalyser** | Customer Journey Analytics | Se [Skapa en anslutning](/help/connections/create-connection.md). |
| **Steg 5: Skapa datavyer** | Customer Journey Analytics | Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 6: Rapportera om dina flerkanalsdata i Workspace** | Customer Journey Analytics | Se [Utför grundläggande analys](/help/projects/perform-basic-analysis.md) och [Utför avancerad analys](/help/projects/perform-adv-analysis.md). |

## Förutsättningar

Customer Journey Analytics är tillgängligt för kunder som

* Är Adobe Analytics [Select-, Prime- eller Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) -kunder, och
* tillhandahålls för [Adobe Experience Platform](https://www.adobe.com/experience-platform.html), och
* Har köpt SKU:n för kundreseanalys

## Förbered ditt dataschema

[Skapa ett schema med Schemaredigeraren](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Steg 1: Hämta data till Adobe Experience Platform

Innan ni kan utnyttja Experience Platform-data i CJA måste ni importera dessa data till Platform. Det finns flera sätt att göra detta:

* Om du vill hämta in dina befintliga Adobe Analytics-data använder du Adobe Analytics Platform Connector.
* Använd format som: S3-lagring, Azure Blob Storage, Kafka-strömmar, SFTP-överföringar, CSV-filöverföringar, JSON-filöverföringar

### Steg 1a: Använd era befintliga analysdata i Adobe Experience Platform

Använd den färdiga Adobe Analytics Platform Connector för att överföra traditionella Adobe Analytics-data till plattformen. Du kan skapa en källanslutning per rapportserie. Se [Skapa en källanslutning med Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) i dokumentationen för Adobe Experience Platform.

När anslutningen har skapats skapas ett målschema och en datauppsättning automatiskt som innehåller inkommande data. Dessutom sker datainfyllning och inmatning av historiska data i upp till 13 månader. När det första intaget är klart kan du fortsätta `Step 4` att skapa en anslutning mellan den här Analytics-datauppsättningen och kundreseanalysen.

### Steg 1b: Importera andra datatyper

[Med batchöverföring](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) kan ni importera data till Experience Platform som batchfiler. Batchar är dataenheter som består av en eller flera filer som ska importeras som en enda enhet. När du har importerat batcharna innehåller de metadata som beskriver antalet poster som har importerats samt eventuella poster som misslyckades och tillhörande felmeddelanden. Manuellt överförda datafiler som platta .CSV-filer (mappade till XDM-scheman) och Parquet-dataramar måste importeras med den här metoden.

[Med direktuppspelande](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) inmatning kan ni skicka data från klient- och serverenheter till Experience Platform i realtid.

[Med andra källkopplingar](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) kan du importera data från externa källor samtidigt som du kan strukturera, etikettera och förbättra inkommande data med hjälp av plattformstjänster. Du kan importera data från en mängd olika källor, till exempel Adobe-program (Adobe Analytics, Audience Manager, Experience Platform Launch, Target), molnbaserad lagring (Azure Blob, Amazon S3, FTP/SFTP, Google Cloud Storage), tredjepartsprogram och ditt CRM (Microsoft Dynamics 365, Salesforce).

## Steg 2: Förbered ditt dataschema

bnbnbnbn
