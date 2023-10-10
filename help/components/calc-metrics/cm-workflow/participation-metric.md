---
description: Med verktyget Beräknade mätvärden kan vem som helst skapa ett deltagandemått.
title: Deltagandemått
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d55df4ea2086278a243af51b698a9822a9a04e04
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# Bygg ett delgivningsmått

Följande information förklarar hur du skapar ett mätvärde som visar vilka sidor som har bidragit till (eller deltagit i) sessioner som innehöll en order.

Den här typen av information kan vara användbar för alla innehållsägare.

>[!NOTE]
>
>Mätvärden med andra attribueringsmodeller, som Deltagande, kan också skapas av administratörer som en del av en [datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). I exemplet nedan visas hur de kan skapas av alla användare som har tillgång till verktyget för beräknade mätvärden i Workspace.

1. Börja skapa ett mätvärde enligt beskrivningen i [Bygg mätvärden](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Ange måttet &quot;Deltagande&quot; eller något liknande i verktyget Beräknade mått
1. Dra success-händelsen &quot;Orders&quot; till arbetsytan Definition.
1. Ändra [attribueringsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) för händelsen till **[!UICONTROL Participation]** under **[!UICONTROL Settings]** utrustning. Välj **[!UICONTROL Session]** uppslag. Definitionen bör se ut ungefär så här:

   ![](assets/participation.png)

1. Välj [!UICONTROL **Spara**] för att spara måtten.
1. Använd det beräknade måttet i **[!UICONTROL Pages]** rapport.

   ![](assets/participation-pages.png)

1. (Valfritt) Dela mätvärdena med andra användare i organisationen enligt beskrivningen i [Dela beräknade värden](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
