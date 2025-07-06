---
description: Lär dig hur du bygger ett enkelt beräknat mätresultat.
title: Bygg ett enkelt beräknat mått
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Bygg ett enkelt beräknat mått

I följande information förklaras hur du skapar en enkel *sidvy per besök*-mätare.

1. Börja med att skapa ett mätvärde enligt beskrivningen i [Bygg mått](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Namnge måttet `Page Views per Session` eller något liknande.
1. Ge måttet ett användarvänligt **[!UICONTROL Description]** för att visa vad måttet används för.
1. Välj höger **[!UICONTROL Format]**. Välj **[!UICONTROL Decimal]** för det här exemplet.
1. Bestäm hur många decimaler du vill att rapporten ska visa.
1. Välj **[!UICONTROL Show updward trend as]** ▲ i listrutan **[!UICONTROL Good (Green)]**.
1. Lägg till en **[!UICONTROL Tag]** för att ordna dina mått.
1. För det här beräknade måttet drar du först **[!UICONTROL Page Views]** från **[!UICONTROL Metrics]**-komponenterna till **[!UICONTROL Definition]**-delen av arbetsytan.
1. Dra sedan **[!UICONTROL Sessions]** från **[!UICONTROL Metrics]**-komponenterna och släpp måttet under **[!UICONTROL Page Views]** (vänta tills den blå linjen visas innan du släpper måttet).
1. Välj divisionsoperatorn ![Dividera](/help/assets/icons/Divide.svg). (Divide är standardoperator.)
1. Du kan se en **[!UICONTROL Preview]** av måtten medan du skapar måttet.
1. **[!UICONTROL Product compatibility]** visar om det beräknade måttet är kompatibelt överallt i Customer Journey Analytics (exklusive experiment).

   ![Enkelt beräknat mått](assets/simple-calculated-metric.png)
1. Välj **[!UICONTROL Save]**.

   Observera att formeln **[!UICONTROL Summary]** uppdateras varje gång du ändrar måttdefinitionen.

1. (Valfritt) Om du vill dela, godkänna, (om-)tagga, byta namn på eller ta bort ett mätresultat går du till [hanteraren för beräknade värden](/help/components/calc-metrics/cm-workflow/cm-manager.md).

