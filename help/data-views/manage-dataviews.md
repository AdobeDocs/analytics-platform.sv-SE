---
title: Hantera datavyer
description: Lär dig hur du hanterar datavyer.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c5cf15ab-3eb1-4e6b-93a3-3d89694ca0ea
source-git-commit: c7cf7250f30e2f6023aa7690391aea149ba12eff
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%

---

# Hantera datavyer


När du har [skapat eller redigerat en eller flera datavyer](/help/data-views/create-dataview.md) kan du hantera dem i **[!UICONTROL Data views]**.

Välj **[!UICONTROL Data Management]** > **[!UICONTROL Data views]** på huvudmenyraden i Customer Journey Analytics.

Gränssnittet **[!UICONTROL Data views]** visar en tabell med alla datavyer som är tillgängliga.

![Gränssnitt för datavyer](/help/data-views/assets/data-views.png)

Följande kolumner och ikoner är tillgängliga i tabellen:

| Kolumn eller ikon | Beskrivning |
| --- | --- |
| **[!UICONTROL Name]** | Datavyns namn. |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Om du vill visa information om datavyn väljer du ![InfoOutline](/help/assets/icons/InfoOutline.svg) bredvid datavyns namn.<br/>Ett popup-fönster visar information om datavyn. |
| ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Välj ![Mer](/help/assets/icons/More.svg) om du vill öppna en snabbmeny. Du kan välja:<br/>![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** om du vill [redigera](#edit-data-views) en datavy.<br/>![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** till [kopiera en datavy](#copy-data-views).<br/>![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** om du vill [ta bort](#delete-data-views) en datavy.<br/>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** för att [exportera informationen om datavyn till en CSV-fil](#export-data-views-to-csv).<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create project]** för att [skapa ett nytt Workspace-projekt](#create-project-from-data-views) för datavyn.<br/>![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]** om du vill aktivera en datavy för Data Insights Agent.<br/>![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]** om du vill inaktivera en datavy för Data Insights Agent. |
| **[!UICONTROL Connection]** | Namnet på anslutningen som är associerad med datavyn. |
| **[!UICONTROL Sandbox]** | Namnet på sandlådan som är associerad med datavyn. |
| **[!UICONTROL Owner]** | Datavyns ägare. |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | Anger om [Data Insights Agent](/help/data-analysis-ai.md) är **[!UICONTROL Enabled]** eller **[!UICONTROL Disabled]** för datavyn. <br/>Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg) om du vill visa ett popup-fönster med **[!UICONTROL Data Insights Agent Status]** över datavyer. <br/>![Användning i Data Insights Agent](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL Integrations]** | Lista integreringar med andra lösningar. Exempel: Adobe Audience Analysis, Content Analytics, Brand Concierge, Journey Optimizer, GenStudio och Usage Analytics. |
| **[!UICONTROL Use in CJA]** | Ange om datavyn används i Customer Journey Analytics. Det här värdet är bara **[!UICONTROL Off]** för datavyer som automatiskt genereras som en del av Adobe Journey Optimizer-integreringen. |
| **[!UICONTROL Date created]** | Tidsstämpeln när datavyn skapades. |
| **[!UICONTROL Last modified]** | Tidsstämpeln när datavyn senast ändrades. |

Om du vill konfigurera vilka kolumner som ska visas i tabellen väljer du ![Kolumninställning](/help/assets/icons/ColumnSetting.svg). Markera de kolumner som ska visas i dialogrutan **[!UICONTROL Customize table]**. Välj sedan **[!UICONTROL Apply]**.


## Sök datavyer

Du kan snabbt söka efter en datavy med rutan ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

## Filtrera datavyer

Om du vill använda ett filter på listan med datavyer markerar du ikonen ![Filter](/help/assets/icons/Filter.svg) och väljer sedan något av följande filteralternativ:

| Filteralternativ | Beskrivning |
|---------|----------|
| **[!UICONTROL Connections]** | Endast datavyer som är kopplade till de anslutningar du väljer visas. |
| **[!UICONTROL Owner]** | Endast datavyer som ägs av de personer du väljer visas. |
| **[!UICONTROL Sandbox]** | Endast datavyer som är tillgängliga i de sandlådor du väljer visas. |
| **[!UICONTROL Integrations]** | Endast datavyer med valda integreringar visas. |
| **[!UICONTROL Use in CJA]** | Välj **[!UICONTROL On]** om du bara vill visa datavyer som har aktiverats för användning med Customer Journey Analytics. Välj **[!UICONTROL Off]** om du bara vill visa datavyer som ännu inte har aktiverats för användning med Customer Journey Analytics. |


Välj ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** om du vill dölja filterrutan.

## Skapa en datavy

Om du vill [skapa en ny datavy](/help/data-views/create-dataview.md) väljer du **[!UICONTROL Create new data view]**.


## Redigera datavyer

Om du vill [redigera en datavy](/help/data-views/create-dataview.md):

1. Välj ![Mer](/help/assets/icons/More.svg) bredvid datavyns namn.
1. Välj ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** på snabbmenyn.

Du kan också:

1. Markera datavyraden.
1. Välj ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** i det blå åtgärdsfältet.


## Kopiera datavyer

Om du vill kopiera en datavy:

1. Välj ![Mer](/help/assets/icons/More.svg) bredvid datavyns namn.
1. Välj ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** på snabbmenyn.

Du kan också:

1. Markera en eller flera datavy-rader.
1. Välj ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** i det blå åtgärdsfältet.

Datavyn kopieras och läggs till i listan med **[!UICONTROL (Copy)]** som tillägg till namnet.


## Ta bort datavyer

Om du vill ta bort en datavy:

1. Välj ![Mer](/help/assets/icons/More.svg) bredvid datavyns namn.
1. Välj ![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** på snabbmenyn.

Du kan också:

1. Markera en eller flera datavy-rader.
1. Välj ![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** i det blå åtgärdsfältet.

När du tar bort en eller flera datavyer visar en **[!UICONTROL Delete data view]**-panel vilka projekt som påverkas.

![Ta bort datavy](/help/data-views/assets/delete-data-view.png)


* I ➊ **[!UICONTROL Confirmation]** visas konsekvenserna av att datavyer tas bort.
* Välj **[!UICONTROL Delete]** om du vill ta bort datavyer permanent. Välj **[!UICONTROL Cancel]** om du vill avbryta.


## Exportera datavyer till CSV

Du kan exportera en datavy till en CSV-fil.

1. Välj ![Mer](/help/assets/icons/More.svg) bredvid datavyns namn.
1. Välj ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** på snabbmenyn.

Du kan också:

1. Markera en eller flera datavy-rader.
1. Välj ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** i det blå åtgärdsfältet.

Information om de markerade datavyerna exporteras till en CSV-fil med namnet `Data views List (x).csv` i mappen Hämtningar i webbläsaren.


## Skapa projekt från datavyer

Du kan skapa ett Workspace-projekt direkt från datavygränssnitt.

1. Välj ![Mer](/help/assets/icons/More.svg) bredvid datavyns namn.
1. Välj ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create project]** på snabbmenyn.

Du kan också:

1. Markera en datavy.
1. Välj ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create project]** i det blå åtgärdsfältet.


## Aktivera eller inaktivera datavyer för Data Insights Agent

Du kan aktivera eller inaktivera en datavy för [Data Insights Agent](/help/data-analysis-ai.md).

1. Välj ![Mer](/help/assets/icons/More.svg) bredvid datavyns namn.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]** eller ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]** på snabbmenyn.

Du kan också:

1. Markera en eller flera datavy-rader som antingen är inaktiverade eller aktiverade för Data Insights Agent.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]** eller ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]** i det blå åtgärdsfältet.
