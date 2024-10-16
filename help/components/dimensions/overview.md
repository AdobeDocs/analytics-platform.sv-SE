---
title: Översikt över Dimensioner
description: Lär dig vilka dimensioner som är och hur de används i Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Översikt över Dimensioner

Dimensioner är en komponenttyp i Customer Journey Analytics som används för att analysera data. Du kan till exempel använda dimensioner när du skapar rapporter i [Analysis Workspace](/help/analysis-workspace/home.md) eller i [Report Builder](/help/report-builder/report-buider-overview.md).

Customer Journey Analytics är av obegränsad typ. Värden kan vara numeriska värden, text, objekt, listor eller blandningar av alla.

En grundläggande rapport i Customer Journey Analytics visar rader med dimensioner (vanligtvis strängvärden) mot en kolumn med mätvärden (vanliga numeriska värden).

Om du till exempel kombinerar siddimensionen med personmåttet får du en rankad rapport som visar dina populäraste sidor för personer:

| Sida | Folk |
| --- | ---: |
| Startsida | 800 |
| Produktsida | 500 |
| Inköpssida | 100 |

{style="table-layout:fixed"}

Varje dimension representerar en annan del eller del av din webbplats. Du kan kombinera en av dessa mått med en eller flera mätvärden för att skapa en önskad rapport.


## Skapa dimensioner

Administratörer i Customer Journey Analytics kan [skapa dimensioner i en datavy](/help/data-views/create-dataview.md#components).

## Standarddimensioner

När du skapar en datavy läggs följande tidsbaserade komponenter till som standard som dimensioner till datavyn:

- 15 minuter
- 30 minuter
- 5 minuter
- Dag
- Dag i månaden
- Veckodag
- Dag på året
- Timme
- Timme på dagen
- Minut
- Minut av timmen
- Månad
- Månad på året
- Kvartal
- Kvartal på året
- Andra
- Vecka på året
- År

## Lägg till dimensionsbeskrivningar

Administratörer i Customer Journey Analytics kan lägga till beskrivningar för dimensioner och andra komponenter antingen i datavyn eller direkt i Analysis Workspace. Mer information om hur du lägger till beskrivningar till dimensioner finns i [Lägg till komponentbeskrivningar](/help/components/add-component-descriptions.md).
