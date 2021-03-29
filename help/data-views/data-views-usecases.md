---
title: Använd exempel för datavyer i Customer Journey Analytics
description: Flera användningsfall som visar flexibiliteten och kraften i datavyer i Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 7db2474bf3cd16863c597295399a262c328172dc
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---


# Datavyer använder exempel

Möjligheterna att

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

## Skapa flera dimensioner från ett schemafält

## Använd heltal som dimensioner

34:00

Inklusive bucketing