---
description: Adobe tillhandahåller olika beräknade värden som du kan använda. På den här sidan visas dessa mått och deras avsedda användning.
title: Standardberäknade värden
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a507417c945f827ebb8bc92f7b5f54a9c4e6faa0
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---

# Standardberäknade värden

Customer Journey Analytics tillhandahåller följande beräknade standardvärden som täcker de vanligaste användningsfallen. Dessa Adobe-definierade beräknade standardvärden identifieras av en liten ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) -logotyp. Om du snabbt vill filtrera efter dessa mått väljer du ![Etikett](/help/assets/icons/Label.svg) **[!UICONTROL Adobe Template]** i [komponentfiltret](/help/components/overview.md#filter).

| Namn på beräknat mätvärde | Beskrivning<br/>Formel |
|---------|----------|
| **[!UICONTROL Session Start Rate]** | Procentvärdet för att någon dimensionsobjekt inträffade vid den första händelsen i en session.<p>Det här beräknade måttet läggs automatiskt till i Workspace när du inkluderar [!UICONTROL Session Starts] [standardkomponenten](/help/data-views/component-reference.md) i [datavyn](/help/data-views/create-dataview.md).</p>Sammanfattning: **(** ![Event](/help/assets/icons/Event.svg) **Sessionen startar** ![Dela](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sessioner** **)** |
| **[!UICONTROL Time Spent Per Person]** | Den genomsnittliga tiden en person tillbringat på en given dimensionspost.<p>Det här beräknade måttet läggs automatiskt till i Workspace när du inkluderar [!UICONTROL Time Spent (seconds)] [standardkomponenten](/help/data-views/component-reference.md) i [datavyn](/help/data-views/create-dataview.md). Filtret Uteslut sista händelsen i sessionen används för personmåttet. Filtret exkluderar den sista händelsen i varje session i en datauppsättning. Det här undantaget kan hjälpa dig att analysera användarbeteende som leder fram till en händelse eller åtgärd, som ett köp eller en inskickning av formulär, och samtidigt utesluta den slutliga åtgärden.</p>Sammanfattning: **(** ![Event](/help/assets/icons/Event.svg) **Tid (sekunder)** ![Dela](/help/assets/icons/Divide.svg) ![Segmentering](/help/assets/icons/Segmentation.svg) **Uteslut senaste händelse för session(** ![Event](/help/assets/icons/Event.svg) **Personer )** |
| **[!UICONTROL Sessions Per Person]** | Genomsnittligt antal sessioner per person.<p>Sammanfattning: **(** ![Event](/help/assets/icons/Event.svg) **Sessioner** ![Dela](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Personer** **)** |
| **[!UICONTROL Time Spent Per Session]** | Den genomsnittliga tiden en person tillbringat per session för ett givet dimensionsobjekt.<p>Det här beräknade måttet läggs automatiskt till i Workspace när du inkluderar [!UICONTROL Time Spent (seconds)] [standardkomponenten](/help/data-views/component-reference.md) i [datavyn](/help/data-views/create-dataview.md). Filtret Uteslut senaste sessionshändelse används i sessionsmätningen. Filtret exkluderar den sista händelsen i varje session i en datauppsättning. Det här undantaget kan hjälpa dig att analysera användarbeteende som leder fram till en händelse eller åtgärd, som ett köp eller en inskickning av formulär, och samtidigt utesluta den slutliga åtgärden.</p>Sammanfattning: **(** ![Händelse](/help/assets/icons/Event.svg) **Tid (sekunder)** ![Dela](/help/assets/icons/Divide.svg) ![Segmentering](/help/assets/icons/Segmentation.svg) **Uteslut senaste händelse för session(** ![Händelse](/help/assets/icons/Event.svg) **sessioner )** |
| **[!UICONTROL Session End Rate]** | Procentvärdet för att ett dimensionsobjekt inträffade vid den senaste händelsen i en session. <p>Det här beräknade måttet läggs automatiskt till i Workspace när du inkluderar [!UICONTROL Session Ends] [standardkomponenten](/help/data-views/component-reference.md) i [datavyn](/help/data-views/create-dataview.md).</p>Sammanfattning: **(** ![Event](/help/assets/icons/Event.svg) **Sessionen avslutas** ![Dela](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sessioner** **)** |

{style="table-layout:auto"}
