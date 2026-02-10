---
title: Standardkomponentreferens
description: Lär dig mer om detaljer och information om alla standardkomponenter som du kan lägga till i en datavy.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 1%

---

# Standard, komponentreferens

De flesta dimensioner och mätvärden i Customer Journey Analytics baseras på schemaelement från Adobe Experience Platform datamängd. Det finns dock flera komponenter som kan läggas till i en datavy, oavsett vilken anslutning du använder.

[!UICONTROL Standard components] är komponenter som inte genereras från schemafält för datauppsättningar, men som i stället genereras av systemet. Vissa systemkomponenter krävs för att underlätta rapporteringen i Analysis Workspace, medan andra systemkomponenter är valfria.

![Standardkomponenter](assets/dataview-standard-components.png)

## Nödvändiga standardkomponenter {#required}

Dessa nödvändiga standardkomponenter läggs som standard till i varje datavy. De är viktiga för de rapporteringsfunktioner som Customer Journey Analytics erbjuder.

### Standarddimensioner

{{standard-dimensions}}


### Standardmått

{{standard-metrics}}


## Valfria standardkomponenter {#optional}

Valfria standardkomponenter finns under **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > fliken **[!UICONTROL Components]** > fliken **[!UICONTROL Standard Components]**.

| Komponentnamn | Dimension eller Metrisk | Anteckningar och värden |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Tidsdelningsdimension | FM eller EM |
| [!UICONTROL Batch ID] | Dimension | Identifierare för den Experience Platform-batch som en [!UICONTROL Event] ingick i. |
| [!UICONTROL Dataset ID] | Dimension | Identifierare för Experience Platform-datauppsättningen som en [!UICONTROL Event] var en del av. |
| [!UICONTROL Day of Month] | Tidsdelningsdimension | 1-31 |
| [!UICONTROL Day of Week] | Tidsdelningsdimension | Måndag, tisdag, onsdag, torsdag, fredag, lördag, söndag |
| [!UICONTROL Day of Year] | Tidsdelningsdimension | 1-366 |
| [!UICONTROL Hour of Day] | Tidsdelningsdimension | 0-23 |
| [!UICONTROL  Month of Year] | Tidsdelningsdimension | Januari-december |
| [!UICONTROL First-time Sessions] | Mått | En persons definierade första session i rapportfönstret. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Return Sessions] | Mått | Antalet sessioner som inte var en persons första session. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Person ID] | Dimension | Varje datamängdsschema som definieras i Experience Platform kan ha en egen uppsättning av en eller flera identiteter som är definierade och associerade med ett identitetsnamnområde. Alla dessa identiteter kan användas som person-ID. Exempel är cookie-ID, Stitched ID, User ID, Tracking Code och så vidare. Dimensionen [!UICONTROL Person ID] är grunden för att kombinera datauppsättningar och identifiera unika personer i Customer Journey Analytics.<p>Möjliga användningsområden:<ul><li>Skapa ett segment för ett specifikt person-ID-värde för att segmentera allt ända ner till användarens beteende.</li><li>Felsökning: Kontrollera att det finns data för ett specifikt cookie-ID (eller ett specifikt kund-ID).</li><li>Identifiera de användare som ringde in till ett callcenter.</li></ul> |
| [!UICONTROL Person ID namespace] | Dimension | Vilken typ av ID som [!UICONTROL Person ID] består av. Exempel: `email address`, `cookie ID`, `Analytics ID` |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Global Account ID] | Dimension | [!UICONTROL Global Account ID] när du använder behållaren för globalt konto i anslutningen. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Account ID] | Dimension | [!UICONTROL Account ID] när du använder kontobehållaren i anslutningen. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Opportunity ID] | Dimension | [!UICONTROL Opportunity ID] när du använder säljprojektsbehållaren i anslutningen. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Buying Group ID] | Dimension | [!UICONTROL Buying Group ID] när du använder Buying group-behållaren i anslutningen. |
| [!UICONTROL Quarter of Year] | Tidsdelningsdimension | Q1, Q2, Q3, Q4 |
| [!UICONTROL Repeat session] | Mått | Antalet sessioner som inte var en persons första session någonsin. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Session Type] | Dimension | Dimensionen har två värden: 1. [!UICONTROL First-Time] och 2. Returnerar. Radobjektet [!UICONTROL First-time] innehåller allt beteende (mått mot den här dimensionen) från en session som har fastställts vara en persons definierade första session. Allt annat ingår i radobjektet [!UICONTROL Returning] (förutsatt att allt tillhör en session). Om mätvärden inte är en del av en session, hamnar de i&quot;Inte tillämpligt&quot;-haken för den här dimensionen. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Time Spent per Event] | Dimension | Buknar måttet [!UICONTROL Time Spent] i [!UICONTROL Event] bucket. |
| [!UICONTROL Time Spent per Session] | Dimension | Buknar måttet [!UICONTROL Time Spent] i [!UICONTROL Session] bucket. |
| [!UICONTROL Time Spent per Person] | Dimension | Buknar måttet [!UICONTROL Time Spent] i [!UICONTROL Person] bucket. |
| [!UICONTROL Weekend]/[!UICONTROL Weekday] | Tidsdelningsdimension | Veckoslut eller veckodag |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Identifiera djupare kundinsikter med händelsedjupsfunktionen](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576)
>