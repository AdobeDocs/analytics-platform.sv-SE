---
title: Integrera Adobe Journey Optimizer Beslutshantering med Adobe Customer Journey Analytics
description: Hämta in data som genererats av Adobe Journey Optimizer Decision Management och analysera dem med Analysis Workspace i Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 0%

---

# Integrera beslutshantering med Adobe Customer Journey Analytics


Adobe Journey Optimizer [Beslutshantering](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) förenklar personaliseringen med ett centralt bibliotek med marknadsföringserbjudanden och en beslutsmotor som tillämpar regler och begränsningar på komplexa realtidsprofiler som skapats av Adobe Experience Platform för att hjälpa er att skicka rätt erbjudande till era kunder vid rätt tidpunkt.

Beslutshantering är en del av och integrerad med Adobe Journey Optimizer. Det kan också användas oberoende av resor och kampanjer som definieras i Adobe Journey Optimizer, med hjälp av de omfattande [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) support.

Du kan importera data som har genererats av Beslutshantering för att utföra avancerad analys i Customer Journey Analytics genom att utföra följande steg:

## Skicka data från beslutshantering till Adobe Experience Platform

Adobe Experience Platform fungerar som den centrala datakällan och länken mellan beslutsfattandet och Customer Journey Analytics. Data från beslutshanteringen samlas in i Experience Platform **automatiskt** eller som en del av **explicit skickade upplevelsehändelser** (till exempel visningar eller klickningar). Se [Komma igång med datainsamling](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) för mer information.

## Skapa en anslutning

När data för beslutshantering finns i Adobe Experience Platform kan du skapa en [Anslutning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en) baserat på data från din beslutshantering. Du kan också lägga till data för beslutshantering i en befintlig anslutning.

Välj och konfigurera följande datauppsättningar:

| Datauppsättning | Datauppsättningstyp | Anslutningsinställningar | Beskrivning |
| --- | --- | --- | --- |
| ODE DecisonEvents - _sandlåda_ beslut | Händelse | Person-ID: `IdentityMap` | Innehåller automatiskt genererade data för beslutshändelsehantering. _Sandbox_ refererar till namnet på den specifika sandlådan. |
| Adobe Journey Optimizer Message Feedback Event Dataset | Händelse | Person-ID: `IdentityMap` | Innehåller meddelandeleveranshändelser. |
| Adobe Journey Optimizer Experience Event-datauppsättning för e-postspårning | Händelse | Person-ID: `IdentityMap` | Innehåller e-postspårningshändelser. |
| Adobe Journey Optimizer Push Tracking Experience, händelsedatauppsättning | Händelse | Person-ID: `IdentityMap` | Innehåller push-spårningshändelser. |
| Adobe Journey Optimizer Entity Dataset | Sök | Nyckel: `_id`<br>Matchningsnyckel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Innehåller klassificeringar som kopplar metadata för resa och kampanj till alla händelsedata för Adobe Journey Optimizer. |

{style="table-layout:auto"}

## Skapa en datavy

När en anslutning har skapats kan du skapa en eller flera [Datavyer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en) för att konfigurera önskade mått och mätvärden som är tillgängliga i Customer Journey Analytics.

>[!NOTE]
>
>Datamatchningar mellan Adobe Journey Optimizer och Customer Journey Analytics är vanligtvis mindre än 1-2 %. Större avvikelser är möjliga för data som samlats in under de senaste två timmarna. Använd datumintervall, exklusive idag, för att minska avvikelser som inbegriper bearbetningstid.

### Konfigurera dimensioner

Du kan skapa följande dimensioner i en datavy för att uppnå en ungefärlig paritet med liknande dimensioner i Beslutshantering. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Data View Manager för mer information om dimensionsanpassningsalternativ.

| Dimension | Schemaelement | Komponentinställningar |
| --- | --- | --- |
| Aktivitetsnamn | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Komponenttyp: Dimension |
| Behållaridentifierare | `_experience.decisioning.containerID` | Komponenttyp: Dimension |
| Korrelations-ID | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Komponenttyp: Dimension |
| Namn på beslutsalternativ | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Komponenttyp: Dimension |
| Alternativ för reservbeslut | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Komponenttyp: Dimension |
| Placeringsnamn | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Komponenttyp: Dimension |

{style="table-layout:auto"}


### Konfigurera mått

Du kan skapa följande mått i en datavy för att få en ungefärlig paritet med liknande mått i Beslutshantering. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Data View Manager för mer information om alternativ för anpassning av mätvärden.

| Mått | Beskrivning | Schemaelement | Komponentinställningar |
| --- | --- | --- | --- |
| Händelsetyp (byta namn för att referera till en viss händelse, till exempel `Feedback` for `message.feedback`) [1] | Mängd för en viss typ av händelse | `eventType` | Komponenttyp: Mått <br/>**[!UICONTROL Set Include Exclude Values]**: På<br/>**[!UICONTROL Match]**: [!UICONTROL If all criteria are met]<br/>**[!UICONTROL Criteria]**:**[!UICONTROL Equals]**`message.feedback` |
| Poäng för beslutsalternativ | Beräknat värde för ett beslutsalternativ i samband med ett enda omfång. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Komponenttyp: Mått |
| Poäng för reservbeslut | Beräknat värde för ett alternativ för reservalternativ i ett enda omfång. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Komponenttyp: Mått |
| Avvisa erbjudanden | Antalet erbjudanden som avvisats eller avvisats utan någon annan direkt interaktion. | `_experience.decisioning.`<br/>`propositionEventType.display` | Komponenttyp: Mått |
| Visa erbjudanden | Antalet erbjudanden som visas för profilen. | `_experience.decisioning.`<br/>`propositionEventType.display` | Komponenttyp: Mått |
| Erbjudandeinteraktion | Antalet erbjudanden som visas för profilen. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Komponenttyp: Mått |
| Skicka erbjudanden | Antalet erbjudanden som skickas till profilen. | `_experience.decisioning.`<br/>`propositionEventType.send` | Komponenttyp: Mått |
| Erbjudandeutlösare | Antalet erbjudanden som ska visas av klient-SDK. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Komponenttyp: Mått |
| Avbeställ | Antalet erbjudanden som efterfrågats av profilen som inte ska visas i framtiden. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Komponenttyp: Mått |

{style="table-layout:auto"}

[1] Du kan definiera flera mått för de olika händelsetyperna som är tillgängliga. Se [Inkludera inställningar för komponenten Uteslut värden](/help/data-views/component-settings/include-exclude-values.md) för mer information.
