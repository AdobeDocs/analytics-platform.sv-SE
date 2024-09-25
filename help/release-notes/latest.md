---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b7e8c535d178ef406e1563408cee83c638d6858b
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 8%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (september 2024)

**Senast uppdaterad**: 11 september 2024

Versionsinformationen gäller den 11 september till början av oktober. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Ytterligare information i kolumnen Används i i den beräknade metriska hanteraren och filterhanteraren** | Kolumnen &quot;Används i&quot; i den beräknade metriska hanteraren och filterhanteraren innehåller följande nya rapporteringsområden:<ul><li>**Report Builder**: Visar antalet beräknade mått eller filter som används i Report Builder.</li><li>**Ad hoc-komponenter**: Visar antalet ad hoc-beräknade mått eller ad hoc-filter som används i projekt. Dessa ad hoc-beräknade mått och filter (kallas annars&quot;snabbberäknade mätvärden&quot; och&quot;snabbfilter&quot;) kan bara användas i det projekt där de skapades, så de rapporteras separat från rapportområdet&quot;Projekt&quot; i kolumnen&quot;Används i&quot;.</li></ul>Mer information finns i [Beräknat mätvärde-hanterare](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) och [Filterhanterare](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters). |  | 11 sept 2024 |
| **Larm** | Med varningar i Customer Journey Analytics kan du meddelas baserat på ändrade procentsatser eller specifika datapunkter.<p>Beroende på ditt Customer Journey Analytics-paket kan du även använda varningar som utlöses baserat på avvikelsetrösklar. Dessa varningar (kallas även&quot;Intelligent Alerts&quot;) ger detaljerade kontroller som kan integreras med Anomaly Detection och aktiveras när du behöver dem som mest.</p><p>Processen med att använda varningar i Customer Journey Analytics är nästan identisk med att använda varningar i Adobe Analytics. En viktig skillnad är att det inte finns timaviseringar i Customer Journey Analytics. Den här skillnaden beror på att datainmatningen för de olika typer av händelsedata som kan importeras är slutförd först efter en fördröjning, vanligtvis från 3 till 9 timmar efter datahändelsetiden.</p><p>Mer information om skillnaderna när du använder aviseringar i Customer Journey Analytics från Adobe Analytics finns i [Jämförelse av aviseringsfunktioner](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).</p><p>Mer information om aviseringar finns i [Översikt över aviseringar](/help/components/c-intelligent-alerts/intelligent-alerts.md) |  | 13 september 2024 |
| **Uppdateringar till Adobe Analytics källanslutning** | Datamängdens aktivitetssida visar ingen information om grupper eftersom Analytics Source Connector helt hanteras av Adobe. Du kan övervaka att data flödar genom att titta på mätvärdena runt inmatade poster. Mer information finns i guiden [Skapa en källanslutning för Analytics-data](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). |  | Ute nu |
| **Guidad analys: Bädda in i Workspace** | Kombinera flera guidade analyser till en enda vy i Analysis Workspace. (Dokumentationslänk följer) | 2 oktober 2024 | 31 oktober 2024 |

## Korrigeringar i Customer Journey Analytics

AN-352461; AN-355446: AN-355665

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation om tilläggsprogrammet för direktuppspelad mediasamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
