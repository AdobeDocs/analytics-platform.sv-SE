---
title: Integrera Adobe Journey Optimizer med Customer Journey Analytics
description: Hämta in data som genererats av AJO och analysera dem med Analysis Workspace i CJA.
source-git-commit: 28bc99a7f5ec7b280fd26a7a45dc076e67f652dc
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---


# Integrera Adobe Journey Optimizer med Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) hjälper er att leverera sammankopplade, kontextuella och personaliserade upplevelser. Det gör att era kunder får ta nästa steg i kundresan.

Du kan importera data som genererats av Journey Optimizer för att utföra avancerad analys i Customer Journey Analytics genom att utföra följande steg:

## Skicka data från Journey Optimizer till Adobe Experience Platform

Adobe Experience Platform är den centrala datakällan och länken mellan Journey Optimizer och Customer Journey Analytics. Se [Kom igång med datauppsättningar](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) i användarhandboken för Journey Optimizer om hur du skickar Journey Optimizer-data till Platform som en datauppsättning.

## Skapa en anslutning i Customer Journey Analytics

När Journey Optimizer data finns i Adobe Experience Platform kan man [Skapa en anslutning](/help/connections/create-connection.md) baserat på din Journey Optimizer-datauppsättning. Markera den datauppsättning som du skickade till plattformen.

## Konfigurera datavyn så att den passar Journey Optimizer mått och mått

När en anslutning har skapats kan du skapa en eller flera [Datavyer](/help/data-views/create-dataview.md) för att konfigurera önskade mått och mätvärden som är tillgängliga i Customer Journey Analytics.

Du kan skapa följande mätvärden i en datavy för att få en ungefärlig paritet med liknande mätvärden i Journey Optimizer. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) i Data View Manager för mer information om hur du anpassar mått och mätvärden.

| Mått | Beskrivning | Inställningar för datavy |
| --- | --- | --- |
| Studsar | Antalet meddelanden som studsade | Använda schemasträntelementet `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Om något villkor uppfylls<br>Lika med: `bounce`<br>Lika med: `denylist` |
| Fel | Antalet meddelanden som har felrapporterats | Använda schemasträntelementet `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `error` |
| Exkluderar | Antalet meddelanden som utelämnats | Använda schemasträntelementet `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `exclude` |
| Avbeställ | Antal avbrutna prenumerationer | Använda schemasträntelementet `_experience.customerJourneyManagement.messageInteraction.interactionType` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `unsubscribe` |
| Klickningar | Antal klick i meddelanden | Använda schemasträntelementet `_experience.customerJourneyManagement.messageInteraction.interactionType` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `click` |
| Öppnar | Antalet öppnade meddelanden | Använda schemasträntelementet `_experience.customerJourneyManagement.messageInteraction.interactionType` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `open` |
| Skräppost | Antal skräppostklagomål | Använda schemasträntelementet `_experience.customerJourneyManagement.messageInteraction.interactionType` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `spam_complaint` |
| Meddelanden har skickats | Antal meddelanden som skickats | Använda schemasträntelementet `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `sent` |
| Synkroniseringsfel | Det totala antalet meddelanden som inte kunde synkroniseras | Använda schemasträntelementet `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` med följande inställningar:<br>Komponenttyp: Mått<br>Inkludera exkluderingsvärden: Lika med `sync` |

## Konfigurera beräknade värden med Journey Optimizer-statistik

När du har konfigurerat önskade mått och mätvärden för Journey Optimizer datauppsättning kan du även konfigurera [Beräknade mått](/help/components/calc-metrics/calc-metr-overview.md) för ytterligare insikter om dessa data. Dessa beräknade värden baseras på ovanstående mått som skapats i Data View Manager.

| Beräknat mätvärde | Beskrivning | Formel |
| --- | --- | --- |
| Totalt antal skickade meddelanden | Det totala antalet meddelanden som skickats, slutförts eller misslyckats | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

## Skillnader i rapporteringen mellan Journey Optimizer och Customer Journey Analytics

Avvikelser mellan produkter ligger vanligtvis mellan 1 och 2 %. Större skillnader mellan produkterna kan eventuellt tillskrivas följande:

* Bearbetningstiden för inkommande data kan skilja sig något mellan produkterna, särskilt för data som samlats in under de senaste två timmarna. Använd datumintervall, exklusive idag, för att minska avvikelser som inbegriper bearbetningstid.
* Det beräknade måttet&quot;Totalt antal skickade meddelanden&quot; inkluderar inte måttet&quot;Försök igen&quot;. Data för mätvärdet &quot;Retries&quot; ingår inte i datauppsättningen, vilket kan visa lägre värden i CJA-rapportering jämfört med AJO-rapportering. Återförsöksdata konverteras dock till måtten&quot;Meddelanden har skickats&quot; eller&quot;studsar&quot;. Använd datumintervall från en vecka eller tidigare för att minska avvikelser med måttet&quot;Totalt antal skickade meddelanden&quot; mellan produkter.
