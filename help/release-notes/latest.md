---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9f60d83673591aebeffeb6442bf9f8b897ab2f20
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 3%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (januari 2024)

**Senaste uppdatering**: 30 januari 2024

Versionsanteckningarna gäller frisläppningsperioden 8 januari 2024 till 13 februari 2024. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Information om överhoppade poster** | Du kan hämta information om varför poster hoppas över när du konfigurerar en anslutning. Se [Anslutningsinformation](../connections/manage-connections.md#connection-details) för mer information. | 5 februari 2024 | 5 februari 2024 |
| **Tidsserieprognoser** | [Prognos](../analysis-workspace/c-forecast/forecasting.md) är en ny Analysis Workspace-funktion som prognostiserar ett standardmått eller beräknade mätvärden med valfri tidshalaritet (timma, dag, vecka, månad och år) för frihandstabeller och linjediagram. | 31 januari 2024 | 21 februari 2024 |
| **Uppdateringar av visualisering av sammanfattning av nyckelmått** | När du använder visualisering av nyckelmätningssammanfattning kan datumintervallet för jämförelsen nu uppdateras automatiskt, beroende på om det alternativ för jämförelsedatumintervall du väljer är relativt till det primära datumintervallet eller fasta. [Läs mer](/help/analysis-workspace/visualizations/key-metric.md). | Ej tillämpligt | 17 januari 2024 |
| **Adobe Product Analytics - Analys av kvarhållningsfrekvenser** | Kvarhållningsfrekvenser är en ny guidad analys som gör att du kan mäta användarnas pågående returvanor. [Läs mer](../guided-analysis/types/retention-rates.md) | Ej tillämpligt | 8 januari 2024 |
| **Adobe Product Analytics - Trendlinjeövertäckning** | Trendlinjer är en ny övertäckningsinställning som är tillgänglig i [Användningstrender](/help/guided-analysis/types/usage.md) visa och hjälpa till att skildra ett tydligare datamönster. | Ej tillämpligt | 17 januari 2024 |
| **Adobe Product Analytics - Förbättringar av frågerubriker** | I en guidad analys innehåller den vänstra frågerastern nu vytypen och Räknas som inställningar, som tidigare fanns i Visualiseringsinställningarna. | Ej tillämpligt | 31 januari 2024 |
| **Adobe Product Analytics - analys av användarströmmar** | Användarströmmar är en ny guidad analys som gör att du kan utforska enskilda användarhändelseströmmar som hjälper dig att hitta upplevelsemönster och berätta bättre användarberättelser. | Ej tillämpligt | 7 februari 2024 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-310972; AN-332774; AN-332793; AN-332796; AN-333157; AN-334067; AN-334134; AN 334968; AN-335315; AN-335518; AN-335533; AN-335736;

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
