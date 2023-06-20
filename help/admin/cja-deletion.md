---
title: Borttagningskonsekvenser
description: Vad händer när du tar bort anslutningar, datauppsättningar eller grupper i Customer Journey Analytics eller Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: ca329bd551990c1fefeda2fe272ed17551cfaac8
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Borttagningskonsekvenser

Tänk på detta innan du tar bort anslutningar, datauppsättningar eller grupper i Customer Journey Analytics eller Adobe Experience Platform:

| När du ... | Det här händer.. |
| --- | --- |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande visar att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla arbetsyteprojekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul>Observera att du inte kan ta bort Customer Journey Analytics-anslutningar som är kopplade till Adobe Experience Platform-sandlådor som du inte har behörighet för. Även om du har behörighet till datavyer som bygger på dessa anslutningar kan du inte ta bort anslutningarna förrän du har beviljats behörighet till de underliggande Adobe Experience Platform-sandlådorna. |
| Ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform] | Om du tar bort en datauppsättning i AEP avbryts dataflödet från den datauppsättningen till alla anslutningar som innehåller den datauppsättningen. Data från den datauppsättningen tas inte automatiskt bort från associerade Customer Journey Analytics-anslutningar. |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | När du tar bort en datauppsättning från en anslutning i Customer Journey Analytics kommer datavyer och projekt som var beroende av den datauppsättningen inte längre att fungera. |
| Ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform]) | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform] datauppsättning, samma batch tas bort från alla [!UICONTROL Customer Journey Analytics] anslutningar som innehåller den specifika gruppen. [!UICONTROL Customer Journey Analytics] meddelas om batchar som har tagits bort i [!UICONTROL Adobe Experience Platform]. |
| Ta bort en grupp **medan den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen kommer inga data eller delar av data från den gruppen att visas i [!UICONTROL Customer Journey Analytics]. Intag kommer att återställas. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när datauppsättningen togs bort, kommer data från dessa tre batchar att visas i [!UICONTROL Customer Journey Analytics]. |
| Ta bort uppslagsdatauppsättningar i [!UICONTROL Adobe Experience Platform] | Även om det är möjligt att ta bort datauppsättningar för andra källanslutningar stöds det för närvarande inte för [Källkoppling för analysklassificeringar](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html). Om du tar bort en datauppsättning av misstag, kontakta Adobe kundtjänst. |
