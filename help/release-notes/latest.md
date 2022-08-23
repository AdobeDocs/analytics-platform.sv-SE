---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e7ff0bfae0f7d041a8131cecbf362cf71aca9740
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 4%

---

# Versionsinformation för Customer Journey Analytics (CJA) (augusti 2022)

**Senaste uppdatering**: 23 augusti 2022

## Viktiga funktioner

| Funktion | Beskrivning | [Måldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Media Concurrent Viewer-panel** | Förstå var maximal samtidighet inträffade eller var bortfall inträffade. Få värdefulla insikter om innehållets och tittarnas engagemang och hjälp med felsökning eller planering av volym och skala. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 9 augusti 2022 |
| **Medieuppspelningstid spenderad panel** | Media Playback Time Spent ger värdefull insikt i tittarnas engagemang och gör det möjligt för medieorganisationer att få djupare och mer detaljerade insikter med användarengagemang varje minut genom avancerad tidsanalys med delningsfunktioner. Du kan se hur mycket tid du har lagt på att visa medieströmmar vid en viss tidpunkt. Du kan dela uppspelningens längd med olika granulariteter, inklusive nya 5-, 15- och 30-minutersgranulariteter.  [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 9 augusti 2022 |
| **Målgruppspublicering i kundprofil i realtid** | Gör att ni kan publicera målgrupper som identifierats i CJA till Adobe Experience Platform/Kundprofil i realtid för kundanpassning och personalisering. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=en) | 17 augusti 2022 |
| **CJA-stöd för etiketter och policyer för datastyrning** | Automatiserar integreringen mellan CJA och Adobe Experience Platform integritetsetiketter och integritetspolicyer. Dataetiketter som skapas på datauppsättningar som används av plattformen visas i CJA-datavyer för att stoppa eller varna användare som skapar mätvärden och/eller dimensioner från känsliga fält. Dessutom, när data exporteras från CJA (via Workspace eller Report Builder-rapportering, export, API osv.) Ytterligare varningar eller etiketter läggs till för att meddela användarna att en rapport innehåller känslig information som behöver behandlas på ett specifikt sätt. [Läs mer](/help/data-views/data-governance.md) | 17 augusti 2022 |
| **Stöd för datumfält i CJA** | Tillåter CJA att rapportera datum- och datumfält. [Läs mer](/help/data-views/data-views-usecases.md#date) | 17 augusti 2022 |
| **Regionövergripande stöd för Analytics Source Connector** | Du kan nu importera rapportsviter från valfri region (USA, Storbritannien eller Singapore). Dessa rapportsviter måste dock mappas till samma organisation som den Experience Platform sandbox-instans i vilken källanslutningen skapas. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) | 24 augusti 2022 |
| **Sessionsrapportering för första kontra upprepade** | Du kan nu identifiera om en viss session var användarens första session någonsin. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 24 augusti 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar

AN-297141

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Förbättrad mappning av IP-till-geopositionering** | 11 juli 2022 | Adobe för IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för mappning från IP till geopositionering. Adobe Analytics kommer att anta den nya datauppsättningen i **Oktober 2022** tidsram. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p> CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
