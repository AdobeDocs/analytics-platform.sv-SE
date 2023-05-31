---
description: Visar hur du skapar ett enkelt mått för"Sidvyer per besök".
title: Skapa ett enkelt mätvärde för sidvisningar per besök
feature: Calculated Metrics
exl-id: 46c83a1f-cb2d-4d5d-af4f-e1d2e4566743
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 3%

---

# Bygg en sidvy per besök-mätare

Visar hur du skapar ett enkelt mått för&quot;Sidvyer per besök&quot;.

En detaljerad beskrivning av UI-komponenterna finns i [Bygg mått](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

Så här skapar du ett enkelt mått för&quot;Sidvyer per besök&quot;.

1. Börja skapa ett mätvärde enligt beskrivningen i [Bygg mätvärden](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Ange måttet&quot;Sidvyer per besök&quot; eller något liknande.
1. Ge den ett användarvänligt **[!UICONTROL Description]** för att visa vad det används för.
1. Välj höger **[!UICONTROL Format]**, i det här fallet Decimal.
1. Bestäm hur många decimaler du vill att rapporten ska visa.
1. Ange metrisk polaritet. För detta mätresultat skulle en uppåtgående trend vara bra (grön) grej.
1. Lägg till en **[!UICONTROL Tag]** för att ordna mätvärden.
1. För detta mått drar du först sidvyer till arbetsytan och drar sedan besök under (vänta tills den blå linjen visas för att släppa den).
1. Välj operatorn Dela. (Divide är standardoperator.)
1. Nu kan du se en **[!UICONTROL Preview]** av mätvärdena när du bygger upp dem, längst upp till höger.
1. Välj **[!UICONTROL Save]**.

   Observera att **[!UICONTROL Summary]** formeln uppdateras varje gång du ändrar måttdefinitionen.

1. (Valfritt) Dela mätvärdena med andra användare i organisationen enligt beskrivningen i [Dela beräknade värden](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
