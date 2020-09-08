---
title: Alternativ för dataintag för Customer Journey Analytics
description: Förstå olika sätt att importera data till Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 540b170c3429f04b7f63872b30cbb01852d30179
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---


# Alternativ för dataintag för Customer Journey Analytics

Du har ett antal alternativ när det gäller att hämta in data till Customer Journey Analytics. Vissa av dem utgår ifrån att man vill flytta traditionella Adobe Analytics-data, vissa av dem förutsätter att man importerar data direkt från Adobe Experience Platform.

## Ingrediera data från traditionella Adobe Analytics

Det här arbetsflödet använder Adobe Analytics Data Connector och varierar beroende på om du använder DTM eller Launch som tagghanterare.

### Via dynamisk tagghantering (DTM)

1. [Skapa ett datalager](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)om du inte redan gjort det. Ett datalager är ett ramverk av JavaScript-objekt på platsen som innehåller alla variabelvärden som används i implementeringen. Det ger bättre kontroll och enklare underhåll vid implementeringen.
1. Använd [DTM](https://docs.adobe.com/content/help/en/analytics/implementation/other/dtm/dtm-implementation-overview.html) för att implementera kod på din webbplats för datainsamling, om du inte redan gjort det. Dynamic Tag Management är ett enda datalager som överför data från flera källor.
1. Skapa en [Adobe Analytics källanslutning](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) i Adobe Experience Platform. Den här källkopplingen kommer att importera dina Analytics-data till Experience Platform i ett standardiserat ramverk som kallas [Experience Data Model (XDM) System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Använd [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) om du vill skapa en eller flera anslutningar och datavyer som ska informera er flerkanalsrapportering.

### Via Launch

1. [Skapa ett datalager](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)om du inte redan gjort det. Ett datalager är ett ramverk av JavaScript-objekt på platsen som innehåller alla variabelvärden som används i implementeringen. Det ger bättre kontroll och enklare underhåll vid implementeringen.
1. Använd [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) för att implementera kod på din webbplats för datainsamling, om du inte redan gjort det. Launch är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Launch erbjuder integrering med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.
1. Skapa en [Adobe Analytics källanslutning](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) i Adobe Experience Platform. Den här källkopplingen kommer att importera dina Analytics-data till Experience Platform i ett standardiserat ramverk som kallas [Experience Data Model (XDM) System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Använd [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) om du vill skapa en eller flera anslutningar och datavyer som ska informera er flerkanalsrapportering.

## Infoga data från AEP Web SDK

TBD

### Via Experience Edge

TBD

### Via Launch

TBD

## Intag av batchdata och direktuppspelning

TBD

## Ingest Google Analytics data

TBD

## Infoga data via API:t för massinmatning

TBD