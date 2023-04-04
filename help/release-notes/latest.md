---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d09094798d22f32d3467527e0c3e1817ff76b5a2
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 6%

---

# Versionsinformation för Customer Journey Analytics (CJA) (mars 2023)

**Senaste uppdatering**: 10 mars 2023

Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Viktiga funktioner och uppdateringar

| Funktion | Beskrivning | [Början av utrullning](/help/release-notes/releases.md) | [Allmän tillgänglighet](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Dataordlista i Analysis Workspace** | Med Data Dictionary kan både användare och administratörer hålla reda på och bättre förstå komponenterna (dimensioner, mått) i sin CJA-miljö. [Läs mer](/help/components/data-dictionary/data-dictionary-overview.md) | 8 mars 2023 | 29 mars 2023 |
| **Dataartiklar på mobilkontrollpaneler** | Med hjälp av dataartiklar kan du lägga till flera anpassningsbara detaljvyer till paneler i projekt i Mobile Scorecard. Använd databerättelser för att fördjupa dig i viktiga drivrutiner, relaterade mätvärden och olika steg längs kundresan. Du kan enkelt svepa igenom de här vyerna för att förstå hela artikeln bakom nyckelmätningarna. [Läs mer](/help/mobile-app/create-scorecard.md#create-data-story) | Ej tillämpligt | 8 mars 2023 |
| **Förfallodatum för schemalagda projekt** | Du kan ange maximalt förfallodatum för schemalagda projekt till upp till ett år, oavsett schemafrekvens. [Läs mer](/help/analysis-workspace/curate-share/t-schedule-report.md) | Ej tillämpligt | 8 mars 2023 |
| **Länkdelning för projekt (ingen inloggning krävs) - endast privat betaåtkomst** | Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till CJA. Du kan dela projektlänkar med personer utanför organisationen eller personer inom organisationen som inte har etablerats för CJA. [Läs mer](/help/analysis-workspace/curate-share/share-projects.md)<p>Om du vill gå med i den privata betaversionen kontaktar du Adobe Account Team. | 26 april 2023 | Juni 2023 |
| **Uppdateringar för paneldatumintervall** | I Workspace har vi lagt till följande förbättringar:<ul><li>Från och med februari-versionen baseras dimensionsobjekt och förhandsgranskningar av data på panelens datumintervall och inte på de senaste 90 dagarna. </li><li>Alla dimensionsobjekt i listan baseras på data inom panelens datumintervall. Om ett dimensionsobjekt har data utanför datumintervallet kan du visa ytterligare data efter datumintervallet längst ned i listan.</li><li>Dimensioner som inte har data kan visas i den vänstra listen. Klicka på Visa fler alternativ för att visa dimensionsobjekt med data utanför panelens datumintervall.</li><li>Förhandsgranskningar av data i segmentet och beräknade mätvärden baseras på panelens datumintervall såvida de inte öppnas av komponenthanterarna, som inte har någon associerad panel och fortfarande baseras på de senaste 90 dagarna.</li><li>Förhandsgranskning av data visar data eller komponenter baserat på panelens datumintervall.</li></ul> | Ej tillämpligt | 8 februari 2023 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-309729; AN-309975; AN-311779; AN-313095

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Tillgänglighet för Analytics Source Connector | 15 februari 2023 | Den 28 februari 2023 blev Analytics Source Connector tillgänglig i det nya datacentret för Adobe Experience Platform i Kanada. |

{style="table-layout:auto"}

## Relaterade resurser

* [Tidigare CJA-versionsinformation för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
