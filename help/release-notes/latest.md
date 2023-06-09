---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a676c5c71e13524ef56143fe0f5d4cf98c64c2f2
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 5%

---

# Versionsinformation för Customer Journey Analytics (CJA) (juni 2023)

**Senaste uppdatering**: 9 juni 2023

Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Frigör högdagrar {#highlights}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Intelligenta bildtexter** | Bättre berättande för användare med naturtrogna sammanfattningar av [!UICONTROL Line] visualisering. [Läs mer](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 maj 2023 | 1 juni 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** | Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Detta inkluderar delning med personer utanför er organisation, eller personer inom er organisation som inte är anställda för Adobe Analytics. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>Den här funktionen är aktiverad som standard och kan inaktiveras av systemadministratören. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 maj 2023 | 6 juni 2023 |
| **Härledda fält** | Detta representerar den första versionen av härledda fält. Med ett härlett fält kan du definiera (ofta komplexa) dataändringar direkt, via en anpassningsbar regelbyggare. Du kan definiera det härledda fältet ytterligare som en komponent (mått eller dimension) i datavyer och sedan använda det härledda fältet som en komponent i Workspace.<p>Den här versionen har stöd för en marknadsföringskanalmall och följande funktioner:</p><ul><li>Sammanfoga</li><li>Skiftläge</li><li>Sök och ersätt</li><li>Sök</li><li>URL-parsning</li></ul> <p>[Läs mer](/help/data-views/derived-fields/derived-fields.md)</p> | 10 maj 2023 | 21 juni 2023 |
| **PowerBI- och Tableau-åtkomst till CJA-datavyer** | SQL Connector för Customer Journey Analytics (CJA) ger SQL-åtkomst till datavyer som du har definierat i CJA. Datatekniker och analytiker som är mer bekanta med Power BI, Tableau eller andra verktyg för affärsintelligens och visualisering kan nu skapa rapporter och kontrollpaneler baserat på samma datavyer som CJA-användare använder för sina Analysis Workspace-projekt. [Läs mer](/help/data-views/sql-connector.md) |  | 30 juni 2023 |
| **Upplev Edge-geosökningar** | Du kan skapa rapporter med hjälp av geolokaliseringsdata i CJA när Experience Edge Geo Lookups har aktiverats för din datastream. |  | 30 juni 2023 |
| **Utökat sökningsstöd för profil- och sökdata** | Du kan lägga till uppslagsdatauppsättningar i händelsedatamängder, men även i profil- och uppslagsdatamängder. | 21 juni 2023 | 12 juli 2023 |
| **Stöd för valutakonvertering** | CJA stöder valutakonvertering som en del av formateringen av en måttkomponent i en datavy. | 7 juni 2023 | 21 juni 2023 |

{style="table-layout:auto"}

## Andra nya funktioner eller uppdateringar {#other-new}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer datavyer** | CJA-administratörer har tillgång till vissa extra datavyer i CJA med namnet&quot;AJO-datavyn (Sandbox-name)&quot;. Dessa datavyer används för att driva rapporterna i Adobe Journey Optimizer (AJO). De kan också användas för att göra en djupare analys av AJO-aktiviteter i CJA. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). | | 25 maj 2023 |
| **Bakgrundsfyllning för icke-produktionssandlådor** | När du skapar ett dataflöde för Analytics Source Connector i en icke-produktionssandlåda, begränsas bakgrundsfyllningen i icke-produktionssandlådor till tre månader. Den kommer att finnas kvar på 13 månader för produktionssandlådor. | Ej tillämpligt | 26 april 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** | Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Detta inkluderar delning med personer utanför er organisation, eller personer inom er organisation som inte är anställda för Adobe Analytics. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>Den här funktionen är aktiverad som standard och kan inaktiveras av systemadministratören. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3 maj 2023 | 6 juni 2023 |
| **Uppdaterad startskärm för kontrollpanelsappen Analytics (mobilapp)** | På den nya uppdaterade startskärmen kan du visa alla dina styrkort i en konsoliderad styrkortslista.  Om du har tillgång till mer än en organisation under en inloggning är alla styrkort från din organisation tillgängliga i en enda lista. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | Ej tillämpligt | 10 maj 2023 |
| **Härledda fält** | Detta representerar den första versionen av härledda fält. Med ett härlett fält kan du definiera (ofta komplexa) dataändringar direkt, via en anpassningsbar regelbyggare. Du kan definiera det härledda fältet ytterligare som en komponent (mått eller dimension) i datavyer och sedan använda det härledda fältet som en komponent i Workspace.<p>Den här versionen har stöd för en marknadsföringskanalmall och följande funktioner:</p><ul><li>Sammanfoga</li><li>Skiftläge</li><li>Sök och ersätt</li><li>Sök</li><li>URL-parsning</li></ul> <p>[Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 10 maj 2023 | 2 augusti 2023 |
| **Report Builder för CJA - Välj datavy från cell** | Med den här funktionen kan användare välja datavyn för ett datablock från en cell. Detta är praktiskt om du skapar en arbetsbok och har flera datavyer som har liknande datauppbyggnad och du vill kunna återanvända en arbetsbok flera gånger, med olika datavyer. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | Ej tillämpligt | 24 maj 2023 |
| **Uppdaterad utbildningssida för CJA** | Fliken&quot;learning&quot; på landningssidan för Customer Journey Analytics innehåller nu innehåll som är specifikt för CJA, inklusive innehåll som är inriktat på att gå över till CJA från Adobe Analytics.<p>Följande ytterligare förbättringar finns också på fliken Utbildning:</p><ul><li>Förbättrad design som visar mer utbildningsmaterial på en enda sida med förbättrad navigering</li><li>Möjlighet att personalisera utbildningsmaterial efter erfarenhetsnivå (nybörjare, mellanhand och avancerat)</li></ul><p>Tidigare innehöll utbildningsfliken i CJA samma information som utbildningsfliken i Adobe Analytics.</p> [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | Ej tillämpligt | 30 juni 2023 |
| **Sortera komponenter i Analysis Workspace** | <p>Ett nytt sorteringsalternativ är nu tillgängligt när du visar komponenter i den vänstra listen eller i datamappningslistan i Analysis Workspace. Du kan sortera komponenter efter Rekommenderat (de som används oftast), Alfabetiskt eller Kategoriserat (text).</p><p>Tidigare kunde du bara söka efter eller filtrera komponenter. [Läs mer](/help/components/overview.md)</p> | Ej tillämpligt | TBD |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-318343; AN-319453

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | Ej tillämpligt | Ej tillämpligt |

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för AdobeIO OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API-, CJA API- och LiveStream-kunder som använder inloggningsuppgifter för AdobeIO JWT måste migrera till autentiseringsuppgifter för AdobeIO OAuth Server-till-Server med **1 januari 2025**. AdobeIO tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Relaterade resurser

* [Tidigare CJA-versionsinformation för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
