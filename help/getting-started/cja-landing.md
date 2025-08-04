---
title: Användarhandbok om Customer Journey Analytics
description: Customer Journey Analytics landningssida.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 830e8312b4be2ffac907baca282ce71029e6ecc5
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 2%

---

# Användarhandbok om Customer Journey Analytics

Den här tekniska handboken ger självhjälp för Customer Journey Analytics. Med Customer Journey Analytics kan ni hämta kunddata från valfri kanal (både online och offline) till Adobe Experience Platform. Och analysera sedan dessa data på samma sätt som ni gör med era befintliga digitala data med Analysis Workspace idag.

Med Customer Journey Analytics kan ni styra hur ni kopplar samman online- och offlinedata i Analysis Workspace med vilket kund-ID som helst, så att ni kan utföra attribuering, segment, flöde, utfall osv. i alla era kunddata.

## Vad är nytt?

Få en glimt av de senaste förbättringarna i Customer Journey Analytics-produkten och -dokumentationen! En omfattande lista med funktioner, förbättringar och korrigeringar finns i den detaljerade [versionsinformationen](../release-notes/latest.md). Besök sidan [dokumentationsuppdateringar](../release-notes/doc-changes.md) om du vill hålla dig uppdaterad med de senaste dokumentationsuppdateringarna.

>[!BEGINTABS]

>[!TAB B2B edition]

Customer Journey Analytics B2B edition hjälper B2B-företag att anpassa sina marknadsförings-, sälj- och produktteam genom att tillhandahålla användbara kontoinsikter som ökar intäkterna. Med kontot som placeras i mitten av datamodellen fokuserar alla analyser på kontoresan.

[![bild](assets/learn-more-button.svg)](/help/getting-started/cja-b2b-edition.md)

>[!TAB Härledda fältfunktioner]

Nya härledda fältsfunktioner: [Datamath](/help/data-views/derived-fields/derived-fields.md#date-math), [Depth](/help/data-views/derived-fields/derived-fields.md#depth) och [Typecast](/help/data-views/derived-fields/derived-fields.md#typecast).

[![bild](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Content Analytics]

Med Content Analytics kan ni snabbt och enkelt undersöka stora volymer innehållsdata för att identifiera trender, upptäcka avvikelser, identifiera innehållets trötthet och få insikter från exponering.

[![bild](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB Händelsedjup]

Händelsedjup är en ny standarddimension som ger nya sätt att mäta och bättre förstå hur händelser placeras i kundsessioner. Dimensionen Händelsedjup möjliggör detaljerad spårning och analys av var specifika händelser inträffar i det sekventiella flödet av användarinteraktioner i en session.

[![bild](assets/learn-more-button.svg)](/help/components/dimensions/overview.md#standard-dimensions)


>[!TAB Delade mått ]

Gemensamma mätvärden och dimensioner utgör en central plats för att hantera mått och mätvärden som kan användas i ett valfritt antal datavyer. Dessa komponenter är särskilt användbara för organisationer som använder flera datavyer, särskilt om dessa datavyer har gemensamma gemensamma komponentinställningar.

[![bild](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)


<!--
>[!TAB AI Assistant] 

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace - whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

[![image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guided Analysis] 

Guided Analysis is now available directly from within Analysis Workspace, enabling users to create dashboards with comprehensive insights from panels, visualizations, and guided analyses.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)



>[!TAB Intelligent captions v2] 

Intelligent captions are now supported, with additional interface improvements, for [Line](/help/analysis-workspace/visualizations/line.md) (including multi-line), [Bar](/help/analysis-workspace/visualizations/bar.md), [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md), [Area](/help/analysis-workspace/visualizations/area.md) (including multiple Area lines), [Donut](/help/analysis-workspace/visualizations/donut.md), [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) visualizations.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Alerts] 

Alerts allow you to be notified based on changed percentages or specific data points. You can preview how often an alert will trigger, send alerts by email or SMS, create stacked alerts, and more.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Summary data] 

Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as 

- Presenting high-level performance indicators as part of or next to event-level data. 
- Uploading targets or goals at an hourly or daily basis, then positioning these targets or goals against event-level metrics. 

[![image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

-->

>[!TAB Diagrambaserad utjämning*]

Med hjälp av diagrambaserad sammanfogning kan du använda identitetsdiagrammet från Experience Platform Identity Service för att få en bättre bild av kundresan genom att: <ul><li>Sammanfoga datauppsättningar med olika identifierare utan att behöva extrahera, omvandla och läsa in ytterligare data för att spegla en enda identifierare.</li> <li>Förbättra täckningen av preferens- eller gyllene identitet för en enskild datauppsättning genom att dela identiteter mellan datauppsättningar.</li><li>Justera profiler som skapats i Real-Time Customer Data Platform och Journey Optimizer med personer i Customer Journey Analytics.</li></ul>

[![bild](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_Du måste ha Prime-paketet för diagrambaserad sammanfogning._*

>[!TAB BI-tillägg*]

BI-tillägget ger SQL-åtkomst till de datavyer som du har definierat i Customer Journey Analytics. Nu kan du använda ditt BI-favoritverktyg (Power BI Desktop, Tableau Desktop, Looker, Juyter Notebook och RStudio) för att skapa rapporter och kontrollpaneler baserat på samma datavyer som Customer Journey Analytics-användare använder i sina Analysis Workspace-projekt. [Användningsexempel](/help/use-cases/data-views/bi-extension-usecases.md) har angetts.

[![bild](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_Du måste ha Select-paketet eller senare för att kunna använda BI-tillägget._*


>[!ENDTABS]

## Börja med grunderna

Börja med att läsa materialet i länkarna nedan för att bekanta dig med Customer Journey Analytics funktioner.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Förutom onlinedata</strong><br/>Lär dig hur Customer Journey Analytics jämför med Adobe Analytics, vilka funktioner som delas och hur du kan använda dina Analytics-data.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Importera och använd data</strong><br/>Lär dig mer om de alternativ som du måste importera data till Experience Platform och använda dem för analys och rapportering i Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Guidad analys</strong><br/>Lär dig hur du använder arbetsflöden för att få data och insikter om din kunds produktupplevelse. Product Analytics genom guidad analys..
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Använd Analysis Workspace för att utföra grundläggande och avancerade analyser, som attribuering, flödes- och utfallsdiagram, dimensionsanalyser.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## Utforska dokumentationen

Jämför Customer Journey Analytics med Adobe Analytics. Och hur ni får in era data i lösningen och sedan kan ta fram, visa, analysera och demokratisera dessa data och de analyser och rapporter som blir resultatet.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong> Jämför med Adobe Analytics </strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Översikt</a> - <a href="/help/getting-started/aa-to-cja.md">Utveckling</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Använd Adobe Analytics-data</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Funktionsstöd</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologi</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Databearbetning</a> - <a href="/help/getting-started/cja-b2b-edition.md">Customer Journey Analytics B2B edition</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong> Anslutningar </strong><br/><a href="/help/connections/overview.md">Översikt</a> - <a href="/help/connections/create-connection.md">Skapa</a> - <a href="/help/connections/manage-connections.md">Hantera</a> - <a href="/help/stitching/overview.md">Stitch</a> - <a href="/help/connections/combined-dataset.md">Kombinerade händelsedatamängder</a> - <a href="/help/connections/standard-lookups.md">Standarduppslag</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong> Datavyer </strong><br/><a href="/help/data-views/data-views.md">Översikt</a> - <a href="/help/data-views/create-dataview.md">Skapa eller redigera</a> - <a href="/help/data-views/session-settings.md">Sessionsinställningar</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Härledda fält</a> - <a href="/help/data-views/summary-data.md">Sammanfattningsdata</a> - <a href="/help/data-views/component-reference.md">Komponentreferens</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong> Workspace-projekt </strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Grundläggande</a> och <a href="/help/analysis-workspace/perform-adv-analysis.md">Avancerad analys</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Projekt</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualiseringar</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Paneler</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong> Guidad analys </strong><br/><a href="/help/guided-analysis/overview.md">Översikt</a> - <a href="/help/guided-analysis/types/active-growth.md">Användartillväxt</a> - <a href="/help/guided-analysis/types/trends.md">Trender</a> - <a href="/help/guided-analysis/types/funnel.md">Tratt</a> - <a href="/help/guided-analysis/types/release-impact.md">Effekt</a> - <a href="/help/guided-analysis/industry-use-cases.md">Branschanvändning</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong> Dela, exportera, integrera </strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projekt</a> - <a href="/help/mobile-app/home.md">Analysinstrumentpaneler</a> - <a href="/help/report-builder/rb-overview.md">Report Builder</a> - <a href="/help/components/exports/manage-exports.md">Cloud-export</a> - <a href="/help/integrations/overview.md">Integreringar</a>
    </td>
  </tr>
</table>

## Ytterligare resurser

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/sv/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Självstudiekurser</a> - <a href="https://helpx.adobe.com/se/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics produktbeskrivning</a> - <a href="https://helpx.adobe.com/se/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics (Customer Journey Analytics-tillägg) produktbeskrivning</a> - <a href="https://helpx.adobe.com/se/legal/product-descriptions/customer-journey-analytics-b2b.html" target="_blank">Customer Journey Analytics B2B edition produktbeskrivning</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API:er</a> - <a href="/help/ai-assistant.md">AI Assistant</a>
</td>
<td><strong>Datainmatning</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Översikt</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">Batch</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Källor</a> - <a href="/help/data-ingestion/serverapi.md">Server-API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Håll dig informerad, delta i communityn och höj din Customer Journey Analytics-upplevelse!</b><br>Besök Adobe Analytics community och diskutera funktionaliteten med andra verksamma. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">Gå med i communityn idag!</a></td></tr></tbody></table>
