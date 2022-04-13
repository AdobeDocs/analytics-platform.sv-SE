---
title: Borttagningskonsekvenser
description: Vad händer när du tar bort anslutningar, datauppsättningar eller grupper i Customer Journey Analytics eller Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Borttagningskonsekvenser

Tänk på detta innan du tar bort anslutningar, datauppsättningar eller grupper i Customer Journey Analytics eller Adobe Experience Platform:

| När du ... | Det här händer.. |
| --- | --- |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande visar att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla arbetsyteprojekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul> |
| Ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform] (AEP) | Om du tar bort en datauppsättning i AEP avbryts dataflödet från den datauppsättningen till alla anslutningar som innehåller den datauppsättningen. Data från den datauppsättningen tas inte automatiskt bort från associerade CJA-anslutningar. |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | För närvarande kan du inte ta bort en datauppsättning i en anslutning som har sparats. Du måste ta bort hela anslutningen och börja om från början. (Du kan dock ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform].) |
| Ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform]) | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform] datauppsättning, samma batch tas bort från alla [!UICONTROL Customer Journey Analytics] anslutningar som innehåller den specifika gruppen. [!UICONTROL Customer Journey Analytics] meddelas om batchar som har tagits bort i [!UICONTROL Adobe Experience Platform]. |
| Ta bort en grupp **medan den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen kommer inga data eller delar av data från den gruppen att visas i [!UICONTROL Customer Journey Analytics]. Intag kommer att återställas. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när datauppsättningen togs bort, kommer data från dessa tre batchar att visas i [!UICONTROL Customer Journey Analytics]. |
| Ta bort datauppsättningar för sökning i [!UICONTROL Adobe Experience Platform] | Även om det är möjligt att ta bort datauppsättningar för andra källanslutningar stöds det för närvarande inte för [Dataanslutning för analysklassificeringar](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html). Om du tar bort en datauppsättning av misstag, kontakta Adobe kundtjänst. |
