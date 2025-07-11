---
description: Lär dig vilka mätvärden som är och hur du använder mätvärden på arbetsytan för analyser.
title: Mätvärden
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '861'
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

  I motsats till Adobe Analytics kan du i Customer Journey Analytics definiera standardvärden på ett flexibelt sätt inom räckvidden för en anslutning och en datavy.

   * **Personer**: Personmåttet i Customer Journey Analytics är antalet som skiljer sig från person-ID:n. Beroende på vad du väljer som person-ID när du konfigurerar datauppsättningar i din anslutning kan personmåttet betyda olika saker.
   * **Sessioner**: Sessionsmätningen i Customer Journey Analytics är den som du definierar som en del av konfigurationen av sessionsinställningarna i datavyn. Se [Sessionsinställningar](/help/data-views/session-settings.md).
   * **Händelser**: Händelsemåttet i Customer Journey Analytics består av händelser som ingår i alla händelsedatamängder som du har konfigurerat som en del av anslutningen.

  I [Standardmått](#standard-metrics) finns en fullständig lista med standardmått.

* **Beräknade mått** ![Beräkna](/help/assets/icons/Calculator.svg): Användardefinierade mått som baseras på standardvärden, statiska tal eller algoritmiska funktioner.

* **Beräknade mätmallar** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : Adobe-definierade mätvärden som beter sig på liknande sätt som beräknade mätvärden. Du kan använda dem som de är i Workspace-projekt eller spara en kopia för att anpassa logiken. Se [Beräknade standardvärden](calc-metrics/cm-workflow/../default-calcmetrics.md).

Du kan se om ett mätresultat har godkänts med ikonen ![Godkänd](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) eller inte. Om du vill ha mer information om ett mätresultat för du pekaren över mätvärdet och väljer ![informationsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Mer information finns i [Komponentinformation](use-components-in-workspace.md#component-info).


## Standardmått

En fullständig lista över standardvärden i Customer Journey Analytics:
{{standard-metrics}}


## Skapa beräknade mått

Med beräknade mätvärden kan ni enkelt konfigurera hur mätvärden relaterar till varandra med hjälp av enkla operatorer eller statistiska funktioner. Mer information finns i [Översikt över beräknade mätvärden](/help/components/calc-metrics/calc-metr-overview.md).

Det finns flera sätt att skapa beräknade mått. Den metod du väljer avgör om det beräknade måttet är tillgängligt från komponentlistan i alla projekt, eller bara i det projekt där det skapades.

### Skapa beräknade mätvärden för alla projekt

Du kan använda verktyget [calculate metric builder](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) för att [skapa beräknade mått](/help/components/calc-metrics/cm-workflow/cm-workflow.md). När de skapas på det här sättet är beräknade värden tillgängliga i komponentlistan och kan sedan användas i projekt i hela organisationen.

### Skapa beräknade mätvärden för ett enskilt projekt

Du kan snabbt skapa ett beräkningsmått som bara är tillgängligt för det projekt där det skapades.

Så här skapar du ett beräknat mått för ett enskilt projekt:

1. Öppna det projekt i Analysis Workspace där du vill skapa det beräknade måttet.

1. Högerklicka på kolumnrubriken i en kolumn i en frihandstabell.

   eller

   Markera två kolumner samtidigt som du håller ned Skift och högerklicka sedan på en av de markerade kolumnerna.

1. Välj **[!UICONTROL Create metric from selection]**

   ![Markering av panelen Workspace Skapa från markering](assets/create-metric-from-selection.png)

1. Om du vill skapa ett beräknat mått för endast det här projektet väljer du bland de tillgängliga alternativen.

   När en kolumn är markerad är följande alternativ tillgängliga:

   * [!UICONTROL **Medel**]: Skapar en ny kolumn som visar medelvärdet i uppsättningen med dimensionselement för kolumnen. Detta använder funktionen [Medel](/help/components/calc-metrics/cm-functions.md#mean).

   * [!UICONTROL **Median**]: Skapar en ny kolumn som visar medianvärdet i uppsättningen med dimensionselement för kolumnen. Detta använder funktionen [Median](/help/components/calc-metrics/cm-functions.md#median).

   * [!UICONTROL **Kolumn max**]: Skapar en ny kolumn som visar det största värdet i uppsättningen med dimensionselement för kolumnen. Detta använder funktionen [Kolumnmaximum](/help/components/calc-metrics/cm-functions.md#column-maximum).

   * [!UICONTROL **Kolumn min**]: Skapar en ny kolumn som visar det minsta värdet i uppsättningen med dimensionselement för kolumnen. Detta använder funktionen [Kolumnminimum](/help/components/calc-metrics/cm-functions.md#column-minimum).

   * [!UICONTROL **Kolumnsumma**]:Skapar en ny kolumn som lägger till alla numeriska värden för ett mått i en kolumn (över elementen i en dimension). Detta använder funktionen [Kolumnsumma](/help/components/calc-metrics/cm-functions.md#column-sum).

   När två kolumner är markerade är följande alternativ tillgängliga:

   * [!UICONTROL **Dela upp**]: Skapar en ny kolumn som delar värdena för de två markerade kolumnerna.

   * [!UICONTROL **Subtrahera**]: Skapar en ny kolumn som subtraherar värdena för de två markerade kolumnerna.

   * [!UICONTROL **Lägg till**]: Skapar en ny kolumn som lägger till värdena för de två markerade kolumnerna.

   * [!UICONTROL **Multiplicera**]: Skapar en ny kolumn som multiplicerar värdena för de två markerade kolumnerna.

   * [!UICONTROL **Procentuell ändring**]: Skapar en ny kolumn som visar procentändringen mellan de två markerade kolumnerna.


## Jämför mätvärden med olika attribueringsmodeller

Om du snabbt vill jämföra en attribueringsmodell med en annan för ett mätresultat väljer du **[!UICONTROL Compare attribution models]** på snabbmenyn för ett mätresultat.

![Workspace-panelen markerar Jämför attribueringsmodeller](assets/compare-attribution.png)

Med den här genvägen kan du jämföra en attribueringsmodell med en annan utan att dra i ett mätresultat och konfigurera det två gånger.


