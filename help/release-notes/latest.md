---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 509eed292df7c778f30389267dc61f900d230024
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 3%

---

# Versionsinformation för Customer Journey Analytics (CJA) (juli 2022)

**Senaste uppdatering**: 4 augusti 2022

## Viktiga funktioner

| Funktion | Beskrivning | [Måldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Stöd för numeriska fält som söknycklar och sökvärden | Detta är användbart om du vill klassificera strängvärden med ett numeriskt fält, t.ex. en COGS eller marginal på en produkts SKU. Genom att tillåta mätvärden från sökningar kan ni få in dessa datapunkter i rapporteringen. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 20 juli 2022 |
| Media Concurrent Viewer-panel | Förstå var maximal samtidighet inträffade eller var bortfall inträffade. Få värdefulla insikter om innehållets och tittarnas engagemang och hjälp med felsökning eller planering av volym och skala. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | **9 augusti 2022** |
| Medieuppspelningstid spenderad panel | Media Playback Time Spent ger värdefull insikt i tittarnas engagemang och gör det möjligt för medieorganisationer att få djupare och mer detaljerade insikter med användarengagemang varje minut genom avancerad tidsanalys med delningsfunktioner. Du kan se hur mycket tid du har lagt på att visa medieströmmar vid en viss tidpunkt. Du kan dela uppspelningens längd med olika granulariteter, inklusive nya 5-, 15- och 30-minutersgranulariteter.  [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | **9 augusti 2022** |
| Sessionsrapportering för första kontra upprepade | Du kan nu identifiera om en viss session var användarens första session någonsin. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 17 augusti 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar

AN-288455; AN-288828; AN-289323

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Förbättrad mappning av IP-till-geopositionering** | 11 juli 2022 | Adobe för IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för mappning från IP till geopositionering. Adobe Analytics kommer att anta den nya datauppsättningen i **Oktober 2022**, tidsram. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p> CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
