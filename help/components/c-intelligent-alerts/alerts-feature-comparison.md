---
description: Läs om hur varningar skiljer sig i Customer Journey Analytics från Adobe Analytics
title: Jämförelse av aviseringsfunktioner i Customer Journey Analytics och Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 9e07dfc84bc06aef987d99c225cefb4e0406f552
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Jämförelse av aviseringsfunktioner

Processen att använda varningar i Customer Journey Analytics är nästan identisk med att använda varningar i Adobe Analytics. Det finns dock viktiga skillnader. I följande avsnitt beskrivs de viktigaste skillnaderna.

## Varningar per timme är inte tillgängliga

Timaviseringar är **inte** tillgängliga i Customer Journey Analytics medan timaviseringar är tillgängliga i Adobe Analytics. I Customer Journey Analytics kan varningar konfigureras för varje dag, vecka eller månad.

Du kan importera data till Adobe Experience Platform på olika sätt. Detta innebär att det inte går att på ett tillförlitligt sätt uppnå fullständighet och tillgänglighet inom en timmes begränsningar.  Flexibiliteten i datainhämtning innebär att varningar per timme är opraktiskt på grund av den stora potentialen för ofullständiga data. Mer information finns i [Tidsåtgången för dataöverföring varierar](#data-ingestion-times-vary-in-customer-journey-analytics).

## Tidsåtgången för datainmatning varierar

Den tid som krävs innan data är fullständiga och tillgängliga att rapporteras i Customer Journey Analytics varierar beroende på organisation.

Detta beror på följande:

* Plattformens möjlighet att lagra alla typer av datamodeller och typer

  Till skillnad från Adobe Analytics (som bara rapporterar om webbdata) kan [många olika typer av data importeras till Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) för att rapporteras i Customer Journey Analytics, och inte alla typer av data kan skickas sekventiellt och i realtid.

* En fördröjning i leveransen av batchdata till plattformsdatauppsättningar

  Vissa data kan vara tillgängliga för rapportering tidigare, men alla [batchdata hämtas till en plattformsdatamängd](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), vanligtvis från 3 till 9 timmar efter datahändelsetiden. För att varningarna ska vara korrekta måste datainmatningen vara fullständig, med alla batchdata tillgängliga i datauppsättningen. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Av dessa anledningar är datainmatningen för de olika typer av händelsedata som kan importeras endast slutförd efter en viss fördröjning, vanligtvis från 3 till 9 timmar efter datahändelsetiden. För att varningarna ska vara korrekta måste händelsedata för ett givet händelseintervall vara fullständiga, vilket innebär att Adobe inte längre tar emot några händelsedata för det angivna händelseintervallet.

Om du vill ta hänsyn till den här fördröjningen av inmatningstiden har aviseringar en standardfördröjning på 9 timmar innan de skickas.

Du kan justera standardfördröjningen på 9 timmar till valfri plats mellan 0 och 24 timmar. Om du minskar fördröjningen till under 9 timmar kan det dock innebära att du rapporterar ofullständiga data, vilket leder till felaktig varningsinformation.

Mer information om hur du justerar fördröjningen och vilka faktorer du bör ta hänsyn till när du gör det finns i [Skapa aviseringar](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Skapa en avisering

I Analysis Workspace i Adobe Analytics kan du [skapa aviseringar från Analysis Workspace på flera sätt](https://experienceleague.adobe.com/en/docs/analytics/components/alerts/alert-builder). I Customer Journey Analytics kan du bara [skapa en avisering](alert-builder.md) i Analysis Workspace från en markering i en frihandstabell.

Både Adobe Analytics och Customer Journey Analytics har stöd för att skapa aviseringar med [Varningshanteraren](alert-manager.md)
