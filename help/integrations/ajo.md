---
title: Integrera Adobe Journey Optimizer med Customer Journey Analytics
description: Hämta in data som genererats av Adobe Journey Optimizer och analysera dem med Analysis Workspace i Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 13c3f99dba7725553c775df4492803f759ebead5
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 0%

---

# Integrera Journey Optimizer med Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/get-started) hjälper er att leverera sammankopplade, kontextuella och personaliserade upplevelser. Det gör att era kunder får ta nästa steg i kundresan.

Du kan konfigurera data som genereras av Journey Optimizer för att utföra avancerad analys i Customer Journey Analytics. Du kan konfigurera integreringen automatiskt. Vid behov kan du göra ytterligare manuella anpassningar av datauppsättningar, dimensioner eller mätvärden som är tillgängliga i din anslutning eller datavyer.

## Konfigurera Journey Optimizer-integrering automatiskt

{{release-limited-testing-section}}

Journey Optimizer har stöd för att använda Customer Journey Analytics som rapporteringsmotor. Se [Kom igång med det nya rapporteringsgränssnittet](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja) i Journey Optimizer-dokumentationen.

När du har aktiverat Customer Journey Analytics-rapportering för Journey Optimizer får du automatiskt en [anslutning](/help/connections/overview.md) och [datavy](/help/data-views/data-views.md) skapas för den specifika sandlådan.

### Anslutning

Anslutningen har namnet **[!UICONTROL AJO Enabled Connection (*sandlådenamn *)]**och har följande ur kartongvärden för konfiguration och datauppsättningar:

| **Anslutningsinställningar** | Värde |
|---|---| 
| [!UICONTROL Connection name] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Connection description] | [!UICONTROL *Beskriv din anslutning här*] |
| [!UICONTROL Tags] | [!UICONTROL *Markera taggar*] |


| **Datainställningar** | Värde |
|---|---| 
| [!UICONTROL Enable rolling data window] | Aktiverad. [!UICONTROL Selected number of months] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *namn på sandlåda*] (inaktiverat; du kan inte ändra den här inställningen). |
| [!UICONTROL Average number of daily events] | mindre än 1 miljon (inaktiverat; du kan inte ändra den här inställningen). |


| Namn på datauppsättning | Schema | Datauppsättningstyp | Datakälltyp | Person-ID | Nyckel | Matchningsnyckel | Importera nya data | Backfill-data |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO Entity Dataset] | [!UICONTROL AJO Entity Record Schema] | [!UICONTROL Lookup] | [!UICONTROL Other] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Status grön](assets/../../connections/assets/status-green.svg) På | ![Status grå](assets/../../connections/assets/status-gray.svg) Av |
| [!UICONTROL Journey Step Events] | [!UICONTROL Journey Step Event schema for Journey Orchestration] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL  IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) På | ![Status grå](assets/../../connections/assets/status-gray.svg) Av |
| [!UICONTROL AJO Email Tracking Experience Event Dataset] | [!UICONTROL AJO Email Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) På | ![Status grå](assets/../../connections/assets/status-gray.svg) Av |
| [!UICONTROL AJO Email Tracking Experience Event Dataset] | [!UICONTROL AJO Email Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) På | ![Status grå](assets/../../connections/assets/status-gray.svg) Av |
| [!UICONTROL AJO Message Feedback Event Dataset] | [!UICONTROL AJO Message Feedback Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) På | ![Status grå](assets/../../connections/assets/status-gray.svg) Av |
| [!UICONTROL AJO Push Tracking Experience Event Dataset] | [!UICONTROL AJO Push Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) På | ![Status grå](assets/../../connections/assets/status-gray.svg) Av |


### Datavy

Datavyn har namnet **AJO Enable Data View (*sandlådenamn*)**.

- I **[!UICONTROL Configure]** och följande värden är konfigurerade utanför rutan.

  | Inställningar | Värde |
  |---|---|
  | [!UICONTROL Connection] | AJO Enabled Connection (*sandlådenamn*) |
  | [!UICONTROL Name] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL External ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (härledd från namnet) |
  | [!UICONTROL Description] | `undefined` |

  {style="table-layout:fixed"}

  | Kompatibilitet | Värde |
  |---|---|
  | [!UICONTROL Set as default data view in Adobe Journey Optimizer] | Aktiverat (standard).<br/><br/>Med det här konfigurationsalternativet kan du ange en datavy som ska användas med Journey Optimizer, utan att behöva konfigurera manuellt. Mer information om hur du aktiverar det här konfigurationsalternativet (om det inte redan är aktiverat som standard) finns i [Kompatibilitet](/help/data-views/create-dataview.md#compatibility) avsnitt i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md). <br/><br/>När du inaktiverar alternativet visas en dialogruta om du vill fortsätta att ändra standarddatavyn. När du väljer **[!UICONTROL Continue]** måste du välja en annan datavy som standarddatavy. Välj **[!UICONTROL Confirm]** för att bekräfta ditt val. Välj **[!UICONTROL Cancel]** om du vill avbryta ändringen av standarddatavyn. |

  | Behållare | Värde |
  |---|---|
  | [!UICONTROL Person container name] | `Person` |
  | [!UICONTROL Session container name] | `Session` |
  | [!UICONTROL Event container name] | `Event` |

  | Kalender | Värde |
  |---|---|
  | [!UICONTROL Time zone] | Tidszon som överensstämmer med din plats |
  | [!UICONTROL Calendar type] | Gregorianska |
  | [!UICONTROL First month of the year] | Januari |
  | [!UICONTROL First day of the week] | söndag |


- I **Komponenter** tab:
   - Alla mått och dimensioner som har [!UICONTROL (AJO)] läggs till i namnet automatiskt som en del av den här automatiska konfigurationen.
   - Vissa mått eller mått, som har lagts till automatiskt, baseras på härledda fält. De här härledda fälten skapas specifikt för den här integreringen. Exempelvis måttet [!UICONTROL Landing Page Clicks (AJO)] baseras på [!UICONTROL Landing Page Clicks] härlett fält.
   - Vissa mått eller dimensioner har ytterligare konfiguration. Till exempel: [!UICONTROL Spam Complaint (AJO)] har [!UICONTROL Format] och [!UICONTROL Include Exclude Values] inställningar som används.
   - Alla automatiskt tillagda mått och mått har en sammanhangsetikett med namnet `:`*`name_of_metric_or_dimension`*. Till exempel [!UICONTROL Landing Page Clicks (AJO)] metriska värden har kontextetiketten `:Landing page clicks (AJO)`.

- I **[!UICONTROL Settings]** -fliken används inga specifika konfigurationsvärden

>[!IMPORTANT]
>
>Om du ändrar något av de automatiskt konfigurerade värdena för anslutningen och datavyn påverkas Journey Optimizer-rapporteringen som är beroende av och använder den automatiskt konfigurerade Customer Journey Analytics-integreringen.


## Konfigurera en datavy som ska användas med Journey Optimizer manuellt

I följande avsnitt beskrivs hur du manuellt kan använda data som genererats av Journey Optimizer för att utföra avancerade analyser i Customer Journey Analytics. Detta är nödvändigt endast om [alternativ för automatisk konfiguration](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) är inte tillräckligt för dina behov.

### Skicka data från Journey Optimizer till Experience Platform

Adobe Experience Platform är den centrala datakällan och länken mellan Journey Optimizer och Customer Journey Analytics. Se [Kom igång med datauppsättningar](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) i användarhandboken för Journey Optimizer om hur du skickar Journey Optimizer-data till Experience Platform som en datauppsättning.

### Skapa en anslutning i Customer Journey Analytics

När Journey Optimizer data finns i Adobe Experience Platform kan man [Skapa en anslutning](/help/connections/create-connection.md) baserat på era Journey Optimizer-datauppsättningar. Du kan också lägga till Journey Optimizer-datauppsättningar i en befintlig anslutning.

Välj och konfigurera följande datauppsättningar:

| Datauppsättning | Datauppsättningstyp | Anslutningsinställningar | Beskrivning |
| --- | --- | --- | --- |
| AJO Message Feedback Event Dataset | Händelse | Person-ID: `IdentityMap` | Innehåller meddelandeleveranshändelser, till exempel[!UICONTROL Sends]och[!UICONTROL Bounces]&#39;. |
| AJO Experience Event-datauppsättning för e-postspårning | Händelse | Person-ID: `IdentityMap` | Innehåller e-postspårningshändelser som &#39;[!UICONTROL Opens]&#39;, &#39;[!UICONTROL Clicks]&#39;, och &#39;[!UICONTROL Unsubscribes]&#39;. |
| AJO Push Tracking Experience, händelsedatauppsättning | Händelse | Person-ID: `IdentityMap` | Innehåller push-spårningshändelser som &#39;[!UICONTROL App Launches]&#39;. |
| Resestegshändelser | Händelse | Person-ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Innehåller händelser som visar vilka profiler som deltog i varje nod av resan. |
| AJO Entity Dataset | Sök | Nyckel: `_id`<br>Matchningsnyckel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Innehåller klassificeringar som kopplar metadata för resa och kampanj till alla händelsedata för Journey Optimizer. |

{style="table-layout:auto"}


### Konfigurera datavyn så att den passar Journey Optimizer mått och mått

När en anslutning har skapats kan du skapa en eller flera [Datavyer](/help/data-views/create-dataview.md) för att konfigurera önskade mått och mätvärden som är tillgängliga i Customer Journey Analytics.

>[!NOTE]
>
>Datamatchningar mellan Journey Optimizer och Customer Journey Analytics är vanligtvis mindre än 1-2 %. Större avvikelser är möjliga för data som samlats in under de senaste två timmarna. Använd datumintervall, exklusive idag, för att minska avvikelser som inbegriper bearbetningstid.


#### Konfigurera dimensioner i datavyn

Du kan skapa följande mått i en datavy för att få en ungefärlig paritet med liknande dimensioner i Journey Optimizer. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Datavy Manager för mer information om alternativ för dimensionsanpassning.

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

#### Konfigurera mått i datavyn

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
| InApp-utlösare | Det antal gånger som beslutsmotorn föreslog att meddelandet ska visas. Mobile SDK kunde åsidosätta beslutet och minska antalet faktiska skärmar. | Använda schemasträntelementet `_experience.decisioning.propositionEventType.trigger` | |
| InApp-avvisningar | Antalet gånger som ett InApp-meddelande tas bort från användargränssnittet av SDK | Använda schemasträntelementet `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### Konfigurera beräknade värden i Analysis Workspace

När du har konfigurerat önskade mått och mätvärden för Journey Optimizer datauppsättning kan du även konfigurera [Beräknade mått](/help/components/calc-metrics/calc-metr-overview.md) för ytterligare insikter om dessa data. Dessa beräknade värden baseras på ovanstående mått som skapats i Data View Manager.

| Beräknat mått | Beskrivning | Formel |
| --- | --- | --- |
| Skickade meddelanden | Totalt antal skickade meddelanden. Inkluderar slutförda eller misslyckade meddelanden. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Levererade meddelanden | Antalet e-postmeddelanden som levereras till kunderna. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
