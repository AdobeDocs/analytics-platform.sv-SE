---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1314'
ht-degree: 5%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (juni 2023)

**Senaste uppdatering**: 19 juni 2023

Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Frigör högdagrar {#highlights}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Intelligenta bildtexter** | Bättre berättande för användare med naturtrogna sammanfattningar av [!UICONTROL Line] visualisering. [Läs mer](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 maj 2023 | 1 juni 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** | Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Detta inkluderar delning med personer utanför er organisation, eller personer inom er organisation som inte är anställda för Adobe Analytics. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>Den här funktionen är aktiverad som standard och kan inaktiveras av systemadministratören. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 maj 2023 | 6 juni 2023 |
| **Härledda fält** | Detta representerar den första versionen av härledda fält. Med ett härlett fält kan du definiera (ofta komplexa) dataändringar direkt, via en anpassningsbar regelbyggare. Du kan definiera det härledda fältet ytterligare som en komponent (mått eller dimension) i datavyer och sedan använda det härledda fältet som en komponent i Workspace.<p>Den här versionen har stöd för en marknadsföringskanalmall och följande funktioner:</p><ul><li>Sammanfoga</li><li>Skiftläge</li><li>Sök och ersätt</li><li>Sök</li><li>URL-parsning</li></ul> <p>[Läs mer](/help/data-views/derived-fields/derived-fields.md)</p> | 10 maj 2023 | 14 juni 2023 |
| **PowerBI- och Tableau-åtkomst till datavyer i Customer Journey Analytics** | Adobe Customer Journey Analytics SQL Connector ger SQL-åtkomst till datavyer som du har definierat i Customer Journey Analytics. Datatekniker och analytiker som är mer bekanta med Power BI, Tableau eller andra verktyg för affärsintelligens och visualisering kan nu skapa rapporter och kontrollpaneler baserat på samma datavyer som Customer Journey Analytics-användare använder för sina Analysis Workspace-projekt. [Läs mer](/help/data-views/sql-connector.md) |  | 30 juni 2023 |
| **Upplev Edge-geosökningar** | Du kan skapa rapporter med hjälp av geopositioneringsdata i Customer Journey Analytics när Experience Edge Geo Lookups har aktiverats för din datastream. |  | 30 juni 2023 |
| **Utökat sökningsstöd för profil- och sökdata** | Du kan lägga till uppslagsdatauppsättningar i händelsedatamängder, men även i profil- och uppslagsdatamängder. | 28 juni 2023 | 12 juli 2023 |
| **Stöd för valutakonvertering** | Valutakonvertering stöds som en del av formateringen av en måttkomponent i en datavy. [Läs mer](../data-views/component-settings/format.md#currency) | 7 juni 2023 | 21 juni 2023 |

{style="table-layout:auto"}

## Andra nya funktioner eller uppdateringar {#other-new}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer datavyer** | Customer Journey Analytics-administratörer har tillgång till vissa extra datavyer i Customer Journey Analytics med namnet&quot;AJO-datavyn (Sandbox-name)&quot;. Dessa datavyer används för att driva rapporterna i Adobe Journey Optimizer. De kan också användas för att göra en djupare analys av Adobe Journey Optimizer aktiviteter i Customer Journey Analytics. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). | | 25 maj 2023 |
| **Bakgrundsfyllning för icke-produktionssandlådor** | När du skapar ett dataflöde för Analytics Source Connector i en icke-produktionssandlåda, begränsas bakgrundsfyllningen i icke-produktionssandlådor till tre månader. Den kommer att finnas kvar på 13 månader för produktionssandlådor. | Ej tillämpligt | 26 april 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** | Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Detta inkluderar delning med personer utanför er organisation, eller personer inom er organisation som inte är anställda för Adobe Analytics. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>Den här funktionen är aktiverad som standard och kan inaktiveras av systemadministratören. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3 maj 2023 | 6 juni 2023 |
| **Uppdaterad startskärm för kontrollpanelsappen Analytics (mobilapp)** | På den nya uppdaterade startskärmen kan du visa alla dina styrkort i en konsoliderad styrkortslista.  Om du har tillgång till mer än en organisation under en inloggning är alla styrkort från din organisation tillgängliga i en enda lista. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | Ej tillämpligt | 10 maj 2023 |
| **Report Builder för Customer Journey Analytics - Välj datavy från cell** | Med den här funktionen kan användare välja datavyn för ett datablock från en cell. Detta är praktiskt om du skapar en arbetsbok och har flera datavyer som har liknande datauppbyggnad och du vill kunna återanvända en arbetsbok flera gånger, med olika datavyer. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | Ej tillämpligt | 24 maj 2023 |
| **Updated Learning page for Customer Journey Analytics** | Fliken&quot;learning&quot; på landningssidan för Customer Journey Analytics innehåller nu innehåll som är specifikt för Customer Journey Analytics, inklusive innehåll som är inriktat på att gå över till Customer Journey Analytics från Adobe Analytics.<p>Följande ytterligare förbättringar finns också på fliken Utbildning:</p><ul><li>Förbättrad design som visar mer utbildningsmaterial på en enda sida med förbättrad navigering</li><li>Möjlighet att personalisera utbildningsmaterial efter erfarenhetsnivå (nybörjare, mellanhand och avancerat)</li></ul><p>Tidigare innehöll fliken Learning i Customer Journey Analytics samma information som i fliken Learning i Adobe Analytics.</p> [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | Ej tillämpligt | 30 juni 2023 |
| **Sortera komponenter i Analysis Workspace** | <p>Ett nytt sorteringsalternativ är nu tillgängligt när du visar komponenter i den vänstra listen eller i datamappningslistan i Analysis Workspace. Du kan sortera komponenter efter Rekommenderat (de som används oftast), Alfabetiskt eller Kategoriserat (text).</p><p>Tidigare kunde du bara söka efter eller filtrera komponenter. [Läs mer](/help/components/overview.md)</p> | Ej tillämpligt | 7 juni 2023 |
| **Ta bort rader som innehåller dynamiska dimensioner från en frihandstabell** | I en friformstabell i Analysis Workspace kan du nu snabbt ta bort specifika rader som innehåller dynamiska dimensioner med hjälp av x-ikonen. När du gör det används automatiskt en filterregel för att alltid utesluta objekt.<p>Tidigare var det enda sättet att ta bort rader som innehöll dynamiska dimensioner att manuellt skapa en regel i filterdialogrutan. [Läs mer](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | Ej tillämpligt | 17 maj 2023 |
| **Ny knapp för att lägga till en visualisering i en panel** | En ny knapp finns nu längst ned på varje panel i Analysis Workspace, så att du snabbt kan lägga till en visualisering. <p>Tidigare var de enda sätten att lägga till en visualisering på en panel att dra en visualisering från den vänstra listen, duplicera eller kopiera en befintlig visualisering eller skapa en tom panel. [Läs mer](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | Ej tillämpligt | 17 maj 2023 |
| **Djuplänkning (mobilapp)** | Tillåter användare att skicka länkar till styrkort som leder dem direkt till styrkortsprojektet i appen. Detta gör det ännu enklare att dela projekt och öka engagemanget från en mindre teknisk målgrupp. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) | Ej tillämpligt | 17 maj 2023 |
| **Intelligenta bildtexter** | Bättre berättande för användare med naturtrogna sammanfattningar av [!UICONTROL Line] visualisering. [Läs mer](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 maj 2023 | 1 juni 2023 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-318343; AN-319453

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | Ej tillämpligt | Ej tillämpligt |

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för AdobeIO OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API-, Customer Journey Analytics API- och LiveStream-kunder som använder inloggningsuppgifter för AdobeIO JWT måste migrera till inloggningsuppgifter för AdobeIO OAuth Server-till-Server med **1 januari 2025**. AdobeIO tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
