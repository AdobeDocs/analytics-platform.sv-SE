---
description: Du kan visa avvikelser i en tabell eller i ett linjediagram.
title: Visa avvikelser i Analysis Workspace
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 4%

---

# Visa avvikelser i Analysis Workspace

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Funktionsuppsättningen skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan visa avvikelser i en tabell eller i ett linjediagram.

## Visa avvikelser i en tabell {#section_869A87B92B574A38B017A980ED8A29C5}

I en friformstabell i en tidsserie flaggas nu varje rad automatiskt med ett mörkgrått utropstecken om en dataavvikelse har upptäckts.

![](assets/anomaly_detected.png)

Den lodräta grå linjen i varje rad anger det förväntade värdet. När du håller pekaren över utropstecknet anges i vilken utsträckning avvikelsen avviker från det förväntade värdet (i + eller - %).

## Visa avvikelser i ett linjediagram {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

Linjediagrammet visar det ljusgröna konfidensbandet med avvikande värden (vita punkter).

Om du klickar på en vit punkt blir den grön och den visar dig:

* Datumet då avvikelsen inträffade
* avvikelsens råvärde
* Procentvärdet över eller under det förväntade värdet, som representeras av den helgröna linjen.

<!--* The Analyze link to start [Contribution Analysis](/help/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md).-->

![](assets/anomaly_linechart.png)

Om du har flera mätvärden i linjediagrammet visar vi bara avvikelserna och du måste hovra över varje avvikelse för att se konfidensintervallet för det måttet.

Konfidensintervallet för avvikelseidentifiering skalar inte automatiskt y-axeln i en visualisering för att göra diagrammet mer läsbart.

Du kan välja att tillåta konfidensintervallet för att skala diagrammet. Klicka bara på inställningsikonen (kugghjulsikonen) och markera **[!UICONTROL Allow Anomaly Detection to Scale Y Axis]**.

![](assets/scale-y-axis.png)
