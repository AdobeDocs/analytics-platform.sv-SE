---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 11171eb6e079adbf41e0abc798a54a5749492eac
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Versionsinformation för Customer Journey Analytics (CJA) (juli 2022)

**Senaste uppdatering**: 19 juli 2022

>[!NOTE]
>
>Den här sidan innehåller information om förhandsversioner och kan komma att ändras.

## Viktiga funktioner

| Funktion | Beskrivning | [Måldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Stöd för numeriska fält som söknycklar och sökvärden | Detta är användbart om du vill klassificera strängvärden med ett numeriskt fält, t.ex. en COGS eller marginal på en produkts SKU. Genom att tillåta mätvärden från sökningar kan ni få in dessa datapunkter i rapporteringen. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 20 juli 2022 |
| Sessionsrapportering för första kontra upprepade | Du kan nu identifiera om en viss session var användarens första session någonsin. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 17 augusti 2022 |

## Korrigeringar

AN-288455; AN-288828; AN-289323

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Tillagd eller uppdaterad | Beskrivning |
| --- | --- | --- |
| Förbättrad mappning av IP-till-geopositionering | 11 juli 2022 | Adobe för IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för mappning från IP till geopositionering. Adobe Analytics kommer att anta den nya datauppsättningen i oktober 2022, som en tidsram. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p> CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |

>[!MORELIKETHIS]
>[Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
