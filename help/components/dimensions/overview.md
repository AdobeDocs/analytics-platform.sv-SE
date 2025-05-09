---
title: Översikt över dimensioner
description: Lär dig vilka dimensioner som är och hur de används i Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 65b4339b4a1b27c41cfe442482a54661989d704b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 1%

---

# Översikt över dimensioner

Dimensioner är en komponenttyp i Customer Journey Analytics som används för att analysera data. Du kan till exempel använda dimensioner när du skapar rapporter i [Analysis Workspace](/help/analysis-workspace/home.md) eller i [Report Builder](/help/report-builder/rb-overview.md).

Customer Journey Analytics-dimensioner är av obegränsad typ. Värden kan vara numeriska värden, text, objekt, listor eller blandningar av alla.

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

Customer Journey Analytics-administratörer kan [skapa dimensioner i en datavy](/help/data-views/create-dataview.md#components).

## Standarddimensioner

När du skapar en datavy läggs följande komponenter till som standard som dimensioner i datavyn:

{{standard-dimensions}}


## Lägg till dimensionsbeskrivningar

Customer Journey Analytics-administratörer kan lägga till beskrivningar för dimensioner och andra komponenter antingen i datavyn eller direkt i Analysis Workspace. Mer information om hur du lägger till beskrivningar till dimensioner finns i [Lägg till komponentbeskrivningar](/help/components/add-component-descriptions.md).
