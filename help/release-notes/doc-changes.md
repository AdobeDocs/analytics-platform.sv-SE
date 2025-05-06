---
title: Customer Journey Analytics dokumentationsuppdateringar
description: Visar innehållsuppdateringar för Customer Journey Analytics-dokumentationen som angetts sedan december 2019.
exl-id: 1cfb9810-e083-4a68-9c58-295e674da8d7
solution: Customer Journey Analytics
feature: Release Notes
source-git-commit: 720751130d0f66bddffd13c6f160a85fcc7a7206
workflow-type: tm+mt
source-wordcount: '5107'
ht-degree: 5%

---

# Customer Journey Analytics - dokumentationsuppdateringar

Följande uppdateringar har gjorts i Customer Journey Analytics-dokumentationen sedan den startades.

## 2025

| Funktion | Beskrivning |
| --- | --- |
| **April 2025** | |
| Förbättrade fullständiga exportbegränsningar för tabeller | [antalet kolumner](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) som kunder kan använda med fullständig tabellexport har ändrats från 5 dimensioner och 5 mätvärden till 10 dimensioner och 10 mätvärden. |
| Anslutningar | Uppdaterade och omarbetade dokumentationen om kundreseanslutningar för kommande B2B edition-kundresa. |
| Produktanalys - användningsfall | [Produktanalys har lagts till i Customer Journey Analytics](/help/use-cases/product-analysis.md). |
| Delade mått | Dokumentation för funktionen [Delade mått och dimensioner](/help/data-views/shared-metrics-dimensions/smd-overview.md) har lagts till. |
| Report Builder | Granskade och uppdaterade dokumentationen för [Report Builder](/help/report-builder/rb-overview.md). |
| Visa och hantera användning | Dokumentationen om hur du [visar](/help/connections/manage-connections.md#usage) och [hanterar](/help/technotes/estimate-usage.md) Customer Journey Analytics-användning har omarbetats |
| Adobe Content Analytics | Med [Content Analytics](/help/content-analytics/content-analytics.md) kan du snabbt och enkelt undersöka stora volymer innehållsdata för att identifiera trender, upptäcka avvikelser, identifiera innehållets trötthet och få insikter från exponering. |
| Uppdaterade XDM-fält för att samla in Streaming Media-data till Adobe Experience Platform | När Streaming Media-data samlas in i Adobe Experience Platform bör de XDM-fältsökvägar som visas under rubriken &quot;XDM Field Path&quot; i dokumentationen för Streaming Media-parametrar inte längre användas. De här fältsökvägarna finns på följande sidor och markeras som &quot;Undertryckta&quot;: [Parametrar för ljud- och videoinnehåll](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Lägg till parametrar](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparametrar](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametrar för spelartillstånd](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/player-state-parameters) och [Kvalitetsparametrar](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/quality-parameters). |
| Media Collection: Adobe Source Connector-uppdateringar för nya Media Reporting XDM | Analytics Source Connector mappar automatiskt strömmande mediedata i Adobe Analytics till samma fält som används av Web SDK. Tidigare mappades data till både gamla och nya platser, men endast den nya platsen kommer att användas i framtiden. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics/implementation/aep-edge/xdm-var-mapping) |
| Terminologisk förändring:&quot;Filter&quot; till&quot;segment&quot; | Tidigare kallade Adobe Customer Journey Analytics segment för&quot;filter&quot;. Terminologin har nu anpassats till Adobe Analytics. &quot;Filter&quot; kallas nu &quot;segment&quot;. (Det är tydligt att sökfilter fortfarande kallas för &quot;filter&quot;.) Gränssnittet och dokumentationen har uppdaterats. |
| **Mars 2025** | |
| Användningsexempel för Quantum Metric | Användningsexempel har lagts till för att samla in data från [kvantmätare](/help/use-cases/third-party/quantum-metric/qm-overview.md). |
| Produktanvändningsmall | Med en ny Workspace-mall kan du visa hur Customer Journey Analytics-produkten används i din organisation. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/templates/use-templates). |
| Customer Journey Analytics uppgraderingsguide | Här kan du skapa en stegvis guide för uppgradering från Adobe Analytics till Customer Journey Analytics. Logga in på [!DNL Customer Journey Analytics] och välj sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** på fliken **[!UICONTROL Workspace]** för att börja generera din anpassade guide. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |
| Uppdaterar till radobjektet Inget värde för numeriska dimensioner | För numeriska dimensioner kan du med den här uppdateringen använda dimensionsobjektet Inget värde i ett segment och utföra en uppdelning i en rapport på radobjektet Inget värde. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) |
| Media Collection: Adobe Source Connector-uppdateringar för nya Media Reporting XDM | Analytics Source Connector mappar automatiskt strömmande mediedata i Adobe Analytics till samma fält som används av Web SDK. Tidigare mappades data till både gamla och nya platser, men endast den nya platsen kommer att användas i framtiden. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics/implementation/aep-edge/xdm-var-mapping) |
| **Februari 2025** |  |
| Media Collection: Adobe Source Connector-uppdateringar för nya Media Reporting XDM | Analytics: Source Connector [mappar automatiskt strömmande mediedata i Adobe Analytics](https://experienceleague.adobe.com/sv/docs/analytics/implementation/aep-edge/xdm-var-mapping?lang=en) till samma fält som används av Web SDK. Tidigare mappades data till både gamla och nya platser, men endast den nya platsen kommer att användas i framtiden. |
| BI-tillägg - utökat stöd | Tillägget Customer Journey Analytics BI har nu stöd för [Looker, Jupyter Notebook och R Studio](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-usecases/data-views/bi-extension-usecases?lang=en). |
| **Januari 2025** |  |
| Uppdaterad upplevelse av anslutningsanvändning | Fliken [Användning](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-connections/manage-connections?lang=en#connections-usage) i Connection innehåller nu förbättrad visualisering för de här typerna av rapportbara rader: kärndata, inkapslade och historiska data. Du kan också visa och dela upp användningsdata efter anslutning, datauppsättning, sandlåda eller tagg. |
| Användningsstatistik | Uppdaterad dokumentation om det förbättrade gränssnittet för [användningsstatistik](/help/connections/manage-connections.md#usage). |
| Produktanvändning | [Produktanvändningen](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/tools/product-usage/usage-overview) visar hur din organisation använder Customer Journey Analytics. |
| Guidad analys | Uppdaterad dokumentation med tillgänglighet för [Guidad analys](/help/guided-analysis/overview.md) inifrån Guidad analys. |
| Dokumentation om hur du använder anpassade mallar från Customer Journey Analytics på rapportsidan i Journey Optimizer | Du kan nu anpassa det nya rapporteringsgränssnittet i Adobe Journey Optimizer genom att [skapa eller redigera en mall i Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/templates/create-templates?lang=en) och sedan spara mallen som ska användas på rapportsidan i Journey Optimizer. Tidigare gick det inte att anpassa det nya rapporteringsgränssnittet i Adobe Journey Optimizer. |
| Mallar i Analysis Workspace | [Färdiga mallar](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/templates/use-templates) och [företagsmallar](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/templates/create-templates) är nu tillgängliga i Customer Journey Analytics. |
| Intelligent Captions v2 | [Intelligenta bildtexter](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions?lang=en) stöds nu för följande visualiseringar: Flera rader, Stapel, Vågrätt fält, Ring upp, Yta, Flöde och Utfall. Du kan välja att visa alla intelligenta bildtexter samtidigt i en utökad vy eller visa enskilda intelligenta bildtexter i en vy i taget. |

## 2024

| Funktion | Beskrivning |
| --- | --- |
| **November 2024** | |
| Användningsexempel för BI-tillägg | Dokumentation för flera [BI-tillägg använder fall](/help/use-cases/data-views/bi-extension-usecases.md) för BI-verktyg som Power BI Desktop och Tableau Desktop. |
| Förfrågningar om titlar och sekretess | Meddelande har lagts till om [kommande ändringar i den upplösande processen](/help/stitching/faq.md#frequently-asked-questions) som är ett resultat av sekretessförfrågningar. |
| **Oktober 2024** | |
| Visualisering av arbetsyta på resans yta | [Researbetsytan](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas?lang=en) är en visualisering i arbetsytan Analys som gör att du kan analysera hur personer går igenom eller faller bort från en definierad resa. |
| Överföring av tillgångar | Gör att du kan [överföra ägarskap](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/tools/asset-transfer/transfer-assets) för komponenter som projekt, segment och beräknade värden till andra användare för att säkerställa kontinuitet och lämplig åtkomst. |
| Förbättrat användargränssnitt | Artikeln om det förbättrade gränssnittet har uppdaterats så att du kan visa din [användning av inkapslade och rapportbara rader över alla anslutningar](/help/connections/manage-connections.md#usage) |
| Delade enheter | En [användningsfallartikel](/help/use-cases/stitching/shared-devices.md) har lagts till som ger kontext på delade enheter, hur du hanterar och reducerar data från delade enheter med hjälp av sammanslagning och hur du förstår exponeringen för delade enheter i dina data med hjälp av frågetjänsten. |
| Ny information om begärandefaktorer i Analysis Workspace prestanda | En ny [Request factor](/help/technotes/optimizing-performance.md#request-factors)-sektion i artikeln [Optimize Analysis Workspace performance](/help/technotes/optimizing-performance.md) förklarar hur begäranden behandlas och de olika faktorer som påverkar bearbetningstiderna. |
| Workspace och komponenter | Uppdaterade dokumentationen om Analysis Workspace-projekt (projekt, visualiseringar och paneler) och komponenter (anteckningar, dimensioner, (beräknade) mått, segment, datumintervall, aviseringar, schemalagda projekt och målgrupper). |
| Guidad analys | Uppdaterad dokumentation med tillgänglighet för [guidad analys](/help/guided-analysis/overview.md) inifrån Analysis Workspace. |
| Uppdaterad målgruppsdokumentation | När [skapar en målgrupp](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-components/audiences/publish?lang=en) från en visualisering i Analysis Workspace, inkluderas nu panelsegment och kolumnsegment som ytterligare kriterier. |
| **September 2024** | |
| Uppdatering av sammanfattningsdata | Sammanfattningsdataartiklar med information om hur [sökdata](/help/data-views/summary-data.md#lookup-data) används korrekt vid rapportering av sammanfattningsdata har uppdaterats. |
| Uppdatering för BI-tillägg | [standardvärden och begränsning](/help/data-views/bi-extension.md#defaults-and-limitations) har lagts till i dokumentationen för BI-tillägget. |
| Aviseringar | Dokumentation har lagts till för funktionen [Alerts](/help/components/c-intelligent-alerts/intelligent-alerts.md) som nu finns i Customer Journey Analytics. |
| Ytterligare information i kolumnen Används i i den beräknade metriska hanteraren och segmenthanteraren | Kolumnen &quot;Används i&quot; i [beräknad måtthanterare](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager?lang=en) och [segmenthanterare](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-components/cja-filters/manage-filters?lang=en) innehåller följande nya rapporteringsområden: Report Builder- och Ad-hoc-komponenter |
| **Augusti 2024** | |
| Ett exempel på ett B2B-projekt | Ett [användningsfall](/help/use-cases/b2b/example.md) har lagts till som dokumenterar hur du konfigurerar, konfigurerar och rapporterar profilnivåbaserade B2B-data i Customer Journey Analytics med den nya funktionen [transformeringsdatauppsättningar för B2B-sökningar](/help/connections/transform-datasets-b2b-lookups.md) . |
| Uppdaterade användningsfall för dataexport | Fler detaljerade frågeexempel har lagts till i [frågetjänsten (Data Distiller) och datauppsättningarna för export](/help/use-cases/data-export/queryservice-export-datasets.md) för att illustrera hur attribuering ska tillämpas på rätt sätt i sessioner med ett uppslagsfönster. |
| Sammanfattningsdata | Dokumentation har lagts till för [sammanfattningsdata](/help/data-views/summary-data.md), [komponentinställningar för sammanfattningsdatagrupp](/help/data-views/component-settings/summary-data-group.md) och ett [användningsfall för sammanfattningsdata](/help/use-cases/data-views/summary-data.md). |
| **Juli 2024** | |
| Lagt till information om snabba beräknade mätvärden | Uppdaterad information i [Metrisk](/help/components/apply-create-metrics.md) för att förtydliga skillnaden mellan [beräknade mått som skapas i beräkningsverktyget](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) och [de som skapas som snabbberäknade mätvärden i ett enskilt projekt](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). Ytterligare information om slangarna för att skapa snabba beräknade mätvärden.<p>Beräknade mätvärden som har skapats i verktyget för beräknade mätvärden är tillgängliga i komponentlistan och kan tillämpas på projekt i hela organisationen, medan beräknade mätvärden som har skapats som snabba beräknade mätvärden endast är tillgängliga i det projekt där de skapades.</p><p>Uppdaterad information i [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) för att göra liknande förtydliganden.</p> |
| Härledd dedupliceringsfunktion för fält | Dokumentation har lagts till i det härledda fältet [deduplicate](/help/data-views/derived-fields/derived-fields.md#deduplicate). |
| Uppdaterade vanliga felmeddelanden | Mindre uppdateringar av de [vanliga felmeddelandena](/help/analysis-workspace/workspace-faq/error-messages.md) har gjorts. |
| **Juni 2024** | |
| Uppdaterat produktnamn som hänvisar till funktioner för direktuppspelande media | Ersatte instanser av&quot;Media Analytics&quot; och&quot;Streaming Media&quot; med namnet&quot;Streaming Media Collection Add-on&quot; och&quot;Streaming Media Collection&quot; när de refererar till en uppsättning funktioner för direktuppspelande media som samlar in direktuppspelningsdata och visar dessa i Analysis Workspace. <p>Dessa uppdateringar är tillgängliga i hela Customer Journey Analytics-dokumentationen samt i [dokumentationen för direktuppspelad mediesamling](https://experienceleague.adobe.com/sv/docs/media-analytics/using/media-overview).</p> |
| Diagrambaserad utjämning | Uppdaterade och omstrukturerade [sammanfogningsdokumentation](/help/stitching/overview.md) med introduktionen av diagrambaserad sammanfogning. |
| AI-assistenten | [dokumentation](../ai-assistant.md) har lagts till i AI-assistenten för Customer Journey Analytics. |
| Omforma datauppsättningar för B2B-sökningar | Lagt till dokumentation om stöd för [personbaserade sökningar på B2B-data](/help/connections//transform-datasets-b2b-lookups.md) (inklusive konton, affärsmöjligheter, marknadsföringslistor och kampanjer) med transformering av B2B-sökningsdatauppsättningar. |
| Härledda fältfunktioner och funktionsmallar | Dokumentation om de ytterligare härledda fältsfunktionerna ([Math](/help/data-views/derived-fields/derived-fields.md#math), [Next eller Previous](/help/data-views/derived-fields/derived-fields.md#next-or-previous) samt [Summarize](/help/data-views/derived-fields/derived-fields.md#summarize)) och [function templates](/help/data-views/derived-fields/derived-fields.md#function-templates) har lagts till. |
| **Maj 2024** | |
| Målintegration | [artikeln har lagts till i Adobe integreringsavsnitt](/help/integrations/at.md) om hur du integrerar Target med Customer Journey Analytics. |
| Nödvändig information när du exporterar Customer Journey Analytics-rapporter till Google Cloud Platform med begränsningar för organisationspolicy | Lagt till det Adobe-ägda organisation-ID:t för Google Cloud-plattformen i dokumentationen [Konfigurera molnexportplatser](/help/components/exports/cloud-export-locations.md) för export av Customer Journey Analytics-rapporter till Google Cloud-plattformen. <p>Den här informationen krävs bara för organisationer som använder [begränsningar för organisationsprinciper](https://cloud.google.com/storage/docs/org-policy-constraints) i Google Cloud Platform.</p> |
| Dokumentation om hur du lägger till komponenter i projekt | Allmän information om hur du [lägger till olika typer av komponenter i projekt i Analysis Workspace](/help/components/use-components-in-workspace.md) har lagts till. |
| Användningsexempel vid dataexport | En uppsättning nya artiklar som beskriver [användningsfall för dataexport](/help/use-cases/data-export/overview.md) och hur du använder Experience Platform- och Customer Journey Analytics-funktioner för att implementera dessa användningsfall |
| Ny dokumentation för uppgradering från Adobe Analytics till Customer Journey Analytics | För organisationer som uppgraderar från Adobe Analytics till Customer Journey Analytics finns det flera uppgraderingsalternativ och många överväganden att tänka på baserat på organisationens nuvarande Adobe Analytics-implementering och långsiktiga mål.<p>Nu finns det nya dokumentationsresurser som hjälper dig att förstå:</p><ul><li>De olika uppgraderingssökvägarna som finns</li><li>Vilka uppgraderingsalternativ som finns tillgängliga baserat på en organisations aktuella implementering av Adobe Analytics</li><li>Fördelar och nackdelar med varje uppgraderingsväg</li><li>Stegvisa anvisningar för varje uppgraderingsväg</li><li>Att tänka på vid hantering av historiska data</li><li>Och mycket mer!</li></ul><p>[Kom igång med uppgraderingen till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md).</p> |
| Uppdaterad dokumentation om anpassade datumintervall | Skärmbilder och procedurer som relaterar till [exempeldatumintervall](/help/components/date-ranges/custom-date-ranges.md) har uppdaterats för att matcha de aktuella produktfunktionerna och designen. |
| Översiktsinformation om dimensioner | Lagt till information om [dimensioner](/help/components/dimensions/overview.md). |
| Exempel på källkopplingar | Exempel på källanslutningar som är tillgängliga när du beskriver hur du [använder en källkoppling](/help/data-ingestion/sources.md#use-a-source-connector) för datainhämtning har lagts till. |
| **April 2024** | |
| Prognostiserade statistiska tekniker | Artikeln som beskriver de [statistiska tekniker som används i prognostjänsten ](../analysis-workspace/c-forecast/statistics-forecasting.md) har lagts till. |
| Tillagd information som rekommenderar fullständig tabellexport för höga kardinalitetsmått | Punkter har lagts till i [Bästa tillvägagångssätt för dimensioner med hög kardinalitet](/help/components/dimensions/high-cardinality.md) för att rekommendera att använda Full tabellexport för dimensioner med hög kardinalitet. |
| Lagt till dokumentation om intelligenta bildtexter i mobilstyrkort | [Intelligenta bildtexter](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) kan hjälpa icke-analytiker att förstå sina data bättre utan hjälp av analytiker. |
| Ny dokumentation om Adobe Product Analytics-funktioner | <ul><li>[Funktionsmatris](/help/guided-analysis/types/funnel.md)</li><li>Förbättrad [lagring](/help/guided-analysis/types/retention.md)</li><li>[Förbättrade insikter i tratt](/help/guided-analysis/types/funnel.md)</li><li>Jämför händelser i ett enda tratt-steg</li></ul> |
| **Mars 2024** | |
| Användningsinformation om kolumnen Används i är tillgänglig först från och med september 2023. | Tydligare är att användningsinformationen för kolumnen **Används i** på [projektstartsidan](/help/getting-started/landing.md) endast går tillbaka till september 2023. |
| Lagt till dokumentation om behörighetsförbättringar för Workspace-komponenter som bara är till för projekt | Om du delar ett projekt med andra användare kan dessa användare redigera [snabbsegment](/help/components/filters/quick-filters.md) och andra komponenter som bara är till för projektet och som är inbäddade i det delade projektet. |
| **Februari 2024** | |
| Uppdateringar av projektdelningsdokumentation | Lagt till information om hur du [visar projekt som delas med dig](/help/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you).<p>Effektivare information om att [dela enskilda eller flera projekt](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).</p> |
| Lagt till behörighetskrav för överföring av filer till Azure SAS och Azure RBAC när molnexportplatser konfigureras | Exakta behörighetskrav för överföring av filer till Azure SAS och Azure RBAC lades till när [molnexportkonton](/help/components/exports/cloud-export-accounts.md) och [konfigurerade molnexportplatser](/help/components/exports/cloud-export-locations.md) konfigurerades. |
| Lagt till behörighetskrav för att överföra filer till Amazon S3 Role ARN- och GCP-bucket när du konfigurerar molnexportplatser | Exakta behörighetskrav för överföring av filer till Amazon S3 Role ARN och Google Cloud Platform har lagts till när [molnexportplatser ](/help/components/exports/cloud-export-locations.md) konfigureras. |
| Klarade att produktadministratörer alltid har tillgång till fullständiga tabeller för export | Gör följande ändringar för att förtydliga att användare som har tilldelats rollen Produktadministratör har åtkomst till att exportera fullständiga tabeller från Analysis Workspace som standard: <ul><li>En ny punkt har lagts till i [standardbehörigheten för produktadministratör](/help/technotes/access-control.md#product-admin-default-permissions).</li><li>En anteckning har lagts till under de [lägsta kraven för export av fullständiga tabeller till molnet](/help/analysis-workspace/export/export-cloud.md#minimum-requirements).</li></ul> |
| Det klargörs att segment återskapas vid komponentmigrering från Adobe Analytics | I [användarhandboken för Adobe Analytics-användare](/help/getting-started/aa-to-cja-user.md) klargjordes att segment automatiskt återskapas i Adobe Analytics som en del av komponentmigreringsprocessen och att de inte behöver återskapas manuellt. |
| Information om överhoppad post | Lagt till dokumentation om funktionen för överhoppad postinformation i Anslutningar. Mer information finns i [Anslutningsinformation](../connections/manage-connections.md#connection-details). |
| **Januari 2024** | |
| Prognos | Lagt till dokumentation om [prognostisering](../analysis-workspace/c-forecast/forecasting.md), den nya Analysis Workspace-funktionen för att prognostisera ett standardmått eller beräknat mätvärde med tidgranularitet (timtal, dag, vecka, månad och år) som stöds för frihandstabeller och linjediagram. |
| Dokumentationen för att lägga till konton och platser vid export av fullständiga register har uppdaterats | Dokumentationen har uppdaterats för att återspegla mindre gränssnittsuppdateringar när ett nytt konto eller en ny plats konfigureras när [fullständiga tabeller exporteras från Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace).<p>Ett nytt alternativ, [!UICONTROL **Lägg till konto**], är nu tillgängligt i listrutan [!UICONTROL **Konto**]. Alternativet [!UICONTROL **Lägg till plats**] som tidigare fanns som en knapp bredvid listrutan [!UICONTROL **Platsnamn**] är nu tillgängligt på själva menyn. |
| Ny information om komponentmigrering vid migrering från Adobe Analytics | Information har lagts till i [Utveckling från Adobe Analytics](/help/getting-started/aa-to-cja.md) som refererar till de nya [komponentmigreringsfunktionerna](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=sv-SE) som finns dokumenterade i Adobe Analytics Admin Guide. |
| Klarade att viss information endast är tillgänglig för administratörer | Tillagd information om att kolumnerna &quot;Senast använd&quot; och &quot;Används i&quot; som beskrivs i [Beräknad mätstatistik-hanteraren](/help/components/calc-metrics/cm-workflow/cm-manager.md) och [Segmenthanteraren](/help/components/filters/manage-filters.md) endast är tillgängliga för systemadministratörer. |
| Behörigheter som krävs för att exportera datauppsättningar | Tillagd information som förklarar [behörigheten som krävs](/help/technotes/access-control.md) för att exportera datamängder till molnmål. |
| Hantera anslutningar | Artikeln [Hantera anslutningar](../connections/manage-connections.md) har uppdaterats baserat på kundfeedback. |
| Härledda fält | En sammanfattning av [begränsningar](/help/data-views/derived-fields/derived-fields.md#limitations) för funktionen har lagts till och en förklaring av hur antalet [operatorer](/help/data-views/derived-fields/derived-fields.md#operators) som används i en funktion ska fastställas. |

{style="table-layout:auto"}


## 2023

| Funktion | Beskrivning |
| --- | --- |
| **December 2023** | |
| Datacenter | En artikel har lagts till på Customer Journey Analytics [värdplatser](../technotes/data-centers.md). |
| Guardrails | En artikel med en lista över Customer Journey Analytics [skyddsutkast](../technotes/guardrails.md) har lagts till. |
| Uppdateringar av valutakonvertering | Tydligare dokumentation om hur du [konfigurerar valutakonvertering](/help/data-views/component-settings/format.md). |
| Uppdateringar av dokumentationen för avvikelseidentifiering | Dokumentationen för avvikelseidentifiering fanns tidigare i ett avsnitt om Virtual Analyst. Följande ändringar har gjorts: <ul><li>Termen Virtual Analyst har tagits bort från dokumentationen.</li><li>Avsnittet om [avvikelseidentifiering](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) flyttades direkt under Analysis Workspace-avsnittet.</li></ul> |
| **Oktober 2023** | |
| Använda härlett fält för att ställa in mål | [Använd case](../use-cases/goals-using-derived-fields.md)-artikel har lagts till som illustrerar hur du använder härledda fält för att ställa in mål och rapportera om dessa. |
| Exportera fullständiga tabeller till molnet | Lagt till dokumentation om export av fullständiga tabeller med miljontals Workspace-rader till molnmål. <p>Vid export av fullständiga tabeller kan du leverera datatabeller som tagits fram i Workspace och som har stöd för upp till fem uppdelningar, fem mätvärden, segment och beräknade mätvärden, allt i en sammanslagen tabell. Det är utvecklingen av Data Warehouse-rapporter i Adobe Analytics, med många nya, ofta efterfrågade funktioner som inte är tillgängliga i Data Warehouse idag.</p><p>Mer information finns i [Exportera Customer Journey Analytics-rapporter till molnet](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=sv-SE). |
| Rapporteringsaktivitetshanteraren | Lagt till dokumentation för Reporting Activity Manager. <p>Med Rapporteringsaktivitetshanteraren kan du se rapporteringskapaciteten för varje anslutning i organisationen. Det ger administratörer detaljerad insyn i rapporteringen av förbrukning för att enkelt kunna diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.</p> <p>Följande nya artiklar har lagts till:<ul><li>[Översikt över Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md)</li><li>[Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity.md)</li><li>[Avbryt begäranden i Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-cancel-requests.md)</ul> |
| Nya kolumner på hanteringssidor | Dokumenterade nya kolumner som nu är tillgängliga i [hanteraren för beräknade värden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html?lang=sv-SE) och [segmenthanteraren](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html?lang=sv-SE). |
| Jämförelse med Adobe Analytics | En [översiktssida](../getting-started/aa-vs-cja/overview.md) har lagts till som en introduktion om att jämföra och förstå skillnaderna mellan Customer Journey Analytics och Adobe Analytics. |
| Funktioner för ytterligare härledda fält | Uppdaterad dokumentation för den nya [`Lookup`](/help/data-views/derived-fields/derived-fields.md#lookup)-funktionen. |
| **September 2023** | |
| Uppdaterad struktur för artiklar för panelen Medieuppspelningstid för spenderad tid | Mappen Media Playback Time Spent har tagits bort och innehållet i mappen har kombinerats till en enda artikel: [Media Playback Time Spent panel](/help/analysis-workspace/c-panels/media-playback-time-spent.md). <p>Den här ändringen är mer i linje med dokumentationen för andra paneler.</p> |
| Funktioner för ytterligare härledda fält | Uppdaterad dokumentation för de nya [`Lowercase`](/help/data-views/derived-fields/derived-fields.md#lowercase)- och [`Trim`](/help/data-views/derived-fields/derived-fields.md#trim)-funktionerna och för de extra CSV-funktionerna som lagts till i funktionen [`Classify`](/help/data-views/derived-fields/derived-fields.md#classify). |
| Regional datainsamling | [Vanliga frågor](../getting-started/cja-faq.md#12-regional-data-collection) har uppdaterats med information om regional datainsamling när Customer Journey Analytics används. |
| **Augusti 2023** | |
| Medieuppspelningstid spenderad panel | Uppdaterat innehåll för [Media Playback Time Spent Panel](/help/analysis-workspace/c-panels/media-playback-time-spent.md) för att förbättra läsbarheten. |
| Report Builder-förbättringar | Innehållet i [Schemalägg arbetsböcker](/help/report-builder/schedule-reportbuilder.md) har uppdaterats för att ge information om hämtning av schemalagda aktiviteter. Uppdaterat innehåll för [Skapa ett datablock](/help/report-builder/create-a-data-block.md) för att tillhandahålla information om hur du använder startdatum som dimension. |
| Flyttat innehåll om hantering av schemalagda projekt | Skapade en ny artikel i Analytics Components Guide med namnet [Schemalagda projekt](/help/components/scheduled-projects-manager.md). Det här innehållet fanns tidigare i artikeln [Schemalägg projekt](/help/analysis-workspace/export/t-schedule-report.md) i verktygshandboken för analyser. |
| Funktioner i Adobe Customer Journey Analytics | Mer information om sessioneringsfunktionerna i Customer Journey Analytics har lagts till i tabellen *Stöds på ett nytt sätt* jämfört med Adobe Analytics. [Läs mer](../getting-started/aa-vs-cja/cja-aa.md#supported-in-a-new-way) |
| Utveckling från Adobe Analytics | Avsnittet *(Återställnings)Konfigurera marknadsföringskanaler* har uppdaterats med en referens till funktionsmallen för härledda fält för marknadsföringskanaler. [Läs mer](../getting-started/aa-to-cja.md#3-reconfigure-your-marketing-channels) |
| Snabbstartsguider för dataöverföring för mobilprogram och andra plattformar | Ytterligare startguider för dataöverföring med information om hur man importerar och använder data från mobilapplikationer eller andra plattformar (som datorapplikationer, spel på konsoler, applikationer på digitalboxar och IoT-enheter) i Customer Journey Analytics. [Läs mer](../data-ingestion/data-ingestion.md) |
| **Juli 2023** | |
| Sessionsinställningar | Ett ämne har lagts till för den här datavyinställningen. [Läs mer](/help/data-views/session-settings.md) |
| Adobe Product Analytics | Adobe Product Analytics är ett nytt sätt att interagera med kanalövergripande data och insikter i Customer Journey Analytics. De nya funktionerna gör att produktteamen kan självbetjäna data och insikter om sina produktupplevelser via [guidade analyser](/help/guided-analysis/overview.md) &#x200B;. |
| Härledda fält | Med ett [härlett fält](/help/data-views/derived-fields/derived-fields.md) kan du definiera (ofta komplexa) dataändringar direkt, via en anpassningsbar regelbyggare. |
| Utökat sökningsstöd för profil- och sökdata | Ger möjlighet att lägga till datauppsättningar som uppslag till fält i datauppsättningar för profiler eller uppslag. Tidigare stöddes endast händelsedatamängder. [Läs mer](/help/connections/create-connection.md) |
| Report Builder-förbättringar | <ul><li>[Filtrera från cell för flera datablock](/help/report-builder/select-data-view.md)</li><li>[Visa och dölj rad- och kolumnrubriker](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=sv-SE#build-the-data-block)</li></ul> |
| Edge Network geosökningar | [Datastream-inställningar](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=sv-SE) visar hur har en geosökningstjänst som tillhandahåller enhetliga geografiska data. |
| **Juni 2023** | |
| Flerkanalsanalys och stygn | I väntan på kommande ändringar för att aktivera sammanfogning och för att ytterligare klargöra hur flerkanalsanalys kan höjas med sammanfogning, redigeras dokumentation som rör funktionen för flerkanalsanalys för att hänvisa till [flerkanalsanalys](../use-cases/cross-channel/cross-channel.md) som Customer Journey Analytics-funktionen och -användningsfall, och [Stitching](../stitching/overview.md) som en viktig funktion för att uppnå detta. |
| PowerBI- och Tableau-åtkomst till datavyer från Customer Journey Analytics | Tillägget Customer Journey Analytics BI ger SQL-åtkomst till datavyer som du har definierat i Customer Journey Analytics. [Läs mer](/help/data-views/bi-extension.md) |
| Adobe Journey Optimizer datavyer | Customer Journey Analytics-administratörer har tillgång till vissa extra datavyer i Customer Journey Analytics med namnet&quot;AJO Data view (Sandbox-name)&quot;. [Läs mer](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/reporting/channel-report/reporting-configuration). |
| Valutakonvertering | Uppdaterad dokumentation om stöd för [valutakonvertering](../data-views/component-settings/format.md#currency). |
| Uppdateringar av beräknade mätvärden | Följande uppdateringar gjordes av dokumentationen för beräknade värden för att den skulle kunna anpassas till den aktuella Customer Journey Analytics-funktionen: <ul><li>Uppdaterade listan över [standardberäknade värden](/help/components/calc-metrics/default-calcmetrics.md) som är tillgängliga i Customer Journey Analytics</li><li>Uppdaterade skärmdumpar och -procedurer i olika beräknade mätningsartiklar </li></ul> |
| **Maj 2023** | |
| Deep Linking-dokumentation (mobilapp) | Tillåter användare att skicka länkar till styrkort som leder dem direkt till styrkortsprojektet i appen. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=sv-SE#share-scorecards-using-a-shareable-link) |
| Dokument om&quot;Välj datavy från cell&quot; i Report Builder | Med den här funktionen kan användare välja datavyn för ett datablock från en cell. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=sv-SE) |
| Dokumentation för den uppdaterade startskärmen för kontrollpanelsappen för Analytics (mobilapp) | På den nya uppdaterade startskärmen kan du visa alla dina styrkort i en konsoliderad styrkortslista. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html?lang=sv-SE#use-dashboards) |
| Optimeringsuppdatering | Uppdaterad artikel om [Optimering av Customer Journey Analytics-prestanda](/help/technotes/optimizing-performance.md) |
| Översikt över Analysis Workspace | [Analysis Workspace-översikt](/help/analysis-workspace/home.md) har uppdaterats med mer allmän översiktsinformation och länkar till relevant innehåll. |
| Skapa projekt | Skapade en ny artikel som förklarar i detalj hur du [skapar projekt](/help/analysis-workspace/build-workspace-project/create-projects.md) i Analysis Workspace. |
| Sortera komponenter i den vänstra listen | Lagt till information om hur du sorterar komponentlistan i den vänstra listen.Se avsnittet Sök, filtrera och sortera komponentlistan i [Komponentöversikt](/help/components/overview.md). |
| Ta bort rader som innehåller dynamiska dimensioner från en frihandstabell | Lagt till information om hur du snabbt tar bort specifika rader som innehåller dynamiska dimensioner med hjälp av x-ikonen. Se avsnittet&quot;Snabb uteslutning av specifika rader från en tabell&quot; i [Filtrera och sortera tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| Knapp för att lägga till en visualisering på en panel | Lagt till information om en ny knapp längst ned på varje panel i Analysis Workspace som gör att du snabbt kan lägga till en visualisering. Se avsnittet&quot;Lägg till visualiseringar i en panel&quot; i [Översikt över visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md). |
| Dokumentation för intelligenta bildtexter | Förbättra berättandet för användare med [naturspråkssammanfattningar](/help/analysis-workspace/visualizations/intelligent-captions.md) av en radvisualisering. |
| Härledda fält | Dokumentation har lagts till för funktionen [härledda fält](../data-views/derived-fields/derived-fields.md). |
| **April 2023** |  |
| Video om hur du använder segment som dimensioner | Videon om att använda segment som dimension har uppdaterats. <p>Den här videon är länkad från sidan [Skapa segment](/help/components/filters/create-filters.md).</p> <p>Följande är en direktlänk till videon: [Använd segment som dimensioner i Analysis Workspace](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/use-filters-as-dimensions.html?lang=sv-SE).</p> |
| Segmentdokumentation | Lagt till artikel om att använda [segmentverktyget](/help/components/filters/filter-builder.md). <p>Effektiv dokumentation i [Skapa segment](/help/components/filters/create-filters.md) och [Segmentöversikt](/help/components/filters/filters-overview.md).</p> |
| Uppdatera till dokumentationen på panelen Experimentation | Ett avsnitt på [tolkade icke-randomiserade dimensioner](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html?lang=sv-SE#non-randomized) har lagts till. |
| Projektsegment (ad hoc- och snabbsegment) | Effektiv dokumentation om projektsegment och borttagen dubblettinformation. Stegen för att skapa ad hoc-segment kombineras nu med stegen för att [skapa snabbsegment](/help/components/filters/quick-filters.md). |
| **Mars 2023** | |
| Integrera beslutsstyrningsdata | Innehåll har lagts till som förklarar hur du [integrerar Adobe Journey Optimizer Decision Management-data i Customer Journey Analytics](/help/integrations/ajo-od.md). |
| Skapa dataartiklar i mobilstyrkort | En [dataartikel](/help/mobile-app/create-scorecard.md#create-data-stories) är en samling med stöddatapunkter, företagskontext och relaterade mått som bygger på ett centralt tema eller mätvärden. |
| Uppdaterat funktionsstöd | Uppdaterat [Funktionsstöd för Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md) med en tabell över funktioner som är tillgängliga i Customer Journey Analytics men som inte är tillgängliga eller stöds i AA. |
| Standardberäknade värden | Innehåll har lagts till som förklarar de [beräknade standardmåtten från Adobe](/help/components/calc-metrics/default-calcmetrics.md). |
| Dataordlista | <p>Lagt till ny dokumentation för datamordlistan, inklusive en [översikt](/help/components/data-dictionary/data-dictionary-overview.md), [visning](/help/components/data-dictionary/view-data-dictionary.md), [redigering](/help/components/data-dictionary/edit-entries-data-dictionary.md) och [övervakning](/help/components/data-dictionary/monitor-data-dictionary-health.md) i datamappningslistan.</p><p>Information i [Att lägga till komponentbeskrivningar](/help/components/add-component-descriptions.md) har uppdaterats för att ta hänsyn till funktionen för dataordlista.</p> |
| Länkdelning för projekt (ingen inloggning krävs) | <p>Befintlig dokumentation som förklarar hur man delar en skrivskyddad länk till ett projekt med personer som inte har tillgång till Analysis Workspace har uppdaterats.</p> <p>Den uppdaterade användardokumentationen innehåller [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md) och [Skapa delningsbara länkar](/help/analysis-workspace/curate-share/shareable-links.md).</p> <p>Alternativ för administratörer lades till i [Inställningar](/help/analysis-workspace/user-preferences.md).</p> |
| **Februari 2023** | |
| Jämför Customer Journey Analytics med BI-lösningar | Nytt dokument på en [jämförelse](../getting-started/cja-vs-bi.md) av Customer Journey Analytics med vanliga BI-lösningar. |
| Uppdatera till publikdokumentation | Nytt avsnitt om [latensöverväganden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=sv-SE#latency). |
| Uppdatera till publikdokumentation | När du har skapat en målgrupp skapar Adobe ett [direktuppspelningssegment för Experience Platform för varje ny Customer Journey Analytics-målgrupp](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=sv-SE#after-audience-created). |
| Workspace-kalendrar och datumintervall | Uppdaterat innehåll som beskriver relativa datumintervall, uppdateringar av formelberäkning och ändringar i kalendergränssnittet. Se [Om relativa paneldatumintervall](/help/components/date-ranges/overview.md#custom-date-ranges). |
| Mobil styrkort | Nytt dokumentationsavsnitt som beskriver hur du visar och döljer datumintervall för jämförelse. Se [Visa datumintervall för jämförelse](/help/mobile-app/create-scorecard.md#show-comparison-dates) i Customer Journey Analytics. |
| **Januari 2023** | |
| Filtrera och ordna tabeller | Uppdaterat innehåll (inklusive att lägga till procedurer och förklara tillgängliga alternativ) i artikeln [Filtrera och sortera tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). Artikelns namn ändrades från&quot;Sidnumrering, filtrering och sortering&quot;. |
| Snabbstartsguider för dataöverföring | Nytt dokumentationsavsnitt om hur du [importerar och använder data](/help/data-ingestion/data-ingestion.md) i Customer Journey Analytics. |
| Workspace-mappar | Dedikerade sidor för [mapphantering](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Användarinställningar för Workspace | Många ytterligare användarinställningar finns nu tillgängliga i [Inställningar](/help/analysis-workspace/user-preferences.md). |
| Spara automatiskt för Workspace-projekt | Innehållet har uppdaterats för att inkludera funktioner för att spara automatiskt i [Spara projekt](/help/analysis-workspace/build-workspace-project/save-projects.md). |
| Landningssida | Ny landningssida uppdaterar [landningssida](/help/getting-started/landing.md). |
| Schemalägg arbetsböcker | Dedikerad sida som beskriver hur du [schemalägger arbetsböcker](/help/report-builder/schedule-reportbuilder.md) i Report Builder. |
| Stöd för objektmatriser för profil- och uppslagsdatauppsättningar | [Använd arrayer med objekt](/help/use-cases/object-arrays.md) och [Ingest Adobe Experience Platform-målgrupper](/help/use-cases/data-ingestion/ingest-aep-segments.md) för att spegla objektarraystöd för profil- och uppslagsdatamängder. |

{style="table-layout:auto"}

## 2022

| Datum | Uppdatera beskrivning |
| --- | --- |
| **December 2022** |  |
| 16 december 2022 | Nytt avsnitt om [hur du hanterar dataanvändningen i Customer Journey Analytics](/help/technotes/estimate-usage.md). |
| **Oktober 2022** | |
| Oktober 2022 | Nytt avsnitt om [lösenordsskydd för schemalagda projekt](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=sv-SE#password). Den här funktionen stöder [HIPAA-beredskap](https://www.adobe.com/trust/compliance/hipaa-ready.html). |
| Oktober 2022 | Nytt avsnitt om [Kundhanterade nycklar](/help/privacy/cmk.md). Den här funktionen stöder [HIPAA-beredskap](https://www.adobe.com/trust/compliance/hipaa-ready.html). |
| Oktober 2022 | Nytt avsnitt om [Customer Journey Analytics granskningslogg](/help/privacy/audit-log.md). |
| Oktober 2022 | Nytt avsnitt om [Visualisering av nyckelmätvärden](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=sv-SE). |
| Oktober 2022 | Nytt avsnitt om [datum- och datum-tid-funktionalitet i datavyer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=sv-SE#date) |
| Oktober 2022 | Mobilapp: Nytt avsnitt om [anpassade detaljvyer](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=sv-SE#view-detail-slides). |
| Oktober 2022 | Uppdateringar av [Customer Journey Analytics-funktionssupport](/help/getting-started/aa-vs-cja/cja-aa.md). |
| **September 2022** | |
| September 2022 | Nytt användningsexempel om [Migrerar Google Analytics-data till Customer Journey Analytics](/help/use-cases/third-party/ga/overview.md). |
| September 2022 | Nytt avsnitt om [Kombinationsdiagram](/help/analysis-workspace/visualizations/combo-charts.md) i Workspace. |
| September 2022 | Nytt avsnitt om [Experimentationspanelen](/help/analysis-workspace/c-panels/experimentation.md) i Workspace. |
| **Augusti 2022** | |
| Augusti 2022 | Adobe Experience Platform-artikel om [Stöd för flera regioner för källkopplingen för Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE). |
| Augusti 2022 | Avsevärt uppdaterad artikel om [Customer Journey Analytics åtkomstkontroll](/help/technotes/access-control.md). |
| Augusti 2022 | Ny artikel om [Customer Journey Analytics-stöd för etiketter och principer för datastyrning](/help/data-views/data-governance.md). |
| Augusti 2022 | Ny artikel om att [jämföra terminologi för analysdata som skickas via Analytics-källkopplingen](/help/getting-started/aa-vs-cja/terminology.md). |
| Augusti 2022 | Ny dokumentation om [målgruppspublicering till kundprofil för realtid](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=sv-SE). |
| **Juli 2022** | |
| Juli 2022 | [Dokumentation om tidsåtgången för mediauppspelning i panelen ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=sv-SE). |
| Juli 2022 | [Dokumentation för panelen för samtidiga visningsprogram för media](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=sv-SE). |
| Juli 2022 | [Rapportdokumentation för första sessionen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=sv-SE#new-repeat). |
| **Juni 2022** | |
| Juni 2022 | Ny artikel om [AAID, ECID, AACUSTOMID och Analytics-källkopplingen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=sv-SE) |
| Juni 2022 | Ny artikel om [Adobe Analytics bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep för Analytics-källkopplingen](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md). |
| Juni 2022 | Ny artikel om [virtuella rapportmiljöer och sandlådemiljöer](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md). |
| Juni 2022 | Ny artikel om att [jämföra databearbetning i Adobe Analytics- och Customer Journey Analytics-rapporteringsfunktioner](/help/getting-started/aa-vs-cja/data-processing-comparisons.md). |
| Juni 2022 | Ny artikel om [kombinerar rapportsviter med olika scheman](/help/use-cases/aa-data/combine-report-suites.md). |
| Juni 2022 | Ny artikel om att [dela anteckningar i mobilstyrkort](/help/components/annotations/mobile-annotations.md). |
| Juni 2022 | Ny artikel om [Analytics Labs i Customer Journey Analytics](/help/labs/labs.md). |
| Juni 2022 | Nytt avsnitt om [stöd för numeriska fält som söknycklar och sökvärden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=sv-SE#numeric). |
| Juni 2022 | Uppdateringar av [visualiseringsarbetsflödet för flöde](/help/analysis-workspace/visualizations/c-flow/create-flow.md). |
| **Maj 2022** | |
| Maj 2022 | Avsevärt uppdaterad artikel om [att skapa anslutningar](/help/connections/create-connection.md) i Customer Journey Analytics. |
| Maj 2022 | Ny artikel om hur du [hanterar datablock i Customer Journey Analytics Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=sv-SE). |
| Maj 2022 | Ny artikel om [inhämtning av Adobe Experience Platform-målgrupper till Customer Journey Analytics](/help/use-cases/data-ingestion/ingest-aep-segments.md). |
| **April 2022** | |
| April 2022 | Dokumentation om [dimensionsdelsträngar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=sv-SE). |
| April 2022 | Ny [användarhandbok för Customer Journey Analytics för Adobe Analytics](/help/getting-started/aa-to-cja-user.md). |
| **Mars 2022** | |
| Mars 2022 | Ny [API-dokumentation för Customer Journey Analytics Annotations](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/). |
| Mars 2022 | Ny dokumentation om [Anteckningar i Workspace](/help/components/annotations/overview.md). |
| Mars 2022 | Innehållet uppdaterades avsevärt på [en uppskattning av anslutningsstorleken](/help/getting-started/cja-faq.md). |
| **Februari 2022** | |
| Februari 2022 | En ny guide som riktar sig till administratörer som flyttar från Adobe Analytics till Customer Journey Analytics: [Adobe Analytics till Customer Journey Analytics-utveckling](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=sv-SE) |
| **Januari 2022** | |
| Januari 2022 | Nytt användningsexempel för [Använda bindningsdimensioner och mätvärden i Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md) |
| Januari 2022 | Dokumentation om nya funktioner har lagts till för [bindningsdimensioner och mätvärden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=sv-SE#binding-dimension) och för nya [[!UICONTROL First Known]- och [!UICONTROL Last Known] allokeringsinställningar](/help/data-views/component-settings/persistence.md#allocation-settings) |
| Januari 2022 | Ny artikel om att [jämföra dina Adobe Analytics-data med analysdata i Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=sv-SE) |

{style="table-layout:auto"}

## 2021

| Datum | Uppdatera beskrivning |
| --- | --- |
| **November 2021** | |
| November 2021 | Uppdaterad dokumentation för [[!UICONTROL Records skipped]](/help/connections/manage-connections.md) på sidan Anslutningsinformation. |
| **Oktober 2021** | |
| Oktober 2021 | Dokumentation för [Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/rb-overview.html#) i Customer Journey Analytics. |
| Oktober 2021 | API-dokumentation för Customer Journey Analytics [granskningslogg](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) |
| Oktober 2021 | Dokumenterade [visualiseringar för kontrollpaneler för analyser](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=sv-SE#apply-visualizations) |
| Oktober 2021 | Dok för rullande fönster för [!UICONTROL Connection] [datalagring](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=sv-SE#set-rolling-window-for-connection-data-retention). |
| **September 2021** | |
| September 2021 | [Metrisk borttagning av dubbletter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=sv-SE) doc |
| September 2021 | [Stöd för sommartid i rapporter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=sv-SE#calendar) |
| September 2021 | [Kundkalendrar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=sv-SE#calendar) - dokumentation |
| September 2021 | Dokumentation för [booleska fält](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/behavior.html?lang=sv-SE) |
| September 2021 | Öka komponentinställningarna i datavyer till enskilda filer:<ul><li>Översikt över inställningarna för [[!UICONTROL Component]](/help/data-views/component-settings/overview.md)</li><li>[[!UICONTROL Attribution] komponentinställningar](/help/data-views/component-settings/attribution.md)</li><li>[[!UICONTROL Behavior] komponentinställningar](/help/data-views/component-settings/behavior.md)</li><li>[[!UICONTROL Format] komponentinställningar](/help/data-views/component-settings/format.md)</li><li>[[!UICONTROL Include/exclude] komponentinställningar](/help/data-views/component-settings/include-exclude-values.md)</li><li>[[!UICONTROL Metric deduplication] komponentinställningar](/help/data-views/component-settings/metric-deduplication.md)</li><li>[[!UICONTROL No value] komponentinställningar](/help/data-views/component-settings/no-value-options.md)</li><li>[[!UICONTROL Persistence] komponentinställningar](/help/data-views/component-settings/persistence.md)</li><li>[[!UICONTROL Value bucketing] komponentinställningar](/help/data-views/component-settings/value-bucketing.md)</li></ul> |
| September 2021 | Nytt avsnitt om [effekterna av sammanslagningen av rapportsviter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=sv-SE#6.-Consi-when-merging-report-suites-in-cja) i Customer Journey Analytics. |
| **Augusti 2021** | |
| Augusti 2021 | Nytt avsnitt om den förbättrade [anslutningsfunktionen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=sv-SE) i Customer Journey Analytics. |
| Augusti 2021 | Nytt avsnitt om [skiftlägeskänslighet i datavyns dimensioner](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=sv-SE#configure-behavior-settings). |
| **Juni 2021** | |
| Juni 2021 | Ny dokumentation om [tidigare projektversioner](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/build-workspace-project/save-projects.html?lang=sv-SE#previous-version) i Workspace. |
| **April 2021** | |
| April 2021 | Nytt ämne om [persistence](/help/data-views/component-settings/persistence.md). |
| April 2021 | Ny dokumentation om stöd för schemalagda projekt i Workspace |
| April 2021 | Nya ämnen om [förbättrad datavyer](/help/data-views/data-views.md). |
| April 2021 | Nya ämnen om [inhämtning av Google Analytics-data](/help/use-cases/third-party/ga/overview.md) och [analys av dessa data](/help/use-cases/third-party/ga/report.md). |
| April 2021 | Avsnittet [Schemalagda rapporter](/help/analysis-workspace/export/t-schedule-report.md) har lagts till i Workspace. |
| April 2021 | Nytt avsnitt om [högkardinalitetsdimensioner i Customer Journey Analytics](/help/components/dimensions/high-cardinality.md). |
| **Mars 2021** | |
| Mars 2021 | Avsnittet om stöd för [kontrollpaneler för analyser](/help/mobile-app/home.md) (mobilapp) har lagts till. |
| Mars 2021 | Nytt avsnitt om [användarinställningar](/help/analysis-workspace/user-preferences.md) i Workspace. |
| **Februari 2021** | |
| Februari 2021 | Nytt avsnitt om hur du använder [mått för marknadsföringskanal i Adobe Experience Platform](/help/use-cases/aa-data/marketing-channels.md). |
| Februari 2021 | Publicerade den nya dokumentationen för [Customer Journey Analytics API](https://www.adobe.io/cja-apis/docs/). |
| **Januari 2021** | |
| Januari 2021 | Nytt avsnitt om [att lägga till standardsökningar i din datauppsättning](/help/connections/standard-lookups.md). |

{style="table-layout:auto"}

## 2020

| Datum | Uppdatera beskrivning |
| --- | --- |
| 13 november 2020 | Nya ämnen om [flerkanalsanalys](/help/stitching/overview.md), som gör att du kan ändra inmatningen för en datauppsättnings person-ID och som möjliggör en sömlös kombination av flera datauppsättningar. |
| 13 november 2020 | Ett nytt användningsfall för [import av callcenter och webbdata](/help/use-cases/cross-channel/call-center.md) har lagts till. |
| 10 november 2020 | Ett avsnitt om konsekvenserna av att ta bort datakomponenter har lagts till i [Vanliga frågor](/help/getting-started/cja-faq.md). |
| 2 november 2020 | Uppdateringar av sidan [Stöd för Customer Journey Analytics-funktioner](/help/getting-started/aa-vs-cja/cja-aa.md). |
| November 2020 | Innehåll har lagts till i [borttagning av begränsningar för bakgrundsfyllning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=sv-SE#backfill-historical-data) för anslutningar. |
| 7 oktober 2020 | Ett ämne har lagts till i [kombinerade händelsedatamängder](/help/connections/combined-dataset.md). |
| 15 september 2020 | Ett ämne har lagts till om [dataöverföring](/help/data-ingestion/data-ingestion.md). |
| 2 september 2020 | Avsnittet om [användarbehörigheter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=sv-SE) har uppdaterats. |
| Juli 2020 | Information har lagts till om alternativet [Identitetskarta för person-ID](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=sv-SE). |
| Juli 2020 | Nytt ämne har lagts till för [objektarrayer](/help/use-cases/object-arrays.md) eller&quot;dataherarkier&quot;. |
| 14 april 2020 | Uppdaterar det senaste användargränssnittet i avsnittet [Skapa anslutningar](/help/connections/create-connection.md). |
| 27 februari 2020 | Uppdateringar av [Customer Journey Analytics-funktionsstöd](/help/getting-started/aa-vs-cja/cja-aa.md) |
| December 2019 | Första utkastet till Customer Journey Analytics-dokumentation |

{style="table-layout:auto"}
