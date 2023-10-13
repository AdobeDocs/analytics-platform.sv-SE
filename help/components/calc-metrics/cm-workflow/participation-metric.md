---
description: Med verktyget Beräknade mätvärden kan vem som helst skapa ett deltagandemått.
title: Deltagandemått
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 6a9cae93011447fff0f74ca4ae15178e0a1f36aa
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# Bygg ett deltagandemått

I den här artikeln beskrivs hur du skapar ett deltagarmått. Ett deltagandemått visar hur enskilda värden för en dimension (som sidvyer, marknadsföringskanal) bidrar till eller deltar i sessioner som innehåller ett visst mått (till exempel Beställningar).

Den här typen av information kan vara användbar för alla innehållsägare.

>[!NOTE]
>
>Mätvärden med andra attribueringsmodeller, som Deltagande, kan också skapas av administratörer som en del av en [datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). I exemplet nedan visas hur de kan skapas av alla användare som har tillgång till verktyget för beräknade mätvärden i Workspace.


1. Börja skapa ett mätvärde enligt beskrivningen i [Bygg mätvärden](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Ange måttet&quot;Deltagande&quot; eller något liknande i verktyget Beräknade mått.
1. Dra ett mätvärde som innehåller en success-händelse, till exempel&quot;Orders&quot;, till arbetsytan Definition.
1. Välj ![Kugghjul](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) för måttet.
1. I popup-fönstret som visas väljer du **[!UICONTROL Use a non-default attribution model]** för att definiera [attribueringsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) för händelsen till **[!UICONTROL Participation]** och markera **[!UICONTROL Session]** för [!UICONTROL Lookback window]. Välj **[!UICONTROL Apply]** för att bekräfta.

   I rutan Definition uppdateras det valda måttet genom att lägga till  **(Partition|Session)** till namnet.

   ![](assets/participation-setup.png)



1. Välj [!UICONTROL **Spara**] för att spara måtten.
1. Använd det beräknade måttet i rapporten. Använd till exempel den beräknade [!DNL Orders (Session Participation)] mätvärden (enligt definition i steg 5) i en rapport för att visa vilken kundnivå som bidragit till (eller deltagit i) sessioner som innehöll en order.

   ![](assets/participation-pages-customer-tier.png)

1. (Valfritt) Dela mätvärdena med andra användare i organisationen enligt beskrivningen i [Dela beräknade värden](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
