---
description: Lär dig mer om alternativen för att öppna projekt.
title: Öppna projekt
feature: Workspace Basics
role: User
exl-id: 5ef235e2-50d8-4202-bad7-06090102cf73
source-git-commit: ab78583eb36d6158630724fbab9eb8148bcdbe23
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---

# Öppna projekt

Du kan öppna ett projekt direkt från sidan [Projekt](/help/analysis-workspace/build-workspace-project/freeform-overview.md). Leta efter ditt projekt i listan. Använd [search](/help/analysis-workspace/build-workspace-project/freeform-overview.md#search) eller [segmentpanelen](/help/analysis-workspace/build-workspace-project/freeform-overview.md#segment-panel) för att begränsa listan.

* Välj projekttitel för att öppna projektet i Analysis Workspace.

Du kan också öppna ett projekt medan du arbetar i ett annat projekt.

* Välj **[!UICONTROL Open]** på menyn **[!UICONTROL Project]**. En dialogruta visas som liknar sidan [Projekt](/help/analysis-workspace/build-workspace-project/freeform-overview.md).  Använd [search](/help/analysis-workspace/build-workspace-project/freeform-overview.md#search) eller [segmentpanelen](/help/analysis-workspace/build-workspace-project/freeform-overview.md#segment-panel) för att begränsa listan.
* Välj projekttitel för att öppna projektet i Analysis Workspace.

Om du inte kan hitta projektet och vill starta ett nytt projekt väljer du **[!UICONTROL Create new]**.

## Öppna föregående version

Så här öppnar du en tidigare sparad version av ett projekt:

1. Välj **[!UICONTROL Open previous version]** på menyn **[!UICONTROL Project]**.

   ![Listan med tidigare sparade projektversioner och alternativ för att visa alla versioner eller endast versioner med anteckningar.](assets/open-previously-saved.png)

1. Granska listan över tidigare versioner i dialogrutan **[!UICONTROL Previously saved versions]**. Du kan växla mellan **[!UICONTROL All versions]** och **[!UICONTROL Only versions with notes]**.

   För varje version visar listan en tidsstämpel, redigeraren och sparade anteckningar.


1. Välj en tidigare version och klicka på **[!UICONTROL Load]**.
Den föregående versionen läses sedan in med ett meddelande. Den tidigare versionen blir inte den aktuella sparade versionen av ditt projekt förrän du klickar på **[!UICONTROL Save]**. Om du navigerar bort från den inlästa versionen visas den senast sparade versionen när du vill öppna en tidigare version en gång till.


## Inkompatibel datavy

När du öppnar ett projekt kanske en **[!UICONTROL Incompatible data view]**-varningsdialogruta visas. I den här dialogrutan förklaras att vissa komponenter i projektet inte är aktiverade i den valda datavyn för någon av panelerna i projektet.

![Inkompatibel](assets/incompatible-data-view.png)

Du kan åtgärda den här varningen genom att:

* **[!UICONTROL Change the data view]**. Välj en korrekt datavy från **[!UICONTROL Change data view:]** ![Data](/help/assets/icons/Data.svg). Om den valda datavyn är giltig öppnas ditt projekt i Analysis Workspace.
* **[!UICONTROL Return to landing page]**. Det valda projektet är inte öppet och du kan välja ett annat projekt.
* **[!UICONTROL Continue anyway]**. Ditt projekt öppnas i Analysis Workspace, men fel visas i vissa visualiseringar och inkompatibla datavyer får en varning ![Alert](/help/assets/icons/Alert.svg) före datavyns namn.
