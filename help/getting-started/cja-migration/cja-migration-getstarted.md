---
title: Kom igång med övergången till Customer Journey Analytics
description: Planera din migrering från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 2d35e49ca9afe37ed53d7c5da5aafd31dd2da632
workflow-type: tm+mt
source-wordcount: '634'
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
Informationen på den här sidan omfattar Steg 1 av migreringen, vilket framgår av tabellen nedan. Slutför alla steg i den här tabellen för att migrera från Adobe Analytics till Customer Journey Analytics.

| Migreringsaktivitet | Information |
|---------|----------|
| <span class="preview">**Steg 1: Kom igång med migreringen**</span> | <span class="preview">Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen.</span> |
| **Steg 2: [Välj migreringsväg](/help/getting-started/cja-migration/cja-migration-path.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform varierar beroende på vilken migreringsväg du väljer i steg 2. |
| **Steg 4: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 5: [Utför ytterligare implementeringsuppgifter](/help/getting-started/cja-getting-started.md)** | I nuläget i migreringsprocessen måste du utföra olika åtgärder innan du kan använda Customer Journey Analytics-miljön.<p>Dessa ytterligare uppgifter gäller migreringar från Adobe Analytics och nya implementeringar i Customer Journey Analytics.</p><p>Bland dessa uppgifter finns:</p><ul><li>Placera andra data i Experience Platform</li><li>Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics</li><li>Skapa datavyer</li><li>Portar för API-användning för rapportering</li><li>Redovisning av datafeeds och Data Warehouse</li><li>Migrera projekt och komponenter</li><li>Planera användarintroduktion</li></ul> <p>Mer information finns i [Komma igång med Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Välj först migreringssökvägen

Det finns olika metoder för att migrera till Customer Journey Analytics. [Välj den metod som passar bäst för din organisation](/help/getting-started/cja-migration/cja-migration-path.md).

Vilken migreringsväg du väljer beror på organisationens nuvarande Adobe Analytics-miljö och långsiktiga mål.
