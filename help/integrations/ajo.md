---
title: Integrera Adobe Journey Optimizer med Customer Journey Analytics
description: Hämta in data som genererats av Adobe Journey Optimizer och analysera dem med Analysis Workspace i Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 5d89d6c3dae4964bc4085110d7baa51199e27044
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 0%

---

# Integrera Adobe Journey Optimizer med Adobe Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) hjälper er att leverera sammankopplade, kontextuella och personaliserade upplevelser. Det gör att era kunder får ta nästa steg i kundresan.

Du kan importera data som genererats av Journey Optimizer för att utföra avancerad analys i Customer Journey Analytics genom att utföra följande steg:

## Skicka data från Journey Optimizer till Adobe Experience Platform

Adobe Experience Platform är den centrala datakällan och länken mellan Journey Optimizer och Customer Journey Analytics. Se [Kom igång med datauppsättningar](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) i användarhandboken för Journey Optimizer om hur du skickar Journey Optimizer-data till Platform som en datauppsättning.

## Skapa en anslutning i Customer Journey Analytics

När Journey Optimizer data finns i Adobe Experience Platform kan man [Skapa en anslutning](/help/connections/create-connection.md) baserat på era Journey Optimizer-datauppsättningar. Du kan också lägga till Journey Optimizer-datauppsättningar i en befintlig anslutning.

Välj och konfigurera följande datauppsättningar:

| Datauppsättning | Datauppsättningstyp | Anslutningsinställningar | Beskrivning |
| --- | --- | --- | --- |
| AJO Message Feedback Event Dataset | Händelse | Person-ID: `IdentityMap` | Innehåller meddelandeleveranshändelser, till exempel[!UICONTROL Sends]och[!UICONTROL Bounces]&#39;. |
| AJO Email Tracking Experience, händelsedatauppsättning | Händelse | Person-ID: `IdentityMap` | Innehåller e-postspårningshändelser som &#39;[!UICONTROL Opens]&#39;, &#39;[!UICONTROL Clicks]&#39;, och &#39;[!UICONTROL Unsubscribes]&#39;. |
| AJO Push Tracking Experience, händelsedatauppsättning | Händelse | Person-ID: `IdentityMap` | Innehåller push-spårningshändelser som &#39;[!UICONTROL App Launches]&#39;. |
| Resestegshändelser | Händelse | Person-ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Innehåller händelser som visar vilka profiler som deltog i varje nod av resan. |
| AJO-entitetsdatauppsättning | Sök | Nyckel: `_id`<br>Matchningsnyckel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Innehåller klassificeringar som kopplar metadata för resa och kampanj till alla händelsedata för Adobe Journey Optimizer. |

{style="table-layout:auto"}


## Konfigurera datavyn så att den passar Journey Optimizer mått och mått

När en anslutning har skapats kan du skapa en eller flera [Datavyer](/help/data-views/create-dataview.md) för att konfigurera önskade mått och mätvärden som är tillgängliga i Customer Journey Analytics.

>[!NOTE]
>
>Datamatchningar mellan Adobe Journey Optimizer och Customer Journey Analytics är vanligtvis mindre än 1-2 %. Större avvikelser är möjliga för data som samlats in under de senaste två timmarna. Använd datumintervall, exklusive idag, för att minska avvikelser som inbegriper bearbetningstid.


### Konfigurera dimensioner i datavyn

Du kan skapa följande mått i en datavy för att få en ungefärlig paritet med liknande dimensioner i Journey Optimizer. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Data View Manager för mer information om dimensionsanpassningsalternativ.

| Dimension | Schemaelement | Komponentinställningar |
| --- | --- | --- |
| Resensnamn | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Komponenttyp: Dimension |
| Resenamn och version | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Komponenttyp: Dimension |
| Namn på resenod | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | Komponenttyp: Dimension |
| Resensnodtyp | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Komponenttyp: Dimension |
| Kampanjnamn | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Komponenttyp: Dimension |
| Kanal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Komponenttyp: Dimension |
| Push-titel | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Komponenttyp: Dimension |
| E-postämne | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Komponenttyp: Dimension |
| Länketikett | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Komponenttyp: Dimension |
| Experimentnamn | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Komponenttyp: Dimension<br>Sammanhangsetiketter: Experimentationsexperiment |
| Behandlingsnamn | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Komponenttyp: Dimension<br>Kontextetiketter: Experimentationsvariant |
| Felorsak vid e-postleverans | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Komponenttyp: Dimension |
| Orsak till undantag av e-postleverans | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Komponenttyp: Dimension |
| Elementetikett | `_experience.decisioning.propositionAction.label` | Komponenttyp: Dimension |

{style="table-layout:auto"}

### Konfigurera mått i datavyn

Du kan skapa följande mätvärden i en datavy för att få en ungefärlig paritet med liknande mätvärden i Journey Optimizer. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Data View Manager för mer information om alternativ för anpassning av mätvärden.

| Mått | Beskrivning | Schemaelement | Komponentinställningar |
| --- | --- | --- | --- |
| Studsar | Antalet meddelanden som studsade, inklusive både omedelbara studsar och studsar efter leveransen. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Om något villkor uppfylls<br>Lika med: `bounce`, är lika med: `denylist` |
| studsar efter leverans | Vissa e-posttjänster rapporterar e-postmeddelanden som skickas och skickar dem sedan. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: lika med `async` |
| E-postklick | Antalet klick i meddelanden. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: lika med `click` |
| E-post öppnas | Antalet öppnade meddelanden. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: lika med `open` |
| Fel | Antalet meddelanden som har felrapporterats. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: lika med `error` |
| Exkluderar | Antalet meddelanden som utelämnats. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: lika med `exclude` |
| Skickar | Antalet meddelanden som e-postleverantörer accepterade. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: lika med `sent` |
| Skräppost | Antalet skräppostklagomål. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: lika med `spam_complaint` |
| Avbeställ | Antal avbrutna prenumerationer. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponenttyp: Mått<br>Inkludera exkluderingsvärden: lika med `unsubscribe` |
| Edge Sends | Antalet gånger som gränsnätverket skickar ett meddelande till antingen webben eller mobil SDK | Använda schemasträntelementet `_experience.decisioning.propositionEventType.send` | |
| Inkommande skärmar | Antalet gånger som ett webb- eller InApp-meddelande visas för användaren | Använda schemasträntelementet `_experience.decisioning.propositionEventType.display` | |
| Inkommande klick | Antal webbklick eller InApp-meddelandeklick | Använda schemasträntelementet `_experience.decisioning.propositionEventType.interact` | |
| InApp-utlösare | Det antal gånger som beslutsmotorn föreslog att meddelandet ska visas. Mobile SDK kunde åsidosätta beslutet om att minska antalet faktiska skärmar. | Använda schemasträntelementet `_experience.decisioning.propositionEventType.trigger` | |
| InApp-avvisningar | Antalet gånger som ett InApp-meddelande tas bort från användargränssnittet av SDK | Använda schemasträntelementet `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

### Konfigurera beräknade värden i Analysis Workspace

När du har konfigurerat önskade mått och mätvärden för Journey Optimizer datauppsättning kan du även konfigurera [Beräknade mått](/help/components/calc-metrics/calc-metr-overview.md) för ytterligare insikter om dessa data. Dessa beräknade värden baseras på ovanstående mått som skapats i Data View Manager.

| Beräknat mått | Beskrivning | Formel |
| --- | --- | --- |
| Skickade meddelanden | Totalt antal skickade meddelanden. Inkluderar slutförda eller misslyckade meddelanden. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Levererade meddelanden | Antalet e-postmeddelanden som levereras till kunderna. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
