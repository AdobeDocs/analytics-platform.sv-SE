---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8552e2e784cefc842f5105c41dcffc14192d5ceb
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 5%

---

# Versionsinformation för Customer Journey Analytics (CJA) (september 2022)

**Senaste uppdatering**: 14 september 2022

## Relaterade resurser

* [Tidigare CJA-versionsinformation för 2022](/help/release-notes/2022.md)

* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)

* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## Viktiga funktioner

| Funktion | Beskrivning | [Måldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Regionövergripande stöd för Analytics Source Connector** | Du kan nu importera rapportsviter från valfri region (USA, Storbritannien eller Singapore). Dessa rapportsviter måste dock mappas till samma organisation som den Experience Platform sandbox-instans i vilken källanslutningen skapas. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) | 24 augusti 2022 |
| **Första sessionsrapportering** | Upptäck om en viss session var användarens första session någonsin. [Läs mer](/help/data-views/data-views-usecases.md) | 24 augusti 2022 |
| **Panelen Experimentation för CJA** | Med den nya Workspace-panelen kan CJA-användare utvärdera hur stort A/B-experimentet blir och hur säkert det är från alla källor - online, offline, från Adobe-lösningar, Adobe Journey Optimizer och till och med BYO-data (ta dina egna). [Läs mer](/help/analysis-workspace/c-panels/experimentation.md) | [Begränsad release](/help/release-notes/releases.md) från och med 14 september 2022 |
| **Visualisering av kombinationsdiagram i arbetsytan** | Med kombinationsdiagram kan du jämföra mätvärden enklare och intuitivare i Workspace. [Läs mer](/help/analysis-workspace/visualizations/combo-charts.md) | 14 september 2022 |
| **CJA-stöd för etiketter och policyer för datastyrning** | Automatiserar integreringen mellan CJA och Adobe Experience Platform integritetsetiketter och integritetspolicyer. Dataetiketter som skapas på datauppsättningar som används av plattformen visas i CJA-datavyer för att stoppa eller varna användare som skapar mätvärden och/eller dimensioner från känsliga fält. Dessutom, när data exporteras från CJA (via Workspace eller Report Builder-rapportering, export, API osv.) Ytterligare varningar eller etiketter läggs till för att meddela användarna att en rapport innehåller känslig information som behöver behandlas på ett specifikt sätt. [Läs mer](/help/data-views/data-governance.md) | 14 september 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar

AN-298412

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Förbättrad mappning av IP-till-geopositionering** | 9 september 2022 | Adobe för IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för mappning från IP till geopositionering. Adobe Analytics kommer att anta den nya datauppsättningen den **5 oktober 2022**. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p> CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
