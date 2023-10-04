---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 84bcf59f27a942d28e71f41966c5de9e8f8bdab0
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 4%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (oktober 2023)

**Senaste uppdatering**: 4 oktober 2023

Versionsinformationen gäller den 4 oktober till 24 oktober 2023. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Exportera fullständiga tabeller till molnet** | Med Customer Journey Analytics Full Table Export kan du exportera miljontals Workspace-rader till molnmål. Vid export av fullständiga tabeller kan du leverera datatabeller som utformats i Workspace en gång eller enligt schema, med stöd för upp till fem uppdelningar, fem mätvärden, filter och beräknade mätvärden, allt i en sammansatt tabell. Det är utvecklingen av rapporter om Data Warehouse i Adobe Analytics, med många nya, ofta efterfrågade funktioner som inte är tillgängliga i Data Warehouse idag. Exportalternativen för molnet omfattar:<ul><li>Adobe Experience Platform Data Landing Zone</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>Mer information finns i [Exportera Customer Journey Analytics-rapporter till molnet](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html). | 4 oktober 2023 | 19 oktober 2023 |
| **Nya kolumner är tillgängliga när komponenter hanteras** | Följande nya kolumner är nu tillgängliga i [Beräknat måttansvarig](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html) och [Filterhantering](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html) vid hantering av komponenter:<ul><li>Används i</li><li>Senast använd</li></ul>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras. Du kan använda ordlistan tillsammans med den här informationen för att hålla reda på och förstå hur komponenter används i organisationen bättre. | 23 september 2023 | 4 oktober 2023 |
| **Migrera Adobe Analytics-projekt och alla komponenter som ingår till Customer Journey Analytics** | Nu kan du migrera dina Adobe Analytics-projekt till Customer Journey Analytics. Den här processen förenklar övergången från Adobe Analytics till Customer Journey Analytics. När du migrerar projekt till Customer Journey Analytics mappas resurserna från en Adobe Analytics-rapportsvit till en datavy i Customer Journey Analytics. **Du migrerar projekt till Customer Journey Analytics från Adobe Analytics gränssnitt.** [Läs mer](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html) | 11 oktober 2023 | 25 oktober 2023 |
| **Adobe Product Analytics: Visa/dölj serie** | Klicka på teckenförklaringen eller tabellraderna för att styra hur serierna ska visas i dina visualiseringar.  [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=en) | Ej tillämpligt | 4 oktober 2023 |
| **Anteckningar i Adobe Product Analytics** | Guidad analys har nu stöd för att visa anteckningar som skapats i Customer Journey Analytics. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=en) | Ej tillämpligt | 4 oktober 2023 |
| **Rapporteringsaktivitetshanteraren** | Med Rapporteringsaktivitetshanteraren kan du se rapporteringskapaciteten för varje anslutning i organisationen. Det ger administratörer detaljerad insyn i rapporteringen av förbrukning för att enkelt kunna diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå. Viktiga funktioner i Rapporteringsaktivitetshanteraren är bland annat:<ul><li>Avbryt aktuella rapportbegäranden (inklusive begäranden från guidade analyser och fullständig registerexport)</li><li>Begränsa efterföljande begäranden för en angiven tidsperiod</li></ul>Förutom att avbryta aktuella begäranden kan administratörer nu begränsa begäranden för en definierad tidsperiod. Administratörer kan begränsa begäranden efter begäran, projekt eller användare.  Läs mer (kommer snart) | 17 oktober 2023 | 23 oktober 2023 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-325940; AN-326468; AN-328301; AN-328640; AN-329370

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | Ej tillämpligt | Ej tillämpligt |

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
