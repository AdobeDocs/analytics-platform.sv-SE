---
title: Standard, komponentreferens
description: Information om och information om alla standardkomponenter som du kan lägga till i en datavy.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# Standard, komponentreferens

De flesta dimensioner och mätvärden i Customer Journey Analytics baseras på schemaelement från Adobe Experience Platform datamängd. Det finns dock flera komponenter som kan läggas till i en datavy, oavsett vilken anslutning du använder.

[!UICONTROL Standard components] är komponenter som inte genereras från schemafält för datauppsättningar, utan i stället genereras av systemet. Vissa systemkomponenter krävs för att underlätta rapporteringen i Analysis Workspace, medan andra systemkomponenter är valfria.

![Standardkomponenter](assets/dataview-standard-components.png)

## Nödvändiga standardkomponenter {#required}

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
| [!UICONTROL Quarter] | Dimension | Det kvartal som en viss händelse inträffade. Den första dimensionsuppgiften är det första kvartalet i datumintervallet, och den sista dimensionsuppgiften är det sista kvartalet i datumintervallet. |
| [!UICONTROL Year] | Dimension | Det år då en viss händelse inträffade. Den första dimensionsuppgiften är det första året i datumintervallet och den sista dimensionsuppgiften är det senaste året i datumintervallet. |

{style="table-layout:auto"}

## Valfria standardkomponenter {#optional}

Valfria standardkomponenter är tillgängliga under **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > **[!UICONTROL Components]** tab > **[!UICONTROL Standard Components]** -fliken.

| Komponentnamn | Dimension eller mått | Anteckningar och värden |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Tidsdelningsdimension | FM eller EM |
| [!UICONTROL Batch ID] | Dimension | Representerar Experience Platform-batchen som en [!UICONTROL Event] ingick i. |
| [!UICONTROL Dataset ID] | Dimension | Representerar datauppsättningen Experience Platform som [!UICONTROL Event] ingick i. |
| [!UICONTROL Day of Month] | Tidsdelningsdimension | 1-31 |
| [!UICONTROL Day of Week] | Tidsdelningsdimension | Måndag, tisdag, onsdag, torsdag, fredag, lördag, söndag |
| [!UICONTROL Day of Year] | Tidsdelningsdimension | 1-366 |
| [!UICONTROL Hour of Day] | Tidsdelningsdimension | 0-23 |
| [!UICONTROL  Month of Year] | Tidsdelningsdimension | Januari-december |
| [!UICONTROL First-time Sessions] | Mått | En persons definierade första session i rapportfönstret. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) |
| [!UICONTROL Return Sessions] | Mått | Antalet sessioner som inte var en persons första session. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) |
| [!UICONTROL Person ID] | Dimension | Varje datamängdsschema som definieras i Experience Platform kan ha en egen uppsättning av en eller flera identiteter som är definierade och associerade med ett identitetsnamnutrymme. Alla dessa identiteter kan användas som person-ID. Exempel är cookie-ID, Stitched ID, User ID, Tracking Code och så vidare. The [!UICONTROL Person ID] är grunden för att kombinera datauppsättningar och identifiera unika personer i Customer Journey Analytics.<p>Möjliga användningsområden:<ul><li>Skapa ett filter för ett specifikt person-ID-värde för att filtrera allt efter användarens beteende.</li><li>Felsökning: Kontrollera att det finns data för ett specifikt cookie-ID (eller ett specifikt kund-ID).</li><li>Identifiera de användare som ringde in till ett callcenter.</li></ul> |
| [!UICONTROL Person ID namespace] | Dimension | Vilken typ av ID [!UICONTROL Person ID] består av. Exempel: `email address`, `cookie ID`, `Analytics ID` |
| [!UICONTROL Quarter of Year] | Tidsdelningsdimension | Q1, Q2, Q3, Q4 |
| [!UICONTROL Repeat session] | Mått | Antalet sessioner som inte var en persons första session någonsin. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) |
| [!UICONTROL Session Starts] | Mått | Antalet händelser som var den första händelsen i en session. Vid användning i en filterdefinition (t.ex. &#39;[!UICONTROL Session Starts] finns&#39;), filtreras ned till den första händelsen i varje session.<p>Den här komponenten måste inkluderas i datavyn för följande [beräknat mått](/help/components/calc-metrics/default-calcmetrics.md) som ska vara tillgänglig i Workspace: <ul><li>Starthastighet för session</li></p> |
| [!UICONTROL Session Ends] | Mått | Antalet händelser som var den sista händelsen i en session. Liknar [!UICONTROL Session Starts]kan den också användas i en filterdefinition för att filtrera fram till den sista händelsen i varje session.<p>Den här komponenten måste inkluderas i datavyn för följande [beräknat mått](/help/components/calc-metrics/default-calcmetrics.md) som ska vara tillgänglig i Workspace: <ul><li>Sessionens sluthastighet</li></p> |
| [!UICONTROL Session Type] | Dimension | Dimensionen har två värden: 1) [!UICONTROL First-Time] och 2) Returning. The [!UICONTROL First-time] radartikel innehåller allt beteende (mått mot den här dimensionen) från en session som har fastställts vara en persons definierade första session. Allt annat ingår i [!UICONTROL Returning] radartikel (om allt tillhör en session). Om mätvärden inte är en del av en session, hamnar de i&quot;Inte tillämpligt&quot;-haken för den här dimensionen. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) |
| [!UICONTROL Time Spent (seconds)] | Mått | Sammanställer tiden mellan två olika värden för en dimension.<p>Den här komponenten måste inkluderas i datavyn för följande [beräknade värden](/help/components/calc-metrics/default-calcmetrics.md) som ska vara tillgänglig i Workspace: <ul><li>Tilldelad tid per person</li><li>Tilldelad tid per session</li></p> |
| [!UICONTROL Time Spent per Event] | Dimension | Bucklar [!UICONTROL Time Spent] mätvärden till [!UICONTROL Event] fickor. |
| [!UICONTROL Time Spent per Session] | Dimension | Bucklar [!UICONTROL Time Spent] mätvärden till [!UICONTROL Session] fickor. |
| [!UICONTROL Time Spent per Person] | Dimension | Bucklar [!UICONTROL Time Spent] mätvärden till [!UICONTROL Person] fickor. |
| [!UICONTROL Weekend]/[!UICONTROL Weekday] | Tidsdelningsdimension | Veckoslut eller veckodag |

{style="table-layout:auto"}
