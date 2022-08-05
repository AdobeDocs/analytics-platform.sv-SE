---
git-repo: https://github.com/AdobeDocs/analytics-platform.sv-SE
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics Guide
user-guide-description: Den här guiden stöder Customer Journey Analytics, nästa generation av Adobe-lösning för flerkanalsanalys, baserad på Adobe Experience Platform.
breadcrumb-title: Customer Journey Analytics Guide
source-git-commit: 94b3e7417b82e9ae3ad080884d4c184bee412c2c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 33%

---


# Customer Journey Analytics Guide {#using}

+ [Customer Journey Analytics Guide](getting-started/cja-landing.md)
+ Versionsinformation {#releases}
   + [Senaste versionen](release-notes/latest.md)
   + [2022 års utgåvor](release-notes/2022.md)
   + [2021 års utgåvor](release-notes/2021.md)
   + [2020-versioner](release-notes/2020.md)
   + [CJA-releaser](release-notes/releases.md)
   + [CJA - dokumentationsuppdateringar](release-notes/doc-changes.md)
+ Customer Journey Analytics - översikt {#cja-overview}
   + [Customer Journey Analytics - översikt](getting-started/cja-overview.md)
   + [Komma igång](getting-started/cja-getting-started.md)
   + [Överensstämmelse i mätvärden och antal målgruppsmedlemskap mellan CDP och CJA i realtid](getting-started/consistency-rcdp-cja.md)
   + [CJA-åtkomstkontroll](getting-started/cja-access-control.md)
   + [Customer Journey Analytics landningssida](getting-started/landing.md)
   + [Frågor och svar](getting-started/cja-faq.md)
   + [Adobe Analytics till Customer Journey Analytics evolutionen](getting-started/aa-to-cja.md)
   + [Användarhandbok för nya användare i Customer Journey Analytics](getting-started/aa-to-cja-user.md)
   + Jämför Adobe Analytics och Customer Journey Analytics {#compare-aa-cja}
      + [Funktioner i Customer Journey Analytics](getting-started/aa-vs-cja/cja-aa.md)
      + [Jämför databehandling i Adobe Analytics och CJA](getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Virtuella rapporteringsmiljöer och sandlådemiljöer](getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep](getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [STÖD, ECID, AACUSTOMID och Analytics Source Connector](getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Borttagningskonsekvenser](getting-started/cja-deletion.md)
   + [CJA-ordlista](getting-started/cja-glossary.md)
+ Anslutningar {#cja-connections}
   + [Anslutningar - översikt](connections/overview.md)
   + [Skapa en anslutning](connections/create-connection.md)
   + [Hantera anslutningar](connections/manage-connections.md)
   + [Kombinerade händelsedatamängder](connections/combined-dataset.md)
   + [Standardsökningar](connections/standard-lookups.md)
   + Flerkanalsanalys {#cca}
      + [Översikt över flerkanalsanalys](connections/cca/overview.md)
      + [Så här spelar du upp](connections/cca/replay.md)
      + [Vanliga frågor om flerkanalsanalys](connections/cca/faq.md)
+ Datavyer {#cja-dataviews}
   + [Översikt över datavyer](data-views/data-views.md)
   + [Skapa eller redigera en datavy](data-views/create-dataview.md)
   + Komponentinställningar {#component-settings}
      + [Översikt över komponentinställningar](data-views/component-settings/overview.md)
      + [Attribuering](data-views/component-settings/attribution.md)
      + [Beteende](data-views/component-settings/behavior.md)
      + [Format](data-views/component-settings/format.md)
      + [Inkludera exkluderingsvärden](data-views/component-settings/include-exclude-values.md)
      + [Metrisk deduplicering](data-views/component-settings/metric-deduplication.md)
      + [Inga värdealternativ](data-views/component-settings/no-value-options.md)
      + [Persistence](data-views/component-settings/persistence.md)
      + [Delsträng](data-views/component-settings/substring.md)
      + [Värdebuckning](data-views/component-settings/value-bucketing.md)
   + [Standard, komponentreferens](data-views/component-reference.md)
   + [Datavyer använder exempel](data-views/data-views-usecases.md)
+ Arbetsyteprojekt {#cja-workspace}
   + [Översikt över Analysis Workspace](analysis-workspace/home.md)
   + [Utför grundläggande analys](analysis-workspace/perform-basic-analysis.md)
   + [Avancerad analys](analysis-workspace/perform-adv-analysis.md)
   + Projekt {#build-workspace-project}
      + [Översikt över projekt](analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Spara projekt](analysis-workspace/build-workspace-project/save-projects.md)
      + [Snabbtangenter (kortkommandon)](analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Färgpaletter](analysis-workspace/build-workspace-project/color-palettes.md)
      + [Visa densitet](analysis-workspace/build-workspace-project/view-density.md)
   + Visualiseringar {#visualizations}
      + [Översikt över visualiseringar](analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Hantera datakällor](analysis-workspace/visualizations/t-sync-visualization.md)
      + Frihandstabell {#freeform-table}
         + [Frihandstabell](analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Kolumn- och radinställningar {#column-row-settings}
            + [Kolumninställningar](analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Radinställningar](analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Dynamiska jämfört med statiska artiklar](analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Sidnumrering, filtrering och sortering av tabeller](analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md)
         + [Summor för Workspace](analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Kohorttabell {#cohort-table}
         + [Vad är kohortanalys?](analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Konfigurera en kohortanalysrapport](analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Användningsexempel på kohortanalyser](analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Utfall {#fallout}
         + [Översikt över utfall](analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Konfigurera en utfallsvisualisering](analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Intradimensionella utfall](analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Använda filter i bortfallsanalys](analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Flöde {#flow}
         + [Översikt över flöden](analysis-workspace/visualizations/c-flow/flow.md)
         + [Konfigurera en flödesvisualisering](analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Intradimensionella flöden](analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Områdesdiagram och staplat områdesdiagram](analysis-workspace/visualizations/area.md)
      + [Stapeldiagram och staplat stapeldiagram](analysis-workspace/visualizations/bar.md)
      + [Punktdiagram](analysis-workspace/visualizations/bullet-graph.md)
      + [Ringdiagram](analysis-workspace/visualizations/donut.md)
      + [Histogram](analysis-workspace/visualizations/histogram.md)
      + [Liggande stapeldiagram och staplat liggande stapeldiagram](analysis-workspace/visualizations/horizontal-bar.md)
      + [Sammanfattning av nyckelmått](analysis-workspace/visualizations/key-metric.md)
      + [Linjediagram](analysis-workspace/visualizations/line.md)
      + [Spridningsdiagram](analysis-workspace/visualizations/scatterplot.md)
      + [Sammanfattning av antal och förändring](analysis-workspace/visualizations/summary-number-change.md)
      + [Text](analysis-workspace/visualizations/text.md)
      + [Trädkarta](analysis-workspace/visualizations/treemap.md)
      + [Venn](analysis-workspace/visualizations/venn.md)
   + Paneler {#panels}
      + [Översikt över paneler](analysis-workspace/c-panels/panels.md)
      + [Panelen Attribution](analysis-workspace/c-panels/attribution.md)
      + [Tom panel](analysis-workspace/c-panels/blank-panel.md)
      + [Frihandspanel](analysis-workspace/c-panels/freeform-panel.md)
      + [Panelen Snabbinsikter](analysis-workspace/c-panels/quickinsight.md)
      + [Panelen för samtidiga medieanvändare](analysis-workspace/c-panels/media-concurrent-viewers.md)
      + Medieuppspelningstid tillagd {#media-playback-timespent}
         + [Översikt](analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [Indata- och utdatainställningar](analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [Vanliga frågor](analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + Kuratera, dela och schemalägg projekt {#curate-share}
      + [Dela-menyn](analysis-workspace/curate-share/send-schedule-files.md)
      + [Kuratprojekt](analysis-workspace/curate-share/curate.md)
      + [Dela projekt](analysis-workspace/curate-share/share-projects.md)
      + [Skapa delningsbara länkar](analysis-workspace/curate-share/shareable-links.md)
      + [Visa endast  projekt](analysis-workspace/curate-share/view-only-projects.md)
      + [Hämta PDF- eller CSV-filer](analysis-workspace/curate-share/download-send.md)
      + [Schemalägg projekt](analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [Översikt över attribuering](analysis-workspace/attribution/overview.md)
      + [Attributmodeller och uppslagsfönster](analysis-workspace/attribution/models.md)
      + [Algoritmisk attribuering](analysis-workspace/attribution/algorithmic.md)
      + [Bästa praxis för attribuering](analysis-workspace/attribution/best-practices.md)
      + [Vanliga frågor](analysis-workspace/attribution/faq.md)
   + Virtual Analyst {#virtual-analyst}
      + [Översikt över Virtual Analyst](analysis-workspace/virtual-analyst/overview.md)
      + Avvikelseidentifiering {#anomaly-detection}
         + [Översikt över avvikelseidentifiering](analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Visa avvikelser i Analysis Workspace](analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Statistiska tekniker som används för avvikelseidentifiering](analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Användarinställningar](analysis-workspace/user-preferences.md)
   + Vanliga frågor om Workspace {#workspace-faq}
      + [Frågor och svar](analysis-workspace/workspace-faq/faq.md)
      + [Optimera prestanda för Analysis Workspace](analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Felmeddelanden](analysis-workspace/workspace-faq/error-messages.md)
      + [Begränsningar i Analysis Workspace](analysis-workspace/workspace-faq/aw-limitations.md)
      + [Administrationskrav](analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Tillgänglighet i Analysis Workspace](analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Långsvansar i Analysis Workspace](analysis-workspace/workspace-faq/long-tail.md)
+ Report Builder {#cja-reportbuilder}
   + [Översikt över Report Builder](report-builder/report-buider-overview.md)
   + [Konfigurera Report Builder](report-builder/report-builder-setup.md)
   + [Skapa ett datablock](report-builder/create-a-data-block.md)
   + [Report Builder Hub](report-builder/report-builder-hub.md)
   + [Välj ett datumintervall](report-builder/select-date-range.md)
   + [Arbeta med filter](report-builder/work-with-filters.md)
   + [Filtrera Dimensioner](report-builder/filter-dimensions.md)
   + [Hantera datablock](report-builder/manage-reportbuilder.md)
   + [Inställningar för Report Builder](report-builder/report-builder-settings.md)
+ Komponenter {#cja-components}
   + [Komponenter – översikt](components/overview.md)
   + Anteckningar {#annotations}
      + [Översikt över anteckningar](components/annotations/overview.md)
      + [Skapa anteckningar](components/annotations/create-annotations.md)
      + [Hantera anteckningar](components/annotations/manage-annotations.md)
      + [Visa anteckningar](components/annotations/view-annotations.md)
      + [Mobilanteckningar](components/annotations/mobile-annotations.md)
   + Målgrupper {#audiences}
      + [Översikt över målgrupper](components/audiences/audiences-overview.md)
      + [Skapa och publicera målgrupper](components/audiences/publish.md)
      + [Hantera målgrupper](components/audiences/manage.md)
   + Dimensioner {#dimensions}
      + [Förhandsvisa dimensioner](components/dimensions/view-dimensions.md)
      + [Dela upp dimensioner](components/dimensions/t-breakdown-fa.md)
      + [Tidsdelning av dimensioner](components/dimensions/time-parting-dimensions.md)
      + [Dimensioner med mycket hög kardinalitet](components/dimensions/high-cardinality.md)
   + [Mätvärden](components/apply-create-metrics.md)
   + Filter {#cja-filters}
      + [Översikt över filter](components/filters/filters-overview.md)
      + [Skapa ett filter](components/filters/create-filters.md)
      + [Hantera filter](components/filters/manage-filters.md)
      + [Snabbfilter](components/filters/quick-filters.md)
      + [Ad hoc-filter](components/filters/ad-hoc-filters.md)
      + [Operatorer](components/filters/operators.md)
   + Beräknade mätvärden {#cja-calcmetrics}
      + [Översikt över beräknade mätvärden](components/calc-metrics/calc-metr-overview.md)
      + Arbetsflöde för beräknade värden {#cm-workflow}
         + [Arbetsflöde för beräknade mätvärden](components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Hitta mätvärden](components/calc-metrics/cm-workflow/cm-finding.md)
         + [Skapa mätvärden](components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Mätvärdestyp och attribuering](components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Skapa ett enkelt mätvärde för sidvisningar per besök](components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Filtrerade mätvärden](components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Stapla och ersätta segment](components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrerade och viktade mätvärden](components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Använda funktioner](components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Mätvärden för deltagande](components/calc-metrics/cm-workflow/participation-metric.md)
         + [Tagga beräknade mätvärden](components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Godkänna beräknade mätvärden](components/calc-metrics/cm-workflow/cm-approving.md)
         + [Dela beräknade mätvärden](components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Hanterare för beräknade mätvärden](components/calc-metrics/cm-workflow/cm-manager.md)
      + [Grundfunktioner](components/calc-metrics/cm-functions.md)
      + [Avancerade funktioner](components/calc-metrics/cm-adv-functions.md)
   + Datumintervall {#cja-date-ranges}
      + [Översikt över datumintervall](components/date-ranges/overview.md)
      + [Skapa ett datumintervall](components/date-ranges/create.md)
      + [Hantera datumintervall](components/date-ranges/manage.md)
      + [Översikt över kalendern](components/date-ranges/calendar.md)
      + [Skapa anpassade datumintervall](components/date-ranges/custom-date-ranges.md)
      + [Datumjämförelse](components/date-ranges/time-comparison.md)
+ Kontrollpaneler för analyser {#cja-dashboards}
   + [Kontrollpaneler för analyser - översikt](mobile-app/home.md)
   + [Läraruppgifter](mobile-app/curator.md)
   + [Skapa ett styrkort](mobile-app/create-scorecard.md)
   + [Konfigurera chefer för att använda kontrollpaneler](mobile-app/set-up-execs.md)
   + [Snabbguide för chefsanvändare](mobile-app/executive.md)
+ Användningsexempel {#cja-usecases}
   + [Användningsexempel i Customer Journey Analytics](use-cases/cja-usecases.md)
   + [Kombinera rapportsviter med olika scheman](use-cases/combine-report-suites.md)
   + [Använda arrayer med objekt](use-cases/object-arrays.md)
   + [Använd bindningsdimensioner och mätvärden](use-cases/binding-dimensions-metrics.md)
   + [(B2B) Lägg till data på kontonivå som en uppslagsuppsättning](use-cases/b2b.md)
   + [Infoga Marketo Engage data i AEP och rapportera i CJA](use-cases/marketo.md)
   + [Ingest AEP-målgrupper into CJA](use-cases/ingest-aep-segments.md)
   + [Analysera data över olika kanaler](use-cases/cross-channel.md)
   + [Importera callcenter och webbdata](use-cases/call-center.md)
   + [Användningsfall vid datainhämtning](use-cases/data-ingestion.md)
   + [Använd mått för marknadsföringskanal](use-cases/marketing-channels.md)
   + [Importera data från Google Analytics till Adobe Experience Platform](use-cases/ga-to-cja.md)
   + [Rapport om Google Analytics data i CJA](use-cases/ga-to-cja-reporting.md)
+ Labs {#labs}
   + [Användarhandbok för Labs](labs/labs.md)
+ Felsökning {#troubleshooting}
   + [Jämför dina Adobe Analytics-data med CJA-data](troubleshooting/compare.md)
+ Sekretess {#cja-privacy}
   + [Sekretessöversikt](privacy/privacy-overview.md)
+ [CJA API](https://developer.adobe.com/cja-apis/docs/)
