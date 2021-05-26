---
title: Använd exempel för datavyer i Customer Journey Analytics
description: Flera användningsfall som visar flexibiliteten och kraften i datavyer i Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
source-git-commit: 27e472f534590112194ce46b28a15b655c9caf2b
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# Datavyer använder exempel

De här användningsexemplen visar hur flexibla och kraftfulla datavyer är i Customer Journey Analytics.

## 1. Skapa ett ordermått från ett pageTitle-schemafält (sträng)

När du skapar en datavy kan du till exempel skapa ett [!UICONTROL Orders]-mått från ett [!UICONTROL pageTitle]-schemafält som är en sträng. Så här gör du:

1. På fliken Komponenter drar du [!UICONTROL pageTitle] till avsnittet [!UICONTROL Metrics] under [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Markera nu måttet som du just drog in och ge det ett nytt namn under [!UICONTROL Component Settings] till höger:
   ![](assets/orders.png)
1. Öppna dialogrutan [!UICONTROL Include/Exclude Values] till höger och ange följande:
   ![](assets/orders2.png)

   &quot;Bekräftelsefrasen&quot; anger att detta är en order. När du har granskat alla sidrubriker där dessa kriterier uppfylls räknas &quot;1&quot; för varje förekomst. Resultatet är ett nytt mått (inte ett beräknat mått). Ett mätvärde som har inkluderade/exkluderade värden kan användas överallt där andra mätvärden kan användas. Det fungerar med Attribution IQ, filter och var du än är kan du använda standardvärden.
1. Du kan ange en attribueringsmodell för det här måttet, till exempel [!UICONTROL Last Touch], med [!UICONTROL Lookback window] [!UICONTROL Session].
Du kan också skapa ytterligare ett [!UICONTROL Orders]-mått från samma fält och ange en annan attribueringsmodell för det, till exempel [!UICONTROL First Touch] och en annan [!UICONTROL Lookback window], till exempel [!UICONTROL 30 days].

## 2. Använd heltal som dimensioner

Tidigare behandlades heltal automatiskt som mått i CJA. Nu kan siffror (inklusive anpassade händelser från Adobe Analytics) behandlas som dimensioner. Här är ett exempel:

1. Dra heltalet [!UICONTROL call_length_min] till avsnittet [!UICONTROL Dimensions] under [!UICONTROL Included Components]:

   ![](assets/integers.png)

1. Nu kan du lägga till [!UICONTROL Value Bucketing] för att presentera den här dimensionen på ett paketerat sätt vid rapportering. (Utan att låsa visas varje instans av den här dimensionen som ett radobjekt i Workspace-rapporten.)

   ![](assets/bucketing.png)

## 3. Använd numeriska mått som&quot;mått&quot; i flödesdiagram

Du kan använda en numerisk dimension för att få in &quot;mått&quot; i din [!UICONTROL  Flow]-visualisering.

1. På fliken Datavyer [Komponenter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) drar du schemafältet [!UICONTROL Marketing Channels] till området [!UICONTROL Metrics] under [!UICONTROL Included components].
2. I Workspace-rapporter visar det här flödet [!UICONTROL Marketing Channels] som flödar in i [!UICONTROL Orders]:

![](assets/flow.png)

## 4. Gör underhändelsefiltrering

Du kan filtrera händelser så att de endast visar det du vill se. Använd till exempel funktionerna Inkludera/exkludera i datavyer om du bara vill fokusera på produkter som genererade mer än 50 dollar för försäljning. Om du har en beställning som innehåller ett produktköp på 50 dollar och ett inköp på 25 dollar tar vi bara bort 25 dollar, inte hela beställningen.

1. På fliken Datavyer [Komponenter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) drar du schemafältet [!UICONTROL Revenue] till området [!UICONTROL Metrics] under [!UICONTROL Included components].
1. Markera måtten och konfigurera följande på höger sida:
a. Välj [!UICONTROL Currency] under [!UICONTROL Format].
b. Välj USD under [!UICONTROL Currency].
c. Markera kryssrutan bredvid [!UICONTROL Set include/exclude values] under [!UICONTROL Include/Exclude Values].
d. Välj [!UICONTROL If all criteria are met] under [!UICONTROL Match].
e. Välj [!UICONTROL is greater than or equal] under [!UICONTROL Criteria].
f. Ange&quot;50&quot; som värde.

Med de här nya inställningarna kan du bara visa värdefulla intäkter och filtrera bort vad som helst under 50 dollar.

## 5. Använd inställningen [!UICONTROL No Value Options]

Företaget kan ha ägnat tid åt att utbilda dina användare så att de förväntar sig&quot;Ospecificerat&quot; i rapporter. Standardvärdet i datavyer är &quot;Inget värde&quot;. Du kan nu [ändra namn på &quot;Inget värde&quot; till &quot;Ospecificerat&quot;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-no-value-options-settings) i användargränssnittet för datavyer.

## 6. Använd funktionen [!UICONTROL Duplicate]

Att duplicera ett mätvärde och sedan ändra specifika inställningar är ett enkelt sätt att skapa flera mätvärden eller dimensioner från ett enda schemafält.

Välj bara inställningen Duplicera under måttets eller dimensionens namn längst upp till höger:

![](assets/duplicate.png)

## Skapa flera mätvärden med olika attributinställningar

Använd [!UICONTROL Duplicate]-funktionen som nämns ovan för att skapa ett antal intäktsmått med olika attribueringsinställningar som [!UICONTROL First Touch], [!UICONTROL Last Touch] och [!UICONTROL Algorithmic].

Glöm inte att byta namn på varje mätvärde för att återspegla skillnaderna, t.ex.&quot;Algoritmisk omsättning&quot;:

![](assets/algo-revenue.png)

Mer information om andra datavyinställningar finns i [Skapa datavyer](/help/data-views/create-dataview.md).
En konceptuell översikt över datavyer finns i [Översikt över datavyer](/help/data-views/data-views.md).