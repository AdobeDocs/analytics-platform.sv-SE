---
description: Adobe tillhandahåller olika beräknade mätvärden som du kan använda. På den här sidan visas dessa mått och deras avsedda användning.
title: Mallar för beräknade mätvärden
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Mallar för beräknade mätvärden

Customer Journey Analytics tillhandahåller följande mallar för beräknade värden som täcker de vanligaste användningsområdena. Dessa Adobe-definierade beräknade värden identifieras med en liten ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) -logotyp. Om du snabbt vill filtrera måtten väljer du ![Etikett](/help/assets/icons/Label.svg) **[!UICONTROL Adobe Template]** i [komponentfiltret](/help/components/overview.md#filter).

| Namn på beräknat mätvärde | Beskrivning<br/>Formel |
|---------|----------|
| **[!UICONTROL Session start rate]** | Procentvärdet för att någon dimensionsobjekt inträffade vid den första händelsen i en session.<p>Det här beräknade måttet läggs automatiskt till i Workspace när du inkluderar [!UICONTROL Session Starts] [standardkomponenten](/help/data-views/component-reference.md) i [datavyn](/help/data-views/create-dataview.md).</p>Sammanfattning: **(** ![Event](/help/assets/icons/Event.svg) **Sessionen startar** ![Dela](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sessioner** **)** |
| **[!UICONTROL Time spent per person]** | Den genomsnittliga tiden en person tillbringat på en given dimensionspost.<p>Det här beräknade måttet läggs automatiskt till i Workspace när du inkluderar [!UICONTROL Time Spent (seconds)] [standardkomponenten](/help/data-views/component-reference.md) i [datavyn](/help/data-views/create-dataview.md). Segmentet Uteslut senaste sessionshändelse används för personmåttet. Segmentet exkluderar den sista händelsen i varje session i en datauppsättning. Det här undantaget kan hjälpa dig att analysera användarbeteende som leder fram till en händelse eller åtgärd, som ett köp eller en inskickning av formulär, och samtidigt utesluta den slutliga åtgärden.</p>Sammanfattning: **(** ![Händelse](/help/assets/icons/Event.svg) **Tid (sekunder)** ![Dela](/help/assets/icons/Divide.svg) ![Segmentering](/help/assets/icons/Segmentation.svg) **Uteslut senaste händelse för session(** ![Händelse](/help/assets/icons/Event.svg) **Personer )** |
| **[!UICONTROL Sessions per person]** | Genomsnittligt antal sessioner per person.<p>Sammanfattning: **(** ![Event](/help/assets/icons/Event.svg) **Sessioner** ![Dela](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Personer** **)** |
| **[!UICONTROL Time spent per session]** | Den genomsnittliga tiden en person tillbringat per session för ett givet dimensionsobjekt.<p>Det här beräknade måttet läggs automatiskt till i Workspace när du inkluderar [!UICONTROL Time Spent (seconds)] [standardkomponenten](/help/data-views/component-reference.md) i [datavyn](/help/data-views/create-dataview.md). Segmentet Uteslut senaste sessionshändelse används i sessionsmätningen. Segmentet exkluderar den sista händelsen i varje session i en datauppsättning. Det här undantaget kan hjälpa dig att analysera användarbeteende som leder fram till en händelse eller åtgärd, som ett köp eller en inskickning av formulär, och samtidigt utesluta den slutliga åtgärden.</p>Sammanfattning: **(** ![Händelse](/help/assets/icons/Event.svg) **Tid (sekunder)** ![Dela](/help/assets/icons/Divide.svg) ![Segmentering](/help/assets/icons/Segmentation.svg) **Uteslut senaste händelse för session(** ![Händelse](/help/assets/icons/Event.svg) **sessioner )** |
| **[!UICONTROL Session end rate]** | Procentvärdet för att ett dimensionsobjekt inträffade vid den senaste händelsen i en session. <p>Det här beräknade måttet läggs automatiskt till i Workspace när du inkluderar [!UICONTROL Session Ends] [standardkomponenten](/help/data-views/component-reference.md) i [datavyn](/help/data-views/create-dataview.md).</p>Sammanfattning: **(** ![Event](/help/assets/icons/Event.svg) **Sessionen avslutas** ![Dela](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sessioner** **)** |
| **[!UICONTROL Web sessions]** | Antalet sessioner som har inträffat på webbplatsen. |
| **[!UICONTROL Survey completion rate]** | Frekvensen med vilken personer slutförde en undersökning efter att den startats. |
| **[!UICONTROL Multi-channel session rate]** | Förhållandet mellan sessioner som innehöll flera kanaler (till exempel webbtrafik och mobiltrafik), jämfört med sessioner som bara innehöll en enda kanal. |
| **[!UICONTROL Multi-channel person rate]** | Andelen personer som har deltagit i flera kanaler, jämfört med dem som bara har deltagit i en enda kanal. |
| **[!UICONTROL Mobile app sessions]** | Antalet sessioner som har inträffat i mobilappen. |
| **[!UICONTROL Web+app cross-channel sessions]** | Antalet sessioner som inkluderade både webbtrafik och mobiltrafik. |
| **[!UICONTROL Cost of calls]** | Den totala kostnaden för kundtjänstsamtal. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Average call duration]** | Genomsnittlig varaktighet för anrop till callcentret. |
| **[!UICONTROL Average cost per call]** | Genomsnittskostnaden för samtal till callcentret. |
| **[!UICONTROL Average call survey score]** | Den genomsnittliga enkätpoängen för samtal till callcentret. |

{style="table-layout:auto"}
