---
title: Borttagningskonsekvenser
description: Vad händer när du tar bort anslutningar, datauppsättningar eller grupper i Customer Journey Analytics eller Adobe Experience Platform.
source-git-commit: 3fa2c562abaf4aa1f18baa5de5ee66c7ad828f52
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---

# Borttagningskonsekvenser

Tänk på detta innan du tar bort anslutningar, datauppsättningar eller grupper i Customer Journey Analytics eller Adobe Experience Platform:

| När du ... | Det här händer.. |
| --- | --- |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande visar att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla arbetsyteprojekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul> |
| Ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform] (AEP) | Om du tar bort en datauppsättning i AEP avbryts dataflödet från den datauppsättningen till alla anslutningar som innehåller den datauppsättningen. Data från den datauppsättningen tas inte automatiskt bort från associerade CJA-anslutningar. |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | För närvarande kan du inte ta bort en datauppsättning i en anslutning som har sparats. Du måste ta bort hela anslutningen och börja om från början. (Du kan dock ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform].) |
| Ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform]) | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform]-datauppsättning, tas samma batch bort från alla [!UICONTROL Customer Journey Analytics]-anslutningar som innehåller den specifika gruppen. [!UICONTROL Customer Journey Analytics] meddelas om batchar som har tagits bort i  [!UICONTROL Adobe Experience Platform]. |
| Ta bort en batch **medan den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen visas inga data eller delar av data från den gruppen i [!UICONTROL Customer Journey Analytics]. Intag kommer att återställas. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när datauppsättningen togs bort, visas data från dessa tre batchar i [!UICONTROL Customer Journey Analytics]. |
| Ta bort datauppsättningar för sökning i [!UICONTROL Adobe Experience Platform] | Det går att ta bort datauppsättningar för andra källanslutningar, men det stöds för närvarande inte för [Analytics Classifications Data Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=en). Om du tar bort en datauppsättning av misstag, kontakta Adobe kundtjänst. |