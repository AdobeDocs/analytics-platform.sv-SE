---
description: Det finns två sätt att använda mätvärden i Analysis Workspace.
title: Mätvärden
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---

# Mätvärden

Med mätvärden kan du kvantifiera datapunkter i Analysis Workspace. De används oftast som kolumner i en visualisering och är knutna till dimensioner.

## Använd mätvärden i Analysis Workspace

Mätvärdena är flexibla i användningen inom Analysis Workspace. Dra ett mätvärde till en tom Freeform-tabell om du vill se mätningen trender över projektets datumperiod. Du kan också dra ett mått när det finns en dimension för att se mätvärdet jämfört med varje dimensionsobjekt. Om du drar ett mätresultat över ett befintligt måtthuvud ersätts det och om du drar ett mätvärde bredvid ett huvud kan du se båda mätvärdena sida vid sida.

Mer information om hur du lägger till mått och andra typer av komponenter i Analysis Workspace finns i [Använda komponenter i Analysis Workspace](/help/components/use-components-in-workspace.md).


## Typer av mätvärden

Adobe erbjuder flera typer av mätvärden som kan användas i Analysis Workspace:


* **Standardmått**: Exempel på standardvärden är Folk, Sessioner och Händelser.

  I motsats till Adobe Analytics kan du i Customer Journey Analytics definiera standardmått på ett flexibelt sätt inom räckvidden för en anslutning och en datavy.

   * **Personer**: Personmåttet i Customer Journey Analytics är antalet som skiljer sig från person-ID:n. Beroende på vad du väljer som person-ID när du konfigurerar datauppsättningar i din anslutning kan personmåttet betyda olika saker.
   * **Sessioner**: Sessionsmätningen i Customer Journey Analytics är den som du definierar som en del av konfigurationen av sessionsinställningarna i datavyn. Se [Sessionsinställningar](/help/data-views/session-settings.md).
   * **Händelser**: Händelsemåttet i Customer Journey Analytics består av händelser som ingår i alla händelsedatamängder som du har konfigurerat som en del av anslutningen.

* **Beräknade mått** ![Beräkna](/help/assets/icons/Calculator.svg): Användardefinierade mått som baseras på standardvärden, statiska tal eller algoritmiska funktioner.

* **Beräknade måttmallar** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : Adobe-definierade mått som fungerar på liknande sätt som beräknade mått. Du kan använda dem som de är i Workspace-projekt eller spara en kopia för att anpassa logiken. Se [Beräknade standardvärden](calc-metrics/cm-workflow/../default-calcmetrics.md).

Du kan se om ett mätresultat har godkänts med ikonen ![Godkänd](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) eller inte. Om du vill ha mer information om ett mätresultat för du pekaren över mätvärdet och väljer ![informationsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Mer information finns i [Komponentinformation](use-components-in-workspace.md#component-info).



## Beräknade mått

Med beräknade mätvärden kan ni enkelt konfigurera hur mätvärden relaterar till varandra med enkla operatorer eller statistiska funktioner. Mer information finns i [Översikt över beräknade mätvärden](/help/components/calc-metrics/calc-metr-overview.md).

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12&learn=on)

+++

-->

## Jämför mätvärden med olika attribueringsmodeller

Om du snabbt och enkelt vill jämföra en attribueringsmodell med en annan för ett mätresultat väljer du **[!UICONTROL Compare attribution models]** på snabbmenyn för ett mätresultat.

![Workspace-panelen markerar Jämför attribueringsmodeller](assets/compare-attribution.png)

Med den här genvägen kan du snabbt och enkelt jämföra attribueringsmodeller.
