---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 730464719f05026eae141c8e6cc656fb0fe4f819
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 3%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (maj 2025)

**Senast uppdaterad**: 22 maj 2025


Versionsanteckningarna gäller den 22 april-18 juni 2025. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Uppdaterade XDM-fält för att samla in strömmande mediedata till Adobe Experience Platform** | När Streaming Media-data samlas in i Adobe Experience Platform bör de XDM-fältsökvägar som visas under rubriken &quot;XDM Field Path&quot; i dokumentationen för Streaming Media-parametrar inte längre användas. De här fältsökvägarna finns på följande sidor och markeras som &quot;Undertryckta&quot;: [Parametrar för ljud- och videoinnehåll](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Lägg till parametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametrar för spelartillstånd](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) och [Kvalitetsparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). <p>I stället bör kunderna migrera till fältsökvägarna `mediaReporting`, vilket visas under rubriken&quot;Rapportera XDM-fältsökväg&quot; i dokumentationen för direktuppspelningsmediaparametrarna ovan.<p>Under en övergångsperiod på tre månader kommer inmatningen av data i de borttagna XDM-fältsvägarna att fortsätta. I slutet av juli 2025 kommer dock inaktuella fältsökvägar att tas bort helt och inte längre visas i användargränssnittet för Adobe Experience Platform-schemat, och data skickas endast med fältsökvägarna `mediaReporting`.<p>Kunder som implementerade Analytics-källkopplingen för att samla in Streaming Media-data till plattformen före 22 april 2025 måste migrera sina befintliga konfigurationer för att använda de nya fältsökvägarna. Migreringen måste vara klar i slutet av juli 2025. Kontakta Adobe Consulting-tjänsterna eller kontoteamet för att få migreringssupport. Ingen åtgärd krävs för kunder som implementerar källkopplingen för Analytics efter den 22 april 2025.</p> |  | 22 april 2025 |
| **Stitching: Hämta beständiga och tillfälliga ID:n från XDM IdentityMap** | Den här funktionen har stöd för att använda identiteter som lagras i XDM identityMap i sammanfogningsprocessen. identityMap kan användas för det beständiga eller transienta ID:t för fältbaserad sammanfogning och kan användas för det beständiga ID:t för diagrambaserad sammanfogning.  Du kan använda ett specifikt namnutrymme eller en primär identitet från identityMap. Läs mer [här](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap) och [här](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap) |  | 28 april 2025 |
| **Delade mått och mått mellan datavyer** | Gör att du kan använda mått- och måttinställningar för flera datavyer. Ändringar som görs i en delad dimension eller mätvärde gäller för alla instanser av den dimensionen eller mätvärdet i alla tillämpliga datavyer. Med det här gränssnittet kan Customer Journey Analytics-administratörer enklare hantera komponenter när många datavyer används. [Läs mer](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30 april 2025 |
| **Ökning av de fullständiga gränserna för tabellexport** | Adobe har ökat antalet kolumner som du kan använda med [fullständig tabellexport](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) från 5 dimensioner och 5 mätvärden till 10 dimensioner och 10 mätvärden. Detta gäller alla Customer Journey Analytics-nivåer. Antalet rader som kan exporteras ändras inte. |  | 30 april 2025 |
| **Händelsedjupdimension** | En ny [händelsedjupsdimension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) lades till i listan över nödvändiga standardkomponenter för en datavy. |  | 8 maj 2025 |
| **Inaktivera manifestfilen när fullständiga tabeller exporteras** | Gör att du kan inaktivera den manifestfil som inkluderas som standard när du exporterar fullständiga tabeller från Analysis Workspace. [Läs mer](/help/analysis-workspace/export/export-cloud.md) |  | 20 maj 2025 |
| **Agenten för datainsikter** | Agenten för datainsikter, som ingår i AI-assistenten i Customer Journey Analytics, är en generativ AI-konversationsagent. Den använder komponenter från datavyn och era faktiska data för att snabbt och effektivt besvara datacentrerade frågor genom att skapa relevanta visualiseringar i Analysis Workspace. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | 28 maj 2025 |
| **Analysis Workspace vänstra panel öppnas inte längre och stängs vid hovring** | Den vänstra panelen i Analysis Workspace används för att lägga till saker som komponenter, paneler och visualiseringar i ditt projekt. Alternativet att tillfälligt öppna den vänstra panelen genom att hålla markören över en av ikonerna längst till vänster är inte längre tillgängligt. Istället klickar du på någon av de här ikonerna för att hålla panelen öppen. Klicka sedan på samma ikon för att stänga den. |  | 29 maj 2025 |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition hjälper B2B-företag att anpassa sina marknadsförings-, sälj- och produktteam genom att tillhandahålla användbara kontoinsikter som ökar intäkterna. Med kontot som placeras i mitten av datamodellen fokuserar alla analyser på kontoresan. Genom att lägga till ett nytt lager av enheter (konton, affärsmöjligheter och inköpsgrupper) utöver personliga och tidsbaserade händelser, får ni en fullständig bild av B2B-marknadsförings- och intäktslivscykeln. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 juni 2025 |
| **Lägg till och visa kommentarer i Analysis Workspace-projekt** | Med en ny [kommentarsfunktion](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) i Analysis Workspace kan du dela insikter och ställa frågor i ett Analysis Workspace-projekt. Detta kan effektivisera diskussioner om data och hålla konversationer inom ramen för de data som ska diskuteras. Du kan <ul><li>Kommentera eventuella Analysis Workspace-projekt som du har tillgång till</li><li>Kommentera en specifik punkt i en visualisering eller göra allmänna kommentarer om ett projekt</li><li>Tagga andra användare för att meddela dem om dina kommentarer</li><li>Hantera befintliga kommentarer (redigera, fästa, lösa osv.)</li></ul>Customer Journey Analytics-administratörer kan [inaktivera kommentarer på organisationsnivå](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Projektägare kan [inaktivera kommentarer på projektnivå](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | 25 juni 2025 <p>(Ursprungligen planerat att släppas den 29 maj 2025)</p> |

## Korrigeringar i Customer Journey Analytics

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-37447; AN-375277; AN-375 680
**Publiker**: AN-372343
**Granskningslogg**: AN-378168
**Anslutningar**: AN-373121; AN-372996
**Dataradering**: AN-375450
**Härledda fält**: AN-373689; AN-377852
**Exportplatser**: AN-374167
**Resa Canvas**: AN-373319
**Report Builder**: AN-369786
**Rapportering**: AN-377326; AN-378051
**Rapportera aktivitetshanterare**: AN-377148


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
