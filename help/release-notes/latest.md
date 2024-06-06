---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c3fbf86e06e47583165a661683bc7490ecd1b17f
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (maj 2024)

**Senaste uppdatering**: 6 juni 2024

Versionsanteckningarna gäller releasetiden 15 maj 2024 till juni 2024. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AI Assistant för Customer Journey Analytics** | Gör att du kan ställa naturspråkliga frågor i användargränssnittet för Customer Journey Analytics och få svar baserat på dokumentationen för Customer Journey Analytics. [Läs mer](/help/ai-assistant.md) | | 6 juni 2024 |
| **BI-tillägg** | BI-tillägget ger SQL-åtkomst till datavyer som du har definierat i Customer Journey Analytics. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 15 maj 2024 |
| **Publiken publiceras i ett nytt&quot;Publiker&quot;-avsnitt i Experience Platform** | Publikationer som publiceras från Customer Journey Analytics är nu tillgängliga i det nya avsnittet&quot;Publiker&quot; i Adobe Experience Platform.<p>Tidigare fanns målgrupper som publicerades från Customer Journey Analytics tillgängliga i Experience Platform under segmentavsnittet.</p><p>Den här förbättringen ger följande fördelar:</p><ul><li>Publiken har inte längre en timmes fördröjning innan de visas i Experience Platform; de är tillgängliga sekunder efter att de har publicerats.</li><li>Publiker kan sorteras i Experience Platform med hjälp av kolumnen &quot;Ursprung&quot;, som visar det program som målgruppen ursprungligen publicerades från.</li><li>Med filtrerings- och sorteringsalternativen i Experience Platform kan du snabbare hitta rätt målgrupper.</li></ul> <p>(Länk till uppdaterad dokumentation följer)</p> |  | Från maj till början av juni 2024 |
| **Direktuppspelningsmedia: Skicka webbdata till Adobe Experience Platform Edge Network med Web SDK** | Nu kan du använda Adobe Experience Platform Web SDK för att skicka Streaming Media-webbdata till Adobe Experience Platform Edge Network, vilket gör att du kan skapa mer personaliserade kampanjer och leverera mer personaliserat innehåll, vilket resulterar i mer spårningsdata att rapportera om.<p>Den här förbättringen erbjuder en enhetlig insamlingsmetod för webblösningar i alla plattformslösningar, till exempel Customer Journey Analytics, RT-CDP, AJO och händelsevidarebefordran. Tidigare var det enda sättet att skicka Streaming Media-webbdata till Edge Network att använda Media Edge API. <p>[Läs mer](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | 29 maj 2024 |
| **Härledda fält - matematisk funktion** | Gör att du kan göra enkla matematiska operatorer i datavyer för att besvara frågor om dina användare. Du kan t.ex. kombinera intäkter från produkt, garanti och frakt. <p>(Länk till uppdaterad dokumentation följer)</p> | | 5 juni 2024 |
| **Dela konton och platser som används för export och import** | Användarna kan nu göra de konton och platser de skapar tillgängliga för alla användare i organisationen. Endast konto- och platsägare och systemadministratörer kan redigera och ta bort konton och platser.<p>Tidigare kunde konton och platser bara användas av den användare som skapade dem.</p><p>De här inställningarna är tillgängliga när användare konfigurerar molnexportkonton och konfigurerar molnexportplatser.</p> <p>(Länk till uppdaterad dokumentation följer)</p> | 12 juni 2024 | 30 juni 2024 |
| **Ny dokumentation för uppgradering från Adobe Analytics till Customer Journey Analytics** | För organisationer som uppgraderar från Adobe Analytics till Customer Journey Analytics finns det flera uppgraderingsalternativ och många överväganden att tänka på baserat på organisationens nuvarande Adobe Analytics-implementering och långsiktiga mål. Nu finns det nya dokumentationsresurser som hjälper dig att förstå:<ul><li>De olika uppgraderingssökvägarna som finns</li><li>Vilka uppgraderingsalternativ som finns tillgängliga baserat på en organisations aktuella implementering av Adobe Analytics</li><li>Fördelar och nackdelar med varje uppgraderingsväg</li><li>Stegvisa anvisningar för varje uppgraderingsväg</li><li>Att tänka på vid hantering av historiska data</li></ul>[Kom igång med uppgraderingen till Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Ute nu |
| **Ny dokumentation om [Användningsexempel vid dataexport](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview)** | I det nya avsnittet beskrivs hur dataexport kan användas till exempel<ul><li>Säkerhetskopiering av data</li><li>Dataverifiering</li><li>Data Lake, Data Warehouse eller BI Tools</li><li>Beredskap för AI/ML</li></ul> och implementera dem med Experience Platform och Customer Journey Analytics. | | Ute nu |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN-4 346287; AN-346624; AN-347919

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
