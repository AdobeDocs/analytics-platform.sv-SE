---
description: Använd snabbfilter i Analysis Workspace för Customer Journey Analytics
title: Snabbfilter
feature: Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: a8e1913fb22414610214f5c0a03f6ef7f3b4f8f0
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 1%

---

# Snabbfilter

Du kan skapa snabbfilter i ett projekt för att kringgå komplexiteten i den fullständiga [filterverktyget](/help/components/filters/create-filters.md). Snabbfilter

* Gäller endast projekt i vilka de har skapats (du kan ändra detta).
* Tillåt upp till tre regler
* Innesluta inte kapslade behållare eller sekventiella regler.
* Arbeta i projekt med flera rapportsviter

En jämförelse av vad snabbfilter kan göra jämfört med fullständiga filter för komponentlistor finns [här](/help/components/filters/filters-overview.md).

>[!IMPORTANT]
> Snabbfilter testas för närvarande i begränsad omfattning och är ännu inte tillgängliga i allmänhet.

## Förutsättningar

Vem som helst kan skapa ett snabbsegment. Du måste dock ha behörighet att skapa segment i [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) för att kunna spara ett snabbsegment eller öppna det i Segment Builder.

## Skapa snabbfilter

I en friformstabell klickar du på ikonen filter+ i panelhuvudet:

![](assets/quick-seg1.png)

| Inställning | Beskrivning |
| --- | --- |
| Namn | Standardnamnet för ett filter är en kombination av regelnamnen i filtret. Du kan byta namn på filtret till ett mer eget namn. |
| Inkludera/exkludera | Du kan antingen inkludera eller exkludera komponenter i filterdefinitionen, men inte båda. |
| Behållare för träff/besök/besök | Snabbfilter innehåller bara en [filterbehållare](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) som gör att du kan inkludera ett mått-/mätvärde-/datumintervall i (eller exkludera det från) filtret. [!UICONTROL Visitor] innehåller översiktsdata som är specifika för besökaren vid besök och sidvisningar. Med en [!UICONTROL Visit]-behållare kan du ange regler för att dela upp besökarens data baserat på besök, och med en [!UICONTROL Hit]-behållare kan du dela upp besökarinformation baserat på enskilda sidvyer. Standardbehållaren är [!UICONTROL Hit]. |
| Komponenter (Dimension/mått/datumintervall) | Definiera upp till tre regler genom att lägga till komponenter (mått och/eller mått och/eller datumintervall) och deras värden. Det finns tre sätt att hitta rätt komponent:<ul><li>Börja skriva så hittar verktyget [!UICONTROL Quick Filter] automatiskt rätt komponent.</li><li>Använd listrutan för att hitta komponenten.</li><li>Dra och släpp komponenter från den vänstra listen.</li></ul> |
| Operator | Använd listrutan för att hitta standardoperatorer och [!UICONTROL Distinct Count]-operatorer. [Läs mer](https://experienceleague.adobe.com/docs/analytics/components/filteration/segment-reference/seg-operators.html?lang=en) |
| Plustecken (+) | Lägg till en annan regel |
| OCH/ELLER-kvalificerare | Du kan lägga till&quot;AND&quot;- eller&quot;OR&quot;-kvalificerare i reglerna, men du kan inte blanda&quot;AND&quot; och&quot;OR&quot; i en enda filterdefinition. |
| Använd | Använd det här filtret på panelen. Om filtret inte innehåller några data tillfrågas du om du vill fortsätta. |
| Open Builder | Öppnar Filter Builder. När du har sparat eller använt filtret i Filter Builder betraktas det inte längre som ett snabbfilter. Den blir en del av komponentlistens filterbibliotek. |
| Avbryt | Avbryt det här snabbfiltret - använd det inte. |
| Datumintervall | Valideraren använder panelens datumintervall för sin datasökning. Alla datumintervall som används i ett snabbfilter åsidosätter panelens datumintervall högst upp på panelen. |
| Förhandsgranska (överst till höger) | Här kan du se om du har ett giltigt filter och hur brett filtret är. Representerar den uppdelning av datauppsättningen som du kan förvänta dig att se när du använder det här filtret. Du kan få ett meddelande som anger att det här filtret saknar data. I så fall kan du fortsätta eller ändra filterdefinitionen. |

Här är ett exempel på ett filter som kombinerar mått och mätvärden:

![](assets/quick-seg2.png)

Filtret visas högst upp. Lägg märke till dess blå, randiga sidospalt, till skillnad från den blå sidopanelen för filter på komponentnivå i filterbiblioteket till vänster.

![](assets/quick-seg3.png)

## Redigera snabbfilter

1. Håll pekaren över snabbfiltret och välj pennikonen.
1. Redigera filterdefinitionen eller filternamnet.

## Spara snabbfilter

Du kan välja att spara snabbfilter antingen i [!UICONTROL Quick Filter Builder] eller i [!UICONTROL Filter Builder].

>[!IMPORTANT]
>När du har sparat eller använt filtret kan du inte längre redigera det i snabbfilterverktyget, utan bara i den vanliga filterverktyget.

### Spara i snabbfilterverktyget

1. När du har använt snabbfiltret håller du pekaren över det och väljer ikonen för info (&quot;i&quot;).
1. Klicka på **[!UICONTROL Make available to all projects and add to your component list]**.
1. (Valfritt) Byt namn på filtret.
1. Klicka på **[!UICONTROL Save]**.

Lägg märke till hur filtrets sidlist ändras från randig blå till ljusblå. Den visas nu i komponentlistan i den vänstra listen.

### Spara i filterverktyget

1. Håll pekaren över snabbfiltret och välj ikonen för info (&quot;i&quot;).
1. Välj **[!UICONTROL Save filter]**
1. Låt namnet vara som det är eller byt namn på filtret.

   Gå tillbaka till arbetsytan och se hur filtret nu har en ljusblå sidospalt. Det innebär att den inte längre kan redigeras/öppnas i snabbfilterverktyget. Och genom att spara det blir det en del av komponentlistan.

   ![](assets/quick-seg4.png)

När du har tillämpat filtret kan du lägga till det i filterkomponentlistan och göra det tillgängligt för alla projekt.

1. Håll pekaren över det sparade filtret och välj pennikonen.

1. Lägg märke till den här dialogrutan längst upp i Filter Builder:

   ![](assets/project-only.png)

1. Markera kryssrutan bredvid **[!UICONTROL Make available to all your projects and add to your component list.]**
1. Klicka på **[!UICONTROL Save]**.
1. Filtret visas nu i filterkomponentlistan för alla dina projekt.
1. Du kan även [dela filtret](/help/components/filters/manage-filters.md) med andra personer i organisationen.

## Vad är filter som endast är projektbaserade?

Endast projektfilter är antingen snabbfilter eller ad hoc-projektfilter för arbetsytan. När du redigerar/öppnar dem i [!UICONTROL Filter Builder] visas rutan för endast projekt.

Om du använder ett snabbfilter i byggaren men inte markerar kryssrutan &quot;Gör tillgänglig&quot; är det fortfarande ett projektfilter, men det kan inte längre öppnas i [!UICONTROL Quick Filter Builder]. Om du markerar rutan och klickar på **[!UICONTROL Save]** är det nu ett komponentlistfilter.
