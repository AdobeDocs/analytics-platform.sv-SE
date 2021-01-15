---
title: Alternativ för dataintag för Customer Journey Analytics
description: Förstå olika sätt att importera data till Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 8a3a868ff4e2fbbcdf83ff7769382c6a92f78ec2
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 1%

---


# Alternativ för dataintag för Customer Journey Analytics

Du har ett antal alternativ när det gäller att hämta in data till Customer Journey Analytics. Vissa av dem utgår ifrån att man vill flytta traditionella Adobe Analytics-data, vissa av dem förutsätter att man importerar data direkt från Adobe Experience Platform. Den här referensen innehåller åtgärder på hög nivå att följa, med länkar till mer detaljerad information.

## Ingrediera data från traditionella Adobe Analytics

Det här arbetsflödet använder Adobe Analytics Data Connector och varierar beroende på om du använder DTM eller Launch som tagghanterare.

### Via dynamisk tagghantering (DTM)

1. [Skapa ett datalager](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), om du inte redan gjort det. Ett datalager är ett ramverk av JavaScript-objekt på platsen som innehåller alla variabelvärden som används i implementeringen. Det ger bättre kontroll och enklare underhåll vid implementeringen.
1. Använd [DTM](https://docs.adobe.com/content/help/en/analytics/implementation/other/dtm/dtm-implementation-overview.html) för att implementera kod på din webbplats för datainsamling, om du inte redan gjort det. Dynamic Tag Management är ett enda datalager som överför data från flera källor.
1. Skapa en [Adobe Analytics-källanslutning](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) i Adobe Experience Platform. Den här källkopplingen kommer att importera dina Analytics-data till Experience Platform i ett standardiserat ramverk som heter [Experience Data Model (XDM) System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Använd [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera anslutningar och datavyer som informerar din flerkanalsrapportering.

### Via Launch

1. [Skapa ett datalager](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), om du inte redan gjort det. Ett datalager är ett ramverk av JavaScript-objekt på platsen som innehåller alla variabelvärden som används i implementeringen. Det ger bättre kontroll och enklare underhåll vid implementeringen.
1. Använd [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) för att implementera kod på din webbplats för datainsamling, om du inte redan gjort det. Launch är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Launch erbjuder integrering med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.
1. Skapa en [Adobe Analytics-källanslutning](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) i Adobe Experience Platform. Den här källkopplingen kommer att importera dina Analytics-data till Experience Platform i ett standardiserat ramverk som heter [Experience Data Model (XDM) System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Använd [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera anslutningar och datavyer som informerar din flerkanalsrapportering.

## Importera data via Adobe Experience Platform Web SDK och Edge Network

[Adobe Experience Platform Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) SDK är ett JavaScript-bibliotek på klientsidan som gör att Adobe Experience Cloud kunder kan interagera med de olika tjänsterna i Experience Cloud via Adobe Experience Platform Edge Network.

1. [Konfigurera AEP Web SDK-tillägget i ](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) Launchför att skicka data till Adobe Experience Cloud från webbegenskaper via Adobe Experience Platform Edge Network.
1. Använd [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera anslutningar och datavyer som informerar din flerkanalsrapportering.

## Inmatningsdata med batchinmatning och direktuppspelning

Adobe Experience Platform sammanför data från olika källor för att hjälpa marknadsförarna att bättre förstå kundernas beteende. Adobe Experience Platform datainmatning representerar de olika metoder som används för att importera data från dessa källor och hur data lagras i datasjön för användning av plattformstjänster längre fram i kedjan.

### Batchförtäring

1. Konfigurera [Gruppinmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch) så att du kan importera data till Adobe Experience Platform som gruppfiler. Data som importeras kan vara profildata från en platt fil i ett CRM-system (till exempel en parquet-fil) eller data som följer ett känt schema i XDM-registret (Experience Data Model).
1. Använd [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera anslutningar och datavyer som informerar din flerkanalsrapportering.

### Direktinmatning

1. Konfigurera [Direktuppspelning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming) för att skicka data från klient- och serverenheter till Experience Platform i realtid.
1. Använd [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera anslutningar och datavyer som informerar din flerkanalsrapportering.

## Använd data från Google Analytics för analys i Customer Journey Analytics

Titta igenom den här självstudiekursen om hur du [analyserar Google Analytics-data med Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives) för detaljerade steg.

## Använd API för datainmatning i grupp för att hämta data till analyser och sedan importera via Adobe Source Connector i Experience Platform

1. [Använd API:t ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) för datainfogning i grupp för att skicka data från serversidan till Adobe Analytics. Du kan skicka CSV-formaterade filer som innehåller händelsedata.
1. [Skapa en Adobe Analytics-](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) källanslutning för att överföra konsumentdata till Adobe Experience Platform.
1. Använd [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera anslutningar och datavyer som informerar din flerkanalsrapportering.