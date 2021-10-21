---
description: Med verktyget Beräknade mätvärden kan vem som helst skapa ett deltagandemått.
title: Mätvärden för deltagande
source-git-commit: 50c56d718ae7a7f6e3d788b9f755831a7522337c
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 2%

---

# Mätvärden för deltagande

Här följer ett enkelt exempel: Du är innehållsägare och vill se vilka sidor som har bidragit till (dvs. deltagit i) besök som innehöll en order. Så här:

>[!NOTE]
>
>Tidigare var du tvungen att göra detta via Admin Tools. Du kan fortfarande aktivera deltagandemått i Admin Tools, men bara för anpassade händelser 1-100.

Här följer några exempel: Du är innehållsägare och vill se vilka sidor som har bidragit till (deltagit i) besök som innehöll en e-postregistrering. Så här:

1. Skapa ett nytt mått i verktyget Beräknade mätvärden.
1. Dra success-händelsen &quot;Orders&quot; till arbetsytan Definition.
1. Ändra [attribueringsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) för händelsen till **[!UICONTROL Participation]** under **[!UICONTROL Settings]** utrustning. Välj **[!UICONTROL Visit]** uppslag. Definitionen bör se ut ungefär så här:

   ![](assets/participation.png)

1. Spara måtten.
1. Använd det beräknade måttet i en **[!UICONTROL Pages]** rapport.

   ![](assets/participation-pages.png)

1. (Valfritt) Dela mätvärdena med andra användare i organisationen.
