---
title: Alternativ för dataintag för Customer Journey Analytics
description: Förstå olika sätt att importera data till Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Alternativ för dataintag för Customer Journey Analytics

Du har ett antal alternativ när det gäller att hämta in data till Customer Journey Analytics. Vissa av dem utgår ifrån att man vill flytta traditionella Adobe Analytics-data, vissa av dem förutsätter att man importerar data direkt från Adobe Experience Platform. Den här referensen innehåller åtgärder på hög nivå att följa, med länkar till mer detaljerad information.

## Ingrediera data från traditionella Adobe Analytics

Det här arbetsflödet använder Analytics-källkopplingen och varierar beroende på om du använder DTM eller Launch som tagghanterare.

### Via taggar i Adobe Experience Platform (kallades tidigare [!UICONTROL Launch])

1. [Skapa ett datalager](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=sv-SE), om du inte redan gjort det. Ett datalager är ett ramverk av JavaScript-objekt på din webbplats som innehåller alla variabelvärden som används i implementeringen. Det ger bättre kontroll och enklare underhåll vid implementeringen.
1. Använd [Adobe Experience Platform-taggar](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=sv-SE) för att implementera kod på din webbplats för datainsamling, om du inte redan har det. Med den här tagghanteringslösningen kan ni driftsätta Analytics-kod tillsammans med andra taggningskrav. Taggar erbjuder integreringar med andra lösningar och produkter, och gör att du kan distribuera anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.
1. Skapa en [Adobe Analytics-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE) i Adobe Experience Platform. Den här källkopplingen kommer att importera dina Analytics-data till Experience Platform i ett standardiserat ramverk som kallas [XDM-system (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv). Se även [Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=sv-SE) för att skapa en eller flera anslutningar och datavyer som informerar din flerkanalsrapportering.

## Importera data via Adobe Experience Platform Web SDK och Edge Network

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) är ett JavaScript-bibliotek på klientsidan som gör att Adobe Experience Cloud kunder kan interagera med de olika tjänsterna i Experience Cloud via Adobe Experience Platform Edge Network.

1. [Konfigurera Adobe Experience Platform Web SDK-tillägget i taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=sv-SE) för att skicka data till Adobe Experience Cloud från webbegenskaper via Adobe Experience Platform Edge Network.
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=sv-SE) för att skapa en eller flera [anslutningar](/help/connections/create-connection.md) och [datavyer](/help/data-views/data-views.md) som informerar din flerkanalsrapportering.

## Inmatningsdata med batchinmatning och direktuppspelning

Adobe Experience Platform sammanför data från olika källor för att hjälpa marknadsförarna att bättre förstå kundernas beteende. Adobe Experience Platform datainmatning representerar de olika metoder som används för att importera data från dessa källor och hur data lagras i datasjön för användning av plattformstjänster längre fram i kedjan.

### Batchförtäring

1. Konfigurera [gruppinmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=sv-SE#batch) så att du kan importera data till Adobe Experience Platform som gruppfiler. Data som importeras kan vara profildata från en platt fil i ett CRM-system (till exempel en parquet-fil) eller data som följer ett känt schema i XDM-registret (Experience Data Model).
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=sv-SE) för att skapa en eller flera [anslutningar](/help/connections/create-connection.md) och [datavyer](/help/data-views/data-views.md) som informerar din flerkanalsrapportering.

### Direktinmatning

1. Konfigurera [Direktuppspelningsinmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=sv-SE#streaming) för att skicka data från klient- och serverenheter till Experience Platform i realtid.
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=sv-SE) för att skapa en eller flera [anslutningar](/help/connections/create-connection.md) och [datavyer](/help/data-views/data-views.md) som informerar din flerkanalsrapportering.

## Använd data från Google Analytics för analys i Customer Journey Analytics

Titta på den här självstudiekursen om hur du [Analyserar Google Analytics-data med Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html?lang=sv-SE) för mer information.

## Använd API:t för datainmatning i grupp för att hämta data till Analytics och sedan importera via Analytics-källkopplingen i Experience Platform

1. [Använd API:t för datainfogning i grupp](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) om du vill skicka data från serversidan till Adobe Analytics. Du kan skicka CSV-formaterade filer som innehåller händelsedata.
1. [Skapa en Adobe Analytics-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE) för att hämta konsumentdata till Adobe Experience Platform.
1. Använd [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=sv-SE) för att skapa en eller flera [anslutningar](/help/connections/create-connection.md) och [datavyer](/help/data-views/data-views.md) som informerar din flerkanalsrapportering.
