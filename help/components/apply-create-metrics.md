---
description: Det finns två sätt att använda mätvärden i Analysis Workspace.
title: Mätvärden
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: cdab5d8b674527a1c3f950284daac65d0ab01900
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Mätvärden

Med mätvärden kan du kvantifiera datapunkter i Analysis Workspace. De används oftast som kolumner i en visualisering och är knutna till dimensioner.

## Typer av mätvärden

Adobe erbjuder flera typer av mätvärden som kan användas i Analysis Workspace:

* **Standardmått**: Exempel på standardvärden är Folk, Sessioner och Händelser.

* **Beräknade mätvärden** ![Ikon för beräknade mätvärden](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): Användardefinierade mätvärden som baseras på standardmått, statiska tal eller algoritmiska funktioner.

* **Mallar för beräknade mått**  <img src="./assets/adobe-logo.svg" width="18"> : Adobe-definierade mått som beter sig på liknande sätt som beräknade värden. Du kan använda dem som de är i Workspace-projekt eller spara en kopia för att anpassa dess logik.


![Workspace-panelen markerar Metrisk i den vänstra rutan.](assets/cja-metrics.png)

Du kan se om ett mätresultat har godkänts med ikonen ![Godkänd](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) eller inte. Om du vill ha mer information om ett mätresultat för du pekaren över mätvärdet och väljer ![informationsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


Mätvärdena är flexibla i användningen inom Analysis Workspace. Dra ett mätvärde till en tom Freeform-tabell om du vill se mätningen trender över projektets datumperiod. Du kan också dra ett mått när det finns en dimension för att se mätvärdet jämfört med varje dimensionsobjekt. Om du drar ett mätresultat över ett befintligt måtthuvud ersätts det och om du drar ett mätvärde bredvid ett huvud kan du se båda mätvärdena sida vid sida.

## Använd mätvärden i Analysis Workspace

Mätvärden kan användas på olika sätt i Analysis Workspace. Mer information om hur du lägger till mått och andra typer av komponenter i Analysis Workspace finns i [Använda komponenter i Analysis Workspace](/help/components/use-components-in-workspace.md).

## Skapa beräknade mått

Beräknade mätvärden gör att du enkelt kan se hur mätvärden relaterar till varandra med enkla operatorer eller statistiska funktioner.

Det finns flera sätt att skapa beräknade mått. Den metod du väljer avgör om det beräknade måttet är tillgängligt från komponentlistan i alla projekt, eller bara i det projekt där det skapades.

### Skapa beräknade mätvärden för alla projekt

Du kan använda verktyget för beräknade mätvärden för att skapa beräknade mätvärden. När de skapas på det här sättet är beräknade värden tillgängliga i komponentlistan och kan sedan användas i projekt i hela organisationen.

Mer information om hur du får åtkomst till verktyget för beräknade värden finns i [Bygg mått](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Skapa beräknade mätvärden för ett enskilt projekt

Du kan skapa snabba beräknade mätvärden som bara är tillgängliga för det projekt där de skapades.

Så här skapar du ett beräknat mått för ett enskilt projekt:

1. Öppna det projekt i Analysis Workspace där du vill skapa det beräknade måttet.

1. Högerklicka på en eller flera rubrikkolumnceller i en frihandstabell och välj sedan **[!UICONTROL Create metric from selection]**

   ![Markering av panelen Workspace Skapa från markering](assets/create-metric-from-selection.png)

1. Om du bara vill skapa ett beräknat mått för det här projektet väljer du bland följande alternativ:

   * [!UICONTROL **Dela**]

   * [!UICONTROL **Subtrahera**]

   * [!UICONTROL **Lägg till**]

   * [!UICONTROL **Multiplicera**]

   Om du vill öppna verktyget för beräknade mått och skapa det beräknade måttet för alla projekt väljer du [!UICONTROL **Öppna i verktyget för beräknade mått**] och fortsätter sedan med [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

[Beräknade mått: Mätvärden utan implementering](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)

## Jämför mätvärden med olika attribueringsmodeller

Om du snabbt och enkelt vill jämföra en attribueringsmodell med en annan högerklickar du på ett mätresultat och väljer **[!UICONTROL Compare Attribution Models]**:

![Workspace-panelen markerar Jämför attribueringsmodeller](assets/compare-attribution.png)

Med den här genvägen kan du snabbt och enkelt jämföra en attribueringsmodell med en annan utan att dra i ett mätresultat och konfigurera det två gånger.
