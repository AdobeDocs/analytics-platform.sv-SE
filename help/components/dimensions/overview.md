---
title: Översikt över Dimensioner
description: Lär dig vilka dimensioner som är och hur de används i Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 1564c91616015311393a643fe7fcecd429cf3a36
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Översikt över Dimensioner

Dimensioner är en komponenttyp i Customer Journey Analytics som används för att analysera data. Du kan till exempel använda dimensioner när du skapar rapporter i [Analysis Workspace](/help/analysis-workspace/home.md) eller in [Report Builder](/help/report-builder/report-buider-overview.md).

Customer Journey Analytics är obegränsat. Värden kan vara numeriska, text, objekt, listor eller blandningar av alla.

En grundläggande rapport i Customer Journey Analytics visar rader med dimensioner (vanligtvis strängvärden) mot en kolumn med mätvärden (vanliga numeriska värden).

Om du t.ex. kombinerat siddimensionen med Visits-måttet får du en rankad rapport som visar dina mest besökta sidor:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

Varje dimension representerar en annan del eller del av din webbplats. Du kan kombinera en av dessa mått med en eller flera mätvärden för att skapa en önskad rapport.

## Skapa dimensioner

Customer Journey Analytics-administratörer kan [skapa dimensioner i en datavy](/help/data-views/create-dataview.md#components).

## Lägg till dimensionsbeskrivningar

Administratörer i Customer Journey Analytics kan lägga till beskrivningar för dimensioner och andra komponenter antingen i datavyn eller direkt i Analysis Workspace. Mer information om hur du lägger till beskrivningar till dimensioner finns i [Lägga till komponentbeskrivningar](/help/components/add-component-descriptions.md).
