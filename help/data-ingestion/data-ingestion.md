---
title: Översikt över dataöverföring
description: Förstå olika sätt att importera data till Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 0%

---

# Översikt över dataöverföring

Det finns flera sätt att importera data till Customer Journey Analytics. Vissa av dem utgår ifrån att man vill flytta traditionella Adobe Analytics-data över dem, vissa av dem utgår ifrån att man använder data som är insamlade i Adobe Experience Platform.

>[!IMPORTANT]
>
>I alla scenarier är de data du vill ha _use_ i Customer Journey Analytics är _inkapslad_ i Adobe Experience Platform.


Se Customer Journey Analytics-arkitekturen på hög nivå som visades tidigare i [Ökning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en):

![Customer Journey Analytics-arkitekturen som beskrivs i detta avsnitt](./assets/cja-architecture.png)

Datauppsättningen i arkitekturen ovan kan komma från olika källor:

- batchdata,

- strömmande data,

- data från en pågående Adobe Analytics-driftsättning,

- data från spårning av din webbplats/mobilapp med Adobe Experience Platform Web/Mobile SDK,

- data från spårning av skrivbordsprogram, konsolspel, digitalbox eller IoT-enheter med Adobe Experience Platform Edge Network Server API, eller

- data som kommer från en tredjepartsleverantör av data för vilken Adobe tillhandahåller en källanslutning.

Och du kan ha många av dessa datauppsättningar.

I det här avsnittet av dokumentationen finns snabbstartsguider för olika scenarier.

## Importera och använda data från traditionella Adobe Analytics

Ni har redan driftsatt Adobe Analytics och vill importera dessa data i Adobe Experience Platform och använda, kombinera och analysera dem med data från andra kanaler och datakällor i Customer Journey Analytics.

Se [Importera och använda data från traditionella Adobe Analytics](./analytics.md) för mer information.


## Importera och använda data via Edge Network

### Använda Adobe Experience Platform Web SDK

Ni vill analysera er webbplats med Adobe-teknik och kanske migrera från en annan lösning eller börja spåra er persons beteende. Du vill följa Adobe bästa praxis för implementering, som använder Adobe Experience Platform SDK:er och Edge Network, för att importera data. Sedan kan ni använda, kombinera och analysera inkapslade data med data från andra kanaler och datakällor i Customer Journey Analytics.

Se [Importera och använda data via Adobe Experience Platform Web SDK](./aepwebsdk.md) för mer information.

### Använda Adobe Experience Platform Mobile SDK

Du vill analysera mobilappen med Adobe-teknik och kanske migrera från en annan lösning eller börja spåra en persons beteende i appen från grunden. Du vill följa Adobe bästa praxis för implementering, som använder Adobe Experience Platform SDK:er och Edge Network, för att importera data. Sedan kan ni använda, kombinera och analysera inkapslade data med data från andra kanaler och datakällor i Customer Journey Analytics.

Se [Importera och använda data via Adobe Experience Platform Mobile SDK](./aepmobilesdk.md) för mer information.

### Använda API:t för Adobe Experience Platform Edge Network Server

Du vill analysera datorprogrammet, spelet som det spelas på en spelkonsol, användningen av ett program för direktuppspelad video i en digitalbox eller IoT-enheten med Adobe-teknik. Kan migrera från en annan lösning eller börja spåra en persons beteende på dessa enheter från grunden. Du vill följa Adobe bästa praxis för implementering, som använder API:erna för Adobe Experience Platform Edge Network Server och Edge Network, för att importera data. Sedan kan ni använda, kombinera och analysera inkapslade data med data från andra kanaler och datakällor i Customer Journey Analytics.

Se [Importera och använda data via Adobe Experience Platform Edge Network Server API](./serverapi.md) för mer information.

## Importera och använda batchdata

Ni har relevanta batchdata tillgängliga som ger er information som kan hjälpa er att förstå kundbeteendet bättre och analysera kundinteraktioner. Exempel på sådana gruppdata är platta filer i CSV-, JSON- eller Parquet-format från ett CRM-system, lojalitetsprogram eller annan lösning som Adobe för närvarande inte har någon källkoppling för. Om du samlar in dessa batchdata i Adobe Experience Platform kan du använda, kombinera och analysera dem med data från andra kanaler och datakällor i Customer Journey Analytics.

Se [Importera och använda batchdata](./batch.md) för mer information.

## Importera och använda strömmande data

Ni har en relevant datakälla, till exempel ett CRM-system, ERP-system eller någon annan källa, som ger er information som hjälper er att förstå kundbeteendet bättre och analysera kundinteraktioner. Datakällan kan kommunicera över HTTP- eller public cloud streaming-infrastruktur, men för vilken Adobe för närvarande inte tillhandahåller någon källanslutning. Genom att lägga in strömmande data i Adobe Experience Platform i realtid kan ni använda, kombinera och analysera dem med data från andra kanaler och datakällor i Customer Journey Analytics.

Se [Importera och använda strömmande data](./streaming.md) för mer information.

## Importera och använda data med hjälp av källkopplingar

Du har data tillgängliga från en källa som stöds av en källkoppling. Källanslutningar är konfigurerbara konfigurationer som gör att du kan importera data från Adobe, program från första part och program från tredje part till Adobe Experience Platform. Se [Översikt över källkopplingar](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) för en översikt över tillgängliga källanslutningar. Med källkopplingen kan du enkelt importera data från källan till Adobe Experience Platform och sedan använda, kombinera och analysera dem med data från andra kanaler och datakällor i Customer Journey Analytics.

Se [Importera och använda data med hjälp av källkopplingar](./sources.md) för mer information.
