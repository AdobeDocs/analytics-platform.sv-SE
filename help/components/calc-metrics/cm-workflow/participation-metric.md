---
description: Med beräkningsverktyget kan vem som helst skapa ett deltagandemått.
title: Deltagandemått
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Deltagandestatistik

Deltagandestatistik används för att kvantifiera hur enskilda värden för en dimension (som sidvyer) bidrar till, eller deltar i sessioner som innehåller ett visst mått (som beställningar).

>[!NOTE]
>
>Administratörer kan skapa mätvärden med icke-standardattribueringsmodeller, som Deltagande, som en del av en [datavy](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/data-views). Mer information finns i [Inställningar för attribueringskomponent](../../../data-views/component-settings/attribution.md).

Stegen nedan visar hur alla användare med [Skapa beräknad metrisk behörighet](/help/technotes//access-control.md#user-level-access) kan skapa ett deltagandemått.

1. [Skapa ett beräknat mått](cm-workflow.md) och i [verktyget för beräknade värden](cm-build-metrics.md) namnger du måttet `Participation` eller något liknande.
1. Dra ett mätvärde som innehåller en lyckad händelse, till exempel [!DNL Orders], till området [!UICONTROL **[!UICONTROL Definition]**].
1. Välj ![Kugga](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) för måttet.
1. I popup-fönstret som visas väljer du **[!UICONTROL Use a non-default attribution model]** för att definiera [-attribueringsmodellen](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) för den händelsen till **[!UICONTROL Participation]** och väljer **[!UICONTROL Session]** för [!UICONTROL Lookback window]. Bekräfta genom att välja **[!UICONTROL Apply]**.


   ![Popup-meny för kolumnattribueringsmodell som visar deltagande som vald modell och session för fönstret Sök efter.](assets/participation-setup.png)

   **(Partition|Session)** har lagts till i måttkomponentens namn.



1. Välj [!UICONTROL **Spara**] om du vill spara måttet.
1. Använd det beräknade måttet i rapporten. Använd till exempel det beräknade [!DNL Orders (Session Participation)]-måttet i en rapport för att visa vilken kundnivå som bidragit till (eller deltagit i) sessioner som innehöll en order.

   ![Frihandsregister med kundnivå och beställningar.](assets/participation-pages-customer-tier.png)
