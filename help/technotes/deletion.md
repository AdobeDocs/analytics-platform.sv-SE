---
title: Borttagningskonsekvenser
description: Vad händer när du tar bort anslutningar, datauppsättningar eller grupper i Customer Journey Analytics eller Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 928c79f9ccf30cc33e0f334f715bf3190a257019
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Borttagningskonsekvenser

Tänk på detta innan du tar bort anslutningar, datauppsättningar eller grupper i Customer Journey Analytics eller Adobe Experience Platform:

| När du ... | Det här händer.. |
| --- | --- |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande visar att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla Workspace-projekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul>Observera att du inte kan ta bort Customer Journey Analytics-anslutningar som: <ul><li>Är knutna till Adobe Experience Platform-sandlådor som du inte har behörighet för. Även om du har behörighet till datavyer som bygger på dessa anslutningar kan du inte ta bort anslutningarna förrän du har beviljats behörighet till de underliggande Adobe Experience Platform-sandlådorna.</li><li>Ha följande kompatibilitetsalternativ valt för en datavy som är associerad med anslutningen: **[!UICONTROL Set as default data view in Adobe Journey Optimizer]**<p>Mer information om det här konfigurationsalternativet finns i [Kompatibilitet](/help/data-views/create-dataview.md#compatibility) i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md)</p></li></ul> |
| Ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform] | Om du tar bort en datauppsättning i AEP avbryts dataflödet från den datauppsättningen till alla anslutningar som innehåller den datauppsättningen. Alla data från den datauppsättningen tas automatiskt bort från associerade Customer Journey Analytics-anslutningar. |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | När du tar bort en datauppsättning från en anslutning i Customer Journey Analytics kommer datavyer och projekt som var beroende av den datauppsättningen inte längre att fungera. |
| Ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform]) | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform]-datauppsättning tas samma batch bort från alla [!UICONTROL Customer Journey Analytics]-anslutningar som innehåller den specifika gruppen. [!UICONTROL Customer Journey Analytics] meddelas om batchar som har tagits bort i [!UICONTROL Adobe Experience Platform]. |
| Ta bort en batch **medan den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen visas inga data eller delar av data från den gruppen i [!UICONTROL Customer Journey Analytics]. Intag kommer att återställas. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när datauppsättningen togs bort, visas data från dessa tre batchar i [!UICONTROL Customer Journey Analytics]. |
| Ta bort uppslagsdatauppsättningar i [!UICONTROL Adobe Experience Platform] | Även om det går att ta bort datauppsättningar för andra källanslutningar stöds det för närvarande inte för [Analytics Classifications Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=sv-SE). Om du tar bort en datauppsättning av misstag kontaktar du Adobe kundtjänst. |
