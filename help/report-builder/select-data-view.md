---
title: Välja en datavy i Report Builder
description: Beskriver hur du väljer datavyer i Adobe Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Välj en datavy

Du kan välja en datavy från den nedrullningsbara menyn eller välja en datavy från en cell och automatiskt uppdatera datablocket med en ny datavy.

## Välj datavy från en cell

Om du väljer en datavy från en cell blir det enkelt att uppdatera datablock med hjälp av olika datavyer. I stället för att skapa helt nya rapporter med separata datablock, kan du uppdatera datablock med en datavy som är markerad från en cell.

Det kan vara praktiskt att välja en datavy från en cell när du har:

* Flera datavyer som liknar eller är identiska med varandra i strukturen.
* Komplicerade datablockformat som innehåller anpassade komponenter och layouter.

Om du vill välja en datavy från en cell skapar du först ett datablock och tilldelar flera datavyer till en cell utanför datablocket. Använd sedan panelen **[!UICONTROL Data view from cell]** för att uppdatera dina datablock från olika datavyer.

1. Skapa ett datablock. Mer information om hur du skapar ett datablock finns i [Skapa ett datablock](/help/report-builder/create-a-data-block.md).

1. Välj ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) i **[!UICONTROL Data views]**.

1. Markera en cell utanför datablocket med ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) .

1. Lägg till en eller flera datavyer från **[!UICONTROL Select data views to add to data view from cell]** genom att dra och släppa. Du kan också dubbelmarkera en datavy för att lägga till datavyn i listan **[!UICONTROL Data views included]**.

   * Du kan använda ![Sök](/help/assets/icons/Search.svg) **[!UICONTROL _Välj datavyer_]** för att söka efter datavyer.
   * Använd ![MoreSmall](/help/assets/icons/MoreSmall.svg) för att öppna en snabbmeny så att du kan flytta datavyer uppåt eller nedåt i **[!UICONTROL Data views included]**-listan.
   * Använd ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort en datavy från listan **[!UICONTROL Data views included]**.

   ![Välj datavy från en cell](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Välj **[!UICONTROL Apply]** om du vill använda de markerade datavyerna på den markerade cellen.


## Ändra datavyn från en cell

1. Markera cellen i datavyn i bladet.
1. I Report Builder-navet väljer du länken **[!UICONTROL Data views from cell]** i **[!UICONTROL Quick edit]**.
1. Välj en datavy i listrutan **[!UICONTROL Data view]**.

   ![Ändra datavy från en cell](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Valfritt, välj **[!UICONTROL Refresh data block(s) upon change]**.

1. Välj **[!UICONTROL Apply]**. Report Builder uppdaterar datablocket baserat på den valda datavyn.
