---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5a4d9ad92de69c91d4cf8f4f400ede37470c3baa
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (april 2025)

**Senast uppdaterad**: 16 april 2025

Versionsanteckningarna gäller den 27 mars-15 maj 2025. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Uppdaterar radobjektet Inget värde på numeriska dimensioner** | För numeriska mått kan du med den här uppdateringen<ul><li>Använd dimensionsobjektet Inget värde i ett segment.</li><li>Utför en uppdelning i en rapport för radobjektet Inget värde.</li></ul> [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | 27 mars 2025 |
| **Adobe Content Analytics** | Med Adobe Content Analytics kan ni snabbt och enkelt undersöka stora volymer innehållsdata för att identifiera trender, upptäcka avvikelser, identifiera innehållets trötthet och få insikter från exponering.<p>Med färdiga rapportmallar och nya funktioner som Asset Inspector kan du spara tid. Med den här funktionen kan du inte bara visualisera mediefilen i linje med dina data, utan även öppna varje mediefil för sammanfattad information, inklusive prestanda, placeringar, attribut med mera.<p>Ni kan undersöka den nya uppsättningen innehållsdata i samband med hela kundresan för att besvara viktiga affärsfrågor, bedöma innehållsprestanda, förbättra segmenteringen, identifiera optimeringsmöjligheter och definiera nya målgrupper för aktivering.<p>Content Analytics är ett tillägg till Customer Journey Analytics. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics) |  | 27 mars 2025 |
| **Mediesamling: Adobe Source Connector-uppdateringar för nya Media Reporting XDM** | Analytics Source Connector mappar automatiskt strömmande mediedata i Adobe Analytics till samma fält som används av Web SDK. Tidigare mappades data till både gamla och nya platser, men endast den nya platsen kommer att användas i framtiden. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 31 mars 2025 |
| **Uppdaterade XDM-fält för att samla in strömmande mediedata till Adobe Experience Platform** | När Streaming Media-data samlas in i Adobe Experience Platform ska fältgruppen `media.mediaTimed` inte längre användas. I stället bör kunderna migrera till fältgruppen `mediaReporting`.<p>Under en övergångsperiod på tre månader kommer inmatningen av data i `media.mediaTimed` fält att fortsätta. I slutet av juli 2025 kommer dock `the media.mediaTimed` fält att vara helt inaktuella och inte längre synliga i användargränssnittet för Adobe Experience Platform-schemat, och data kommer endast att skickas med hjälp av fälten `mediaReporting`.<p>Kunder som implementerade Analytics-källanslutningen för att samla in Streaming Media-data till plattformen före 22 april 2025 måste migrera sina befintliga konfigurationer för att använda den nya fältgruppen. Denna migrering måste vara slutförd i slutet av juli 2025. Kontakta Adobe Consulting-tjänsterna eller kontoteamet för att få migreringssupport. Ingen åtgärd krävs för kunder som implementerar källkopplingen för Analytics efter den 22 april 2025. |  | 22 april 2025 |
| **Terminologisk ändring: &quot;Filter&quot; till &quot;Segment&quot;** | Tidigare kallade Adobe Customer Journey Analytics segment för&quot;filter&quot;. Terminologin har nu anpassats till Adobe Analytics. &quot;Filter&quot; kallas nu &quot;segment&quot;. (Det är tydligt att sökfilter fortfarande kallas för&quot;filter&quot;.) Användargränssnittet har uppdaterats och dokumentationen håller på att uppdateras. |  | 16 april 2025 |
| **Stitching: Hämta beständiga och tillfälliga ID:n från XDM IdentityMap** | Den här funktionen har stöd för att använda identiteter som lagras i XDM identityMap i sammanfogningsprocessen. identityMap kan användas för det beständiga eller transienta ID:t för fältbaserad sammanfogning och kan användas för det beständiga ID:t för diagrambaserad sammanfogning.  Du kan använda ett specifikt namnutrymme eller en primär identitet från identityMap. (Dokumentationslänk följer) |  | 25 april 2025 |
| **Delade mått och mått mellan datavyer** | Gör att du kan använda mått- och måttinställningar för flera datavyer. Ändringar som görs i en delad dimension eller mätvärde gäller för alla instanser av den dimensionen eller mätvärdet i alla tillämpliga datavyer. Med det här gränssnittet kan Customer Journey Analytics-administratörer enklare hantera komponenter när många datavyer används. (Dokumentationslänk följer) |  | 30 april 2025 |


## Korrigeringar i Customer Journey Analytics

**Admin Console**: AN-370228
**Analysis Workspace**: AN-371933; AN-371933; AN-371979
**Publiker**: AN-373032
**Komponentinställningar**: AN-367400
**Härledda fält**: AN-370614; AN-370959
**Exportplatser**: AN-371670
**Fullständig tabellexport**: AN-360492; AN-369204; AN-370755;AN-372294; AN-372363; AN-372754; AN-4 373040; AN-373081; AN-373168
**Resa Canvas**: AN-373294
**Mobilapp**: AN-363169; AN-368496; AN-371766
**Produktanvändning**: AN-369501
**Rapportering**: AN-369085; AN-371094; AN-372580


## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

## Relaterade resurser

* [Tidigare versionsinformation för Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics dokumentationsuppdateringar](/help/release-notes/doc-changes.md)
