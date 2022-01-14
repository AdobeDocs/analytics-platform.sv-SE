---
title: Standard, komponentreferens
description: Information och information om alla standardkomponenter som du kan lägga till i en datavy.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
source-git-commit: b4d2c564f9fc477212306dc022b4afc5ab92db97
workflow-type: tm+mt
source-wordcount: '634'
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

Valfria standardkomponenter finns under **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > **[!UICONTROL Components]** tab > **[!UICONTROL Standard Components]** -fliken.

| Komponentnamn | Dimension eller mått | Anteckningar och värden |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Tidsdelningsdimension | FM eller EM |
| [!UICONTROL Batch ID] | Dimension | Representerar Experience Platform-batchen som en [!UICONTROL Event] var en del av. |
| [!UICONTROL Dataset ID] | Dimension | Representerar datauppsättningen Experience Platform som [!UICONTROL Event] var en del av. |
| [!UICONTROL Day of Month] | Tidsdelningsdimension | 1-31 |
| [!UICONTROL Day of Week] | Tidsdelningsdimension | Måndag, tisdag, onsdag, torsdag, fredag, lördag, söndag |
| [!UICONTROL Day of Year] | Tidsdelningsdimension | 1-366 |
| [!UICONTROL Hour of Day] | Tidsdelningsdimension | 0-23 |
| [!UICONTROL  Month of Year] | Tidsdelningsdimension | Januari-december |
| [!UICONTROL Person ID] | Dimension | Varje datamängdsschema som definieras i Experience Platform kan ha en egen uppsättning av en eller flera identiteter som är definierade och associerade med ett identitetsnamnutrymme. Alla dessa kan användas som person-ID. Exempel är cookie-ID, Stitched ID, User ID, Tracking Code osv. The [!UICONTROL Person ID] är grunden för att kombinera datauppsättningar och identifiera unika besökare i CJA. |
| [!UICONTROL Person ID namespace] | Dimension | Vilken typ av ID [!UICONTROL Person ID] består av. Exempel: `email address`, `cookie ID`, `Analytics ID`, osv. |
| [!UICONTROL Quarter of Year] | Tidsdelningsdimension | Q1, Q2, Q3, Q4 |
| [!UICONTROL Session Starts] | Mått | Antalet händelser som var den första händelsen i en session. Vid användning i en filterdefinition (t.ex. &#39;[!UICONTROL Session Starts] finns&#39;), filtreras ned till den första händelsen i varje session. |
| [!UICONTROL Session Ends] | Mått | Antalet händelser som var den sista händelsen i en session. Liknar [!UICONTROL Session Starts]kan den också användas i en filterdefinition för att filtrera fram till den sista händelsen i varje session. |
| [!UICONTROL Time Spent (seconds)] | Mått | Sammanställer tiden mellan två olika värden för en dimension. |
| [!UICONTROL Time Spent per Event] | Dimension | Bucklar [!UICONTROL Time Spent] mätvärden in [!UICONTROL Event] fickor. |
| [!UICONTROL Time Spent per Session] | Dimension | Bucklar [!UICONTROL Time Spent] mätvärden in [!UICONTROL Session] fickor. |
| [!UICONTROL Time Spent per Person] | Dimension | Bucklar [!UICONTROL Time Spent] mätvärden in [!UICONTROL Person] fickor. |
| [!UICONTROL Weekend]/[!UICONTROL Weekday] | Tidsdelningsdimension | Veckoslut eller Veckodag |
