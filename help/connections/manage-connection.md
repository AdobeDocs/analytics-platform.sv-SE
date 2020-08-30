---
title: Hantera anslutningar
description: Beskriver hur anslutningar till plattformsdatauppsättningar hanteras.
translation-type: tm+mt
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 2%

---


# Hantera anslutningar

När du har skapat en eller flera anslutningar kan du hantera dem i [!UICONTROL Connections] Chef. Ni kan

* Ta bort en anslutning.
* Byt namn på en anslutning.
* Skapa en datavy från en anslutning.
* Starta och stoppa dataströmning.

![Anslutningshanteraren](assets/connections-manager.png)

1. Klicka på **[!UICONTROL Connections]** flik.

2. Välj vilken eller vilka anslutningar du vill redigera eller hantera.

3. Gör något av följande:

   | Åtgärd | Beskrivning |
   |---|---|
   | [!UICONTROL Delete] | Om du tar bort en anslutning tas inte datauppsättningen bort eftersom data fortfarande finns i [!DNL Adobe Experience Platform]. |
   | [!UICONTROL Rename] | Du kan byta namn på anslutningen med ett mer beskrivande namn. |
   | [!UICONTROL Create Data View] | Den här länken tar dig till [datavy Builder](/help/data-views/create-dataview.md). |
   | [!UICONTROL Start or stop data streaming] | &quot;Strömning&quot; innebär att om nya batchar läggs till i någon av datauppsättningarna i anslutningen, kommer dessa nya data att läggas till [!UICONTROL Customer Journey Analytics] för rapportering. |


