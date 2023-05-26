---
description: Med verktyget Beräknade mätvärden kan vem som helst skapa ett deltagandemått.
title: Deltagandemått
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 5fbffb01c08b5f8069b2670742f7ae3836ad8357
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 0%

---

# Bygg ett delgivningsmått

Följande information förklarar hur du skapar ett mätvärde som visar vilka sidor som bidragit till (eller deltagit i) besök som innehöll en order.

Den här typen av information kan vara användbar för alla innehållsägare.

>[!NOTE]
>
>Du kan aktivera deltagandemått i Admin Tools, men bara för anpassade händelser 1-100.

1. Börja skapa ett mätvärde enligt beskrivningen i [Bygg mätvärden](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Ange måttet &quot;Deltagande&quot; eller något liknande i verktyget Beräknade mått
1. Dra success-händelsen &quot;Orders&quot; till arbetsytan Definition.
1. Ändra [attribueringsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) för händelsen till **[!UICONTROL Participation]** under **[!UICONTROL Settings]** utrustning. Välj **[!UICONTROL Visit]** uppslag. Definitionen bör se ut ungefär så här:

   ![](assets/participation.png)

1. Välj [!UICONTROL **Spara**] för att spara måtten.
1. Använd det beräknade måttet i en **[!UICONTROL Pages]** rapport.

   ![](assets/participation-pages.png)

1. (Valfritt) Dela mätvärdena med andra användare i organisationen.
