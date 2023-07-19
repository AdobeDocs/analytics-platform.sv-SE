---
description: Det finns två sätt att använda mätvärden i Analysis Workspace.
title: Mätvärden
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
source-git-commit: 202a726dc68853f55a24e566c656c92785e3b3f0
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 4%

---

# Mätvärden

Med hjälp av mätvärden kan du kvantifiera datapunkter i Analysis Workspace. De används oftast som kolumner i en visualisering och är knutna till dimensioner.

## Typer av mätvärden

Adobe erbjuder flera typer av mätvärden som kan användas i Analysis Workspace:

* **Standardmått**: Exempel på standardmått är Folk, Sessioner och Händelser.

* **Beräknade mått** ![Ikon för beräknat mått](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): Användardefinierade mätvärden som bygger på standardvärden, statiska tal eller algoritmiska funktioner.

* **Mallar för beräknade mätvärden**  <img src="./assets/adobe-logo.svg" width="18"> : Adobe-definierade mått som beter sig på liknande sätt som beräknade värden. Du kan använda dem som de är i Workspace-projekt eller spara en kopia för att anpassa dess logik.


![Mätvärden i användargränssnittet](assets/cja-metrics.png)

Du kan se om ett mätresultat har godkänts ![Ikonen Godkänd](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  eller inte. Om du vill ha mer information om ett mätresultat håller du pekaren över mätvärdet och väljer ![Ikonen Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


Mätvärdena är flexibla i användningen inom Analysis Workspace. Dra ett mätvärde till en tom Freeform-tabell om du vill se mätningen trender över projektets datumperiod. Du kan också dra ett mått när det finns en dimension för att se mätvärdet jämfört med varje dimensionsobjekt. Om du drar ett mätresultat över ett befintligt måtthuvud ersätts det och om du drar ett mätvärde bredvid ett huvud kan du se båda mätvärdena sida vid sida.

## Beräknade värden

Beräknade mätvärden gör att du enkelt kan se hur mätvärden relaterar till varandra med enkla operatorer eller statistiska funktioner. Det finns flera sätt att skapa beräknade mått:

Du kan välja **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**. Det här tar dig till [Bygg beräknade mätvärden](/help/components/calc-metrics/calc-metr-overview.md), där ni kan bygga anpassade mätvärden utifrån befintliga mätvärden.

För att göra det enklare att snabbt skapa beräknade mätvärden **[!UICONTROL Create metric from selection]** har lagts till på högerklicksmenyn i frihandstabeller i kolumnen. Det här alternativet visas när en eller flera rubrikkolumnceller är markerade.

![Skapa från markering](assets/create-metric-from-selection.png)

[Beräknade mått: Implementeringsfria mätvärden](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)

## Jämför mätvärden med olika attribueringsmodeller

Om du snabbt och enkelt vill jämföra en attribueringsmodell med en annan högerklickar du på ett mätresultat och väljer **[!UICONTROL Compare Attribution Models]**:

![Jämför attribuering](assets/compare-attribution.png)

Med den här genvägen kan du snabbt och enkelt jämföra en attribueringsmodell med en annan utan att dra i ett mätresultat och konfigurera det två gånger.
