---
description: Lär dig hur du skapar beräknade värden.
title: Skapa beräknade mått
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: 17d3e8ed5986348bb4ba50822dfd9bb43d5a7570
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Skapa beräknade mått

Som standard kan bara administratörer skapa beräknade värden. Användare har behörighet att visa beräknade värden, ungefär som hur användare visar andra komponenter (till exempel filter, anteckningar och annat).

Administratörer kan dock ge användare behörighet **[!UICONTROL Calculated Metric Creation]** för **[!UICONTROL Reporting Tools]** i **[!UICONTROL Edit permissions for CJA Workspace Access]** via [Admin Console](/help/technotes/access-control.md#user-level-access).


Du kan skapa ett beräknat mått på följande sätt:

![Olika sätt att skapa ett filter](assets/create-metric.png)

* ? I huvudgränssnittet väljer du **[!UICONTROL Components]** och sedan **[!UICONTROL Calculated metrics]**. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] i [[!UICONTROL Calculated metrics] manager](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* ? I ett Workspace-projekt väljer du ![Lägg till](/help/assets/icons/Add.svg) vid ![Händelse](/help/assets/icons/Event.svg) **Mätvärden** från den vänstra panelen Komponenter.
* ? I ett Workspace-projekt väljer du **[!UICONTROL Create metric from selection]** på snabbmenyn i kolumnrubriken Mått. På undermenyn kan du välja en funktion eller välja **[!UICONTROL Open in calculated metric builder]**. <br/>Om du väljer en funktion definieras det beräknade måttet som ett projekttsmått. När du senare redigerar det här måttet visas ett meddelande i [verktyget för beräknade mätvärden](/help/components/use-components-in-workspace.md#component-info) via popup-fönstret [Komponentinformation](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* ? I ett Workspace-projekt väljer du **[!UICONTROL Components]** på menyn och sedan **[!UICONTROL Create metric]**.
* ? Använd genvägen **[!UICONTROL shift+cmd+c]** (macOS) eller **[!UICONTROL shift+ctrl+c]** (Windows) i ett Workspace-projekt.

Om du vill definiera det nya beräknade måttet använder du verktyget [Beräknade mätvärden](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

<!--

Learn about the steps to take for creating calculated metrics.

| Workflow Task | Description |
| --- | --- |
| Plan Calculated Metrics | Especially for metrics that are going to be officially "approved", it makes sense to outline which calculated metrics will be widely used and how they will be defined. |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Calculated Metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components. |
| [Tag](cm-tagging.md) Calculated Metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization. |
| [Approve](cm-approving.md) Calculated Metrics | Approve calculated metrics to make them canonical. |
| Apply Calculated Metrics | You can apply metrics directly from a report, from the Metric Selector (to access it, click [!UICONTROL Show Metrics]). |
| Filter Calculated Metrics | In the Metric Selector, click [!UICONTROL Advanced Selection] and filter by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.) |
| Mark Calculated Metrics as [Favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.|

-->
