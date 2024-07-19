---
description: Med verktyget Beräknade mätvärden kan vem som helst skapa ett deltagandemått.
title: Deltagandemått
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Bygg ett deltagandemått

I den här artikeln beskrivs hur du skapar ett deltagarmått. Ett deltagandemått visar hur enskilda värden för en dimension (som sidvyer, marknadsföringskanal) bidrar till eller deltar i sessioner som innehåller ett visst mått (till exempel Beställningar).

Den här typen av information kan vara användbar för alla innehållsägare.

>[!NOTE]
>
>Mätvärden med andra attribueringsmodeller, som Deltagande, kan också skapas av administratörer som en del av en [datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). Mer information finns i [Inställningar för attribueringskomponent](../../../data-views/component-settings/attribution.md).<br/>I exemplet nedan visas hur en deltagarmätare kan skapas av alla användare med tillgång till den beräknade metriska byggaren i Workspace.


1. Börja skapa ett mätvärde enligt beskrivningen i [Bygg mått](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Ange ett namn för måttet `Participation` eller något liknande i verktyget Beräknade mått.
1. Dra ett mätvärde som innehåller en lyckad händelse, till exempel [!DNL Orders], till arbetsytan i [!UICONTROL Definition].
1. Välj ![Kugga](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) för måttet.
1. I popup-fönstret som visas väljer du **[!UICONTROL Use a non-default attribution model]** för att definiera [-attribueringsmodellen](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) för den händelsen till **[!UICONTROL Participation]** och väljer **[!UICONTROL Session]** för [!UICONTROL Lookback window]. Bekräfta genom att välja **[!UICONTROL Apply]**.

   I rutan Definition uppdateras det valda måttet genom att **(partition|Session)** läggs till i namnet.

   ![Popup-meny för kolumnattribueringsmodell som visar deltagande som vald modell och session för fönstret Sök efter.](assets/participation-setup.png)



1. Välj [!UICONTROL **Spara**] om du vill spara måttet.
1. Använd det beräknade måttet i rapporten. Använd till exempel det beräknade [!DNL Orders (Session Participation)]-måttet (enligt definition i steg 5) i en rapport för att visa vilken kundnivå som bidragit till (eller deltagit i) sessioner som innehöll en order.

   ![Frihandsregister med kundnivå och beställningar.](assets/participation-pages-customer-tier.png)

1. (Valfritt) Dela mätvärdena med andra användare i organisationen, enligt beskrivningen i [Dela beräknade värden](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
