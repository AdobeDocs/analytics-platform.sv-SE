---
title: Hantera anslutningar
description: Beskriver hur du hanterar anslutningar till plattformsdatauppsättningar.
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---


# Hantera anslutningar

När du har skapat en eller flera anslutningar kan du hantera dem i [!UICONTROL Connections]-hanteraren. Ni kan

* Ta bort en anslutning.
* Byt namn på en anslutning.
* Skapa en datavy från en anslutning.
* Starta och stoppa dataströmning.

![Anslutningshanteraren](assets/connections-manager.png)

1. Klicka på fliken **[!UICONTROL Connections]**.

2. Välj vilka anslutningar du vill redigera eller hantera.

3. Gör något av följande:

   | Åtgärd | Beskrivning |
   |---|---|
   | [!UICONTROL Delete] | Datauppsättningen tas inte bort när du tar bort en anslutning eftersom data fortfarande finns i [!DNL Adobe Experience Platform]. Se&quot;Ta bort anslutningar&quot; nedan. |
   | [!UICONTROL Rename] | Du kan byta namn på anslutningen med ett mer beskrivande namn. |
   | [!UICONTROL Create Data View] | Den här länken tar dig till [datavyverktyget](/help/data-views/create-dataview.md). |
   | [!UICONTROL Start or stop data streaming] | &quot;Strömning&quot; innebär att om nya grupper läggs till i någon av datauppsättningarna i anslutningen, kommer dessa nya data att hämtas till [!UICONTROL Customer Journey Analytics] för rapportering. |

## Ta bort anslutningar

| Tänk om jag.. | Detta händer |
| --- | --- |
| Vill du ta bort en anslutning i [!UICONTROL Customer Journey Analytics]? | Ett felmeddelande visar att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla arbetsyteprojekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul> |
| Vill du ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform]? | Om du tar bort en datauppsättning i AEP avbryts dataflödet från den datauppsättningen till alla anslutningar som innehåller den datauppsättningen. Data från den datauppsättningen tas inte automatiskt bort från associerade CJA-anslutningar. |
| Vill du ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics]? | För närvarande kan du inte ta bort en datauppsättning i en anslutning som har sparats. Du måste ta bort hela anslutningen och börja om från början. (Du kan dock ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform].) |
| Vill du ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform])? | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform]-datauppsättning, tas samma batch bort från alla [!UICONTROL Customer Journey Analytics]-anslutningar som innehåller den specifika gruppen. [!UICONTROL Customer Journey Analytics] meddelas om batchar som har tagits bort i  [!UICONTROL Adobe Experience Platform]. |
| Vill du ta bort en batch **medan den hämtas** till [!UICONTROL Customer Journey Analytics]? | Om det bara finns en batch i datauppsättningen visas inga data eller delar av data från den gruppen i [!UICONTROL Customer Journey Analytics]. Intag kommer att återställas. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när datauppsättningen togs bort, visas data från dessa tre batchar i [!UICONTROL Customer Journey Analytics]. |
