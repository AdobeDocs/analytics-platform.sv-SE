---
title: Integrera Adobe Journey Optimizer
description: Hämta in data som genererats av Adobe Journey Optimizer och analysera dem med Analysis Workspace i Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '3354'
ht-degree: 0%

---

# Integrera Journey Optimizer

[Adobe Journey Optimizer](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/get-started/get-started) hjälper dig att leverera sammankopplade, kontextuella och personaliserade upplevelser. Det gör att era kunder får ta nästa steg i kundresan.

Du kan konfigurera data som genereras av Journey Optimizer för att utföra avancerad analys i Customer Journey Analytics. Du kan konfigurera integreringen automatiskt. Vid behov kan du göra ytterligare manuella anpassningar av datauppsättningar, dimensioner eller mätvärden som är tillgängliga i din anslutning eller datavyer.

## Konfigurera Journey Optimizer-integrering automatiskt

Journey Optimizer har stöd för att använda Customer Journey Analytics som rapportmotor. Se [Kom igång med det nya rapporteringsgränssnittet](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) i Journey Optimizer-dokumentationen.

När du har aktiverat Customer Journey Analytics-rapportering för Journey Optimizer skapas automatiskt en [anslutning](/help/connections/overview.md) och [datavy](/help/data-views/data-views.md) för den specifika sandlådan.

### Anslutning

Anslutningen har namnet **[!UICONTROL AJO Enabled Connection (*sandbox name *)]**&#x200B;och har följande utanför rutans värden för konfiguration och datauppsättningar:

| **Anslutningsinställningar** | Värde |
|---|---|
| [!UICONTROL Connection name] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Connection description] | [!UICONTROL *Beskriv din anslutning här*] |
| [!UICONTROL Tags] | [!UICONTROL *Markera taggar*] |


| **Datainställningar** | Värde |
|---|---|
| [!UICONTROL Enable rolling data window] | Aktiverad. [!UICONTROL Selected number of months] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *namnet på sandlådan*] (inaktiverad; du kan inte ändra den här inställningen). |
| [!UICONTROL Average number of daily events] | mindre än 1 miljon (inaktiverat; du kan inte ändra den här inställningen). |


| Namn på datauppsättning | Schema | Datauppsättningstyp | Datakälltyp | Person-ID | Nyckel | Matchningsnyckel | Importera nya data | Backfill-data |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO Entity Dataset] | [!UICONTROL AJO Entity Record Schema] | [!UICONTROL Lookup] | [!UICONTROL Other] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Status grön](assets/../../connections/assets/status-green.svg) på | ![Status grå](assets/../../connections/assets/status-gray.svg) av |
| [!UICONTROL Journey Step Events] | [!UICONTROL Journey Step Event schema for Journey Orchestration] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL &#x200B; IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) på | ![Status grå](assets/../../connections/assets/status-gray.svg) av |
| [!UICONTROL AJO Email Tracking Experience Event Dataset] | [!UICONTROL AJO Email Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) på | ![Status grå](assets/../../connections/assets/status-gray.svg) av |
| [!UICONTROL AJO Message Feedback Event Dataset] | [!UICONTROL AJO Message Feedback Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) på | ![Status grå](assets/../../connections/assets/status-gray.svg) av |
| [!UICONTROL AJO Push Tracking Experience Event Dataset] | [!UICONTROL AJO Push Tracking Experience Event Schema] | [!UICONTROL Event] | [!UICONTROL Other] | [!UICONTROL IdentityMap(\<primary\>)] | - | - | ![Status grön](assets/../../connections/assets/status-green.svg) på | ![Status grå](assets/../../connections/assets/status-gray.svg) av |


### Datavy

Datavyn har namnet **AJO Enable Data View (Aktivera datavy) (*sandlådenamn*)**.

- På fliken **[!UICONTROL Configure]** är följande värden konfigurerade utanför rutan.

  | Inställningar | Värde |
  |---|---|
  | [!UICONTROL Connection] | AJO Enabled Connection (*sandlådenamn*) |
  | [!UICONTROL Name] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL External ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (härledd från namnet) |
  | [!UICONTROL Description] | `undefined` |

  {style="table-layout:fixed"}

  | Kompatibilitet | Värde |
  |---|---|
  | [!UICONTROL Set as the default data view in Adobe Journey Optimizer] | Aktiverat (standard).<br/><br/>Med det här konfigurationsalternativet kan du ange en datavy som ska användas med Journey Optimizer, utan att behöva konfigurera manuellt. Mer information om hur du aktiverar det här konfigurationsalternativet (om det inte redan är aktiverat som standard) finns i avsnittet [Kompatibilitet](/help/data-views/create-dataview.md#compatibility) i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md). <br/><br/>När du inaktiverar alternativet visas en dialogruta om du vill fortsätta ändra standarddatavyn. När du väljer **[!UICONTROL Continue]** måste du välja en annan datavy som standarddatavy. Välj **[!UICONTROL Confirm]** för att bekräfta ditt val. Välj **[!UICONTROL Cancel]** om du vill avbryta ändringen av standarddatavyn. |

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


- På fliken **Komponenter**:
   - Alla mått och mått som har [!UICONTROL (AJO)] tillagda i sitt namn läggs till automatiskt som en del av den här automatiska konfigurationen.
   - Vissa mått som har lagts till automatiskt baseras på härledda fält. De här härledda fälten skapas specifikt för den här integreringen. Måttet [!UICONTROL Landing Page Clicks (AJO)] är till exempel baserat på det härledda fältet [!UICONTROL Landing Page Clicks].
   - Vissa mått eller dimensioner har ytterligare konfiguration. [!UICONTROL Spam Complaint (AJO)] har till exempel [!UICONTROL Format]- och [!UICONTROL Include Exclude Values]-inställningar.
   - Alla automatiskt tillagda mått och mått har en sammanhangsetikett med namnet `:`*`name_of_metric_or_dimension`*. Måttet [!UICONTROL Landing Page Clicks (AJO)] har till exempel sammanhangsetiketten `:Landing page clicks (AJO)`.

- På fliken **[!UICONTROL Settings]** används inga specifika konfigurationsvärden

>[!IMPORTANT]
>
>Om du ändrar något av de automatiskt konfigurerade värdena för anslutningen och datavyn påverkas Journey Optimizer-rapporteringen som är beroende av och använder den automatiskt konfigurerade Customer Journey Analytics-integreringen.


## Konfigurera en datavy som ska användas med Journey Optimizer manuellt

I följande avsnitt beskrivs hur du manuellt kan använda data som genererats av Journey Optimizer för att utföra avancerade analyser i Customer Journey Analytics. Den här manuella konfigurationen är bara nödvändig om det [automatiska konfigurationsalternativet](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) inte räcker till för dina behov.

### Skicka data från Journey Optimizer till Experience Platform

Adobe Experience Platform är den centrala datakällan och länken mellan Journey Optimizer och Customer Journey Analytics. I [Kom igång med datauppsättningar](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) i användarhandboken för Journey Optimizer finns anvisningar om hur du skickar Journey Optimizer-data till Experience Platform som en datauppsättning.

### Skapa en anslutning

När Journey Optimizer-data finns i Adobe Experience Platform kan du [skapa en anslutning](/help/connections/create-connection.md) baserat på dina Journey Optimizer-datauppsättningar. Du kan också lägga till Journey Optimizer-datauppsättningar i en befintlig anslutning.

Välj och konfigurera följande datauppsättningar:

| Datauppsättning | Datauppsättningstyp | Anslutningsinställningar | Beskrivning |
| --- | --- | --- | --- |
| AJO Message Feedback Event Dataset | Händelse | Person-ID: `IdentityMap` | Innehåller meddelandeleveranshändelser, till exempel [!UICONTROL Sends] och [!UICONTROL Bounces]. |
| AJO Experience Event-datauppsättning för e-postspårning | Händelse | Person-ID: `IdentityMap` | Innehåller e-postspårningshändelser som [!UICONTROL Opens], [!UICONTROL Clicks] och [!UICONTROL Unsubscribes]. |
| AJO Push Tracking Experience, händelsedatauppsättning | Händelse | Person-ID: `IdentityMap` | Innehåller push-spårningshändelser som [!UICONTROL App Launches]. |
| Resestegshändelser | Händelse | Person-ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Innehåller händelser som visar vilka profiler som deltog i varje nod av resan. |
| AJO Entity Dataset | Sök | Nyckel: `_id`<br>Matchande nyckel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Innehåller klassificeringar som kopplar metadata för resa och kampanj till alla händelsedata för Journey Optimizer. |

{style="table-layout:auto"}


### Konfigurera datavyn

När en anslutning har skapats kan du skapa en eller flera [datavyer](/help/data-views/create-dataview.md) för att konfigurera önskade mått och mätvärden som är tillgängliga i Customer Journey Analytics.

>[!NOTE]
>
>Datamatchningar mellan Journey Optimizer och Customer Journey Analytics är vanligtvis mindre än 1-2 %. Större avvikelser är möjliga för data som samlats in under de senaste två timmarna. Använd datumintervall, exklusive idag, för att minska avvikelser som inbegriper bearbetningstid.


#### Konfigurera dimensioner

Du kan skapa följande mått i en datavy för att få en ungefärlig paritet med liknande dimensioner i Journey Optimizer. Mer information om alternativ för dimensionsanpassning finns i [Komponentinställningar](/help/data-views/component-settings/overview.md) i Datavy Manager.

| Dimension | Beskrivning | Datauppsättning(ar) | Schemaelement | Komponentinställningar |
| --- | --- | --- | --- | --- |
| Körningsfel för åtgärd (AJO) | Feltillstånd som förhindrade att körtidsmiljön för resan kunde köra åtgärden. | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | Komponenttyp: Dimension |
| Åtgärdsetikett (AJO) | Kundens genererade visningsnamn för elementet som slutanvändaren interagerade med. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.`<br/>`propositionAction.label` | Komponenttyp: Dimension |
| Batch-ID (AJO) | GUID som skapas vid anrop av varje ny batchinstans för en schemalagd resa eller kampanjåtgärd. Om t.ex. en schemalagd resa eller en Campaign-åtgärd körs på 08.00 och 01.00 finns det två olika batchInstanceID:n. | AJO Push Tracking Experience Event datauppsättning, AJO Message Feedback Event datauppsättning, AJO Email Tracking Experience Event datauppsättning | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | Komponenttyp: Dimension |
| Tidsstämpel för batchinstans (AJO) | Tidsstämpeln för batchinstansen. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | Härledda fält | Komponenttyp: Dimension (härlett fält) |
| Kampanj-ID (AJO) | Kampanjens ID. | AJO Entity Dataset | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | Komponenttyp: Dimension |
| Kampanjnamn (AJO) | Namnet på kampanjen. | AJO Entity Dataset | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | Komponenttyp: Dimension |
| Kampanjversion-ID (AJO) | Kampanjens version-ID. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | Komponenttyp: Dimension |
| Kanal (AJO) | Den kanal som dessa data ska korreleras till. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | Komponenttyp: Dimension |
| Korrelations-ID (AJO) | Korrelations-ID. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | Komponenttyp: Dimension |
| ID för beslutspolicy (AJO) | ID för beslutspolicyn som används vid beslut om vilka poster som ska tas med i förslaget. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | Härledda fält | Komponenttyp: Dimension (härlett fält) |
| E-postmottagardomän (AJO) | Domän för e-postadress | AJO Push Tracking Experience Event datauppsättning, AJO Message Feedback Event datauppsättning, AJO Email Tracking Experience Event datauppsättning | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | Komponenttyp: Dimension |
| Ämne för e-post (AJO) | Ämne, icke-personaliserat | AJO Entity Dataset | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | Komponenttyp: Dimension |
| Händelse-ID (AJO) | En unik identifierare för tidsseriehändelsen. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_id` | Komponenttyp: Dimension (härlett fält) |
| ID för avslutningsvillkor (AJO) | ID för de utträdeskriterier som används för att avgöra om resan ska avslutas. | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | Komponenttyp: Dimension |
| Namn på avslutsvillkor (AJO) | Namn på avslutningskriterier. | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | Komponenttyp: Dimension |
| Experiment-ID (AJO) | ID:t för experimentet. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Komponenttyp: Dimension |
| Experimentnamn (AJO) | Namnet på experimentet. | AJO Entity Dataset | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | Komponenttyp: Dimension Context Labels: Experimentation Experiment |
| Hämtningsfel (AJO) | Feltillstånd som förhindrade att hämtningen kördes av körningsmiljön. | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | Komponenttyp: Dimension |
| Är optimerad för sändning (AJO) | Är meddelandekörning SendTimeOptimized? | AJO Push Tracking Experience Event datauppsättning, AJO Message Feedback Event datauppsättning, AJO Email Tracking Experience Event datauppsättning | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | Komponenttyp: Dimension |
| Är testresa (AJO) | Är händelsen en del av körningen av en testresa | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | Komponenttyp: Dimension |
| Är testmeddelande (AJO) | Är meddelandet skickat som testkörning | AJO Push Tracking Experience Event datauppsättning, AJO Message Feedback Event datauppsättning, AJO Email Tracking Experience Event datauppsättning | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | Komponenttyp: Dimension |
| Objekt-ID (AJO) | Objektets ID. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.`<br/>`propositions.items.id` | Komponenttyp: Dimension |
| Objektnamn (AJO) | Namnet på objektet | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.`<br/>`propositions.items.name` | Komponenttyp: Dimension |
| Reseåtgärds-ID | Åtgärds-ID för resan som MessageExecution aktiveras för. | AJO Push Tracking Experience Event datauppsättning, AJO Message Feedback Event datauppsättning, AJO Email Tracking Experience Event datauppsättning | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | Komponenttyp: Dimension |
| Nodnamn för reseåtgärd (AJO) | Åtgärdsnodens namn för resan. | AJO Push Tracking Experience Event dataset, Journey Step Events, AJO Message Feedback Event Dataset, AJO Email Tracking Experience Event Dataset, AJO Entity Dataset | Härledda fält | Komponenttyp: Dimension (härlett fält) |
| Namn på nod för resehändelse (AJO) | Det här värdet anges när ett segment eller en extern händelse inträffar under en resa. | AJO Push Tracking Experience Event dataset, Journey Step Events, AJO Message Feedback Event Dataset, AJO Email Tracking Experience Event Dataset, AJO Entity Dataset | Härledda fält | Komponenttyp: Dimension (härlett fält) |
| Resurs-ID (AJO) | ID för resan. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | Komponenttyp: Dimension |
| Resensnamn (AJO) | Namnet på resan. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | Komponenttyp: Dimension |
| Resensnamn och version (AJO) | Namnet på och versionen av resan. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | Komponenttyp: Dimension |
| Reseversions-ID (AJO) | Resans version-ID. | AJO Entity Dataset | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | Komponenttyp: Dimension |
| ID för landningssida (AJO) | Unik identifierare för landningssida. | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | Komponenttyp: Dimension |
| Landningssida Source (AJO) | Startsidans källa. | AJO Experience Event-datauppsättning för e-postspårning | Härledda fält | Komponenttyp: Dimension (härlett fält) |
| Länk-URL (AJO) | Den URL som användaren klickade på. | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | Komponenttyp: Dimension |
| Orsak till uteslutning av meddelande (AJO) | Uteslutningsorsak | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageExclusion.reason` | Komponenttyp: Dimension |
| Meddelandefelkategori (AJO) | Felkategori | AJO Message Feedback Event Dataset | ` _experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageFailure.category` | Komponenttyp: Dimension |
| Orsak till meddelandefel (AJO) | Felorsak | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageFailure.reason` | Komponenttyp: Dimension |
| Meddelandefelstyp (AJO) | Feltyp | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageFailure.type` | Komponenttyp: Dimension |
| Status för meddelandefel (AJO) | Felstatus | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageFailure.status` | Komponenttyp: Dimension |
| Meddelande-ID (AJO) | Det meddelande-ID som dessa data ska korreleras till. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.messageID` | Komponenttyp: Dimension |
| Försök igen (AJO) | Antal nya försök | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.retryCount` | Komponenttyp: Dimension |
| Nod-ID (AJO) | Nod-ID för kundnoden. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNodeID` | Komponenttyp: Dimension |
| Nodnamn (AJO) | Nodnamnet för kundnoden. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNodeName` | Komponenttyp: Dimension |
| Nodtyp (AJO) | Nodtypen för kundnoden. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNodeID` | Komponenttyp: Dimension |
| OS (AJO) | Operativsystemets namn. | AJO Push Tracking Experience, händelsedatauppsättning | `environment.operatingSystem` | Komponenttyp: Dimension |
| OS-version (AJO) | Operativsystemets version. | AJO Push Tracking Experience, händelsedatauppsättning | environment.operatingSystemVersion | Komponenttyp: Dimension |
| Push Platform (AJO) | Push-tjänster, t.ex. apns eller fcm. | AJO händelsedatauppsättning för e-postspårning, händelsedatauppsättning för AJO-meddelanden, AJO händelsedatauppsättning för push-spårning | `_experience.customerJourneyManagement.`<br/>`pushChannelContext.platform` | Komponenttyp: Dimension |
| Push Title (AJO) | Push Title, ej personaliserad. | AJO Entity DataSet, AJO Message Feedback Event Dataset, AJO Push Tracking Experience Event Dataset | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.push.title | Component type: Dimension` |
| Avvisad godkännandeprincip (AJO) | Namn på motsvarande princip för avvisat samtycke. | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.consent.rejectedPolicies.name` | Komponenttyp: Dimension |
| SMS inkommande meddelande (AJO) | SMS inkommande svar, t.ex. stopp, start, prenumeration osv. | AJO händelsedatauppsättning för e-postspårning, händelsedatauppsättning för AJO-meddelanden, AJO händelsedatauppsättning för push-spårning | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | Komponenttyp: Dimension |
| SMS-meddelandetyp (AJO) | SMS-provider, t.ex. inkommande, inkommande svar eller skicka. | AJO händelsedatauppsättning för e-postspårning, händelsedatauppsättning för AJO-meddelanden, AJO händelsedatauppsättning för push-spårning | ` _experience.customerJourneyManagement.`<br/>`smsChannelContext.messageType` | Komponenttyp: Dimension |
| SMS-provider (AJO) | SMS-leverantör, t.ex. sinch eller twilio. | AJO händelsedatauppsättning för e-postspårning, händelsedatauppsättning för AJO-meddelanden, AJO händelsedatauppsättning för push-spårning | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.messageType` | Komponenttyp: Dimension |
| Markeringstyp (AJO) | Kanalytan som meddelandet visades på. | Resestegshändelser, AJO händelsedatauppsättning för e-postspårning, händelsedatauppsättning för AJO-meddelandefeedback, händelsedatauppsättning för AJO Push Tracking Experience | `_experience.decisioning.propositions.`<br/>`items.itemSelection.`<br/>`selectionDetail.selectionType` | Komponenttyp: Dimension |
| Prenumerationslista-ID (AJO) | Unik identifierare för prenumerationslista. | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.subscription.`<br/>` subscriptionListID` | Komponenttyp: Dimension |
| Yta (AJO) |  | Resestegshändelser, AJO händelsedatauppsättning för e-postspårning, händelsedatauppsättning för AJO-meddelandefeedback, händelsedatauppsättning för AJO Push Tracking Experience | `_experience.decisioning.`<br/>`propositions.scope` | Komponenttyp: Dimension |
| Bearbetnings-ID (AJO) | ID för vald behandling för experimentet. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.experiment.treatmentID` | Komponenttyp: Dimension |
| Behandlingsnamn (AJO) | Namnet på den valda behandlingen för experimentet. | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.experiment.treatmentName` | Komponenttyp: Dimension |
| URL-ID (AJO) | Unik identifierare för den URL som användaren klickade på. | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | Komponenttyp: Dimension |
| URL-etikett (AJO) | Etikett för personlig URL. | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.label` | Komponenttyp: Dimension |

{style="table-layout:auto"}

#### Konfigurera mått

Du kan skapa följande mätvärden i en datavy för att få en ungefärlig paritet med liknande mätvärden i Journey Optimizer. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Datavy Manager för mer information om alternativ för måttanpassning.

| Mått | Beskrivning | Datauppsättning(ar) | Schemaelement | Komponentinställningar |
| --- | --- | --- | --- | --- |
| Appinstallationer (AJO) | Antal programinstallationer | AJO Push Tracking Experience, händelsedatauppsättning | `application.installs.value` | Komponenttyp: Mått |
| Applanseringar (AJO) | Antal gånger mobilappen startas | AJO Push Tracking Experience, händelsedatauppsättning | `application.launches.value` | Komponenttyp: Mått |
| studsar för utgående kanaler (AJO) | Totalt antal meddelanden som studsat över utgående kanaler | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått |
| Klicka (AJO) | Totalt antal klick i alla kanaler | AJO Push Tracking Experience, händelsedatauppsättning, händelser för kundresa, händelseuppsättning för AJO e-postspårning, händelsedatauppsättning för AJO Message Feedback, händelsedatauppsättning för | Härledda fält | Komponenttyp: Mått (härlett fält) |
| Antal reserverbjudanden (AJO) | Antal reserverbjudanden. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | Komponenttyp: Mått |
| Antal erbjudanden (AJO) | Antal erbjudanden. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | ` _experience.decisioning.`<br/>`propositions.items.id` | Komponenttyp: Mått |
| Dedupliceringsmått (AJO) | Dedupliceringsmått | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_id` | Komponenttyp: Mått |
| Levererat (AJO) | Totalt antal meddelanden som levererats. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | Härledda fält | Komponenttyp: Mått (härlett fält) |
| Avvisad (AJO) | Räknas varje gång inApp-meddelandet stängs av Adobe SDK, oavsett vilken åtgärd slutanvändaren väljer att stänga det. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Komponenttyp: Mått |
| Skärmar (AJO) | Det här antalet visar AJO-meddelanden. Detta inkluderar e-postöppningar, webbvisningar och visning i appen. Mobilplattformar rapporterar inte SMS och push-meddelanden, och därför räknas de inte. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för kundresa, händelseuppsättning för AJO e-postspårning, händelsedatauppsättning för AJO Message Feedback, händelsedatauppsättning för | Härledda fält | Komponenttyp: Mått (härlett fält) |
| E-post öppnas (AJO) | Totalt antal e-postöppningar | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponenttyp: Mått |
| Inkommande klick (AJO) | Totalt antal klick i inkommande kanaler | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.`<br/>`propositionEventType.interact` | Komponenttyp: Mått |
| Inkommande avstängningar (AJO) | Totalt antal stängningar över inkommande kanaler | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Komponenttyp: Mått |
| Inkommande Impressions (AJO) | Totalt antal visningar över inkommande kanaler | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.`<br/>`propositionEventType.display` | Komponenttyp: Mått |
| Reseslut (AJO) | True om det aktuella steget ledde till att en instans av resan avslutades. Det sista steget i en resa för en viss profil har körts. | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Komponenttyp: Mått |
| Resebyråer (AJO) | True if the step event was a travel entrance event for a profile. | Resestegshändelser | Härledda fält | Komponenttyp: Mått (härlett fält) |
| Reseutträde (AJO) | True om det aktuella steget ledde till att en instans av resan avslutades. Detta är det sista steget i en resa för en viss profil som utfördes utan fel. | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Komponenttyp: Mått |
| Resefel (AJO) | Ger det aktuella läget för steget som har slutförts. Möjliga värden: `Transitions` (Nästa steg inträffar vid en händelseövergång), `EndStep` (Det sista steget i den här reseinstansen har körts), `Error` (Det här steget påträffade ett feltillstånd och avslutar den aktuella reseinstansen), `TimedOut` (Det aktuella steget har avslutats på grund av en timeout för en hämtning eller en åtgärd). | Resestegshändelser | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | Komponenttyp: Mått |
| Landing Page Click (AJO) | Totalt antal klick på landningssidan. | AJO Experience Event-datauppsättning för e-postspårning | Härledda fält | Komponenttyp: Mått (härlett fält) |
| Konverteringar av landningssidor (AJO) | Totalt antal konverteringar på landningssidan. | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponenttyp: Mått |
| Landing Page Views (AJO) | Totalt antal visningar på landningssidan. | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponenttyp: Mått |
| Node Enters (AJO) | True if the step event was a node entrance event for a profile. | Resestegshändelser | Härledda fält | Komponenttyp: Mått (härlett fält) |
| Utgående klick (AJO) | Totalt antal klick i utgående kanaler | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponenttyp: Mått |
| Utgående fel (AJO) | Totalt antal meddelanden med fel i utgående kanaler | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått |
| Utgående undantag (AJO) | Totalt antal uteslutningshändelser över utgående kanaler | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått |
| Utgående sändningar (AJO) | Totalt antal meddelanden som skickas via utgående kanaler | AJO Message Feedback Event Dataset | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Komponenttyp: Mått |
| Push Custom Actions (AJO) | Totalt antal anpassade åtgärder i push-interaktion. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `eventType` | Komponenttyp: Mått |
| Push-interaktioner (AJO) | Antal gånger mobilappen startas på grund av en direkt push-meddelandeinteraktion | AJO Push Tracking Experience, händelsedatauppsättning | `application.launches.value` | Komponenttyp: Mått |
| Skickar (AJO) | Totalt antal meddelanden som skickas över alla kanaler | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | Härledda fält | Komponenttyp: Mått (härlett fält) |
| SMS inkommande meddelanden (AJO) | SMS inkommande svar. Exempel: stoppa, starta, prenumerera osv. | AJO Push Tracking Experience Event datauppsättning, AJO Message Feedback Event datauppsättning, AJO Email Tracking Experience Event datauppsättning | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | Komponenttyp: Mått |
| Spam Complaint (AJO) | Totalt antal skräppostklagomål | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponenttyp: Mått |
| Prenumerationslista - tillägg (AJO) | Totalt antal tillägg i prenumerationslistan. | AJO Experience Event-datauppsättning för e-postspårning | Härledda fält | Komponenttyp: Mått (härlett fält) |
| Prenumerationslista tas bort (AJO) | Totalt antal borttagningar från prenumerationslistan. | AJO Experience Event-datauppsättning för e-postspårning | Härledda fält | Komponenttyp: Mått (härlett fält) |
| Målinriktad (AJO) | Detta antal gånger ett förslag har riktats till en person. Detta är det antal gånger ett förslag övervägdes för visning till en person. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | Härledda fält | Komponenttyp: Mått (härlett fält) |
| Utlöst (AJO) | Propositionen valdes för visning av Adobe SDK. Andra faktorer kan förhindra att den faktiskt visas. | AJO Push Tracking Experience, händelsedatauppsättning, händelser för resesteg, händelseuppsättning för AJO Message Feedback, händelsedatauppsättning för AJO Email Tracking Experience | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Komponenttyp: Mått |
| Unika besökare i expertvyn (AJO) | De unika besökarna i experimentet | AJO Entity Dataset | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Komponenttyp: Mått |
| Avbeställ (AJO) | Totalt antal avbeställningar | AJO Experience Event-datauppsättning för e-postspårning | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponenttyp: Mått |

{style="table-layout:auto"}
