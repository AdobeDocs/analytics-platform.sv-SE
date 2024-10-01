---
description: Läs om hur varningar skiljer sig i Customer Journey Analytics från Adobe Analytics
title: Funktionsjämförelse för aviseringar Customer Journey Analytics och Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 0%

---

# Jämförelse av aviseringsfunktioner

Processen med att använda varningar i Customer Journey Analytics är nästan identisk med att använda varningar i Adobe Analytics. Det finns dock viktiga skillnader. I följande avsnitt beskrivs de viktigaste skillnaderna.

## Varningar per timme är inte tillgängliga i Customer Journey Analytics

Varningar per timme är inte tillgängliga i Customer Journey Analytics som i Adobe Analytics. I Customer Journey Analytics kan varningar konfigureras för varje dag, vecka eller månad.

Detta beror på de olika sätt som data kan importeras till Adobe Experience Platform, innan de rapporteras i Customer Journey Analytics. Det går inte att på ett tillförlitligt sätt uppnå fullständighet och tillgänglighet för data inom en timme, vilket gör att det inte går att göra timaviseringar på grund av den stora risken för ofullständiga data. Mer information finns i [Tidsåtgången för dataöverföring varierar](#data-ingestion-times-vary-in-customer-journey-analytics).

## Tidpunkterna för dataintaget varierar i Customer Journey Analytics

Den tid som krävs innan data är fullständiga och tillgängliga att rapporteras i Customer Journey Analytics varierar beroende på organisation.

Detta beror på följande:

* Plattformens möjlighet att lagra alla typer av datamodeller och typer

  Till skillnad från Adobe Analytics (som bara rapporterar om webbdata) kan [många olika typer av data importeras till Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) för att rapporteras i Customer Journey Analytics, och inte alla typer av data kan skickas sekventiellt och i realtid.

* En fördröjning i leveransen av batchdata till plattformsdatauppsättningar

  Vissa data kan vara tillgängliga för rapportering tidigare, men alla [batchdata hämtas till en plattformsdatamängd](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), vanligtvis från 3 till 9 timmar efter datahändelsetiden. För att varningarna ska vara korrekta måste datainmatningen vara fullständig, med alla batchdata tillgängliga i datauppsättningen. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Av dessa anledningar är datainmatningen för de olika typer av händelsedata som kan importeras endast slutförd efter en viss fördröjning, vanligtvis från 3 till 9 timmar efter datahändelsetiden. För att varningarna ska vara korrekta måste händelsedata för ett givet händelseintervall vara fullständiga, vilket innebär att Adobe inte längre tar emot händelsedata för det angivna händelseintervallet.

Om du vill ta hänsyn till den här fördröjningen av inmatningstiden har aviseringar en standardfördröjning på 9 timmar innan de skickas.

Du kan justera standardfördröjningen på 9 timmar till valfri plats mellan 0 och 24 timmar. Om du minskar fördröjningen till under 9 timmar kan det dock innebära att du rapporterar ofullständiga data, vilket leder till felaktig varningsinformation.

Mer information om hur du justerar fördröjningen och vilka faktorer du bör ta hänsyn till när du gör det finns i [Skapa aviseringar](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Det går inte att skapa en avisering från Analysis Workspace

I Analysis Workspace i Adobe Analytics kan du skapa varningar från Analysis Workspace på något av de sätt som beskrivs nedan. I Customer Journey Analytics är alternativen för att skapa aviseringar från Analysis Workspace ännu inte tillgängliga. I stället öppnar du varningsverktyget enligt beskrivningen i [Skapa aviseringar](/help/components/c-intelligent-alerts/alert-builder.md).

I Adobe Analytics finns följande alternativ:

* Markera ett eller flera linjeobjekt i en frihandstabell, högerklicka och välj **[!UICONTROL Create alert from selection]**.

  Varningsbyggaren fylls i automatiskt för att skapa en avisering med rätt mätvärden och filter.

* Öppna ett projekt i Analysis Workspace och välj sedan **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.

* Öppna ett projekt i Analysis Workspace och använd sedan följande kortkommando:

  `ctrl (or cmd) + shift + a`






