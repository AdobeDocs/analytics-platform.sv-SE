---
title: Standard, komponentreferens
description: Information och information om alla standardkomponenter som du kan lägga till i en datavy.
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---


# Standard, komponentreferens

De flesta dimensioner och mått i CJA baseras på schemaelement från din Adobe Experience Platform-datauppsättning. Det finns dock flera komponenter som kan läggas till i en datavy, oavsett vilken anslutning du använder.

[!UICONTROL Standard components] är komponenter som inte genereras från schemafält för datauppsättningar, utan i stället genereras av systemet. Vissa systemkomponenter krävs för att underlätta rapporteringen i Analysis Workspace, medan andra systemkomponenter är valfria.

![Standardkomponenter](assets/standard-components.png)

## Nödvändiga standardkomponenter

Dessa nödvändiga standardkomponenter läggs som standard till i varje datavy. De är nödvändiga för de rapporteringsfunktioner som Customer Journey Analytics erbjuder.

| Komponentnamn | Dimension eller mått | Anteckningar |
| --- | --- | --- |
| [!UICONTROL People] | Mått | Baserat på det person-ID som anges i en [!UICONTROL Connection]. |
| [!UICONTROL Sessions] | Mått | Baserat på sessionsinställningarna i datavyn. |
| [!UICONTROL Events] | Mått | Antalet rader från alla händelsedatamängder i en [!UICONTROL Connection]. |
| [!UICONTROL Minute] | Dimension | Den minut som en viss händelse inträffade (avrundad nedåt). Den första dimensionsposten är den första minuten i datumintervallet och den sista dimensionsposten är den sista minuten i datumintervallet. |
| [!UICONTROL Hour] | Dimension | Den timme då en viss händelse inträffade (avrundad nedåt). Den första dimensionsartikeln är den första timmen i datumintervallet, och den sista dimensionsartikeln är den sista timmen i datumintervallet. |
| [!UICONTROL Day] | Dimension | Dagen då en viss händelse inträffade. Den första dimensionsartikeln är den första dagen i datumintervallet och den sista dimensionsuppgiften är den sista dagen i datumintervallet. |
| [!UICONTROL Week] | Dimension | Veckan då en viss händelse inträffade. Den första dimensionsuppgiften är den första veckan i datumintervallet och den sista dimensionsuppgiften är den sista veckan i datumintervallet. |
| [!UICONTROL Month] | Dimension | Den månad då en viss händelse inträffade. Den första dimensionsuppgiften är den första månaden i datumintervallet och den sista dimensionsuppgiften är den sista månaden i datumintervallet. |
| [!UICONTROL Quarter] | Dimension | Det kvartal som en viss händelse inträffade. Den första dimensionsuppgiften är det första kvartalet i datumintervallet och den sista dimensionsuppgiften är det sista kvartalet i datumintervallet. |
| [!UICONTROL Year] | Dimension | Det år då en viss händelse inträffade. Den första dimensionsuppgiften är det första året i datumintervallet och den sista dimensionsuppgiften är det senaste året i datumintervallet. |

## Valfria standardkomponenter

Valfria standardkomponenter finns under **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > fliken **[!UICONTROL Components]** > fliken **[!UICONTROL Standard Components]**.

| Komponentnamn | Dimension eller mått | Anteckningar |
| --- | --- | --- |
| [!UICONTROL Session Starts] | Mått | Antalet händelser som var den första händelsen i en session. Vid användning i en filterdefinition (t.ex. [!UICONTROL Session Starts] existerar&#39;), filtreras ned till den första händelsen i varje session. |
| [!UICONTROL Session Ends] | Mått | Antalet händelser som var den sista händelsen i en session. På liknande sätt som [!UICONTROL Session Starts] kan den även användas i en filterdefinition för att filtrera ned saker till den sista händelsen i varje session. |
| [!UICONTROL Time Spent (seconds)] | Mått | Sammanställer tiden mellan två olika värden för en dimension. |
| [!UICONTROL Time Spent per Event] | Dimension | Sparar [!UICONTROL Time Spent]-måttet i [!UICONTROL Event]-bucket. |
| [!UICONTROL Time Spent per Session] | Dimension | Sparar [!UICONTROL Time Spent]-måttet i [!UICONTROL Session]-bucket. |
| [!UICONTROL Time Spent per Person] | Dimension | Sparar [!UICONTROL Time Spent]-måttet i [!UICONTROL Person]-bucket. |
| [!UICONTROL Batch ID] | Dimension | Representerar den Experience Platform-batch som en [!UICONTROL Event] var en del av. |
| [!UICONTROL Dataset ID] | Dimension | Representerar datauppsättningen Experience Platform som en [!UICONTROL Event] var en del av. |
