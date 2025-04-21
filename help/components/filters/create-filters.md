---
title: Skapa segment
description: Förstå användargränssnittet för att skapa segment.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
feature: Filters
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Skapa segment

Du kan skapa olika typer av segment i Customer Journey Analytics.  Vilken typ du väljer beror på hur komplexa segmenten behöver vara och om segmenten bara ska gälla för det aktuella Workspace-projektet eller för alla projekt. Du kan skapa segment direkt i Customer Journey Analytics huvudgränssnitt eller när du arbetar i ett Workspace-projekt.

Som standard kan bara administratörer skapa segment. Användare har behörighet att visa segment, på liknande sätt som användare visar andra komponenter (som anteckningar, beräknade värden osv.).

Administratörer kan dock ge användare behörighet **[!UICONTROL Segment Creation]** för **[!UICONTROL Reporting Tools]** i **[!UICONTROL Edit permissions for CJA Workspace Access]** via [Admin Console](/help/technotes/access-control.md#user-level-access).

Du kan skapa ett segment på följande sätt:

![Olika sätt att skapa ett segment](assets/create-filter.png)

* **A**. I huvudgränssnittet väljer du **[!UICONTROL Components]** och sedan **[!UICONTROL Segments]**. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] i [[!UICONTROL Segment] manager](/help/components/filters/manage-filters.md).
* **B**. I ett Workspace-projekt väljer du ![Lägg till](/help/assets/icons/Add.svg) vid ![Segment](/help/assets/icons/Segmentation.svg) **Segment** från den vänstra panelen Komponenter.
* **C**. I ett Workspace-projekt väljer du **[!UICONTROL Create segment from selection]** på snabbmenyn i en visualisering.
* **D**. I ett Workspace-projekt väljer du **[!UICONTROL Components]** på menyn och sedan **[!UICONTROL Create segment]**.
* **E**. Använd genvägen **[!UICONTROL shift+cmd+e]** (macOS) eller **[!UICONTROL shift+ctrl+e]** (Windows) i ett Workspace-projekt.
* **F**. Välj ![Lägg till](/help/assets/icons/Add.svg) i ***Släpp ett segment här (eller någon annan komponent)***. Den här åtgärden skapar ett segment som bara innehåller projekt.

Om du vill definiera det nya segmentet använder du [segmentverktyget](/help/components/filters/filter-builder.md).

När du arbetar i ett Workspace-projekt kan du även skapa ett segment snabbt med [snabbsegmentet](/help/components/filters/quick-filters.md).
