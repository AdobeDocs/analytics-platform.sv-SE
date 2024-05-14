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
source-git-commit: 3d090bd6fafe58f2e7024964a2b3ec91624c63cb
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 8%

---


# Adobe Customer Journey Analytics Guide {#using}

+ [Adobe Customer Journey Analytics Guide](../getting-started/cja-landing.md)
+ [AI Assistant för Adobe Customer Journey Analytics](../ai-assistant.md)
+ Versionsinformation {#releases}
   + [Senaste versionen](../release-notes/latest.md)
   + [2024 års utgåvor](../release-notes/2024.md)
   + [2023 års utgåvor](../release-notes/2023.md)
   + [2022 års utgåvor](../release-notes/2022.md)
   + [2021 års utgåvor](../release-notes/2021.md)
   + [2020-versioner](../release-notes/2020.md)
   + [Strategi för funktionsreleaser](../release-notes/releases.md)
   + [Dokumentationsuppdateringar](../release-notes/doc-changes.md)

+ Komma igång {#cja-overview}
   + [Customer Journey Analytics - översikt](../getting-started/cja-overview.md)
   + [Snabbstartsguide](../getting-started/cja-getting-started.md)
   + [Landningssida](../getting-started/landing.md)
   + [Landningssida (gammal)](../getting-started/cja-landing-old.md)
   + [Frågor och svar](../getting-started/cja-faq.md)
   + [Jämför Customer Journey Analytics med BI-lösningar](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics och Adobe Analytics {#compare-aa-cja}
   + Uppgradera till Customer Journey Analytics {#upgrade-to-cja}
      + [Kom igång](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Välj uppgraderingsväg](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Skicka data till plattformen](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Behåll historiska data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
   + Jämförelse med Adobe Analytics {#cja-aa-comparison}
      + [Översikt](../getting-started/aa-vs-cja/overview.md)
      + [Använd Adobe Analytics-data i Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Funktioner i Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Jämför terminologi för analysdata som skickas via Analytics-källkopplingen](../getting-started/aa-vs-cja/terminology.md)
      + [Jämför databehandling i Adobe Analytics och Customer Journey Analytics](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Virtuella rapporteringsmiljöer och sandlådemiljöer](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID och Analytics-källkopplingen](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Utveckling från Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Användarhandbok för Adobe Analytics](../getting-started/aa-to-cja-user.md)

+ Inmatning av data {#cja-data-ingestion}
   + [Översikt över dataöverföring](../data-ingestion/data-ingestion.md)
   + Infoga och använda snabbstartguider{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Adobe Experience Platform Edge Network {#edge-network}
         + [Webb-SDK](../data-ingestion/aepwebsdk.md)
         + [Mobil-SDK](../data-ingestion/aepmobilesdk.md)
         + [Server-API](../data-ingestion/serverapi.md)
      + [Batchdata](../data-ingestion/batch.md)
      + [Strömmande data](../data-ingestion/streaming.md)
      + [Källkopplingar](../data-ingestion/sources.md)

+ Anslutningar {#cja-connections}
   + [Anslutningar - översikt](../connections/overview.md)
   + [Skapa eller redigera en anslutning](../connections/create-connection.md)
   + [Hantera anslutningar](../connections/manage-connections.md)
   + [Kombinerade händelsedatamängder](../connections/combined-dataset.md)
   + [Standardsökningar](../connections/standard-lookups.md)

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
      + [Värdebuckning](../data-views/component-settings/value-bucketing.md)
   + [Standard, komponentreferens](../data-views/component-reference.md)
   + [BI-tillägg](../data-views/bi-extension.md)
   + [Härledda fält](../data-views/derived-fields/derived-fields.md)
   + [Etiketter och profiler](../data-views/data-governance.md)

+ Arbetsyteprojekt {#cja-workspace}
   + [Översikt över Analysis Workspace](../analysis-workspace/home.md)
   + [Utför grundläggande analys](../analysis-workspace/perform-basic-analysis.md)
   + [Avancerad analys](../analysis-workspace/perform-adv-analysis.md)
   + Projekt {#build-workspace-project}
      + [Projektöversikt](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Skapa projekt](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Spara projekt](../analysis-workspace/build-workspace-project/save-projects.md)
      + Mappar på arbetsytan {#workspace-folders}
         + [Om mappar i arbetsytan](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Skapa mappar och undermappar](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Ta bort mappar](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [Lägg till projekt](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [Ta bort ett projekt](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [Spara ett nytt projekt](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [Snabbtangenter (kortkommandon)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Färgpaletter](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Visa densitet](../analysis-workspace/build-workspace-project/view-density.md)
   + Visualiseringar {#visualizations}
      + [Visualiseringar - översikt](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Hantera datakällor](../analysis-workspace/visualizations/t-sync-visualization.md)
      + Frihandsregister {#freeform-table}
         + [Frihandsregister](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Kolumn- och radinställningar {#column-row-settings}
            + [Kolumninställningar](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Radinställningar](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Dynamiska jämfört med statiska artiklar](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrera och ordna tabeller](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Summor för arbetsyta](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Kohorttabell {#cohort-table}
         + [Vad är kohortanalys?](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Konfigurera en kohortanalysrapport](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Användningsexempel för kohortanalyser](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Utfall {#fallout}
         + [Utfallsöversikt](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Konfigurera en utfallsvisualisering](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Interdimensionellt utfall](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Använda filter i bortfallsanalys](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flöde {#flow}
         + [Flödesöversikt](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Konfigurera en flödesvisualisering](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Flerdimensionella flöden](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Område och område staplade](../analysis-workspace/visualizations/area.md)
      + [Stolpstreck och stapel](../analysis-workspace/visualizations/bar.md)
      + [Punktdiagram](../analysis-workspace/visualizations/bullet-graph.md)
      + [Kombinationsdiagram](../analysis-workspace/visualizations/combo-charts.md)
      + [Munk](../analysis-workspace/visualizations/donut.md)
      + [Histogram](../analysis-workspace/visualizations/histogram.md)
      + [Vågrätt streck och vågrätt streck staplade](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Intelligenta bildtexter](../analysis-workspace/visualizations/intelligent-captions.md)
      + [Sammanfattning av nyckelmått](../analysis-workspace/visualizations/key-metric.md)
      + [Linje](../analysis-workspace/visualizations/line.md)
      + [Scatterplot](../analysis-workspace/visualizations/scatterplot.md)
      + [Sammanfattningsnummer och sammanfattning](../analysis-workspace/visualizations/summary-number-change.md)
      + [Text](../analysis-workspace/visualizations/text.md)
      + [Trädkarta](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Paneler {#panels}
      + [Paneler - översikt](../analysis-workspace/c-panels/panels.md)
      + [Attributionspanelen](../analysis-workspace/c-panels/attribution.md)
      + [Tom panel](../analysis-workspace/c-panels/blank-panel.md)
      + [Panelen Experimentation](../analysis-workspace/c-panels/experimentation.md)
      + [Frihandspanelen](../analysis-workspace/c-panels/freeform-panel.md)
      + [Panelen Mediegenomsnitt för miniatyrmålgrupp](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Panelen Snabbinsikter](../analysis-workspace/c-panels/quickinsight.md)
      + [Media Concurrent Viewers panel](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Medieuppspelningstid spenderad panel](../analysis-workspace/c-panels/media-playback-time-spent.md)
   + Kuratera, dela och schemalägg projekt {#curate-share}
      + [Dela-menyn](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Kuratprojekt](../analysis-workspace/curate-share/curate.md)
      + [Dela projekt](../analysis-workspace/curate-share/share-projects.md)
      + [Skapa delningsbara länkar](../analysis-workspace/curate-share/shareable-links.md)
      + [projekt med endast visning](../analysis-workspace/curate-share/view-only-projects.md)
   + Exportera {#export}
      + [Exportera översikt](../analysis-workspace/export/export-project-overview.md)
      + [Ladda ned](../analysis-workspace/export/download-send.md)
      + [Skicka till andra](../analysis-workspace/export/t-schedule-report.md)
      + [Exportera till molnet](../analysis-workspace/export/export-cloud.md)
   + Avvikelseidentifiering {#anomaly-detection}
      + [Översikt över avvikelseidentifiering](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Visa avvikelser i Analysis Workspace](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Statistiska tekniker som används för avvikelseidentifiering](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Prognos {#forecasting}
      + [Prognosöversikt](../analysis-workspace/c-forecast/forecasting.md)
      + [Visa prognoser i Analysis Workspace](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Statistiska tekniker som används i prognostjänsten](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Användarinställningar](../analysis-workspace/user-preferences.md)
   + Vanliga frågor om Workspace {#workspace-faq}
      + [Frågor och svar](../analysis-workspace/workspace-faq/faq.md)
      + [Felmeddelanden](../analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace begränsningar](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Administrationskrav](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Tillgänglighet i Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Kontrollpaneler för analyser {#cja-dashboards}
   + [Kontrollpaneler för analyser - översikt](../mobile-app/home.md)
   + [Läraruppgifter](../mobile-app/curator.md)
   + [Skapa ett mobilstyrkort](../mobile-app/create-scorecard.md)
   + [Hantera styrkort för mobila enheter](../mobile-app/manage-scorecard.md)
   + [Konfigurera chefer för att använda kontrollpaneler](../mobile-app/set-up-execs.md)
   + [Snabbguide för chefsanvändare](../mobile-app/executive.md)

+ Guidad analys {#guided-analysis}
   + [Översikt](../guided-analysis/overview.md)
   + Funktionsmatris {#feature-matrix}
      + [Engagemang](../guided-analysis/types/engagement.md)
   + Tratt {#funnel}
      + [Bildvy](../guided-analysis/types/friction.md)
      + [Vy över konverteringstrender](../guided-analysis/types/conversion-trends.md)
   + Effekt {#impact}
      + [Versionsvy](../guided-analysis/types/release.md)
      + [Vyn Första användningen](../guided-analysis/types/first-use.md)
   + Kvarhållning {#retention}
      + [Bevarandegrad](../guided-analysis/types/retention-rates.md)
   + Trender {#trends}
      + [Användningsvy](../guided-analysis/types/usage.md)
      + [Frekvensvy](../guided-analysis/types/frequency.md)
   + Användartillväxt {#user-growth}
      + [Aktiv vy](../guided-analysis/types/active.md)
      + [Vyn Nettotillväxt](../guided-analysis/types/net-growth.md)
   + Användarström {#streams}
      + [Tidslinje](../guided-analysis/types/timeline.md)
   + [Användningsexempel](../guided-analysis/industry-use-cases.md)
   + [Vanliga frågor och svar](../guided-analysis/faq.md)

+ Komponenter {#cja-components}
   + [Komponenter - översikt](../components/overview.md)
   + [Lägga till komponentbeskrivningar](../components/add-component-descriptions.md)
   + Anteckningar {#annotations}
      + [Översikt över anteckningar](../components/annotations/overview.md)
      + [Skapa anteckningar](../components/annotations/create-annotations.md)
      + [Hantera anteckningar](../components/annotations/manage-annotations.md)
      + [Visa anteckningar](../components/annotations/view-annotations.md)
      + [Mobilanteckningar](../components/annotations/mobile-annotations.md)
   + [Schemalagt projekt](../components/scheduled-projects-manager.md)
   + Målgrupper {#audiences}
      + [Översikt över målgrupper](../components/audiences/audiences-overview.md)
      + [Skapa och publicera målgrupper](../components/audiences/publish.md)
      + [Hantera målgrupper](../components/audiences/manage.md)
   + Dimensioner {#dimensions}
      + [Översikt över Dimensioner](../components/dimensions/overview.md)
      + [Förhandsvisa dimensioner](../components/dimensions/view-dimensions.md)
      + [Dela upp dimensioner](../components/dimensions/t-breakdown-fa.md)
      + [Tidsdelningsdimensioner](../components/dimensions/time-parting-dimensions.md)
      + [Dimensioner med mycket hög kardinalitet](../components/dimensions/high-cardinality.md)
   + [Mätvärden](../components/apply-create-metrics.md)
   + Filter {#cja-filters}
      + [Översikt över filter](../components/filters/filters-overview.md)
      + [Skapa filter](../components/filters/create-filters.md)
      + [Dela filter](../components/filters/filters-share.md)
      + [Taggfilter](../components/filters/filters-tag.md)
      + [Filtrera filterlistan](../components/filters/filters-filter.md)
      + [Markera filter som favoriter](../components/filters/filters-favorite.md)
      + [Godkänn filter](../components/filters/filters-approve.md)
      + [Kopiera filter](../components/filters/filters-copy.md)
      + [Snabbfilter](../components/filters/quick-filters.md)
      + [Filter Builder](../components/filters/filter-builder.md)
      + [Hantera filter](../components/filters/manage-filters.md)
      + [Operatorer](../components/filters/operators.md)
   + Beräknade mått {#cja-calcmetrics}
      + [Översikt över beräknade mätvärden](../components/calc-metrics/calc-metr-overview.md)
      + Arbetsflöde för beräknade mätvärden {#cm-workflow}
         + [Arbetsflöde för beräknade mätvärden](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Hitta mätvärden](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Bygg mätvärden](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Mättyp och attribuering](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Bygg ett deltagandemått](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Filtrerade mätvärden](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Stapla och ersätta filter](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrerade och viktade mätvärden](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Filtrera beräknade värden](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Markera beräknade värden som favoriter](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Kopiera beräknade värden](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Använd funktioner](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Tagga beräknade värden](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Godkänn beräknade värden](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Dela beräknade värden](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Beräknad måtthanterare](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Standardberäknade värden](../components/calc-metrics/default-calcmetrics.md)
      + [Grundfunktioner](../components/calc-metrics/cm-functions.md)
      + [Avancerade funktioner](../components/calc-metrics/cm-adv-functions.md)
   + Kalender och datumintervall {#cja-date-ranges}
      + [Översikt över kalender- och datumintervall](../components/date-ranges/calendar.md)
      + [Skapa ett datumintervall](../components/date-ranges/create.md)
      + [Hantera datumintervall](../components/date-ranges/manage.md)
      + [Skapa anpassade datumintervall](../components/date-ranges/custom-date-ranges.md)
      + [Datumjämförelse](../components/date-ranges/time-comparison.md)
   + Export {#exports}
      + [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md)
      + [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md)
      + [Hantera platser för molnexport](/help/components/exports/manage-export-locations.md)
      + [Hantera exporter](/help/components/exports/manage-exports.md)
      + [Hantera exportloggar](/help/components/exports/manage-export-logs.md)
      + [Felsöka exporter](/help/components/exports/troubleshoot-exports.md)
   + Dataordlista {#data-dictionary}
      + [Översikt över dataordlistan](../components/data-dictionary/data-dictionary-overview.md)
      + [Visa komponentinformation i Data Dictionary](../components/data-dictionary/view-data-dictionary.md)
      + [Redigera komponentposter i Data Dictionary](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Övervaka dataordlistans hälsa](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Översikt över Report Builder](../report-builder/report-buider-overview.md)
   + [Konfigurera Report Builder](../report-builder/report-builder-setup.md)
   + [Skapa ett datablock](../report-builder/create-a-data-block.md)
   + [Report Builder Hub](../report-builder/report-builder-hub.md)
   + [Välj en datavy](../report-builder/select-data-view.md)
   + [Välj ett datumintervall](../report-builder/select-date-range.md)
   + [Arbeta med filter](../report-builder/work-with-filters.md)
   + [Filtrera Dimensioner](../report-builder/filter-dimensions.md)
   + [Hantera datablock](../report-builder/manage-reportbuilder.md)
   + [Schemalägg arbetsböcker](../report-builder/schedule-reportbuilder.md)
   + [Begränsade etiketter](../report-builder/restricted-labels.md)
   + [Inställningar för Report Builder](../report-builder/report-builder-settings.md)

+ Rapporteringsaktivitetshanteraren {#reporting-activity-manager}
   + [Översikt](../reporting-activity-manager/reporting-activity-overview.md)
   + [Visa rapporteringsaktivitet](../reporting-activity-manager/reporting-activity.md)
   + [Avbryt rapporteringsbegäranden](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Stitlar {#stitching}
   + [Översikt](../stitching/overview.md)
   + [Hur stygn fungerar](../stitching/explained.md)
   + [Skapa och hantera sammanslagna datauppsättningar](../stitching/stitching-ui.md)
   + [Vanliga frågor](../stitching/faq.md)

+ Integreringar med Adobe {#integrations}
   + [Integrera Adobe-lösningar med Customer Journey Analytics i korthet](/help/integrations/overview.md)
   + [Integrera Adobe Analytics med Customer Journey Analytics](/help/integrations/aa.md)
   + [Integrera Journey Optimizer-data med Customer Journey Analytics](/help/integrations/ajo.md)
   + [Integrera beslutsledningens data med Customer Journey Analytics](/help/integrations/ajo-od.md)
   + [Integrera kundens AI med Customer Journey Analytics](/help/integrations/customer-ai.md)

+ Datastyrning {#cja-privacy}
   + [Datastyrning](../privacy/privacy-overview.md)
   + [Granskningslogg](../privacy/audit-log.md)
   + [Kundhanterade nycklar](../privacy/cmk.md)

+ Användningsexempel {#cja-usecases}
   + [Användningsexempel i Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Google Analytics data {#ga}
      + [Migrera data från Google Analytics till Customer Journey Analytics - översikt](../use-cases/ga/overview.md)
      + [Infoga Google Analytics historiska data i plattformen](../use-cases/ga/backfill.md)
      + [Konfigurera strömmande Google Analytics-data i plattformen](../use-cases/ga/streaming.md)
      + [Rapport om Google Analytics data i Customer Journey Analytics](../use-cases/ga/report.md)
   + Intag av data {#data-ingestion}
      + [Infoga Marketo Engage data i Adobe Experience Platform och rapportera i Customer Journey Analytics](../use-cases/data-ingestion/marketo.md)
      + [Engagera Adobe Experience Platform-målgrupper i Customer Journey Analytics](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Datavyer {#data-views}
      + [Datavyer använder exempel](../use-cases/data-views/data-views-usecases.md)
      + [Använd bindningsdimensioner och mätvärden](../use-cases/data-views/binding-dimensions-metrics.md)
   + Dataexport {#data-export}
      + [Översikt](../use-cases/data-export/overview.md)
      + [BI-tillägg](../use-cases/data-export/bi-extension.md)
      + [Exportera datauppsättningar](../use-cases/data-export/export-datasets.md)
      + [Exportera fullständig tabell](../use-cases/data-export/export-full-table.md)
      + [Frågetjänst och exportera datauppsättningar](../use-cases/data-export/queryservice-export-datasets.md)
   + B2B {#b2b}
      + [Ett exempel på ett B2B-projekt](../use-cases/b2b/example.md)
      + [Lägg till data på kontonivå som en uppslagsdatauppsättning](../use-cases/b2b/b2b.md)
   + Flerkanalsdata {#cross-channel}
      + [Analysera data över olika kanaler](../use-cases/cross-channel/cross-channel.md)
      + [Importera callcenter och webbdata](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics data {#aa-data}
      + [Använd mått för marknadsföringskanal](../use-cases/aa-data/marketing-channels.md)
      + [Kombinera rapportsviter med olika scheman](../use-cases/aa-data/combine-report-suites.md)
   + Komplexa data {#complex-data}
      + [Använda arrayer med objekt](../use-cases/object-arrays.md)
   + Härledda fält {#derived-fields}
      + [Använd härledda fält för att rapportera mål](../use-cases/goals-using-derived-fields.md)

+ Labs {#labs}
   + [Användarhandbok för Labs](../labs/labs.md)

+ Felsökning {#troubleshooting}
   + [Jämför dina Adobe Analytics-data med Customer Journey Analytics](../troubleshooting/compare.md)
   + [Överensstämmelse i mätvärden och antalet målgruppsmedlemskap mellan CDP och Customer Journey Analytics i realtid](../troubleshooting/consistency-rcdp-cja.md)
   + [Brist på behörigheter](../troubleshooting/lack-of-permissions.md)

+ Tekniska anteckningar {#technotes}
   + [Åtkomstkontroll](../technotes/access-control.md)
   + [Datacenter](../technotes/data-centers.md)
   + [Borttagningskonsekvenser](../technotes/deletion.md)
   + [Domäner](../technotes/domains.md)
   + [Ordlista](../technotes/glossary.md)
   + [Guardrails](../technotes/guardrails.md)
   + [IP-adresser](../technotes/ip-addresses.md)
   + [Optimera Customer Journey Analytics prestanda](../technotes/optimizing-performance.md)
   + [Visa och hantera användning](../technotes/estimate-usage.md)

+ [CUSTOMER JOURNEY ANALYTICS API](https://developer.adobe.com/cja-apis/docs/)
