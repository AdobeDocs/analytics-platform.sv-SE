---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4de95c6c869e25a0301990669b7c8409ab025350
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 7%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (september 2023)

**Senaste uppdatering**: 13 september 2023

Versionsinformationen gäller den 13 september till 3 oktober 2023. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Stöd för A4T-klassificeringar i Analytics Source Connector** | Stöd för nya `correlationID` fält för Adobe Analytics | The `_experience.decisioning.propositions.scopeDetails.correlationID` -fältet är nu tillgängligt i Adobe Analytics källanslutningsschema. Det här fältet används som stöd för A4T-klassificeringar och kommer att fyllas i från och med september 2023. | | Ej tillämpligt | 12 september 2023 |
| **Uppdateringar av härledda fält** | Följande uppdateringar gjordes för funktionen för härledda fält:<ul><li>The [!UICONTROL Lookup] funktionen har bytt namn till [!UICONTROL Classify], med ytterligare alternativ för att läsa in CSV-data. **(Utgåvor 27 september 2023)**</li><li>Ytterligare funktioner är tillgängliga när du definierar ett härlett fält: [!UICONTROL Trim], [!UICONTROL Lowercase] och [!UICONTROL Lookup].</li><li>Härledda fältdefinitioner har nu även stöd för fält från [!UICONTROL Lookup] och [!UICONTROL Profile] datauppsättningar.</li></ul>[Läs mer](/help/data-views/derived-fields/derived-fields.md) | Ej tillämpligt | 13 september 2023 |
| **Nya funktioner i Adobe Product Analytics** | <ul><li>**Analysidentifiering**: Jämför händelser med förväntade värden som härleds från historiska trender. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**Trends Frequency of use view**: Mät användningen av funktionerna efter användningsfrekvens. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**Användarinställningar**: Konfigurera ett antal användarinställningar, t.ex. färgpaletter och sifferformat. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html)</li></ul> | Ej tillämpligt | 18 september 2023 |
| **Upplev Edge-enhetssökningar** | Aktivera automatisk datainsamling av enhetstyp via Experience Platform Edge-nätverket. Den här Experience Edge-tjänsten är till stor nytta för Customer Journey Analytics och andra Experience Platform-appar. (Dokumentationslänk följer) | Ej tillämpligt | 27 september 2023 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-AN 326888


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
