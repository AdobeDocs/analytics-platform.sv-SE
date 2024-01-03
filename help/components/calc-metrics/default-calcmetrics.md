---
description: Adobe tillhandahåller olika beräknade värden som du kan använda. På den här sidan visas dessa mått och deras avsedda användning.
title: Standardberäknade värden
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# Standardberäknade värden

Customer Journey Analytics tillhandahåller följande beräknade mått för att täcka de vanligaste användningsfallen:

| Namn på beräknat mätvärde | Beskrivning | Formel |
|---------|----------|---------|
| Starthastighet för session | Procentvärdet för att någon dimensionsobjekt inträffade vid den första händelsen i en session.<p>Det här beräknade måttet läggs automatiskt till i arbetsytan när du inkluderar `[Session Starts]` [standardkomponent](/help/data-views/component-reference.md) i [datavy](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| Tilldelad tid per person | Den genomsnittliga tiden en person tillbringat på en given dimensionspost.<p>Det här beräknade måttet läggs automatiskt till i arbetsytan när du inkluderar `[Time Spent (seconds)]` [standardkomponent](/help/data-views/component-reference.md) i [datavy](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| Sessioner per person | Genomsnittligt antal sessioner per person. | `[Sessions] / [Users]` |
| Tilldelad tid per session | Den genomsnittliga tiden en person tillbringat per session för ett givet dimensionsobjekt.<p>Det här beräknade måttet läggs automatiskt till i arbetsytan när du inkluderar `[Time Spent (seconds)]` [standardkomponent](/help/data-views/component-reference.md) i [datavy](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| Sessionens sluthastighet | Procentvärdet för att ett dimensionsobjekt inträffade vid den senaste händelsen i en session. <p>Det här beräknade måttet läggs automatiskt till i arbetsytan när du inkluderar `[Session Ends]` [standardkomponent](/help/data-views/component-reference.md) i [datavy](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
