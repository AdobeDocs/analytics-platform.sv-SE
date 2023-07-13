---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9e6231e4dc9770fbb7c859b397ea8c57e7dff478
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 4%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (juli 2023)

**Senaste uppdatering**: 13 juli 2023

Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics är ett nytt sätt att interagera med data och insikter över flera kanaler i Customer Journey Analytics. Dessa nya funktioner gör det möjligt för produktteamen att självbetjäna data och insikter om sina produktupplevelser via guidade analysarbetsflöden &#x200B;. Team kan:<ul><li>Förstå mönster i användarengagemanget över tid &#x200B;</li><li>Spåra tillväxten och lojaliteten hos &#x200B;</li><li>Identifiera friktionsområden i produkten</li><li>Mät effekten av &#x200B; och första användningen av nya funktioner</li><li>Identifiera meningsfulla användarsegment för att engagera och vårda användare under hela deras livslånga resa med &#x200B;</li><li>Anslut till Analysis Workspace för djupare analyser och samarbete med analytiker</li></ul>Adobe Product Analytics är ett betalt tillägg till Customer Journey Analytics. Om din organisation vill bli etablerad för att använda den här funktionen kontaktar du kontoteamet på Adobe. [Läs mer](/help/guided-analysis/overview.md) | Ej tillämpligt | 17 juli 2023 |
| **Härledda fält** | Detta representerar den första versionen av härledda fält. Med ett härlett fält kan du definiera (ofta komplexa) dataändringar direkt, via en anpassningsbar regelbyggare. Du kan definiera det härledda fältet ytterligare som en komponent (mått eller dimension) i datavyer och sedan använda det härledda fältet som en komponent i Workspace.<p>Den här versionen har stöd för en marknadsföringskanalmall och följande funktioner:</p><ul><li>Sammanfoga</li><li>Skiftläge</li><li>Sök och ersätt</li><li>Sök</li><li>URL-parsning</li></ul> <p>[Läs mer](/help/data-views/derived-fields/derived-fields.md)</p> | 10 maj 2023 | 2 augusti 2023 |
| **Utökat sökningsstöd för profil- och sökdata** | Ger möjlighet att lägga till datauppsättningar som uppslag till fält i datauppsättningar för profiler eller uppslag. Tidigare stöddes endast händelsedatamängder. [Läs mer](/help/connections/create-connection.md) | 21 juni 2023 | 12 juli 2023 |
| **Förbättringar i Report Builder** | <ul><li>Filtrera från cell för flera datablock. Du kan ändra filtren för flera datablock från en cell. Använd en fördefinierad cell, tilldela den till flera datablock och uppdatera data baserat på de filter som definieras i cellen. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>Visa och dölj rad- och kolumnrubriker. Du kan visa eller dölja tabellrubriker för datablock, eller rad- och kolumnrubriker för att formatera om tabellen och justera datablock i en rapport. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | Ej tillämpligt | 19 juli 2023 |
| **Upplev Edge-geosökningar** | Adobe Experience Edge lägger till en geosökningstjänst som ger enhetliga geografiska data till alla Experience Edge-användare (Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Media Analytics, Adobe Experience Platform osv.). | Ej tillämpligt | 26 juli 2023 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444; AN-323116

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| **Förändringar i hur Customer Journey Analytics bearbetar data** | 22 juni 2023 | Vi ändrade nyligen hur vi behandlar data i Customer Journey Analytics.<ul><li>Alla händelsedata med en tidsstämpel som är mindre än 24 timmar gamla direktuppspelas.</li><li>Alla händelsedata med en tidsstämpel som är mer än 24 timmar gamla (även om de finns i samma batch som nyare data) betraktas som förifyllda och kapslade med lägre prioritet.</li></ul> |

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
