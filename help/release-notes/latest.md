---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0160aee587c1f88e4889f26757b1962c3d59b9fa
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 6%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (augusti 2023)

**Senaste uppdatering**: 17 augusti 2023

Versionsanteckningarna gäller den 9 augusti-13 september 2023. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Förbättringar i Report Builder** | <ul><li>Du kan hämta en schemalagd uppgift från fliken Arbetsböcker och sedan ge den en rubrik, spara den och dela den. [Läs mer](/help/report-builder/schedule-reportbuilder.md)</li><li>Startdatum som dimension gör att du kan visa startdatumet för datablocket som en dimension i datablockets utdata. [Läs mer](/help/report-builder/create-a-data-block.md) </li></ul> | Ej tillämpligt | 17 augusti 2023 |
| **Valutakonvertering** | Kundresan ger möjlighet att stödja flera valutor. Du kan konvertera en valuta till en annan valuta i datavyinställningarna. [Läs mer](/help/data-views/component-settings/format.md) | Ej tillämpligt | 31 augusti 2023 |
| **Stöd för A4T-klassificeringar i Analytics Source Connector** | Vi lägger till ett korrelations-ID för enkel koppling av klassificeringsdata för Adobe Target-aktiviteter och upplevelsehändelser. | Ej tillämpligt | 31 augusti 2023 |
| **Rapporteringsaktivitetshanteraren** | Ger administratörer detaljerad insyn i hur de rapporterar förbrukning för varje anslutning, vilket gör det möjligt för administratörer att enkelt diagnostisera och sedan åtgärda kapacitetsproblem under högbelastade rapporteringstider. | Ej tillämpligt | 6 september 2023 |
| **PowerBI- och Tableau-åtkomst till datavyer i Customer Journey Analytics** | Adobe Customer Journey Analytics SQL Connector ger SQL-åtkomst till datavyer som du har definierat i Customer Journey Analytics. Datatekniker och analytiker som är mer bekanta med Power BI, Tableau eller andra verktyg för affärsintelligens och visualisering kan nu skapa rapporter och kontrollpaneler baserat på samma datavyer som Customer Journey Analytics-användare använder för sina Analysis Workspace-projekt. [Läs mer](/help/data-views/sql-connector.md) | Ej tillämpligt | 13 september 2023 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| **Förändringar i hur Customer Journey Analytics bearbetar data** | 22 juni 2023 | Vi har nyligen ändrat hur vi behandlar data i Customer Journey Analytics.<ul><li>Alla händelsedata med en tidsstämpel som är mindre än 24 timmar gamla direktuppspelas.</li><li>Alla händelsedata med en tidsstämpel som är mer än 24 timmar gamla (även om de finns i samma batch som nyare data) betraktas som förifyllda och kapslade med lägre prioritet.</li></ul> |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life)

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API-, Customer Journey Analytics API- och LiveStream-kunder som använder inloggningsuppgifter för Adobe I/O JWT måste migrera till inloggningsuppgifterna för Adobe I/O OAuth Server-till-Server med **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
