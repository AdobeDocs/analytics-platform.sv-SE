---
title: Översikt över dataöverföring
description: Förstå olika sätt att importera data till Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: 8071e8d5e1ab7e9cfc5037d710361a4d10285704
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 0%

---

# Översikt över dataöverföring

Det finns flera sätt att importera data till Customer Journey Analytics. Vissa av dem utgår ifrån att man vill flytta traditionella Adobe Analytics-data över dem, vissa av dem utgår ifrån att man använder data som är insamlade i Adobe Experience Platform.

>[!IMPORTANT]
>
>I alla scenarier är de data som du vill _använda_ i Customer Journey Analytics faktiskt _inkapslade_ i Adobe Experience Platform.

Se Customer Journey Analytics-arkitekturen på hög nivå som visades tidigare i [Översikt](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=sv-SE):

![Customer Journey Analytics-arkitektur som beskrivs i det här avsnittet](./assets/cja-architecture.png)

Datauppsättningen i arkitekturen ovan kan komma från olika källor:

- batchdata,

- strömmande data,

- data från en pågående Adobe Analytics-driftsättning,

- data från spårning av din webbplats/mobilapp med Adobe Experience Platform Web/Mobile SDK,

- data från spårning av skrivbordsprogram, konsolspel, digitalbox eller IoT-enheter med Adobe Experience Platform Edge Network Server API, eller

- data som kommer från en tredjepartsleverantör av data för vilken Adobe tillhandahåller en källanslutning.

Och du kan ha många av dessa datauppsättningar.

I det här avsnittet av dokumentationen finns snabbstartsguider för olika scenarier.

## Inmatningsprioritering och fördröjning

Du kan importera dina händelsedata till Customer Journey Analytics inom 90 minuter (SLT), oavsett om dessa data är 24 timmar, 48 timmar eller 7 dagar gamla.

Observera att den här funktionen skiljer sig åt beroende på vilket SKU-paket ditt företag har köpt:

- Prioritet Grundläggande om intag: 24-timmars gamla data inom 90 minuters SLT-bearbetning (tillgängligt för **CJA Foundation** och **CJA Select**)

- Prioritet Inmatningsintervall: 72-timmars gamla data inom 90 minuters SLT-bearbetning (tillgängligt för **CJA Prime**)

- Prioriterat intag avancerat: 1-veckors gamla data inom 90-minuters SLT-bearbetning (tillgängligt för **CJA Ultimate**)

## Importera och använda data från traditionella Adobe Analytics

Ni har redan driftsatt Adobe Analytics och vill importera dessa data i Adobe Experience Platform och använda, kombinera och analysera dem med data från andra kanaler och datakällor i Customer Journey Analytics.

Mer information finns i [Importera och använda data från traditionella Adobe Analytics](./analytics.md).


## Importera och använda data via Edge Network

### Använda Adobe Experience Platform Web SDK

Du vill analysera din webbplats med Adobe-teknik och kanske migrera från en annan lösning eller börja spåra din persons beteende. Du vill följa Adobe bästa praxis för implementering, som använder Adobe Experience Platform SDK:er och Edge Network, för att importera data. Sedan kan ni använda, kombinera och analysera inkapslade data med data från andra kanaler och datakällor i Customer Journey Analytics.

Mer information finns i [Importera och använda data via Adobe Experience Platform Web SDK](./aepwebsdk.md).

### Använda Adobe Experience Platform Mobile SDK

Du vill analysera din mobilapp med Adobe-teknik och kanske migrera från en annan lösning eller börja spåra en persons beteende i appen från grunden. Du vill följa Adobe bästa praxis för implementering, som använder Adobe Experience Platform SDK:er och Edge Network, för att importera data. Sedan kan ni använda, kombinera och analysera inkapslade data med data från andra kanaler och datakällor i Customer Journey Analytics.

Mer information finns i [Importera och använda data via Adobe Experience Platform Mobile SDK](./aepmobilesdk.md).

### Använda Adobe Experience Platform Edge Network Server API

Du vill analysera datorprogrammet, spelet som det spelas på en spelkonsol, användningen av ett program för direktuppspelad video i en digitalbox eller IoT-enheten med Adobe-teknik. Kan migrera från en annan lösning eller börja spåra en persons beteende på dessa enheter från grunden. Du vill följa Adobe bästa praxis för implementering, som använder Adobe Experience Platform Edge Network Server API:er och Edge Network, för att importera data. Sedan kan ni använda, kombinera och analysera inkapslade data med data från andra kanaler och datakällor i Customer Journey Analytics.

Mer information finns i [Importera och använda data via Adobe Experience Platform Edge Network Server API](./serverapi.md).

## Importera och använda batchdata

Ni har relevanta batchdata tillgängliga som ger er information som kan hjälpa er att förstå kundbeteendet bättre och analysera kundinteraktioner. Exempel på sådana gruppdata är platta filer i CSV-, JSON- eller Parquet-format från ett CRM-system, lojalitetsprogram eller annan lösning som Adobe inte har någon källanslutning för. Om du samlar in batchdata i Adobe Experience Platform kan du använda, kombinera och analysera dem med data från andra kanaler och datakällor i Customer Journey Analytics.

Mer information finns i [Importera och använda gruppdata](./batch.md).

## Importera och använda strömmande data

Ni har en relevant datakälla, till exempel ett CRM-system, ERP-system eller någon annan källa, som ger er information som hjälper er att förstå kundbeteendet bättre och analysera kundinteraktioner. Datakällan kan kommunicera över HTTP- eller public cloud streaming-infrastruktur, men för vilken Adobe för närvarande inte tillhandahåller någon källanslutning. Genom att lägga in strömmande data i Adobe Experience Platform i realtid kan ni använda, kombinera och analysera dem med data från andra kanaler och datakällor i Customer Journey Analytics.

Mer information finns i [Importera och använda strömmande data](./streaming.md).

## Importera och använda data med hjälp av källkopplingar

Du har data tillgängliga från en källa som stöds av en källkoppling. Source-anslutningar är konfigurerbara så att du kan importera data från Adobe, program från första part och program från tredje part till Adobe Experience Platform. Se [Översikt över Source-anslutningar](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=sv-SE) för en översikt över tillgängliga källanslutningar. Med källkopplingen kan du enkelt importera data från källan till Adobe Experience Platform och sedan använda, kombinera och analysera dem med data från andra kanaler och datakällor i Customer Journey Analytics.

Mer information finns i [Importera och använda data med hjälp av källanslutningar](./sources.md).

>[!MORELIKETHIS]
>
>Blogg: [En närmare titt på databearbetning och inmatning i Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091)

