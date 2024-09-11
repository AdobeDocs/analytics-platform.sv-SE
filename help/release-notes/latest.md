---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d0315fe645e62a2c67148cb0fc3fbd4c1b780187
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (september 2024)

**Senast uppdaterad**: 11 september 2024

Versionsinformationen gäller den 11 september till början av oktober. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Användningsanalys** | Se hur er organisation använder Customer Journey Analytics. Om du aktiverar den här funktionen skapas en datauppsättning i Adobe Experience Platform som samlar in data när någon i organisationen använder Analysis Workspace. En anslutning och en datavy skapas också automatiskt, vilket ger dig åtkomst till dimensioner som de vanligaste projekttyperna, de mest aktiva användarna och de vanligaste komponenterna som används i projekt. (Dokumentationslänk följer) |  | 18 september 2024 |
| **Ytterligare information i kolumnen Används i i den beräknade metriska hanteraren och filterhanteraren** | Kolumnen &quot;Används i&quot; i den beräknade metriska hanteraren och filterhanteraren innehåller följande nya rapporteringsområden:<ul><li>**Report Builder**: Visar antalet beräknade mått eller filter som används i Report Builder.</li><li>**Ad hoc-komponenter**: Visar antalet ad hoc-beräknade mått eller ad hoc-filter som används i projekt. Dessa ad hoc-beräknade mått och filter (kallas annars&quot;snabbberäknade mätvärden&quot; och&quot;snabbfilter&quot;) kan bara användas i det projekt där de skapades, så de rapporteras separat från rapportområdet&quot;Projekt&quot; i kolumnen&quot;Används i&quot;.</li></ul>(Dokumentationslänk följer) |  | 11 sept 2024 |
| **Guidad analys: Bädda in i Workspace** | Kombinera flera guidade analyser till en enda vy i Analysis Workspace. (Dokumentationslänk följer) | 22 september 2024 | 2 oktober 2024 |
| **Intelligenta aviseringar** | Med intelligenta aviseringar i Customer Journey Analytics kan ni meddelas omedelbart när onormala händelser inträffar i era data.<p>Du kan ange att aviseringar ska utlösas baserat på avvikelsetrösklar, ändrade procentsatser eller specifika datapunkter. Varningar ger detaljerade kontroller som kan integreras med avvikelseidentifiering och aktiveras när du behöver dem som mest.</p><p>Processen att använda intelligenta aviseringar i Customer Journey Analytics är nästan identisk med att använda intelligenta aviseringar i Adobe Analytics. En viktig skillnad är att det inte finns timaviseringar i Customer Journey Analytics. Den här skillnaden beror på att datainmatningen för de olika typer av händelsedata som kan importeras är slutförd först efter en fördröjning, vanligtvis från 3 till 9 timmar efter datahändelsetiden. (Dokumentationslänk följer)</p><p><!--[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)--></p> |  | 11 september 2024 |
| **Uppdateringar till Adobe Analytics källanslutning** | Datamängdens aktivitetssida visar ingen information om grupper eftersom Analytics Source Connector hanteras helt av Adobe. Ni kan övervaka att data flödar genom att titta på mätvärdena runt inkapslade poster. Mer information finns i guiden [Skapa en källanslutning för Analytics-data](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). |  | Ute nu |


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
