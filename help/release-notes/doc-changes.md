---
title: Dokumentationsuppdateringar för Customer Journey Analytics
description: Listar innehållsuppdateringar för den dokumentation för Customer Journey Analytics som angetts sedan december 2019.
exl-id: 1cfb9810-e083-4a68-9c58-295e674da8d7
solution: Customer Journey Analytics
feature: Release Notes
source-git-commit: 12007130027d152038b1210070f6ebd5de15c762
workflow-type: tm+mt
source-wordcount: '3226'
ht-degree: 6%

---

# Customer Journey Analytics - dokumentationsuppdateringar

Följande uppdateringar har gjorts i dokumentationen för Customer Journey Analytics sedan den startades.

## 2024

| Funktion | Beskrivning |
| --- | --- |
| **Mars 2024** | |
| Användningsinformation om kolumnen Används i är tillgänglig först från och med september 2023. | Tydligare användningsinformation om **Används i** kolumn på [landningssida för projekt](/help/getting-started/landing.md) går tillbaka endast till september 2023. |
| **Februari 2024** | |
| Uppdateringar av projektdelningsdokumentation | Lagt till information om hur [visa projekt som delas med dig](/help/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you).<p>Effektivare information om [dela enskilda eller flera projekt](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).</p> |
| Lagt till behörighetskrav för överföring av filer till Azure SAS och Azure RBAC när molnexportplatser konfigureras | Exakta behörighetskrav för överföring av filer till Azure SAS och Azure RBAC har lagts till när [konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md) och [konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md). |
| Lagt till behörighetskrav för att överföra filer till Amazon S3 Role ARN- och GCP-bucket när du konfigurerar molnexportplatser | Exakta behörighetskrav för överföring av filer till Amazon S3 Role ARN och Google Cloud Platform har lagts till när [konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md). |
| Klarade att produktadministratörer alltid har tillgång till fullständiga tabeller för export | Gör följande ändringar för att förtydliga att användare som har tilldelats rollen Produktadministratör har åtkomst till att exportera fullständiga tabeller från Analysis Workspace som standard: <ul><li>En ny punkt har lagts till i [Standardbehörigheter för produktadministratör](/help/admin/cja-access-control.md#product-admin-default-permissions).</li><li>Lade till en anteckning under [minimikrav för export av fullständiga tabeller till molnet](/help/analysis-workspace/export/export-cloud.md#minimum-requirements).</li></ul> |
| Det klargörs att segment återskapas vid komponentmigrering från Adobe Analytics | I [Användarhandbok för Adobe Analytics](/help/getting-started/aa-to-cja-user.md), klargjorde att segment automatiskt återskapas i Adobe Analytics som en del av komponentmigreringsprocessen och inte behöver återskapas manuellt. |
| Information om överhoppad post | Lagt till dokumentation om funktionen för överhoppad postinformation i Anslutningar. Se [Anslutningsinformation](../connections/manage-connections.md#connection-details) för mer information. |
| **Januari 2024** | |
| Prognos | Lagt till dokumentation om [prognos](../analysis-workspace/c-forecast/forecasting.md), den nya Analysis Workspace-funktionen för att prognostisera ett standardmått eller beräknade mätvärden med valfri tidshalaritet (timma, dag, vecka, månad och år) för frihandstabeller och linjediagram. |
| Dokumentationen för att lägga till konton och platser vid export av fullständiga register har uppdaterats | Dokumentationen har uppdaterats för att återspegla mindre gränssnittsuppdateringar när ett nytt konto eller en ny plats konfigureras när [exportera hela tabeller från Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace).<p>En ny [!UICONTROL **Lägg till konto**] finns nu i [!UICONTROL **Konto**] listruta. The [!UICONTROL **Lägg till plats**] som tidigare var tillgängligt som en knapp bredvid [!UICONTROL **Platsnamn**] rullgardinsmenyn finns nu tillgänglig på själva menyn. |
| Ny information om komponentmigrering vid migrering från Adobe Analytics | Lagt till information i [Utveckling från Adobe Analytics](/help/getting-started/aa-to-cja.md) som refererar till det nya [komponentmigrering](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html) funktioner som beskrivs i Adobe Analytics Admin Guide. |
| Klarade att viss information endast är tillgänglig för administratörer | Tillagd information om att kolumnerna &quot;Senast använd&quot; och &quot;Används i&quot; beskrivs i [Beräknat måttansvarig](/help/components/calc-metrics/cm-workflow/cm-manager.md) och [Filterhantering](/help/components/filters/manage-filters.md) är bara tillgängliga för systemadministratörer. |
| Behörigheter som krävs för att exportera datauppsättningar | Ytterligare information som förklarar [behörigheter krävs](/help/admin/cja-access-control.md) för att exportera datauppsättningar till molnmål. |
| Hantera anslutningar | Uppdaterade [Hantera anslutningar](../connections/manage-connections.md) artikel, baserat på kundernas feedback. |
| Härledda fält | Tillagd sammanfattning av funktionen [begränsningar](/help/data-views/derived-fields/derived-fields.md#limitations) och förklaringar av hur man avgör antalet [operatorer](/help/data-views/derived-fields/derived-fields.md#operators) används i en funktion. |

{style="table-layout:auto"}


## 2023

| Funktion | Beskrivning |
| --- | --- |
| **December 2023** | |
| Datacenter | En artikel på Customer Journey Analytics har lagts till [värdplatser](../technotes/cja-datacenters.md). |
| Guardrails | Lagt till artikellista Customer Journey Analytics [skyddsräcken](../admin/guardrails.md). |
| Uppdateringar av valutakonvertering | Tydlig dokumentation om hur man [konfigurera valutakonvertering](/help/data-views/component-settings/format.md). |
| Uppdateringar av dokumentationen för avvikelseidentifiering | Dokumentationen för avvikelseidentifiering fanns tidigare i ett avsnitt om Virtual Analyst. Följande ändringar har gjorts: <ul><li>Termen Virtual Analyst har tagits bort från dokumentationen.</li><li>Avsnittet om [Analysidentifiering](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) har flyttats direkt under Analysis Workspace.</li></ul> |
| **Oktober 2023** | |
| Använda härlett fält för att ställa in mål | Tillagd [användningsfall](../use-cases/goals-using-derived-fields.md) artikel som illustrerar hur du använder härledda fält för att ställa in mål och rapportera om dessa. |
| Exportera fullständiga tabeller till molnet | Lagt till dokumentation om export av fullständiga tabeller med miljontals Workspace-rader till molnmål. <p>Vid export av fullständiga tabeller kan du leverera datatabeller som utformats i Workspace en gång eller enligt schema, med stöd för upp till fem uppdelningar, fem mätvärden, filter och beräknade mätvärden, allt i en sammansatt tabell. Det är utvecklingen av rapporter om Data Warehouse i Adobe Analytics, med många nya, ofta efterfrågade funktioner som inte är tillgängliga i Data Warehouse idag.</p><p>Mer information finns i [Exportera Customer Journey Analytics-rapporter till molnet](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html). |
| Rapporteringsaktivitetshanteraren | Lagt till dokumentation för Reporting Activity Manager. <p>Med Rapporteringsaktivitetshanteraren kan du se rapporteringskapaciteten för varje anslutning i organisationen. Det ger administratörer detaljerad insyn i rapporteringen av förbrukning för att enkelt kunna diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.</p> <p>Följande nya artiklar har lagts till:<ul><li>[Översikt över Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md)</li><li>[Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity.md)</li><li>[Avbryt begäranden i Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity-cancel-requests.md)</ul> |
| Nya kolumner på hanteringssidor | Dokumenterade nya kolumner som nu är tillgängliga i [Beräknat måttansvarig](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html) och [Filterhantering](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html). |
| Jämförelse med Adobe Analytics | Tillagda [översiktssida](../getting-started/aa-vs-cja/overview.md) som en introduktion till att jämföra och förstå skillnaderna mellan Customer Journey Analytics och Adobe Analytics. |
| Funktioner för ytterligare härledda fält | Uppdaterad dokumentation för den nya [`Lookup`](/help/data-views/derived-fields/derived-fields.md#lookup) funktion. |
| **September 2023** | |
| Uppdaterad struktur för artiklar för panelen Medieuppspelningstid för spenderad tid | Mappen Media Playback Time Spent har tagits bort och innehållet i mappen har kombinerats till en enda artikel: [Medieuppspelningstid spenderad panel](/help/analysis-workspace/c-panels/media-playback-time-spent.md). <p>Den här ändringen är mer i linje med dokumentationen för andra paneler.</p> |
| Funktioner för ytterligare härledda fält | Uppdaterad dokumentation för den nya [`Lowercase`](/help/data-views/derived-fields/derived-fields.md#lowercase) och [`Trim`](/help/data-views/derived-fields/derived-fields.md#trim) funktioner och ytterligare CSV-funktioner som lagts till i [`Classify`](/help/data-views/derived-fields/derived-fields.md#classify) funktion. |
| Regional datainsamling | Uppdaterat [Vanliga frågor](../getting-started/cja-faq.md#12-regional-data-collection) med information om regional datainsamling när Customer Journey Analytics används. |
| **Augusti 2023** | |
| Medieuppspelningstid spenderad panel | Uppdaterat innehåll för  [Medieuppspelningstid spenderad panel](/help/analysis-workspace/c-panels/media-playback-time-spent.md) för att förbättra läsbarheten. |
| Förbättringar i Report Builder | Uppdaterat innehåll för [Schemalägg arbetsböcker](/help/report-builder/schedule-reportbuilder.md) för att tillhandahålla information för hämtning av schemalagda aktiviteter. Uppdaterat innehåll för  [Skapa ett datablock](/help/report-builder/create-a-data-block.md) om du vill ange information om hur du använder startdatum som dimension. |
| Flyttat innehåll om hantering av schemalagda projekt | Skapade en ny artikel i Analytics Components Guide med namnet [Schemalagda projekt](/help/components/scheduled-projects-manager.md). Innehållet fanns tidigare i [Schemalägg projekt](/help/analysis-workspace/export/t-schedule-report.md) artikel i Analytics Tools Guide. |
| Funktioner i Adobe Customer Journey Analytics | Mer information finns i *Stöds på ett nytt sätt* tabellen över sessionerna i Customer Journey Analytics jämfört med Adobe Analytics. [Läs mer](../getting-started/aa-vs-cja/cja-aa.md#supported-in-a-new-way) |
| Utveckling från Adobe Analytics | Uppdaterade *(Gör om)Konfigurera marknadsföringskanaler* -avsnitt med en referens till funktionsmallen för härledda fält Marknadskanaler. [Läs mer](../getting-started/aa-to-cja.md#3-reconfigure-your-marketing-channels) |
| Snabbstartsguider för dataöverföring för mobilprogram och andra plattformar | Ytterligare startguider för dataöverföring med information om hur man importerar och använder data från mobilapplikationer eller andra plattformar (som datorapplikationer, spel på konsoler, applikationer på digitalboxar och IoT-enheter) i Customer Journey Analytics. [Läs mer](../data-ingestion/data-ingestion.md) |
| **Juli 2023** | |
| Sessionsinställningar | Ett ämne har lagts till för den här datavyinställningen. [Läs mer](/help/data-views/session-settings.md) |
| Adobe Product Analytics | Adobe Product Analytics är ett nytt sätt att interagera med data och insikter över flera kanaler i Customer Journey Analytics. Dessa nya funktioner gör det möjligt för produktteamen att självbetjäna data och insikter om sina produktupplevelser via [guidad analys](/help/guided-analysis/overview.md) &#x200B;. |
| Härledda fält | A [härlett fält](/help/data-views/derived-fields/derived-fields.md) gör att du kan definiera (ofta komplexa) dataändringar direkt med hjälp av ett anpassningsbart regelverktyg. |
| Utökat sökningsstöd för profil- och sökdata | Ger möjlighet att lägga till datauppsättningar som uppslag till fält i datauppsättningar för profiler eller uppslag. Tidigare stöddes endast händelsedatamängder. [Läs mer](/help/connections/create-connection.md) |
| Förbättringar i Report Builder | <ul><li>[Filtrera från cell för flera datablock](/help/report-builder/select-data-view.md)</li><li>[Visa och dölja rad- och kolumnrubriker](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html#build-the-data-block)</li></ul> |
| Geografiska sökningar i Edge Network | [Datastream-inställningar](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) hur har en geosökningstjänst som tillhandahåller enhetliga geografiska data. |
| **Juni 2023** | |
| Flerkanalsanalys och stygn | I väntan på kommande ändringar för att möjliggöra sammanfogning och för att ytterligare klargöra hur flerkanalsanalys kan höjas med sammanfogning redigeras dokumentation om funktionen för flerkanalsanalys för att hänvisa till [flerkanalsanalys](../use-cases/cross-channel/cross-channel.md) som Customer Journey Analytics och användningsfall, och [Stitlar](../stitching/overview.md) som en viktig funktion för att uppnå detta. |
| PowerBI- och Tableau-åtkomst till datavyer i Customer Journey Analytics | Tillägget Customer Journey Analytics BI ger SQL-åtkomst till datavyer som du har definierat i Customer Journey Analytics. [Läs mer](/help/data-views/bi-extension.md) |
| Adobe Journey Optimizer datavyer | Customer Journey Analytics-administratörer har tillgång till vissa extra datavyer i Customer Journey Analytics med namnet&quot;AJO-datavyn (Sandbox-name)&quot;. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). |
| Valutakonvertering | Uppdaterad dokumentation för [valutakonvertering](../data-views/component-settings/format.md#currency) support. |
| Uppdateringar av beräknade mätvärden | Följande uppdateringar gjordes av dokumentationen för beräknade värden för att den skulle överensstämma med den nuvarande funktionaliteten i Customer Journey Analytics: <ul><li>Listan med [standardberäknade värden](/help/components/calc-metrics/default-calcmetrics.md) finns i Customer Journey Analytics</li><li>Uppdaterade skärmdumpar och -procedurer i olika beräknade mätningsartiklar </li></ul> |
| **Maj 2023** | |
| Deep Linking-dokumentation (mobilapp) | Tillåter användare att skicka länkar till styrkort som leder dem direkt till styrkortsprojektet i appen. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) |
| Dok på &quot;Välj datavy från cell&quot; i Report Builder | Med den här funktionen kan användare välja datavyn för ett datablock från en cell. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) |
| Dokumentation för den uppdaterade startskärmen för kontrollpanelsappen för Analytics (mobilapp) | På den nya uppdaterade startskärmen kan du visa alla dina styrkort i en konsoliderad styrkortslista. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) |
| Optimeringsuppdatering | Uppdaterad artikel om [Optimera prestanda för Customer Journey Analytics](/help/admin/optimizing-performance.md) |
| Översikt över Analysis Workspace | Uppdaterat [Analysis Workspace - översikt](/help/analysis-workspace/home.md) för att inkludera mer allmän översiktsinformation och länkar till relevant innehåll. |
| Skapa projekt | Skapade en ny artikel som förklarar i detalj hur du [Skapa projekt](/help/analysis-workspace/build-workspace-project/create-projects.md) i Analysis Workspace. |
| Sortera komponenter i den vänstra listen | Lagt till information om hur du sorterar komponentlistan i den vänstra listen.Se avsnittet Sök, filtrera och sortera komponentlistan i [Komponenter - översikt](/help/components/overview.md). |
| Ta bort rader som innehåller dynamiska dimensioner från en frihandstabell | Lagt till information om hur du snabbt tar bort specifika rader som innehåller dynamiska dimensioner med hjälp av x-ikonen. Se avsnittet&quot;Snabb uteslutning av specifika rader från en tabell&quot; i [Filtrera och ordna tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| Knapp för att lägga till en visualisering på en panel | Lagt till information om en ny knapp längst ned på varje panel i Analysis Workspace som gör att du snabbt kan lägga till en visualisering. Se avsnittet&quot;Lägga till visualiseringar i en panel&quot; i [Visualiseringar - översikt](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md). |
| Dokumentation för intelligenta bildtexter | Ge nytt liv åt användarna med [naturspråkssammanfattningar](/help/analysis-workspace/visualizations/intelligent-captions.md) av en linjevisualisering. |
| Härledda fält | Lagt till dokumentation för [härledda fält](../data-views/derived-fields/derived-fields.md) funktionalitet. |
| **April 2023** |  |
| Video om hur du använder filter som dimensioner | Videon om att använda filter som dimension har uppdaterats. <p>Den här videon är länkad från [Skapa filter](/help/components/filters/create-filters.md) sida.</p> <p>Här följer en direktlänk till videon: [Använd filter som dimensioner i Analysis Workspace](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/use-filters-as-dimensions.html).</p> |
| Filterdokumentation | Lagt till artikel om hur du använder [Filter Builder](/help/components/filters/filter-builder.md). <p>Effektivare dokumentation i [Skapa filter](/help/components/filters/create-filters.md) och [Översikt över filter](/help/components/filters/filters-overview.md).</p> |
| Uppdatera till dokumentationen på panelen Experimentation | Ett avsnitt har lagts till [tolka icke-slumpmässiga dimensioner](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html#non-randomized). |
| Projektfilter (ad hoc- och snabbfilter) | Effektiv dokumentation om projektfilter och borttagen dubblettinformation. Stegen för att skapa ad hoc-filter kombineras nu med stegen för [skapa snabbfilter](/help/components/filters/quick-filters.md). |
| **Mars 2023** | |
| Integrera beslutsstyrningsdata | Lagt till innehåll som förklarar hur [integrera data från Adobe Journey Optimizer:s beslutshantering i Customer Journey Analytics](/help/integrations/ajo-od.md). |
| Skapa dataartiklar i mobilstyrkort | A [dataartikel](/help/mobile-app/create-scorecard.md#create-data-stories) är en samling datapunkter, företagskontext och relaterade mätvärden som bygger på ett centralt tema eller mätvärden. |
| Uppdaterat funktionsstöd | Uppdaterat [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md) med en tabell över funktioner som är tillgängliga i Customer Journey Analytics men inte tillgängliga eller stöds i AA. |
| Standardberäknade värden | Innehåll som förklarar [standardberäknade värden från Adobe](/help/components/calc-metrics/default-calcmetrics.md). |
| Dataordlista | <p>Lagt till ny dokumentation för Data Dictionary, inklusive en [Ökning](/help/components/data-dictionary/data-dictionary-overview.md), [Visning](/help/components/data-dictionary/view-data-dictionary.md), [Redigering](/help/components/data-dictionary/edit-entries-data-dictionary.md)och [Övervakning](/help/components/data-dictionary/monitor-data-dictionary-health.md) Data Dictionary.</p><p>Information i [Lägga till komponentbeskrivningar](/help/components/add-component-descriptions.md) har uppdaterats för att ta hänsyn till funktionen för datamordlista.</p> |
| Länkdelning för projekt (ingen inloggning krävs) | <p>Befintlig dokumentation som förklarar hur man delar en skrivskyddad länk till ett projekt med personer som inte har tillgång till Analysis Workspace har uppdaterats.</p> <p>Uppdaterad användardokumentation innehåller [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md) och [Skapa delningsbara länkar](/help/analysis-workspace/curate-share/shareable-links.md).</p> <p>Alternativ för administratörer lades till i [Inställningar](/help/analysis-workspace/user-preferences.md).</p> |
| **Februari 2023** | |
| Jämför Customer Journey Analytics med BI-lösningar | Nytt dokument på en [jämförelse](../getting-started/cja-vs-bi.md) från Customer Journey Analytics till vanliga BI-lösningar. |
| Uppdatera till publikdokumentation | Nytt avsnitt på [latenshändelser](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency). |
| Uppdatera till publikdokumentation | När du har skapat en målgrupp skapar Adobe en Experience Platform [direktuppspelningssegment för varje ny Customer Journey Analytics-publik](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created). |
| Arbetsytekalendrar och datumintervall | Uppdaterat innehåll som beskriver relativa datumintervall, uppdateringar av formelberäkning och ändringar i kalendergränssnittet. Se [Om relativa paneldatumintervall](/help/components/date-ranges/calendar.md#relative-panel-dates). |
| Mobil styrkort | Nytt dokumentationsavsnitt som beskriver hur du visar och döljer datumintervall för jämförelse. Se [Visa datumintervall för jämförelse](/help/mobile-app/create-scorecard.md#show-comparison-dates) i Customer Journey Analytics. |
| **Januari 2023** | |
| Filtrera och ordna tabeller | Uppdaterat innehåll (inklusive att lägga till procedurer och förklara tillgängliga alternativ) i [Filtrera och ordna tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) artikel. Artikelns namn ändrades från&quot;Sidnumrering, filtrering och sortering&quot;. |
| Snabbstartsguider för dataöverföring | Nytt dokumentationsavsnitt om hur [importera och använda data](/help/data-ingestion/data-ingestion.md) i Customer Journey Analytics. |
| Arbetsytemappar | Särskilda sidor för [Mapphantering](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Användarinställningar för arbetsyta | Många andra användarinställningar finns nu tillgängliga i [Inställningar](/help/analysis-workspace/user-preferences.md). |
| Spara automatiskt för arbetsyteprojekt | Uppdaterat innehåll som inkluderar autosparfunktion i [Spara projekt](/help/analysis-workspace/build-workspace-project/save-projects.md). |
| Landningssida | Nya uppdateringar av landningssidor [landningssida](/help/getting-started/landing.md). |
| Schemalägg arbetsböcker | Dedikerad sida som beskriver hur [Schemalägg arbetsböcker](/help/report-builder/schedule-reportbuilder.md) i Report Builder. |
| Stöd för objektmatriser för profil- och uppslagsdatauppsättningar | Uppdaterat [Använda arrayer med objekt](/help/use-cases/object-arrays.md) och [Intressanta Adobe Experience Platform-målgrupper](/help/use-cases/data-ingestion/ingest-aep-segments.md) för att spegla stöd för objektmatriser för profil- och uppslagsdatauppsättningar. |

{style="table-layout:auto"}

## 2022

| Datum | Uppdatera beskrivning |
| --- | --- |
| **December 2022** |  |
| 16 december 2022 | Nytt ämne [mäta och hantera dataanvändningen i Customer Journey Analytics](/help/admin/estimate-usage.md). |
| **Oktober 2022** | |
| Oktober 2022 | Nytt ämne [lösenordsskydd för schemalagda projekt](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#password). Den här funktionen har stöd för [HIPAA-beredskap](https://www.adobe.com/trust/compliance/hipaa-ready.html). |
| Oktober 2022 | Nytt ämne [Kundhanterade nycklar](/help/privacy/cmk.md). Den här funktionen har stöd för [HIPAA-beredskap](https://www.adobe.com/trust/compliance/hipaa-ready.html). |
| Oktober 2022 | Nytt ämne [Customer Journey Analytics granskningslogg](/help/privacy/audit-log.md). |
| Oktober 2022 | Nytt ämne [Sammanfattning av nyckelmått](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html) visualisering. |
| Oktober 2022 | Nytt avsnitt på [datum- och datumfunktioner i datavyer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#date) |
| Oktober 2022 | Mobilapp: Nytt avsnitt om [anpassade detaljvyer](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#view-detail-slides). |
| Oktober 2022 | Uppdateringar av [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md) ämne. |
| **September 2022** | |
| September 2022 | Nytt användningsexempel på [Migrera Google Analytics-data till Customer Journey Analytics](/help/use-cases/ga/overview.md). |
| September 2022 | Nytt ämne [Kombinationsdiagram](/help/analysis-workspace/visualizations/combo-charts.md) i Workspace. |
| September 2022 | Nytt ämne [Panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md) i Workspace. |
| **Augusti 2022** | |
| Augusti 2022 | Adobe Experience Platform artikel om [Stöd för olika regioner för Analytics-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html). |
| Augusti 2022 | Avsevärt uppdaterad artikel om [Åtkomstkontroll för Customer Journey Analytics](/help/admin/cja-access-control.md). |
| Augusti 2022 | Ny artikel på [Customer Journey Analytics stöd för dataförvaltningsrubriker och datapolicyer](/help/data-views/data-governance.md). |
| Augusti 2022 | Ny artikel på [Jämföra terminologi för analysdata som skickas via Analytics-källkopplingen](/help/getting-started/aa-vs-cja/terminology.md). |
| Augusti 2022 | Ny dokumentation om [Målgruppspublicering i kundprofil i realtid](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html). |
| **Juli 2022** | |
| Juli 2022 | [Medieuppspelningstid spenderad panel](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) dokumentation. |
| Juli 2022 | [Media Concurrent Viewer-panel](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) dokumentation. |
| Juli 2022 | [Första sessionen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) rapporteringsdokumentation. |
| **Juni 2022** | |
| Juni 2022 | Ny artikel på [AAID, ECID, AACUSTOMID och Analytics-källkopplingen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html) |
| Juni 2022 | Ny artikel på [Adobe Analytics bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep för källkopplingen för Analytics](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md). |
| Juni 2022 | Ny artikel på [virtuella rapporteringsmiljöer och sandlådemiljöer](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md). |
| Juni 2022 | Ny artikel på [jämföra databehandling i Adobe Analytics och Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md). |
| Juni 2022 | Ny artikel på [kombinera rapportsviter med olika scheman](/help/use-cases/aa-data/combine-report-suites.md). |
| Juni 2022 | Ny artikel på [dela anteckningar i mobilstyrkort](/help/components/annotations/mobile-annotations.md). |
| Juni 2022 | Ny artikel på [Analytics Labs i Customer Journey Analytics](/help/labs/labs.md). |
| Juni 2022 | Nytt avsnitt på [stöd för numeriska fält som söknycklar och sökvärden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric). |
| Juni 2022 | Uppdateringar av [Arbetsflöde för visualisering av flöde](/help/analysis-workspace/visualizations/c-flow/create-flow.md). |
| **Maj 2022** | |
| Maj 2022 | Avsevärt uppdaterad artikel om [skapa anslutningar](/help/connections/create-connection.md) i Customer Journey Analytics. |
| Maj 2022 | Ny artikel om hur man [hantera datablock i Customer Journey Analytics Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html). |
| Maj 2022 | Ny artikel på [inhämta Adobe Experience Platform-målgrupper i Customer Journey Analytics](/help/use-cases/data-ingestion/ingest-aep-segments.md). |
| **April 2022** | |
| April 2022 | Dokumentation på [dimensionsdelsträngar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html). |
| April 2022 | Nytt [Customer Journey Analytics användarhandbok för Adobe Analytics](/help/getting-started/aa-to-cja-user.md). |
| **Mars 2022** | |
| Mars 2022 | Nytt [API-dokumentation för Customer Journey Analytics Annotations](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/). |
| Mars 2022 | Ny dokumentation om [Anteckningar i arbetsytan](/help/components/annotations/overview.md). |
| Mars 2022 | Innehåll som uppdaterats avsevärt på [beräknar anslutningsstorlek](/help/getting-started/cja-faq.md). |
| **Februari 2022** | |
| Februari 2022 | En ny guide som riktar sig till administratörer som flyttar från Adobe Analytics till Customer Journey Analytics: [Adobe Analytics till Customer Journey Analytics evolutionen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html) |
| **Januari 2022** | |
| Januari 2022 | Nytt användningsexempel för [Använda bindningsdimensioner och mätvärden i Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md) |
| Januari 2022 | Dokumentation om tillagda nya funktioner på [bindningsdimensioner och mätvärden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) och på nya [[!UICONTROL First Known] och [!UICONTROL Last Known] allokeringsinställningar](/help/data-views/component-settings/persistence.md#allocation-settings) |
| Januari 2022 | Ny artikel på [jämföra era Adobe Analytics-data med Analytics-data i Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html) |

{style="table-layout:auto"}

## 2021

| Datum | Uppdatera beskrivning |
| --- | --- |
| **November 2021** | |
| November 2021 | Uppdaterad dokumentation för [[!UICONTROL Records skipped]](/help/connections/manage-connections.md) på sidan Anslutningsinformation. |
| **Oktober 2021** | |
| Oktober 2021 | Dokumentation för [Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/report-buider-overview.html#) i Customer Journey Analytics. |
| Oktober 2021 | Customer Journey Analytics [Granskningslogg](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) API-dokumentation |
| Oktober 2021 | Dokumenterad [Visualiseringar för kontrollpaneler i Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#apply-visualizations) |
| Oktober 2021 | Dok för rullande fönster för [!UICONTROL Connection] [datalagring](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html#set-rolling-window-for-connection-data-retention). |
| **September 2021** | |
| September 2021 | [Metrisk deduplicering](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html) doc |
| September 2021 | [Tidsstöd för sommartid vid rapportering](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#calendar) |
| September 2021 | [Kundkalendrar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#calendar) dokumentation |
| September 2021 | [Booleska fält](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/behavior.html) dokumentation |
| September 2021 | Öka komponentinställningarna i datavyer till enskilda filer:<ul><li>[[!UICONTROL Component] översikt över inställningar](/help/data-views/component-settings/overview.md)</li><li>[[!UICONTROL Attribution] komponentinställningar](/help/data-views/component-settings/attribution.md)</li><li>[[!UICONTROL Behavior] komponentinställningar](/help/data-views/component-settings/behavior.md)</li><li>[[!UICONTROL Format] komponentinställningar](/help/data-views/component-settings/format.md)</li><li>[[!UICONTROL Include/exclude] komponentinställningar](/help/data-views/component-settings/include-exclude-values.md)</li><li>[[!UICONTROL Metric deduplication] komponentinställningar](/help/data-views/component-settings/metric-deduplication.md)</li><li>[[!UICONTROL No value] komponentinställningar](/help/data-views/component-settings/no-value-options.md)</li><li>[[!UICONTROL Persistence] komponentinställningar](/help/data-views/component-settings/persistence.md)</li><li>[[!UICONTROL Value bucketing] komponentinställningar](/help/data-views/component-settings/value-bucketing.md)</li></ul> |
| September 2021 | Nytt avsnitt på [konsekvenser av sammanslagna rapportsviter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#6.-Consi-when-merging-report-suites-in-cja) i Customer Journey Analytics. |
| **Augusti 2021** | |
| Augusti 2021 | Nytt avsnitt på den förbättrade [Anslutningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html) upplevelsen i Customer Journey Analytics. |
| Augusti 2021 | Nytt avsnitt på [skiftlägeskänslighet i datavy-dimensioner](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-behavior-settings). |
| **Juni 2021** | |
| Juni 2021 | Ny dokumentation om [tidigare projektversioner](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/build-workspace-project/save-projects.html#previous-version) i Workspace. |
| **April 2021** | |
| April 2021 | Nytt ämne [beständighet](/help/data-views/component-settings/persistence.md). |
| April 2021 | Ny dokumentation om stöd för schemalagda projekt i Workspace. |
| April 2021 | Nya ämnen på [förbättrad datavyer](/help/data-views/data-views.md). |
| April 2021 | Nya ämnen om [inhämta Google Analytics-data](/help/use-cases/ga/overview.md) och [analysera dessa data](/help/use-cases/ga/report.md). |
| April 2021 | Lagt till ämne om [schemalagda rapporter](/help/analysis-workspace/export/t-schedule-report.md) i Workspace. |
| April 2021 | Nytt ämne [högkardinalitetsmått i Customer Journey Analytics](/help/components/dimensions/high-cardinality.md). |
| **Mars 2021** | |
| Mars 2021 | Tillagt ämne om stöd för [Kontrollpaneler för analyser](/help/mobile-app/home.md) (mobilapp). |
| Mars 2021 | Nytt ämne [användarinställningar](/help/analysis-workspace/user-preferences.md) i Workspace. |
| **Februari 2021** | |
| Februari 2021 | Nytt ämne om att använda [Marketing Channel-dimensioner i Adobe Experience Platform](/help/use-cases/aa-data/marketing-channels.md). |
| Februari 2021 | Publicera det nya [CUSTOMER JOURNEY ANALYTICS API](https://www.adobe.io/cja-apis/docs/) dokumentation. |
| **Januari 2021** | |
| Januari 2021 | Nytt ämne [lägga till standardsökningar i datauppsättningen](/help/connections/standard-lookups.md). |

{style="table-layout:auto"}

## 2020

| Datum | Uppdatera beskrivning |
| --- | --- |
| 13 november 2020 | Nya ämnen om [Flerkanalsanalys](/help/stitching/overview.md)som gör att du kan ändra inmatningen av en datauppsättnings person-ID och som möjliggör en sömlös kombination av flera datauppsättningar. |
| 13 november 2020 | Ett nytt användningsexempel på [importera callcenter och webbdata](/help/use-cases/cross-channel/call-center.md) lades till. |
| 10 november 2020 | Ett avsnitt om konsekvenserna av att ta bort datakomponenter har lagts till i [Vanliga frågor](/help/getting-started/cja-faq.md). |
| 2 november 2020 | Uppdateringar av [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md) sida. |
| November 2020 | Lagt till innehåll på [ta bort begränsningar för bakgrundsfyllning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#backfill-historical-data) för anslutningar. |
| 7 oktober 2020 | Lagt till ett ämne [kombinerade händelsedatamängder](/help/connections/combined-dataset.md). |
| 15 september 2020 | Lagt till ett ämne [dataintag](/help/data-ingestion/data-ingestion.md). |
| 2 september 2020 | Uppdaterat avsnitt om [användarbehörigheter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). |
| 7 augusti 2020 | Nytt ämne [Användningsexempel B2B - sökdatauppsättning](/help/use-cases/b2b/b2b.md) tillagd. |
| Juli 2020 | Ytterligare information om [Identitetskarta, alternativ för person-ID](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html). |
| Juli 2020 | Nytt ämne [objektarrayer](/help/use-cases/object-arrays.md) eller&quot;dataherarkier&quot; har lagts till. |
| 14 april 2020 | Uppdateringar av det senaste användargränssnittet i [Skapa anslutningar](/help/connections/create-connection.md) ämne. |
| 27 februari 2020 | Uppdateringar av [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md) |
| December 2019 | Första utkastet till dokumentation om Customer Journey Analytics |

{style="table-layout:auto"}
