---
title: Alternativ för dataintag för Customer Journey Analytics
description: Förstå olika sätt att importera data till Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 2%

---

# Alternativ för dataintag för Customer Journey Analytics

Du har ett antal alternativ när det gäller att hämta in data till Customer Journey Analytics. Vissa av dem utgår ifrån att man vill flytta traditionella Adobe Analytics-data, vissa av dem förutsätter att man importerar data direkt från Adobe Experience Platform. Den här referensen innehåller åtgärder på hög nivå att följa, med länkar till mer detaljerad information.

## Ingrediera data från traditionella Adobe Analytics

Det här arbetsflödet använder Adobe Analytics Data Connector och varierar beroende på om du använder DTM eller Launch som tagghanterare.

### Via-taggar i Adobe Experience Platform (kallades tidigare [!UICONTROL Launch])

1. [Skapa ett datalager](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html)om du inte redan gjort det. Ett datalager är ett ramverk av JavaScript-objekt på platsen som innehåller alla variabelvärden som används i implementeringen. Det ger bättre kontroll och enklare underhåll vid implementeringen.
1. Använd [Adobe Experience Platform-taggar](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html) för att implementera kod på din webbplats för datainsamling, om du inte redan gjort det. Med den här tagghanteringslösningen kan ni driftsätta Analytics-kod tillsammans med andra taggningskrav. Taggar erbjuder integreringar med andra lösningar och produkter, och gör att du kan distribuera anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.
1. Skapa en [Adobe Analytics källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) i Adobe Experience Platform. Den här källkopplingen kommer att importera dina Analytics-data till Experience Platform i ett standardiserat ramverk som kallas [Experience Data Model (XDM) System](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv).
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) om du vill skapa en eller flera anslutningar och datavyer som ska informera er flerkanalsrapportering.

## Importera data via Adobe Experience Platform Web SDK och Edge Network

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) är ett JavaScript-bibliotek på klientsidan som gör det möjligt för Adobe Experience Cloud-kunder att interagera med de olika tjänsterna i Experience Cloud via Adobe Experience Platform Edge Network.

1. [Konfigurera AEP Web SDK-tillägget i taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) för att skicka data till Adobe Experience Cloud från webbegenskaper via Adobe Experience Platform Edge Network.
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera [anslutningar](/help/connections/create-connection.md) och [datavyer](/help/data-views/data-views.md) som informerar er flerkanalsrapportering.

## Inmatningsdata med batchinmatning och direktuppspelning

Adobe Experience Platform sammanför data från olika källor för att hjälpa marknadsförarna att bättre förstå kundernas beteende. Adobe Experience Platform datainmatning representerar de olika metoder som används för att importera data från dessa källor och hur data lagras i datasjön för användning av plattformstjänster längre fram i kedjan.

### Batchförtäring

1. Konfigurera [Batchintag](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html#batch) så att du kan importera data till Adobe Experience Platform som gruppfiler. Data som importeras kan vara profildata från en platt fil i ett CRM-system (till exempel en parquet-fil) eller data som följer ett känt schema i XDM-registret (Experience Data Model).
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera [anslutningar](/help/connections/create-connection.md) och [datavyer](/help/data-views/data-views.md) som informerar er flerkanalsrapportering.

### Direktinmatning

1. Konfigurera [Direktinmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html#streaming) för att skicka data från klient- och serverenheter till Experience Platform i realtid.
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera [anslutningar](/help/connections/create-connection.md) och [datavyer](/help/data-views/data-views.md) som informerar er flerkanalsrapportering.

## Använd data från Google Analytics för analys i Customer Journey Analytics

Granska den här självstudiekursen om hur du [Analysera Google Analytics-data med Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html#objectives) för detaljerade steg.

## Använd API för datainmatning i grupp för att hämta data till analyser och sedan importera via Adobe Source Connector i Experience Platform

1. [Använd API för massdatainmatning](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) för att skicka data från serversidessamlingar till Adobe Analytics. Du kan skicka CSV-formaterade filer som innehåller händelsedata.
1. [Skapa en Adobe Analytics-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) för att överföra dessa konsumentdata till Adobe Experience Platform.
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) för att skapa en eller flera [anslutningar](/help/connections/create-connection.md) och [datavyer](/help/data-views/data-views.md) som informerar er flerkanalsrapportering.
