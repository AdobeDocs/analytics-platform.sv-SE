---
title: Integrera Adobe Journey Optimizer (AJO) med Customer Journey Analytics (CJA)
description: Hämta in data som genererats av AJO och analysera dem med Analysis Workspace i CJA.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: adf5671f80b122b7bcc77dea9c3e57d133961266
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---

# Integrera Adobe Journey Optimizer med Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) hjälper er att leverera sammankopplade, kontextuella och personaliserade upplevelser. Det gör att era kunder får ta nästa steg i kundresan.

Du kan importera data som genererats av Journey Optimizer för att utföra avancerad analys i Customer Journey Analytics genom att utföra följande steg:

## Skicka data från Journey Optimizer till Adobe Experience Platform

Adobe Experience Platform är den centrala datakällan och länken mellan Journey Optimizer och Customer Journey Analytics. Se [Kom igång med datauppsättningar](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) i användarhandboken för Journey Optimizer om hur du skickar Journey Optimizer-data till Platform som en datauppsättning.

## Skapa en anslutning i Customer Journey Analytics

När Journey Optimizer data finns i Adobe Experience Platform kan man [Skapa en anslutning](/help/connections/create-connection.md) baserat på din Journey Optimizer-datauppsättning. Markera den datauppsättning som du skickade till plattformen.

| Datauppsättning | Datauppsättningstyp | Anslutningsinställningar | Beskrivning |
| --- | --- | --- | --- |
| AJO Message Feedback Event Dataset | Händelse | Person-ID: `IdentityMap` | Innehåller meddelandeleveranshändelser, t.ex.[!UICONTROL Sends]och[!UICONTROL Bounces]&#39;. |
| AJO Email Tracking Experience, händelsedatauppsättning | Händelse | Person-ID: `IdentityMap` | Innehåller e-postspårningshändelser som &#39;[!UICONTROL Opens]&#39;, &#39;[!UICONTROL Clicks]&#39;, och &#39;[!UICONTROL Unsubscribes]&#39;. |
| AJO Push Tracking Experience, händelsedatauppsättning | Händelse | Person-ID: `IdentityMap` | Innehåller push-spårningshändelser som &#39;[!UICONTROL App Launches]&#39;. |
| Resestegshändelser | Händelse | Person-ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Innehåller händelser som visar vilka profiler som deltog i varje nod av resan. |
| AJO-entitetsdatauppsättning | Post | Nyckel: `_id`<br>Matchningsnyckel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Innehåller klassificeringar som kopplar metadata för resa och kampanj till alla AJO-händelsedata. |

## Konfigurera datavyn så att den passar Journey Optimizer mått och mått

När en anslutning har skapats kan du skapa en eller flera [Datavyer](/help/data-views/create-dataview.md) för att konfigurera önskade mått och mätvärden som är tillgängliga i Customer Journey Analytics.

>!![NOTE]
Datamatchningar mellan AJO och CJA är vanligtvis mindre än 1-2 %. Större avvikelser är möjliga för data som samlats in under de senaste två timmarna. Använd datumintervall, exklusive idag, för att minska avvikelser som inbegriper bearbetningstid.

### Konfigurera dimensioner i datavyn

Du kan skapa följande mått i en datavy för att få en ungefärlig paritet med liknande dimensioner i Journey Optimizer. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Data View Manager för mer information om dimensionsanpassningsalternativ.

| Dimension | Schemaelement | Komponentinställningar |
| --- | --- | --- |
| Resensnamn | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Komponenttyp: Dimension |
| Resenamn och version | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Komponenttyp: Dimension |
| Namn på resenod | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Komponenttyp: Dimension |
| Resensnodtyp | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Komponenttyp: Dimension |
| Kampanjnamn | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Komponenttyp: Dimension |
| Kanal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Komponenttyp: Dimension |
| Push-titel | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Komponenttyp: Dimension |
| E-postämne | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Komponenttyp: Dimension |
| Länketikett | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Komponenttyp: Dimension |
| Experimentnamn | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Komponenttyp: Dimension<br>Kontextetiketter: Experimentationsexperiment |
| Behandlingsnamn | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Komponenttyp: Dimension<br>Kontextetiketter: Experimentationsvariant |
| Felorsak vid e-postleverans | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Komponenttyp: Dimension |
| Orsak till undantag av e-postleverans | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Komponenttyp: Dimension |

{style=&quot;table-layout:auto&quot;}

### Konfigurera mått i datavyn

Du kan skapa följande mätvärden i en datavy för att få en ungefärlig paritet med liknande mätvärden i Journey Optimizer. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Data View Manager för mer information om alternativ för anpassning av mätvärden.

| Mått | Beskrivning | Schemaelement | Komponentinställningar |
| --- | --- | --- | --- |
| Studsar | Antalet meddelanden som studsade, inklusive både omedelbara studsar och studsar efter leveransen. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Om något villkor uppfylls<br>Lika med: `bounce`, är lika med: `denylist` |
| studsar efter leverans | Vissa e-posttjänster rapporterar e-postmeddelanden som skickas och skickar dem sedan. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `async` |
| E-postklick | Antalet klick i meddelanden. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `click` |
| E-post öppnas | Antalet öppnade meddelanden. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `open` |
| Fel | Antalet meddelanden som har felrapporterats. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `error` |
| Exkluderar | Antalet meddelanden som utelämnats. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `exclude` |
| Skickar | Antalet meddelanden som e-postleverantörer accepterade. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `sent` |
| Skräppost | Antalet skräppostklagomål. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `spam_complaint` |
| Avbeställ | Antal avbrutna prenumerationer. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `unsubscribe` |

{style=&quot;table-layout:auto&quot;}

### Konfigurera beräknade värden i Analysis Workspace

När du har konfigurerat önskade mått och mätvärden för Journey Optimizer datauppsättning kan du även konfigurera [Beräknade mått](/help/components/calc-metrics/calc-metr-overview.md) för ytterligare insikter om dessa data. Dessa beräknade värden baseras på ovanstående mått som skapats i Data View Manager.

| Beräknat mätvärde | Beskrivning | Formel |
| --- | --- | --- |
| Skickade meddelanden | Totalt antal skickade meddelanden. Inkluderar slutförda eller misslyckade meddelanden. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Levererade meddelanden | Antalet e-postmeddelanden som levereras till kunderna. | `[Sends] - [Bounces After Delivery]` |

{style=&quot;table-layout:auto&quot;}
