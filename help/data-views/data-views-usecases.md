---
title: Använd exempel för datavyer i Customer Journey Analytics
description: Flera användningsfall som visar flexibiliteten och kraften i datavyer i Customer Journey Analytics
translation-type: tm+mt
source-git-commit: f8dfc10b926031838d084acf3dadd9ce3f83541e
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---


# Datavyer använder exempel

De här användningsexemplen visar flexibiliteten och kraften i datavyer i Customer Journey Analytics.

## Skapa ett ordermått från ett pageTitle-schemafält (sträng)

När du skapar en datavy kan du till exempel skapa ett [!UICONTROL Orders]-mått från ett [!UICONTROL pageTitle]-schemafält som är en sträng. Så här gör du:

1. På fliken Komponenter drar du [!UICONTROL pageTitle] till avsnittet [!UICONTROL Metrics] under [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Markera nu måttet som du just drog in och ge det ett nytt namn under [!UICONTROL Component Settings] till höger:
   ![](assets/orders.png)
1. Öppna dialogrutan [!UICONTROL Include/Exclude Values] till höger och ange följande:
   ![](assets/orders2.png)

   &quot;Bekräftelsefrasen&quot; anger att detta är en order. När du har granskat alla sidrubriker där dessa kriterier uppfylls räknas &quot;1&quot; för varje förekomst. Resultatet är ett nytt mått (inte ett beräknat mått). Det fungerar med Attribution IQ, filter och var du än är kan du använda standardvärden.
1. Du kan ange en attribueringsmodell för det här måttet, till exempel [!UICONTROL Last Touch], med [!UICONTROL Lookback window] [!UICONTROL Session].
Du kan också skapa ytterligare ett [!UICONTROL Orders]-mått från samma fält och ange en annan attribueringsmodell för det, till exempel [!UICONTROL First Touch] och en annan [!UICONTROL Lookback window], till exempel [!UICONTROL 30 days].

## Använd heltal som dimensioner

Tidigare behandlades heltal automatiskt som mått i CJA. Nu kan siffror (inklusive anpassade händelser från Adobe Analytics) behandlas som dimensioner. Här är ett exempel:

1. Dra heltalet [!UICONTROL call_length_min] till avsnittet [!UICONTROL Dimensions] under [!UICONTROL Included Components]:
   ![](assets/integers.png)

1. Nu kan du lägga till [!UICONTROL Value Bucketing] för att presentera den här dimensionen på ett paketerat sätt vid rapportering. I annat fall visas varje instans av den här dimensionen som ett radobjekt i arbetsytan.
   ![](assets/bucketing.png)
