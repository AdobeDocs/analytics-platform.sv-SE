---
title: Användarhandbok om Customer Journey Analytics
description: Customer Journey Analytics landningssida.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: e16bfa01dd3bedc96a147b2510ba33f4b88b01b9
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 2%

---

# Användarhandbok om Customer Journey Analytics

Den här tekniska handboken ger självhjälp för Customer Journey Analytics. Med Customer Journey Analytics kan ni hämta kunddata från valfri kanal (både online och offline) till Adobe Experience Platform. Och analysera sedan dessa data på samma sätt som ni gör med era befintliga digitala data med Analysis Workspace idag.

Med Customer Journey Analytics kan ni styra hur ni kopplar samman online- och offlinedata i Analysis Workspace med vilket kund-ID som helst, så att ni kan utföra attribuering, segment, flöde, utfall osv. i alla era kunddata.

## Vad är nytt?

Få en glimt av de senaste förbättringarna i Customer Journey Analytics-produkten och -dokumentationen! En omfattande lista med funktioner, förbättringar och korrigeringar finns i den detaljerade [versionsinformationen](../release-notes/latest.md). Besök sidan [Dokumentationsuppdateringar](../release-notes/doc-changes.md) om du vill hålla dig uppdaterad med de senaste ändringarna.

>[!BEGINTABS]

>[!TAB Content Analytics]

Med Content Analytics kan ni snabbt och enkelt undersöka stora volymer innehållsdata för att identifiera trender, upptäcka avvikelser, identifiera innehållets trötthet och få insikter från exponering.

[![bild](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB Delade mått ]

Gemensamma mätvärden och dimensioner utgör en central plats för att hantera mått och mätvärden som kan användas i ett valfritt antal datavyer. Dessa komponenter är särskilt användbara för organisationer som använder flera datavyer, särskilt om dessa datavyer har gemensamma gemensamma komponentinställningar.

[![bild](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)

>[!TAB AI-assistenten]

AI Assistant är en konversationsupplevelse som gör det möjligt för yrkesverksamma att utföra uppgifter snabbt - oavsett om de förstår koncept, felsöker problem eller söker igenom information. Det gör det även möjligt för icke-experter att utföra expertuppgifter och ökar den övergripande kvaliteten på arbetet.

[![bild](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guidad analys]

Guidad analys är nu tillgängligt direkt från Analysis Workspace, så att användare kan skapa instrumentpaneler med omfattande insikter från paneler, visualiseringar och guidade analyser.

[![bild](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)


>[!TAB Intelligenta bildtexter v2]

Intelligenta bildtexter stöds nu, med ytterligare gränssnittsförbättringar, för visualiseringar för [Rad](/help/analysis-workspace/visualizations/line.md) (inklusive flera rader), [Stapel](/help/analysis-workspace/visualizations/bar.md), [Vågrätt streck](/help/analysis-workspace/visualizations/horizontal-bar.md), [Område](/help/analysis-workspace/visualizations/area.md) (inklusive flera riktningslinjer), [Ring upp](/help/analysis-workspace/visualizations/donut.md), [Utfall](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) och [Flöde ](/help/analysis-workspace/visualizations/c-flow/flow.md) .

[![bild](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB Larm]

Med varningar kan du meddelas baserat på ändrade procentsatser eller specifika datapunkter. Du kan förhandsgranska hur ofta en avisering kommer att utlösas, skicka aviseringar via e-post eller SMS, skapa staplade aviseringar med mera.

[![bild](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Sammanfattningsdata]

Gör att du kan hämta in tidsseriedata som inte har något person-ID. Dessa tidsseriedata kan användas för att stödja olika användningsfall, t.ex.

- Presentera högnivåindikatorer som en del av eller bredvid data på händelsenivå.
- Överför mål per timme eller dag och positionera sedan dessa mål mot händelsenivåstatistik.

[![bild](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

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
      <strong> Jämför med Adobe Analytics </strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Översikt</a> - <a href="/help/getting-started/aa-to-cja.md">Utveckling</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Använd Adobe Analytics-data</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Funktionsstöd</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologi</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Databearbetning</a>
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
      <strong> Dela, exportera, integrera </strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projekt</a> - <a href="/help/mobile-app/home.md">Analysinstrumentpaneler</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a> - <a href="/help/components/exports/manage-exports.md">Cloud-export</a> - <a href="/help/integrations/overview.md">Integreringar</a>
    </td>
  </tr>
</table>

## Ytterligare resurser

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/sv/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Självstudiekurser</a> - <a href="https://helpx.adobe.com/se/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics produktbeskrivning</a> - <a href="https://helpx.adobe.com/se/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics (Customer Journey Analytics-tillägg) produktbeskrivning</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics-API:er</a> - <a href="/help/ai-assistant.md">AI-assistenten</a>
</td>
<td><strong>Datainmatning</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Översikt</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">Batch</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Källor</a> - <a href="/help/data-ingestion/serverapi.md">Server-API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Håll dig informerad, delta i communityn och höj din Customer Journey Analytics-upplevelse!</b><br>Besök Adobe Analytics community och diskutera funktionaliteten med andra verksamma. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">Gå med i communityn idag!</a></td></tr></tbody></table>
