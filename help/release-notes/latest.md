---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 55f917530b2b3d6117b631738c125cf27a43bee4
workflow-type: tm+mt
source-wordcount: '1107'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (juni 2024)

**Senaste uppdatering**: 18 juni 2024

Versionsanteckningarna gäller den 6 juni till juli 2024. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AI Assistant för Customer Journey Analytics** | Gör att du kan ställa naturspråkliga frågor i användargränssnittet för Customer Journey Analytics och få svar baserat på dokumentationen för Customer Journey Analytics. [Läs mer](/help/ai-assistant.md) | | 6 juni 2024 |
| **Diagrambaserad sammanfogning: Stitching Using UIS Graph Export** | Med hjälp av diagrambaserad sammanfogning kan du använda identitetsdiagrammet för att få en bättre bild av kundresan genom att:<ul><li>Sammanfoga datauppsättningar med olika identifierare utan att behöva extrahera, omvandla och läsa in ytterligare data för att spegla en enda identifierare.</li><li>Förbättra täckningen av preferens- eller gyllene identitet för en enskild datauppsättning genom att dela identiteter mellan datauppsättningar.</li><li>Justera profiler som skapats i Real-time Customer Data Platform och Journey Optimizer med personer i Customer Journey Analytics.</li></ul>(Dokumentationslänk följer) |  | 28 juni 2024 |
| **B2B-schemaomvandling för person till konto** | För att ge stöd åt personbaserade sökningar på B2B-data (inklusive konton, affärsmöjligheter, marknadsföringslistor och kampanjer) kan ni omvandla datauppsättningar för B2B-sökning. Den här omvandlingen är bara tillgänglig för datauppsättningar med data för B2B-sökningsscheman, baserat på följande klasser:<ul><li>XDM Business Account Person Relation</li><li>XDM - affärsmöjlighet, personrelation</li><li>XDM Business Marketing List-medlemmar</li><li>XDM Business Campaign-medlemmar</li></ul>[Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 5 juni 2024 |
| **Härledda fält - matematisk funktion** | Gör att du kan göra enkla matematiska operatorer i datavyer för att besvara frågor om dina användare. Du kan t.ex. kombinera intäkter från produkt, garanti och frakt. <p>[Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 5 juni 2024 |
| **Härledda fält - nästa eller föregående funktion** | Här kan du se vad nästa eller föregående värde är. Vilka tidigare marknadsföringskanaler interagerade någon med före den valda marknadsföringskanalen? Eller hur interagerade sidanvändarna med före eller efter den valda sidan? Vad interagerar de populäraste kanalanvändarna med innan de går till butiken? <p>[Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p> | | 12 juni 2024 |
| **Härledda fält - sammanfattningsfunktion** | Ger möjlighet att tillämpa aggregeringsfunktioner på mått och mått på händelse-, sessions- och användarnivå. (Dokumentationslänk följer) | | 26 juni 2024 |
| **Härledda fält - borttagningsfunktion** | Förhindra upprepad räkning av ett värde. Kan tillämpas på användar- eller sessionsnivå eller baserat på ett dimensions unika värde. (Dokumentationslänk följer) |  | 26 juni 2024 |
| **Inmatningsprioritering och svarstid** | Du kan nu importera dina händelsedata i Customer Journey Analytics inom 90 minuter (SLT), oavsett om dessa data är 24 timmar, 48 timmar eller 7 dagar gamla. Observera att den här funktionen skiljer sig åt beroende på vilket SKU-paket ditt företag har köpt:<ul><li>CJA-prioritet Grundläggande om intag: 24-timmars gamla data inom 90 minuters SLT-bearbetning (tillgängligt för CJA Foundation och CJA Select)</li><li>CJA-prioritet Inmatningsmellanliggande: 72 timmars gamla data inom 90 minuters SLT- behandling (tillgängligt för CJA Prime)</li><li>CJA-prioritet Avancerat intag: 1-veckors gamla data inom 90 minuters SLT-bearbetning (tillgängligt för CJA Ultimate)</li></ul> |  | 12 juni 2024 |
| **Dela konton och platser som används för export och import** | Användarna kan nu göra de konton och platser de skapar tillgängliga för alla användare i organisationen. Endast konto- och platsägare och systemadministratörer kan redigera och ta bort konton och platser. Tidigare kunde konton och platser bara användas av den användare som skapade dem. Dessa inställningar är tillgängliga när användare [konfigurera molnexportkonton](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) och [konfigurera platser för molnexport](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 juni 2024 | 18 juni 2024 |
| **Markera flera fält i ett nedrullningsbart filter** | När flera fält har lagts till i ett nedrullningsbart filter kan användare nu markera mer än ett fält i taget. Panelen filtreras så att den innehåller något av de markerade fälten. <p>Tidigare kunde användaren bara markera ett fält i taget i ett droppfilter.</p><p>Alternativet att kräva en markering i ett nedrullningsbart filter har flyttats till menyn när du högerklickar på ett nedrullningsbart filter.</p><p>Tidigare kunde användare klicka på (x) bredvid alternativet Inget filter i listrutan.</p><p>Mer information finns i [Statiska nedrullningsbara filter](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters) in [Paneler - översikt](/help/analysis-workspace/c-panels/panels.md).</p> |  | 19 juni 2024 |
| **Innehållsförteckning för arbetsyteprojekt** | En ny innehållsförteckning är nu tillgänglig för projekt. Innehållsförteckningen innehåller länkar som gör att användare snabbt kan gå till paneler och visualiseringar i projektet. <p>Innehållsförteckningen är tillgänglig i den vänstra listen i alla projekt.</p><p>Mer information finns i [Innehållsförteckning för projekt](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md). |  | 19 juni 2024 |
| **Skapa hyperlänkar för dimensionsobjekt i en frihandstabell** | Du kan skapa hyperlänkar för ett eller flera dimensionsobjekt för att göra dem klickbara i en frihandstabell i Analysis Workspace. <p>Du kan skapa hyperlänkar för dimensionsobjekt som har URL-värden, eller så kan du skapa anpassade URL:er för dimensionsobjekt som inte har URL-värden.</p><p>Du kan skapa dynamiska anpassade URL:er för flera dimensionsobjekt med hjälp av variabler. Variabler kan referera till värdet för en dimensionsartikel eller referera till uppdelningsdimensionen.</p><p>Mer information finns i [Skapa hyperlänkar för dimensioner i en frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p> |  | 19 juni 2024 |
| **Använd datavyn i Customer Journey Analytics med Adobe Journey Optimizer** | Med ett nytt konfigurationsalternativ i Customer Journey Analytics kan du definiera en datavy för Customer Journey Analytics som ska användas med Adobe Journey Optimizer, utan att behöva konfigurera manuellt. <p>Mer information om hur du aktiverar det här konfigurationsalternativet finns i [Kompatibilitet](/help/data-views/create-dataview.md#compatibility) avsnitt i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).</p><p>Tidigare var du tvungen att konfigurera en anslutning och datavyer manuellt när du visade Journey Optimizer-data i Customer Journey Analytics.</p> |  | 19 juni 2024 |
| **Publiken publiceras i ett nytt&quot;Publiker&quot;-avsnitt i Experience Platform** | Publikationer som publiceras från Customer Journey Analytics är nu tillgängliga i det nya avsnittet&quot;Publiker&quot; i Adobe Experience Platform.<p>Tidigare fanns målgrupper som publicerades från Customer Journey Analytics tillgängliga i Experience Platform under segmentavsnittet.</p><p>Den här förbättringen ger följande fördelar:</p><ul><li>Publiken har inte längre en timmes fördröjning innan de visas i Experience Platform; de är tillgängliga sekunder efter att de har publicerats.</li><li>Publiker kan sorteras i Experience Platform med hjälp av kolumnen &quot;Ursprung&quot;, som visar det program som målgruppen ursprungligen publicerades från.</li><li>Med filtrerings- och sorteringsalternativen i Experience Platform kan du snabbare hitta rätt målgrupper.</li></ul> <p>(Dokumentationslänk följer)</p> |  | 14 juli 2024 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-345454; AN-349816; AN-349905; AN-350617

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
