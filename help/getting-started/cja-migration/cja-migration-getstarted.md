---
title: Kom igång med övergången till Customer Journey Analytics
description: Planera din migrering från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 0%

---

# Steg 1: Kom igång med migreringen till Customer Journey Analytics

Customer Journey Analytics är nästa generation av analyser. Den möjliggör datainsamling i flera kanaler (både online- och offlinedata), kombinerat med kraftfull rapporttidsbearbetning (genom definition av komponenter och härledda fält i datavyer).

Innan du börjar migrera från Adobe Analytics till Customer Journey Analytics bör du känna till fördelarna med Customer Journey Analytics samt vilka steg som krävs för att migrera.

## Förstå fördelarna med Customer Journey Analytics

Nedan följer några av de viktigaste fördelarna: (En utförlig lista samt mer information om de här nyckelfunktionerna finns i [Endast i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Flerkanalsrapportering](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics kombineras med Experience Platform för att kunna lagra alla typer av datarotor och datatyper. Samla in och rapportera data från olika kanaler, t.ex. digitala (webb), butikssystem, mobiler, CRM-system med mera.

* [Omformningar i rapporttid i datavyer](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Med datavyer i Customer Journey Analytics kan du tolka data från en anslutning ytterligare. Du kan ändra eller ta bort data utan att ändra implementeringen, använda delsträngar för att ändra dimensioner, skapa mätvärden från valfritt värde, filtrera delmängder eller använda härledda fält. Alla dessa omformningar är icke-förstörande.

* [Omvandlingar gäller historiska och nya data](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  Hantering av datavy kan tillämpas på både historiska och nya data på ett icke-förstörande sätt.

* [Härledda fält](/help/data-views/derived-fields/derived-fields.md)

  Härledda fält gör det möjligt att göra omformningar av data vid rapporttillfället. Data kan kombineras, korrigeras eller skapas direkt och gäller retroaktivt för alla rapporter.

* [Datavyer ersätter virtuella rapportsviter](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Datavyer använder begreppet virtuella rapportsviter så som de finns idag och utökar det för att möjliggöra ytterligare kontroller av data som blir tillgängliga via anslutningar. Dessa ändringar gör allmänna inställningar som tidszon och tidsgränsintervall för sessioner konfigurerbara och retroaktiva.

* [Obegränsade kunddimensioner och mätvärden](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Värdena kan vara numeriska värden, text, objekt, listor eller blandningar av alla. Dimensioner kan vara kapslade eller hierarkiska.

## Förstå migreringsprocessen

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Den här sidan representerar Steg 1 av migreringen, vilket visas i följande tabell. Slutför alla steg i den här tabellen för att migrera från Adobe Analytics till Customer Journey Analytics.

| Uppgift | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsmetod](/help/getting-started/cja-migration/cja-migration-method.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som passar bäst för er organisation, med hänsyn tagen till er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken migreringsmetod du väljer i steg 1. |
| **Steg 4: [Mappa data till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta flyttningsmetoder kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p> |
| **Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics. |
| **Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)** | Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics. |
| **Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics. |
| **Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)** | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics. |
| **Steg 10: [Utföra uppgifter efter migrering](/help/getting-started/cja-getting-started.md)** | När du är klar med migreringen måste du utföra olika uppgifter, till exempel att hämta andra data till Experience Platform, skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics, skapa datavyer och lära dig hur du rapporterar data över flera kanaler i Analysis Workspace. |

{style="table-layout:auto"}

## Välj först migreringsmetoden

Det finns olika metoder för att migrera till Customer Journey Analytics. [Välj den metod som passar bäst för din organisation](/help/getting-started/cja-migration/cja-migration-method.md).

Vilken migreringsmetod du väljer beror på organisationens nuvarande Adobe Analytics-miljö och långsiktiga mål.
