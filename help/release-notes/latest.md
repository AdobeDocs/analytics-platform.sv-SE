---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 806bcaa72479c3e871e12fd1c4802bac97eda439
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 3%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (januari 2025)

**Senast uppdaterad**: 22 januari 2025

Versionsanteckningarna gäller den 23 oktober 2024-30 januari 2025. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Användningsgränssnittet för uppdaterade anslutningar** | Fliken **[!UICONTROL Usage]** i Connection innehåller nu förbättrade visualiseringar för dessa typer av rapportbara rader: core, ingested och history data. Du kan också visa och dela upp användningsdata efter anslutning, datauppsättning, sandlåda eller tagg. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage) |  | 15 januari 2025 |
| **API för migrering av Adobe Analytics-projekt och eventuella inkluderade komponenter till Customer Journey Analytics** | Nu finns ett API för migrering av dina Adobe Analytics-projekt och inkluderade komponenter till Customer Journey Analytics. Tidigare var projekt- och komponentmigrering bara tillgängligt via användargränssnittet. [Läs mer](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=CJA%20Migration%20APIs). Välj **CJA-migrerings-API:er** i listrutan. |  | 15 januari 2025 |
| **Använd egna mallar från Customer Journey Analytics på rapportsidan i Journey Optimizer** | Nu kan du anpassa det nya rapporteringsgränssnittet i Adobe Journey Optimizer genom att skapa eller redigera en mall i Customer Journey Analytics och sedan spara mallen som ska användas på rapportsidan i Journey Optimizer. Tidigare gick det inte att anpassa det nya rapporteringsgränssnittet i Adobe Journey Optimizer. <p>Mer information finns i&quot;Skapa en mall&quot; eller&quot;Redigera eller ta bort en mall&quot; i [Skapa och hantera mallar](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/create-templates).  |  | 15 januari 2025 |
| **Mallar i Analysis Workspace** | Mallar finns nu i Customer Journey Analytics.<ul><li>**Fördefinierade mallar**: Det finns ett stort urval av fördefinierade mallar. Du kan använda de här mallarna för att få snabba insikter i de vanligaste rapportscenarierna. Fördefinierade mallar kan användas som de är. De kan också användas som utgångspunkt för ett projekt, som sedan kan anpassas för att passa ett visst ändamål. [Läs mer](/help/analysis-workspace/templates/use-templates.md)</li><li>**Företagsmallar**: Administratörer kan skapa företagsmallar som uppfyller behoven för användningsfall som är specifika för deras organisation. Företagsmallar som administratörer skapar är tillgängliga för användare i organisationen. [Läs mer](/help/analysis-workspace/templates/create-templates.md)</li></ul> | Januari 15 | 30 januari 2025 |
| **Produktanvändning** | Se hur er organisation använder Customer Journey Analytics. Om du aktiverar den här funktionen skapas en datauppsättning i Adobe Experience Platform som samlar in data när någon i organisationen använder Analysis Workspace. En anslutning och en datavy skapas också automatiskt, vilket ger dig åtkomst till dimensioner som de vanligaste projekttyperna, de mest aktiva användarna och de vanligaste komponenterna som används i projekt. [Läs mer](/help/tools/product-usage/usage-overview.md) | 23 oktober 2024 | 22 januari 2025 |
| **Intelligenta bildtexter v2** | Intelligenta bildtexter stöds nu för följande visualiseringar: Flera rader, Stolpstreck, Vågrätt streck, Ring ut, Yta, Flöde och Utfall. Du kan välja att visa alla intelligenta bildtexter samtidigt i en utökad vy eller visa enskilda intelligenta bildtexter i en vy i taget. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) |  | 22 januari 2025 |
| **Lägg till guidade analyser i projekt från den guidade analysen** | Gör att du kan lägga till guidade analyser i Workspace-projekt från den guidade analysen. Du kan också lägga till guidade analyser direkt i Analysis Workspace. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview) |  | 22 januari 2025 |
| **Mediesamling: Adobe Source Connector-uppdateringar för nya Media Reporting XDM** | Analytics Source Connector mappar automatiskt strömmande mediedata i Adobe Analytics till samma fält som används av Web SDK. För närvarande mappas data till både gamla och nya platser, men endast den nya platsen kommer att användas i framtiden. (Dokumentationslänk följer) |  | 30 januari 2025 |

## Korrigeringar i Customer Journey Analytics

Varningar: AN-363263; AN-364880; AN-365029; AN-365960
Målgrupper: AN-362564; AN-363254;
Intag av data: AN-362359; AN-362751
Datavyer: AN-362089; AN-365213; AN-365770; AN-366171; AN-366681
Härledda fält: AN-359711; AN-362496
Exportplatser: AN-363999
Fullständig tabellexport: AN-363055
Report Builder: AN-362937
Workspace: AN-359012; AN-359145; AN-359914; AN-361455; AN-361934; AN-362469; AN-363460; AN-364714; AN-364918; AN-366277;


## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

## Relaterade resurser

* [Tidigare versionsinformation för Customer Journey Analytics 2024](/help/release-notes/2024.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics dokumentationsuppdateringar](/help/release-notes/doc-changes.md)
