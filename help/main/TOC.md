---
git-repo: https://github.com/AdobeDocs/analytics-platform.sv-SE
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Användarhandbok om Customer Journey Analytics
user-guide-description: Lär dig mer om Customer Journey Analytics (CJA) och hur du använder Analysis Workspace med data från Experience Platform.
breadcrumb-title: Användarhandbok om Customer Journey Analytics
source-git-commit: 5929d56bef8f756967926482f80014db0d43d3e3
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 32%

---


# Användarhandbok om Customer Journey Analytics {#using}

+ [Användarhandbok om Customer Journey Analytics](../getting-started/cja-landing.md)

+ Versionsinformation {#releases}
   + [Senaste versionen](../release-notes/latest.md)
   + [2023 års utgåvor](../release-notes/2023.md)
   + [2022 års utgåvor](../release-notes/2022.md)
   + [2021 års utgåvor](../release-notes/2021.md)
   + [2020-versioner](../release-notes/2020.md)
   + [CJA-releaser](../release-notes/releases.md)
   + [CJA - dokumentationsuppdateringar](../release-notes/doc-changes.md)

+ Komma igång {#cja-overview}
   + [Customer Journey Analytics - översikt](../getting-started/cja-overview.md)
   + [Snabbstartsguide](../getting-started/cja-getting-started.md)
   + [Landningssida](../getting-started/landing.md)
   + [Frågor och svar](../getting-started/cja-faq.md)
   + [Jämför CJA med BI-lösningar](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics och Adobe Analytics {#compare-aa-cja}
   + [Utveckling från Adobe Analytics ](../getting-started/aa-to-cja.md)
   + [Användarhandbok för Adobe Analytics](../getting-started/aa-to-cja-user.md)
   + Jämförelse med Adobe Analytics {#cja-aa-comparison}
      + [Använd Adobe Analytics-data i Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Funktioner i Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Jämför terminologi för analysdata som skickas via Analytics Source Connector](../getting-started/aa-vs-cja/terminology.md)
      + [Jämför databehandling i Adobe Analytics och CJA](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Virtuella rapporteringsmiljöer och sandlådemiljöer](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [STÖD, ECID, AACUSTOMID och Analytics Source Connector](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ Datainmatning {#cja-data-ingestion}
   + [Översikt över dataöverföring](../data-ingestion/data-ingestion.md)
   + Infoga och använda snabbstartguider{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + [Adobe Experience Platform Web SDK och Edge Network](../data-ingestion/aepwebsdk.md)
      + [Batchdata](../data-ingestion/batch.md)
      + [Strömmande data](../data-ingestion/streaming.md)
      + [Källkopplingar](../data-ingestion/sources.md)

+ Anslutningar {#cja-connections}
   + [Anslutningar - översikt](../connections/overview.md)
   + [Skapa en anslutning](../connections/create-connection.md)
   + [Hantera anslutningar](../connections/manage-connections.md)
   + [Kombinerade händelsedatamängder](../connections/combined-dataset.md)
   + [Standardsökningar](../connections/standard-lookups.md)
   + [Flerkanalsanalys](../connections/cca.md)

+ Datavyer {#cja-dataviews}
   + [Översikt över datavyer](../data-views/data-views.md)
   + [Skapa eller redigera en datavy](../data-views/create-dataview.md)
   + Komponentinställningar {#component-settings}
      + [Översikt över komponentinställningar](../data-views/component-settings/overview.md)
      + [Attribuering](../data-views/component-settings/attribution.md)
      + [Beteende](../data-views/component-settings/behavior.md)
      + [Format](../data-views/component-settings/format.md)
      + [Inkludera exkluderingsvärden](../data-views/component-settings/include-exclude-values.md)
      + [Metrisk deduplicering](../data-views/component-settings/metric-deduplication.md)
      + [Inga värdealternativ](../data-views/component-settings/no-value-options.md)
      + [Persistence](../data-views/component-settings/persistence.md)
      + [Delsträng](../data-views/component-settings/substring.md)
      + [Värdebuckning](../data-views/component-settings/value-bucketing.md)
   + [Standard, komponentreferens](../data-views/component-reference.md)
   + [Etiketter och profiler](../data-views/data-governance.md)


+ Arbetsyteprojekt {#cja-workspace}
   + [Översikt över Analysis Workspace](../analysis-workspace/home.md)
   + [Utför grundläggande analys](../analysis-workspace/perform-basic-analysis.md)
   + [Avancerad analys](../analysis-workspace/perform-adv-analysis.md)

   + Projekt {#build-workspace-project}
      + [Översikt över projekt](../analysis-workspace/build-workspace-project/freeform-overview.md)
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
      + [Översikt över visualiseringar](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Hantera datakällor](../analysis-workspace/visualizations/t-sync-visualization.md)

      + Frihandstabell {#freeform-table}
         + [Frihandstabell](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Kolumn- och radinställningar {#column-row-settings}
            + [Kolumninställningar](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Radinställningar](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Dynamiska jämfört med statiska artiklar](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Sidnumrering, filtrering och sortering av tabeller](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)

         + [Summor för Workspace](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Kohorttabell {#cohort-table}
         + [Vad är kohortanalys?](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Konfigurera en kohortanalysrapport](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Användningsexempel på kohortanalyser](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Utfall {#fallout}
         + [Översikt över utfall](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Konfigurera en utfallsvisualisering](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Intradimensionella utfall](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Använda filter i bortfallsanalys](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flöde {#flow}
         + [Översikt över flöden](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Konfigurera en flödesvisualisering](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Intradimensionella flöden](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Områdesdiagram och staplat områdesdiagram](../analysis-workspace/visualizations/area.md)

      + [Stapeldiagram och staplat stapeldiagram](../analysis-workspace/visualizations/bar.md)
      + [Punktdiagram](../analysis-workspace/visualizations/bullet-graph.md)
      + [Kombinationsdiagram](../analysis-workspace/visualizations/combo-charts.md)
      + [Ringdiagram](../analysis-workspace/visualizations/donut.md)
      + [Histogram](../analysis-workspace/visualizations/histogram.md)
      + [Liggande stapeldiagram och staplat liggande stapeldiagram](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Sammanfattning av nyckelmått](../analysis-workspace/visualizations/key-metric.md)
      + [Linjediagram](../analysis-workspace/visualizations/line.md)
      + [Spridningsdiagram](../analysis-workspace/visualizations/scatterplot.md)
      + [Sammanfattning av antal och förändring](../analysis-workspace/visualizations/summary-number-change.md)
      + [Text](../analysis-workspace/visualizations/text.md)
      + [Trädkarta](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Paneler {#panels}
      + [Översikt över paneler](../analysis-workspace/c-panels/panels.md)
      + [Panelen Attribution](../analysis-workspace/c-panels/attribution.md)
      + [Tom panel](../analysis-workspace/c-panels/blank-panel.md)
      + [Panelen Experimentation](../analysis-workspace/c-panels/experimentation.md)
      + [Frihandspanel](../analysis-workspace/c-panels/freeform-panel.md)
      + [Panelen Snabbinsikter](../analysis-workspace/c-panels/quickinsight.md)
      + [Panelen för samtidiga medieanvändare](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + Medieuppspelningstid tillagd {#media-playback-timespent}
         + [Översikt](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [Indata- och utdatainställningar](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [Vanliga frågor](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + Kuratera, dela och schemalägg projekt {#curate-share}
      + [Dela-menyn](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Kuratprojekt](../analysis-workspace/curate-share/curate.md)
      + [Dela projekt](../analysis-workspace/curate-share/share-projects.md)
      + [Skapa delningsbara länkar](../analysis-workspace/curate-share/shareable-links.md)
      + [Visa endast  projekt](../analysis-workspace/curate-share/view-only-projects.md)
      + [Hämta PDF- eller CSV-filer](../analysis-workspace/curate-share/download-send.md)
      + [Schemalägg projekt](../analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [Översikt över attribuering](../analysis-workspace/attribution/overview.md)
      + [Attributmodeller och uppslagsfönster](../analysis-workspace/attribution/models.md)
      + [Algoritmisk attribuering](../analysis-workspace/attribution/algorithmic.md)
      + [Bästa praxis för attribuering](../analysis-workspace/attribution/best-practices.md)
      + [Vanliga frågor](../analysis-workspace/attribution/faq.md)
   + Virtual Analyst {#virtual-analyst}
      + [Översikt över Virtual Analyst](../analysis-workspace/virtual-analyst/overview.md)
      + Avvikelseidentifiering {#anomaly-detection}
         + [Översikt över avvikelseidentifiering](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Visa avvikelser i Analysis Workspace](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Statistiska tekniker som används för avvikelseidentifiering](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Användarinställningar](../analysis-workspace/user-preferences.md)

   + Vanliga frågor om Workspace {#workspace-faq}
      + [Frågor och svar](../analysis-workspace/workspace-faq/faq.md)
      + [Optimera prestanda för Analysis Workspace](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Felmeddelanden](../analysis-workspace/workspace-faq/error-messages.md)
      + [Begränsningar i Analysis Workspace](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Administrationskrav](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Tillgänglighet i Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Långsvansar i Analysis Workspace](../analysis-workspace/workspace-faq/long-tail.md)












+ Komponenter {#cja-components}
   + [Komponenter – översikt](../components/overview.md)
   + [Lägga till komponentbeskrivningar](../components/add-component-descriptions.md)
   + Anteckningar {#annotations}
      + [Översikt över anteckningar](../components/annotations/overview.md)
      + [Skapa anteckningar](../components/annotations/create-annotations.md)
      + [Hantera anteckningar](../components/annotations/manage-annotations.md)
      + [Visa anteckningar](../components/annotations/view-annotations.md)
      + [Mobilanteckningar](../components/annotations/mobile-annotations.md)
   + Målgrupper {#audiences}
      + [Översikt över målgrupper](../components/audiences/audiences-overview.md)
      + [Skapa och publicera målgrupper](../components/audiences/publish.md)
      + [Hantera målgrupper](../components/audiences/manage.md)
   + Dimensioner {#dimensions}
      + [Förhandsvisa dimensioner](../components/dimensions/view-dimensions.md)
      + [Dela upp dimensioner](../components/dimensions/t-breakdown-fa.md)
      + [Tidsdelning av dimensioner](../components/dimensions/time-parting-dimensions.md)
      + [Dimensioner med mycket hög kardinalitet](../components/dimensions/high-cardinality.md)
   + [Mätvärden](../components/apply-create-metrics.md)
   + Filter {#cja-filters}
      + [Översikt över filter](../components/filters/filters-overview.md)
      + [Skapa ett filter](../components/filters/create-filters.md)
      + [Hantera filter](../components/filters/manage-filters.md)
      + [Snabbfilter](../components/filters/quick-filters.md)
      + [Ad hoc-filter](../components/filters/ad-hoc-filters.md)
      + [Operatorer](../components/filters/operators.md)
   + Beräknade mätvärden {#cja-calcmetrics}
      + [Översikt över beräknade mätvärden](../components/calc-metrics/calc-metr-overview.md)
      + Arbetsflöde för beräknade värden {#cm-workflow}
         + [Arbetsflöde för beräknade mätvärden](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Hitta mätvärden](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Skapa mätvärden](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Mätvärdestyp och attribuering](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Skapa ett enkelt mätvärde för sidvisningar per besök](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Filtrerade mätvärden](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Stapla och ersätta segment](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrerade och viktade mätvärden](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Använda funktioner](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Mätvärden för deltagande](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Tagga beräknade mätvärden](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Godkänna beräknade mätvärden](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Dela beräknade mätvärden](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Hanterare för beräknade mätvärden](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Standardberäknade värden](../components/calc-metrics/default-calcmetrics.md)
      + [Grundfunktioner](../components/calc-metrics/cm-functions.md)
      + [Avancerade funktioner](../components/calc-metrics/cm-adv-functions.md)
   + Datumintervall {#cja-date-ranges}
      + [Översikt över datumintervall](../components/date-ranges/overview.md)
      + [Skapa ett datumintervall](../components/date-ranges/create.md)
      + [Hantera datumintervall](../components/date-ranges/manage.md)
      + [Översikt över kalendern](../components/date-ranges/calendar.md)
      + [Skapa anpassade datumintervall](../components/date-ranges/custom-date-ranges.md)
      + [Datumjämförelse](../components/date-ranges/time-comparison.md)
   + Dataordlista {#data-dictionary}
      + [Översikt över dataordlistan](../components/data-dictionary/data-dictionary-overview.md)
      + [Visa komponentinformation i Data Dictionary](../components/data-dictionary/view-data-dictionary.md)
      + [Redigera komponentposter i Data Dictionary](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Övervaka dataordlistans hälsa](../components/data-dictionary/monitor-data-dictionary-health.md)
+ Kontrollpaneler för analyser {#cja-dashboards}
   + [Kontrollpaneler för analyser - översikt](../mobile-app/home.md)
   + [Läraruppgifter](../mobile-app/curator.md)
   + [Skapa ett mobilstyrkort](../mobile-app/create-scorecard.md)
   + [Konfigurera chefer för att använda kontrollpaneler](../mobile-app/set-up-execs.md)
   + [Snabbguide för chefsanvändare](../mobile-app/executive.md)

+ Report Builder {#cja-reportbuilder}
   + [Översikt över Report Builder](../report-builder/report-buider-overview.md)
   + [Konfigurera Report Builder](../report-builder/report-builder-setup.md)
   + [Skapa ett datablock](../report-builder/create-a-data-block.md)
   + [Report Builder Hub](../report-builder/report-builder-hub.md)
   + [Välj ett datumintervall](../report-builder/select-date-range.md)
   + [Arbeta med filter](../report-builder/work-with-filters.md)
   + [Filtrera Dimensioner](../report-builder/filter-dimensions.md)
   + [Hantera datablock](../report-builder/manage-reportbuilder.md)
   + [Schemalägg arbetsböcker](../report-builder/schedule-reportbuilder.md)
   + [Begränsade etiketter](../report-builder/restricted-labels.md)
   + [Inställningar för Report Builder](../report-builder/report-builder-settings.md)

+ Flerkanalsanalys {#cca}
   + [Översikt över flerkanalsanalys](../cca/overview.md)
   + [Så här spelar du upp](../cca/replay.md)
   + [Vanliga frågor om flerkanalsanalys](../cca/faq.md)

+ Integreringar med Adobe {#integrations}
   + [Integrera Adobe-lösningar med CJA - översikt](/help/integrations/overview.md)
   + [Integrera Adobe Analytics med Customer Journey Analytics](/help/integrations/aa.md)
   + [Integrera Journey Optimizer-data med CJA](/help/integrations/ajo.md)
   + [Integrera kundens AI-data med CJA](/help/integrations/customer-ai.md)

+ Datastyrning {#cja-privacy}
   + [Datastyrning](../privacy/privacy-overview.md)
   + [Granskningslogg](../privacy/audit-log.md)
   + [Kundhanterade nycklar](../privacy/cmk.md)

+ Användningsexempel {#cja-usecases}
   + [Användningsexempel i Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Google Analytics data {#ga}
      + [Migrera data från Google Analytics till CJA - översikt](../use-cases/ga/overview.md)
      + [Infoga Google Analytics historiska data i plattformen](../use-cases/ga/backfill.md)
      + [Konfigurera strömmande Google Analytics-data i plattformen](../use-cases/ga/streaming.md)
      + [Rapport om Google Analytics data i CJA](../use-cases/ga/report.md)
   + Intag av data {#data-ingestion}
      + [Infoga Marketo Engage data i AEP och rapportera i CJA](../use-cases/data-ingestion/marketo.md)
      + [Ingest AEP-målgrupper into CJA](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Datavyer {#data-views}
      + [Datavyer använder exempel](../use-cases/data-views/data-views-usecases.md)
      + [Använd bindningsdimensioner och mätvärden](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [Lägg till data på kontonivå som en uppslagsdatauppsättning](../use-cases/b2b/b2b.md)
   + Flerkanalsdata {#cross-channel}
      + [Analysera data över olika kanaler](../use-cases/cross-channel/cross-channel.md)
      + [Importera callcenter och webbdata](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics data {#aa-data}
      + [Använd mått för marknadsföringskanal](../use-cases/aa-data/marketing-channels.md)
      + [Kombinera rapportsviter med olika scheman](../use-cases/aa-data/combine-report-suites.md)
   + Komplexa data {#complex-data}
      + [Använda arrayer med objekt](../use-cases/object-arrays.md)

+ Administrering {#cja-admin}
   + [Åtkomstkontroll](../admin/cja-access-control.md)
   + [Visa och hantera användning](../admin/estimate-usage.md)
   + [Borttagningskonsekvenser](../admin/cja-deletion.md)

+ Labs {#labs}
   + [Användarhandbok för Labs](../labs/labs.md)

+ Felsökning {#troubleshooting}
   + [Jämför dina Adobe Analytics-data med CJA-data](../troubleshooting/compare.md)
   + [Överensstämmelse i mätvärden och antal målgruppsmedlemskap mellan CDP och CJA i realtid](../troubleshooting/consistency-rcdp-cja.md)

+ [CJA-ordlista](../getting-started/cja-glossary.md)

+ [CJA API](https://developer.adobe.com/cja-apis/docs/)
