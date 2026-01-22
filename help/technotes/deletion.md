---
title: Borttagningskonsekvenser
description: Förstå konsekvenserna av att ta bort eller återställa Customer Journey Analytics- eller Experience Platform-objekt.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 6c53e0cd13bd08a874a160851f925e7acc99bcd2
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 0%

---

# Återställnings- och raderingskonsekvenser

Borttagning eller återställning av Customer Journey Analytics- eller Experience Platform-objekt har ingen inverkan. Dessa konsekvenser beskrivs i den här artikeln.

## Customer Journey Analytics

Tänk på följande innan du tar bort anslutningar, datavyer eller datauppsättningar i Customer Journey Analytics:

| Åtgärd | Konsekvenser |
| --- | --- |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande anger att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla Workspace-projekt som är beroende av datavyer i den borttagna anslutningen fungerar inte heller längre.</li></ul><p>Observera att du inte kan ta bort Customer Journey Analytics-anslutningar som:</p><ul><li>Är knutna till Adobe Experience Platform-sandlådor som du inte har behörighet för. Även om du har behörighet till datavyer som bygger på dessa anslutningar kan du inte ta bort anslutningarna förrän du har beviljats behörighet till de underliggande Adobe Experience Platform-sandlådorna.</li><li>Ha följande kompatibilitetsalternativ valt för en datavy som är associerad med anslutningen: **[!UICONTROL Set as default data view in Adobe Journey Optimizer]**<p>Mer information om det här konfigurationsalternativet finns i [Kompatibilitet](/help/data-views/create-dataview.md#compatibility) i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).</p></li><li>Används i en konfiguration för någon av följande tjänster:<ul><li>[Målgruppsanalys](/help/connections/audience-analysis/audience-analysis-overview.md): Tillhandahåller målgruppsdata till Customer Journey Analytics för en djupgående analys</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md): Tillhandahåller data om innehållskonsumtion och påverkan på Customer Journey Analytics</li></ul><p>Innan du kan ta bort anslutningen måste du först ta bort eller redigera konfigurationen som använder anslutningen.</p></li></ul> |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | När du tar bort en datauppsättning från en anslutning i Customer Journey Analytics fungerar inte längre datavyer och projekt som är beroende av den datauppsättningen. |
| Ta bort en datavy i [!UICONTROL Customer Journey Analytics] | När du tar bort en datavy i Customer Journey Analytics fungerar inte längre paneler i ett Workspace-projekt som är beroende av datavyn korrekt.<p>Observera att du inte kan ta bort datavyer från Customer Journey Analytics som används i en konfiguration för någon av följande tjänster:</p><ul><li>[Målgruppsanalys](/help/connections/audience-analysis/audience-analysis-overview.md): Tillhandahåller målgruppsdata till Customer Journey Analytics för en djupgående analys</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md): Tillhandahåller data om innehållskonsumtion och påverkan på Customer Journey Analytics</li></ul><p>Innan du kan ta bort datavyn måste du först ta bort eller redigera konfigurationen som använder den här datavyn.</p></li></ul> |



## Experience Platform

Tänk på följande innan du tar bort datauppsättningar eller grupper, eller när du återställer eller tar bort sandlådor i Experience Platform:

| Åtgärd | Konsekvenser |
| --- | --- |
| Ta bort en datauppsättning i [!UICONTROL Experience Platform] | Dataflödet från den datauppsättningen i Experience Platform avbryts till alla anslutningar som innehåller den datauppsättningen. Alla data från den datauppsättningen tas automatiskt bort från de associerade Customer Journey Analytics-anslutningarna. |
| Ta bort en batch från en datauppsättning i [!UICONTROL Experience Platform] | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform]-datauppsättning tas samma batch bort från alla [!UICONTROL Customer Journey Analytics]-anslutningar som innehåller den specifika gruppen. [!UICONTROL Customer Journey Analytics] meddelas om batchar som har tagits bort i [!UICONTROL Adobe Experience Platform]. |
| Ta bort en batch från [!UICONTROL Experience Platform] **när den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen visas inga data eller delar av data från den gruppen i [!UICONTROL Customer Journey Analytics]. Intag har återställts. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när den fjärde batchen togs bort, visas data från dessa tre batchar i [!UICONTROL Customer Journey Analytics]. |
| Ta bort uppslagsdatauppsättningar i [!UICONTROL Experience Platform] | När det går att ta bort datauppsättningar för andra källanslutningar stöds inte borttagning av [Analytics-klassificeringar i Source Connector](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications)-datauppsättningar. Om du tar bort en sådan datauppsättning av misstag, kontakta kundtjänst. |
| Ta bort eller återställa en sandlåda i Experience Platform | När du [tar bort en Experience Platform-sandlåda](https://experienceleague.adobe.com/sv/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox) tas även alla scheman, datamängder, grupper, principer och annat bort i den sandlådan. Sandlådan finns inte längre, inte heller sandlådeidentifieraren och namnet på sandlådan.<br/>När du [återställer en Experience Platform-sandlåda](https://experienceleague.adobe.com/sv/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox) tas alla scheman, datamängder, grupper, principer och annat bort i den sandlådan. Även om namnet och behörigheterna för sandlådan inte påverkas ändras sandlådeidentifieraren när återställningen är klar.<br/><br/>Customer Journey Analytics använder sandlådeidentifieraren och sandlådenamnet för att associera en anslutning med en sandlåda. Resultatet blir: <ul><li>Anslutningar som är associerade med den borttagna eller återställda sandlådan tas bort.</li><li>Datavyer (och alla komponentdefinitioner, t.ex. härledda fält, i datavyn) som baseras på de borttagna anslutningarna tas bort.</li><li>Komponenter som förlitar sig på de borttagna datavyerna tas bort. t.ex. segment, beräknade värden, anteckningar, aviseringar, publicerade målgrupper och export.</li><li>Paneler i Workspace-projekt som refererar till de borttagna datavyerna blir oanvändbara. De här panelerna visar **[!UICONTROL Unknown data view]** fel. Ta bort panelerna eller, om det är möjligt, associera panelerna med en befintlig datavy.</li><li>Du bör inte längre fråga (historik) data från den borttagna anslutningen som redan är tillgänglig i Customer Journey Analytics med hjälp av frågetjänsten eller verktyg som är beroende av BI-tillägget. När allt kommer omkring tar Adobe support eller teknik bort dessa data från Customer Journey Analytics.</li></ul>Eftersom konsekvenserna av en återställning eller borttagning av en sandlåda i Experience Platform är betydande bör du tänka på följande innan du återställer eller tar bort en sandlåda:<ul><li>Visa en lista över dina anslutningar för att förstå vilka anslutningar som tillhör vilka sandlådor.</li><li>Visa datavyer för att förstå vilka datavyer som är associerade med vilka anslutningar.</li><li>Identifiera viktiga Workspace-projekt och förstå vilka datavyer dessa projekt refererar till i sina paneler.</li><li>Identifiera integreringar med verktyg som använder BI-tillägget och förstå vilka datavyer dessa integreringar är beroende av.</li></ul> |
