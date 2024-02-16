---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 22b87a6f64c296e3eb05ec3b7076bf6dfa2935f9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (februari 2024)

**Senaste uppdatering**: 14 februari 2024

Versionsanteckningarna gäller frisläppningsperioden från 14 februari 2024 till 11 mars 2024. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Tidsserieprognoser** | [Prognos](../analysis-workspace/c-forecast/forecasting.md) är en ny Analysis Workspace-funktion som används för att förutsäga ett standardmått eller beräknat mått med en tidshalaritet som stöds (timvis, daglig, veckovis, månadsvis och årsvis) för frihandstabeller och linjediagram. | 31 januari 2024 | 21 februari 2024 |
| **Media Analytics-rapportering - genomsnittlig miniatyrpublik (AMA)** | Panelen för genomsnittlig minutpublik är nu tillgänglig i CJA. Media Analytics-kunder kan använda panelen för normal målgrupp för att bättre förstå den genomsnittliga användningen av deras innehåll. Den genomsnittliga minuten-målgruppen möjliggör jämförelser av programmering oavsett längd eller genre. Dessutom kan kunderna jämföra eller lägga till den digitala genomsnittliga minuten-publiken med den linjära minuten-mätningen för tv. Panelen ger större flexibilitet för att mäta den genomsnittliga publiken för anpassade tidsperioder samt när tidsklassificeringen har uppdaterats efter detta. |  | Februari 2024 |
| **Radräkningsmått för sök- och profildata** | Radräkningsmått för datauppsättningar, konfigurerade som en del av en anslutning, inkluderar nu poster som lagts till, hoppats över eller tagits bort från profil- och uppslagsdatauppsättningar. |  | 14 februari 2024 |
| **Upplev Edge Bot Detection** | [Punktavkänning](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) gör att du kan identifiera händelser som genererats av Web SDK, Mobile SDK och Server API som om de genererats av kända spindlar och bottar. | | 21 februari 2024 |
| **Användningsstatistik** | Gränssnittet för användningsstatistik visar användningen av inkapslade och rapporteringsbara rader i alla anslutningar. Med det här gränssnittet kan du avgöra om din användning i Customer Journey Analytics överensstämmer med det som avtalats. | 20 februari 2024 | Tidig mars 2024 |
| **Adobe Product Analytics: Dela med vem som helst** | Här kan du dela en skrivskyddad länk till Adobe Product Analytics-projekt med personer som inte har tillgång till Product Analytics. |  | 21 februari 2024 |
| **Adobe Product Analytics: Använd beräknade värden** | Nu kan du få tillgång till beräknade värden som skapats i Analysis Workspace eller verktyget Beräknade mätvärden i vyn Trends: Usage, vilket gör att du kan trender och jämföra mätvärden över tid. |  | 16 februari 2024 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-333172; AN-336887; AN-337402; AN-337593; AN-338482; AN-338684; AN-33983; AN-3 340200

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Tillägg för Adobe API-objektmedlemmar | 17 januari 2024 | Adobe kan lägga till valfria fråge- och svarsmedlemmar (namn/värde-par) i befintliga API-objekt utan föregående meddelande eller ändringar i versionshanteringen. Sådana tillägg bör vara fasta ändringar för implementeringen. Adobe rekommenderar att du läser API-dokumentationen för alla tredjepartsverktyg som du integrerar med våra API:er så att sådana tillägg ignoreras vid bearbetningen om de inte tolkas. Adobe tar inte bort parametrar eller lägger till obligatoriska parametrar utan att först skicka standardmeddelanden via versionsinformation. |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
