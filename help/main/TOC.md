---
git-repo: https://github.com/AdobeDocs/analytics-platform.sv-SE
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Användarhandbok om Customer Journey Analytics
user-guide-description: Läs mer om Adobe Customer Journey Analytics och hur du använder Analysis Workspace med data från Experience Platform.
breadcrumb-title: Användarhandbok om Customer Journey Analytics
source-git-commit: c78bb901b40eb31fe5a08f4bd8b5ee797e43d18f
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 10%

---


# Adobe Customer Journey Analytics Guide {#using}

+ [Adobe Customer Journey Analytics Guide](../getting-started/cja-landing.md)

+ Versionsinformation {#releases}
   + [Senaste versionen](../release-notes/latest.md)
   + [2025 års utgåvor](../release-notes/2025.md)
   + [2024 års utgåvor](../release-notes/2024.md)
   + [2023 års utgåvor](../release-notes/2023.md)
   + [2022 års utgåvor](../release-notes/2022.md)
   + [2021 års utgåvor](../release-notes/2021.md)
   + [2020-versioner](../release-notes/2020.md)
   + [Strategi för funktionsreleaser](../release-notes/releases.md)
   + [Dokumentationsuppdateringar](../release-notes/doc-changes.md)

+ Kom igång {#cja-overview}
   + Customer Journey Analytics {#cja-b2c-overview}
      + [Översikt](../getting-started/cja-overview.md)
      + [Snabbstartsguide](../getting-started/cja-getting-started.md)
      + [Landningssida](../getting-started/landing.md)
      + [Frågor och svar](../getting-started/cja-faq.md)
      + [Jämför med BI-lösningar](../getting-started/cja-vs-bi.md)
      + [AI-assistenten](../ai-assistant.md)
      + [Agent för datainsikter](../data-analysis-ai.md)
   + Customer Journey Analytics B2B edition {#cja-b2b}
      + [Översikt](/help/getting-started/cja-b2b-edition.md)
      + [B2B-koncept och -funktioner](/help/getting-started/cja-b2b-concepts-features.md)
      + [Snabbstartsguide](/help/getting-started/cja-b2b-quick-start-guide.md)

+ Customer Journey Analytics och Adobe Analytics {#compare-aa-cja}
   + Uppgradera till Customer Journey Analytics {#upgrade-to-cja}
      + [Kom igång](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Välj uppgraderingsväg](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Skicka data till plattformen](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Behåll historiska data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [Rekommenderad uppgraderingsprocess](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + Arkitekt och skapa ett schema {#schema}
         + [Arkitektur av ditt schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
         + [Skapa ditt schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
         + [Använd ditt befintliga schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + Skapa ett datastream {#create-datastream}
         + [Skapa ett datastream](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
         + [Lägg till plattform som en tjänst](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + Skapa datauppsättningar {#create-datasets}
         + [Skapa en datauppsättning](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
         + [Skapa uppslagsdatauppsättningar för klassificeringar](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
         + [Övervaka datamängdsinmatning](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + Implementera Web SDK med taggar {#create-tags}
         + [Skapa en tagg för din egenskap](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
         + [Lägg till tillägget Web SDK i taggen](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
         + [Implementera taggen loader för Web SDK-tillägget](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
         + [Lägg till logik för XDM-datainsamling i taggen](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [Implementera Web SDK manuellt](/help/getting-started/cja-upgrade/cja-upgrade-manual.md)
      + [Implementera Web SDK med API](/help/getting-started/cja-upgrade/cja-upgrade-api.md)
      + [Skapa en anslutning](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [Skapa en datavy](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [Skapa ett härlett fält för marknadsföringskanal](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Validera dataflöde](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [Ställ in direktuppspelad mediesamling](/help/getting-started/cja-upgrade/cja-upgrade-streaming-media.md)
      + Behåll historiska data med Analytics-källkopplingen {#historical-data-source-connector}
         + [Skapa ett XDM-schema för Analytics-källkopplingen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
         + [Skapa Analytics-källkopplingen och kartfälten](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
         + [Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Utvärdera när Adobe Analytics ska inaktiveras](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)
      + [Inaktivera Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + Alternativa uppgraderingsmetoder {#alternative-upgrade-methods}
         + [Använda AppMeasurement datainsamling](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)
         + [Skicka datalager](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)
         + [Källanslutning för analyser](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)
      + Andra uppgraderingsscenarier {#other-upgrade-scenarios}
         + [Gå från Analytics-källkopplingen till Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
         + [Uppgradera från en icke-Adobe Analytics-lösning](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + Ytterligare information {#additional-information}
         + [Analysimplementering](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
         + [Funktionssupport för Adobe Analytics vid uppgradering](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
         + [Customer Journey Analytics-funktioner](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md)
         + [Implementeringsalternativ för SDK](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md)
         + [Konfigurera Adobe Analytics Web SDK for Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)
         + [Använd personalisering med Adobe Journey Optimizer](/help/getting-started/cja-upgrade/cja-upgrade-personalization-journeyoptimizer.md)
   + Jämförelse med Adobe Analytics {#cja-aa-comparison}
      + [Översikt](../getting-started/aa-vs-cja/overview.md)
      + [Använd Adobe Analytics-data](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Funktioner](../getting-started/aa-vs-cja/cja-aa.md)
      + [Jämför terminologi](../getting-started/aa-vs-cja/terminology.md)
      + [Jämför databearbetning](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Miljö](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Analysbearbetning jämfört med Data Prep](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Analysidentiteter](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Utveckling från Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Användarhandbok för Adobe Analytics](../getting-started/aa-to-cja-user.md)

+ Intag av data {#cja-data-ingestion}
   + [Översikt över dataöverföring](../data-ingestion/data-ingestion.md)
   + Infoga och använda snabbstartguider{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [Server-API](../data-ingestion/serverapi.md)
      + [Batchdata](../data-ingestion/batch.md)
      + [Strömmande data](../data-ingestion/streaming.md)
      + [Source-anslutningar](../data-ingestion/sources.md)

+ Anslutningar {#cja-connections}
   + [Anslutningar - översikt](../connections/overview.md)
   + [Skapa eller redigera en anslutning](../connections/create-connection.md)
   + [Hantera anslutningar](../connections/manage-connections.md)
   + [Kombinerade händelsedatamängder](../connections/combined-dataset.md)
   + [Standardsökningar](../connections/standard-lookups.md)
   + [B2B-sökningar](../connections/transform-datasets-b2b-lookups.md)

+ Datavyer {#cja-dataviews}
   + [Översikt över datavyer](../data-views/data-views.md)
   + [Skapa eller redigera en datavy](../data-views/create-dataview.md)
   + [Sessionsinställningar](../data-views/session-settings.md)
   + Komponentinställningar {#component-settings}
      + [Översikt över komponentinställningar](../data-views/component-settings/overview.md)
      + [Tillskrivning](../data-views/component-settings/attribution.md)
      + [Beteende](../data-views/component-settings/behavior.md)
      + [Format](../data-views/component-settings/format.md)
      + [Inkludera exkluderingsvärden](../data-views/component-settings/include-exclude-values.md)
      + [Metrisk deduplicering](../data-views/component-settings/metric-deduplication.md)
      + [Inga värdealternativ](../data-views/component-settings/no-value-options.md)
      + [Persistence](../data-views/component-settings/persistence.md)
      + [Delsträng](../data-views/component-settings/substring.md)
      + [Sammanfattningsdatagrupp](../data-views/component-settings/summary-data-group.md)
      + [Värdebuckning](../data-views/component-settings/value-bucketing.md)
   + [Standard, komponentreferens](../data-views/component-reference.md)
   + [BI-tillägg](../data-views/bi-extension.md)
   + [Härledda fält](../data-views/derived-fields/derived-fields.md)
   + [Sammanfattningsdata](../data-views/summary-data.md)
   + [Etiketter och profiler](../data-views/data-governance.md)
   + Delade mått{#shared-metrics-dimensions}
      + [Översikt](/help/data-views/shared-metrics-dimensions/smd-overview.md)
      + [Redigerare](/help/data-views/shared-metrics-dimensions/shared-component-editor.md)

+ verktyg {#tools}
   + Tillgångsöverföring {#asset-transfer}
      + [Överför resurser](../tools/asset-transfer/transfer-assets.md)
   + Produktanvändning {#product-usage}
      + [Översikt](../tools/product-usage/usage-overview.md)
      + [Datainställningar](../tools/product-usage/data-settings.md)
      + [Inställningar för avanmälan](../tools/product-usage/opt-out-settings.md)

+ Workspace-projekt {#cja-workspace}
   + [Översikt över Analysis Workspace](../analysis-workspace/home.md)
   + [Utför grundläggande analys](../analysis-workspace/perform-basic-analysis.md)
   + [Avancerad analys](../analysis-workspace/perform-adv-analysis.md)
   + Projekt {#build-workspace-project}
      + [Översikt](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Skapa projekt](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Öppna projekt](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Kommentera projekt](/help/analysis-workspace/build-workspace-project/comment-projects.md)
      + [Spara projekt](../analysis-workspace/build-workspace-project/save-projects.md)
      + Mappar i Workspace {#workspace-folders}
         + [Om mappar](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Skapa mappar och undermappar](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Hantera mappar](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Lägg till eller flytta projekt till mappar](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Snabbtangenter (kortkommandon)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Färgpaletter](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Visa densitet](../analysis-workspace/build-workspace-project/view-density.md)
   + Mallar {#templates}
      + [Använd mallar](../analysis-workspace/templates/use-templates.md)
      + [Skapa och hantera mallar](../analysis-workspace/templates/create-templates.md)
   + Visualiseringar {#visualizations}
      + [Översikt](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Hantera datakällor](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [Intelligenta bildtexter](../analysis-workspace/visualizations/intelligent-captions.md)
      + Frihandsregister {#freeform-table}
         + [Översikt](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [Skapa hyperlänkar](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + Kolumn- och radinställningar {#column-row-settings}
            + [Kolumninställningar](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Radinställningar](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Dynamiska och statiska objekt](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrera och ordna tabeller](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Workspace summor](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Kohortabell {#cohort-table}
         + [Översikt](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Konfigurera](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Användningsexempel](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Utfall {#fallout}
         + [Översikt](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Konfigurera](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Interdimensionellt utfall](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Använd segment](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flöde {#flow}
         + [Översikt](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Konfigurera](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flerdimensionella flöden](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + Reseduk {#journey-canvas}
         + [Översikt](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [Konfigurera](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [Felsökning](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [Yta (staplad)](../analysis-workspace/visualizations/area.md)
      + [Stapel (staplad)](../analysis-workspace/visualizations/bar.md)
      + [Punkt](../analysis-workspace/visualizations/bullet-graph.md)
      + [Kombination](../analysis-workspace/visualizations/combo-charts.md)
      + [Munk](../analysis-workspace/visualizations/donut.md)
      + [Histogram](../analysis-workspace/visualizations/histogram.md)
      + [Vågrätt streck (staplat)](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Sammanfattning av nyckelmått](../analysis-workspace/visualizations/key-metric.md)
      + [Linje](../analysis-workspace/visualizations/line.md)
      + [Karta](/help/analysis-workspace/visualizations/map.md)
      + [Spridning](../analysis-workspace/visualizations/scatterplot.md)
      + [Avsnittshuvud](/help/analysis-workspace/visualizations/section-header.md)
      + [Sammanfattningsnummer och ändring](../analysis-workspace/visualizations/summary-number-change.md)
      + [Text](../analysis-workspace/visualizations/text.md)
      + [Trädkarta](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Panel {#panels}
      + [Översikt](../analysis-workspace/c-panels/panels.md)
      + [Tom panel](../analysis-workspace/c-panels/blank-panel.md)
      + [Tillskrivning](../analysis-workspace/c-panels/attribution.md)
      + [Experimentation](../analysis-workspace/c-panels/experimentation.md)
      + [Frihandsfigur](../analysis-workspace/c-panels/freeform-panel.md)
      + [Genomsnittlig minutmålgrupp för media](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Medievisningsprogram för samtidig användning](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Medieuppspelningstid](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Nästa eller föregående objekt](../analysis-workspace/c-panels/next-previous.md)
      + [Snabba insikter](../analysis-workspace/c-panels/quickinsight.md)
   + Kuratera, dela och schemalägg projekt {#curate-share}
      + [Översikt](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Kuratprojekt](../analysis-workspace/curate-share/curate.md)
      + [Dela projekt](../analysis-workspace/curate-share/share-projects.md)
      + [Skapa delningsbara länkar](../analysis-workspace/curate-share/shareable-links.md)
      + [projekt med endast visning](../analysis-workspace/curate-share/view-only-projects.md)
   + Exportera {#export}
      + [Översikt](../analysis-workspace/export/export-project-overview.md)
      + [Ladda ned](../analysis-workspace/export/download-send.md)
      + [Skicka till andra](../analysis-workspace/export/t-schedule-report.md)
      + [Exportera till molnet](../analysis-workspace/export/export-cloud.md)
   + Avvikelseidentifiering {#anomaly-detection}
      + [Översikt](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Visa avvikelser](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Statistisk teknik](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Prognos {#forecasting}
      + [Översikt](../analysis-workspace/c-forecast/forecasting.md)
      + [Visa prognoser](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Statistisk teknik](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Innehållsförteckning](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
   + [Användarinställningar](../analysis-workspace/user-preferences.md)
   + Vanliga frågor och svar om Workspace med mera {#workspace-faq}
      + [Frågor och svar](../analysis-workspace/workspace-faq/faq.md)
      + [Felmeddelanden](../analysis-workspace/workspace-faq/error-messages.md)
      + [Begränsningar](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Administrationskrav](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Tillgänglighet](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Content Analytics {#content-analytics}
   + [Översikt](/help/content-analytics/content-analytics.md)
   + Rapport {#report}
      + [Översikt](/help/content-analytics/report/report.md)
      + [Komponenter](/help/content-analytics/report/components.md)
   + Konfiguration {#configuration}
      + [Översikt](/help/content-analytics/config/configuration.md)
      + [Guidad konfiguration](/help/content-analytics/config/guided.md)
      + [Manuell konfiguration](/help/content-analytics/config/manual.md)
      + [Datainsamling](/help/content-analytics/config/datacollection.md)

+ Kontrollpaneler för analyser {#cja-dashboards}
   + [Översikt](../mobile-app/home.md)
   + [Läraruppgifter](../mobile-app/curator.md)
   + [Skapa mobilstyrkort](../mobile-app/create-scorecard.md)
   + [Hantera styrkort för mobila enheter](../mobile-app/manage-scorecard.md)
   + [Konfigurera chefer för att använda kontrollpaneler](../mobile-app/set-up-execs.md)
   + [Snabbguide för chefsanvändare](../mobile-app/executive.md)

+ Guidad analys {#guided-analysis}
   + [Översikt](../guided-analysis/overview.md)
   + [Aktiv tillväxt](../guided-analysis/types/active-growth.md)
   + [Konverteringstrender](../guided-analysis/types/conversion-trends.md)
   + [Engagemang](../guided-analysis/types/engagement.md)
   + [Effekt för första användningen](../guided-analysis/types/first-use-impact.md)
   + [Frekvens](../guided-analysis/types/frequency.md)
   + [Tratt](../guided-analysis/types/funnel.md)
   + [Nettotillväxt](../guided-analysis/types/net-growth.md)
   + [Frisläpp påverkan](../guided-analysis/types/release-impact.md)
   + [Kvarhållning](../guided-analysis/types/retention.md)
   + [Tidslinje](../guided-analysis/types/timeline.md)
   + [Trender](../guided-analysis/types/trends.md)
   + [Användningsexempel](../guided-analysis/industry-use-cases.md)
   + [Vanliga frågor och svar](../guided-analysis/faq.md)

+ Komponenter {#cja-components}
   + [Översikt](../components/overview.md)
   + [Använda komponenter i Analysis Workspace](../components/use-components-in-workspace.md)
   + [Lägga till komponentbeskrivningar](../components/add-component-descriptions.md)
   + Anteckningar {#annotations}
      + [Översikt över anteckningar](../components/annotations/overview.md)
      + [Skapa anteckningar](../components/annotations/create-annotations.md)
      + [Hantera anteckningar](../components/annotations/manage-annotations.md)
      + [Visa anteckningar](../components/annotations/view-annotations.md)
      + [Mobilanteckningar](../components/annotations/mobile-annotations.md)
   + [Schemalagda projekt](../components/scheduled-projects-manager.md)
   + Målgrupper {#audiences}
      + [Översikt över målgrupper](../components/audiences/audiences-overview.md)
      + [Skapa och publicera målgrupper](../components/audiences/publish.md)
      + [Hantera målgrupper](../components/audiences/manage.md)
   + Mått {#dimensions}
      + [Översikt över dimensioner](../components/dimensions/overview.md)
      + [Förhandsvisa dimensioner](../components/dimensions/view-dimensions.md)
      + [Dela upp dimensioner](../components/dimensions/t-breakdown-fa.md)
      + [Tidsdelningsdimensioner](../components/dimensions/time-parting-dimensions.md)
      + [Höga kardinaldimensioner](../components/dimensions/high-cardinality.md)
   + [Mätvärden](../components/apply-create-metrics.md)
   + Segment {#cja-filters}
      + [Översikt](../components/filters/filters-overview.md)
      + [Skapa segment](../components/filters/create-filters.md)
      + [Skapa segment](../components/filters/filter-builder.md)
      + [Snabbsegment](../components/filters/quick-filters.md)
      + [Sekventiella segment](../components/filters/seg-sequential-build.md)
      + [Dela segment](../components/filters/filters-share.md)
      + [Tagga segment](../components/filters/filters-tag.md)
      + [Filtrera listan med segment](../components/filters/filters-filter.md)
      + [Markera segment som favoriter](../components/filters/filters-favorite.md)
      + [Godkänn segment](../components/filters/filters-approve.md)
      + [Kopiera segment](../components/filters/filters-copy.md)
      + [Hantera segment](../components/filters/manage-filters.md)
      + [Operatorer](../components/filters/operators.md)
   + Beräknade mått {#cja-calcmetrics}
      + [Översikt](../components/calc-metrics/calc-metr-overview.md)
      + Arbetsflöde för beräknade mätvärden {#cm-workflow}
         + [Skapa beräknade mått](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Bygg beräknade värden](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Hitta mätvärden](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Mättyp och attribuering](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Bygg ett deltagandemått](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Segmenterade mätvärden](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Stapla och ersätta segment](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrera beräknade värden](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Markera beräknade värden som favoriter](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Kopiera beräknade värden](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Använd funktioner](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Tagga beräknade värden](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Godkänn beräknade värden](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Dela beräknade värden](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Hantera beräknade värden](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [Exempel](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [Mallar för beräknade mätvärden](../components/calc-metrics/default-calcmetrics.md)
      + [Grundfunktioner](../components/calc-metrics/cm-functions.md)
      + [Avancerade funktioner](../components/calc-metrics/cm-adv-functions.md)
   + Datumintervall {#cja-date-ranges}
      + [Översikt](../components/date-ranges/overview.md)
      + [Skapa datumintervall](../components/date-ranges/create.md)
      + [Hantera datumintervall](../components/date-ranges/manage.md)
      + [Datumjämförelse](../components/date-ranges/time-comparison.md)
      + [Exempel](../components/date-ranges/custom-date-ranges.md)
   + Aviseringar {#alerts}
      + [Översikt](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [Skapa aviseringar](/help/components/c-intelligent-alerts/alert-builder.md)
      + [Hantera aviseringar](/help/components/c-intelligent-alerts/alert-manager.md)
      + [Jämförelse av funktioner](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [Användningsexempel](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + Export {#exports}
      + [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md)
      + [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md)
      + [Hantera platser för molnexport](/help/components/exports/manage-export-locations.md)
      + [Hantera exporter](/help/components/exports/manage-exports.md)
      + [Hantera exportloggar](/help/components/exports/manage-export-logs.md)
      + [Felsöka exporter](/help/components/exports/troubleshoot-exports.md)
   + Dataordlista {#data-dictionary}
      + [Översikt](../components/data-dictionary/data-dictionary-overview.md)
      + [Visa komponentinformation i Data Dictionary](../components/data-dictionary/view-data-dictionary.md)
      + [Redigera komponentposter i Data Dictionary](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Övervaka dataordlistans hälsa](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Översikt](../report-builder/report-buider-overview.md)
   + [Report Builder](../report-builder/report-builder-setup.md)
   + [Skapa ett datablock](../report-builder/create-a-data-block.md)
   + [Report Builder nav](../report-builder/report-builder-hub.md)
   + [Välj en datavy](../report-builder/select-data-view.md)
   + [Välj ett datumintervall](../report-builder/select-date-range.md)
   + [Arbeta med segment](../report-builder/work-with-filters.md)
   + [Filterdimensioner](../report-builder/filter-dimensions.md)
   + [Hantera datablock](../report-builder/manage-reportbuilder.md)
   + [Schemalägg arbetsböcker](../report-builder/schedule-reportbuilder.md)
   + [Begränsade etiketter](../report-builder/restricted-labels.md)
   + [Report Builder-inställningar](../report-builder/report-builder-settings.md)


+ Rapporteringsaktivitetshanteraren {#reporting-activity-manager}
   + [Översikt](../reporting-activity-manager/reporting-activity-overview.md)
   + [Visa rapporteringsaktivitet](../reporting-activity-manager/reporting-activity.md)
   + [Avbryt rapporteringsbegäranden](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Stitlar {#stitching}
   + [Översikt](/help/stitching/overview.md)
   + [Fältbaserad stygn](/help/stitching/fbs.md)
   + [Diagrambaserad stygn](/help/stitching/gbs.md)
   + [Använd stygn](/help/stitching/use-stitching.md)
   + [Skapa och hantera sammanslagna datauppsättningar](/help/stitching/stitching-ui.md)
   + [Vanliga frågor](/help/stitching/faq.md)

+ Adobe-integreringar {#integrations}
   + [Översikt](/help/integrations/overview.md)
   + [Integrera Adobe Analytics](/help/integrations/aa.md)
   + [Integrera mål](/help/integrations/at.md)
   + [Integrera Journey Optimizer-data](/help/integrations/ajo.md)
   + [Integrera beslutsstyrningsdata](/help/integrations/ajo-od.md)
   + [Integrera kundens AI](/help/integrations/customer-ai.md)

+ Dataförvaltning {#cja-privacy}
   + [Dataförvaltning](../privacy/privacy-overview.md)
   + [Granskningslogg](../privacy/audit-log.md)
   + [Kundhanterade nycklar](../privacy/cmk.md)

+ Användningsexempel {#cja-usecases}
   + [Användningsexempel för Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Adobe Analytics data {#aa-data}
      + [Använd mått för marknadsföringskanal](../use-cases/aa-data/marketing-channels.md)
      + [Kombinera rapportsviter med olika scheman](../use-cases/aa-data/combine-report-suites.md)
   + B2B {#b2b}
      + [Ett exempel på ett B2B-projekt](../use-cases/b2b/example.md)
   + Komplexa data {#complex-data}
      + [Använda arrayer med objekt](../use-cases/object-arrays.md)
   + Flerkanalsdata {#cross-channel}
      + [Analysera data över olika kanaler](../use-cases/cross-channel/cross-channel.md)
      + [Importera callcenter och webbdata](../use-cases/cross-channel/call-center.md)
   + Dataexport {#data-export}
      + [Översikt](../use-cases/data-export/overview.md)
      + [BI-tillägg](../use-cases/data-export/bi-extension.md)
      + [Exportera datauppsättningar](../use-cases/data-export/export-datasets.md)
      + [Exportera fullständig tabell](../use-cases/data-export/export-full-table.md)
      + [Frågetjänst och exportera datauppsättningar](../use-cases/data-export/queryservice-export-datasets.md)
   + Intag av data {#data-ingestion}
      + [Importera och använda Marketo Engage-data](../use-cases/data-ingestion/marketo.md)
      + [Importera och använda Experience Platform-målgrupper](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Datavyer {#data-views}
      + [Datavyer använder exempel](/help/use-cases/data-views/data-views-usecases.md)
      + [Använd bindningsdimensioner och mätvärden](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [Använd sammanfattningsdata](/help/use-cases/data-views/summary-data.md)
      + [Användningsexempel för BI-tillägg](/help/use-cases/data-views/bi-extension-usecases.md)
   + Härledda fält {#derived-fields}
      + [Rapport om mål](../use-cases/goals-using-derived-fields.md)
   + Produktanalys {#product-analysis}
      + [Produktanalys](/help/use-cases/product-analysis.md)
   + Stitlar {#stitching}
      + [Delade enheter](/help/use-cases/stitching/shared-devices.md)
   + Tredjepartsdata {#third-party}
      + [Översikt](/help/use-cases/third-party/overview.md)
      + Google Analytics {#ga}
         + [Migrera data från Google Analytics](/help/use-cases/third-party/ga/overview.md)
         + [Ingest Google Analytics history data](/help/use-cases/third-party/ga/backfill.md)
         + [Konfigurera strömmande Google Analytics-data](/help/use-cases/third-party/ga/streaming.md)
         + [Rapport om Google Analytics-data](/help/use-cases/third-party/ga/report.md)
      + Quantum Metric {#qm}
         + [Översikt](/help/use-cases/third-party/quantum-metric/qm-overview.md)
         + [Sessionsrepriser](/help/use-cases/third-party/quantum-metric/tie-session-replays.md)
         + [Använd heatmaps](/help/use-cases/third-party/quantum-metric/heatmap.md)
         + [Lägg till friktionshändelser](/help/use-cases/third-party/quantum-metric/friction-events.md)
         + [Source Connector](/help/use-cases/third-party/quantum-metric/source-connector.md)

+ Labs {#labs}
   + [Användarhandbok för Labs](../labs/labs.md)

+ Felsökning {#troubleshooting}
   + [Jämför data](../troubleshooting/compare.md)
   + [Överensstämmelse mellan mätvärden och målgrupper](../troubleshooting/consistency-rcdp-cja.md)
   + [Brist på behörigheter](../troubleshooting/lack-of-permissions.md)

+ Tekniska anteckningar {#technotes}
   + [Åtkomstkontroll](../technotes/access-control.md)
   + [Datacenter](../technotes/data-centers.md)
   + [Borttagningskonsekvenser](../technotes/deletion.md)
   + [Domäner](../technotes/domains.md)
   + [Ordlista](../technotes/glossary.md)
   + [Guardrails](../technotes/guardrails.md)
   + [IP-adresser](../technotes/ip-addresses.md)
   + [Optimera prestanda](../technotes/optimizing-performance.md)
   + [Hantera användning](../technotes/estimate-usage.md)

+ [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/)
