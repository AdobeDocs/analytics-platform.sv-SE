---
description: Använd snabbfilter i Analysis Workspace för Customer Journey Analytics
title: Snabbfilter
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 0%

---

# Snabbfilter

Du kan skapa snabbfilter i ett projekt för att slippa komplexiteten i den fullständiga [Filter Builder](/help/components/filters/create-filters.md). Snabbfilter

* Använd som [filter endast för projekt](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html#project-only).
* Tillåt upp till tre regler
* Innesluta inte kapslade behållare eller sekventiella regler.

En jämförelse mellan vad snabbfilter kan göra och fullständiga filter för komponentlistor finns på [här](/help/components/filters/filters-overview.md).

Här är en video om snabbfilter (observera att termen&quot;snabbsegment&quot; används i stället). Funktionen är dock densamma.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Förutsättningar {#prereqs}

Vem som helst kan skapa ett snabbfilter. Du måste dock ha behörigheten Skapa filter i [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) för att kunna spara ett snabbfilter eller öppna det i Filter Builder.

## Skapa snabbfilter {#create}

I en friformstabell klickar du på ikonen filter+ i panelhuvudet:

![Segmentfilter](assets/quick-seg1.png)

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Name] | Standardnamnet för ett filter är en kombination av regelnamnen i filtret. Du kan byta namn på filtret till ett mer eget namn. |
| [!UICONTROL Include/exclude] | Du kan antingen inkludera eller exkludera komponenter i filterdefinitionen, men inte båda. |
| [!UICONTROL Hit/Visit/Visitor] container | Snabbfilter innehåller ett [filterbehållare](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers) bara det som gör att du kan inkludera ett mått/mått/datumintervall i (eller exkludera det från) filtret. [!UICONTROL Visitor] innehåller översiktsdata som är specifika för besökaren vid besök och sidvisningar. A [!UICONTROL Visit] kan du ange regler för att dela upp besökarens data baserat på besök och en [!UICONTROL Hit] kan du dela upp besökarinformation baserat på enskilda sidvyer. Standardbehållaren är [!UICONTROL Hit]. |
| [!UICONTROL Components] (Dimension/mått/datumintervall) | Definiera upp till tre regler genom att lägga till komponenter (dimensioner, mått, datumintervall eller dimensionsvärden). Det finns tre sätt att hitta rätt komponent:<ul><li>Börja skriva och [!UICONTROL Quick Filter] builder hittar automatiskt rätt komponent.</li><li>Använd listrutan för att hitta komponenten.</li><li>Dra och släpp komponenter från den vänstra listen.</li></ul> |
| [!UICONTROL Operator] | Använd listrutan för att hitta standardoperatorer och [!UICONTROL Distinct Count] operatorer. Se [Filteroperatorer](operators.md). |
| Plustecken (+) | Lägg till en annan regel |
| OCH/ELLER-kvalificerare | Du kan lägga till&quot;AND&quot;- eller&quot;OR&quot;-kvalificerare i reglerna, men du kan inte blanda&quot;AND&quot; och&quot;OR&quot; i en enda filterdefinition. |
| [!UICONTROL Apply] | Använd det här filtret på panelen. Om filtret inte innehåller några data tillfrågas du om du vill fortsätta. |
| [!UICONTROL Open builder] | Öppnar Filter Builder. När du har sparat eller använt filtret i Filter Builder betraktas det inte längre som ett snabbfilter. Den blir en del av komponentlistens filterbibliotek. |
| [!UICONTROL Cancel] | Avbryt det här snabbfiltret - använd det inte. |
| [!UICONTROL Date range] | Valideraren använder panelens datumintervall för sin datasökning. Alla datumintervall som används i ett snabbfilter åsidosätter panelens datumintervall högst upp på panelen. |
| Förhandsgranska (överst till höger) | Här kan du se om du har ett giltigt filter och hur brett filtret är. Representerar den uppdelning av datauppsättningen som du kan förvänta dig att se när du använder det här filtret. Du kan få ett meddelande som anger att det här filtret saknar data. I så fall kan du fortsätta eller ändra filterdefinitionen. |

Här är ett exempel på ett filter som kombinerar mått och mätvärden:

![Exempel på filterdefinition](assets/quick-seg2.png)

Filtret visas högst upp. Lägg märke till dess blå, randiga sidospalt, till skillnad från den blå sidopanelen för filter på komponentnivå i filterbiblioteket till vänster.

![Filtrera komponentplatser](assets/quick-seg3.png)

## Redigera snabbfilter {#edit}

1. Håll pekaren över snabbfiltret och välj pennikonen.
1. Redigera filterdefinitionen eller filternamnet.
1. Klicka på [!UICONTROL Apply].

## Spara snabbfilter {#save}

Du kan välja att spara snabbfilter i [!UICONTROL Quick Filter Builder] eller i [!UICONTROL Filter Builder].

>[!IMPORTANT]
>När du har sparat eller använt filtret kan du inte längre redigera det i snabbfilterverktyget, utan bara i den vanliga filterverktyget.

### Spara i snabbfilterverktyget {#save2}

1. När du har använt snabbfiltret håller du pekaren över det och väljer ikonen för info (&quot;i&quot;).
1. Klicka på **[!UICONTROL Make available to all projects and add to your component list]**.
1. (Valfritt) Byt namn på filtret.
1. Klicka på **[!UICONTROL Save]**.

Lägg märke till hur filtrets sidlist ändras från randig blå till ljusblå. Den visas nu i komponentlistan i den vänstra listen.

### Spara i filterverktyget {#save3}

1. Håll pekaren över snabbfiltret och välj ikonen för info (&quot;i&quot;).
1. Välj **[!UICONTROL Save filter]**
1. Låt namnet vara som det är eller byt namn på filtret.

   Gå tillbaka till arbetsytan och se hur filtret nu har en ljusblå sidospalt. Det innebär att den inte längre kan redigeras/öppnas i snabbfilterverktyget. Och genom att spara det blir det en del av komponentlistan.

   ![Filtrera komponentlista](assets/quick-seg4.png)

När du har tillämpat filtret kan du lägga till det i filterkomponentlistan och göra det tillgängligt för alla projekt.

1. Håll pekaren över det sparade filtret och välj pennikonen.

1. Lägg märke till den här dialogrutan längst upp i Filter Builder:

   ![Dialogrutan Filter](assets/project-only.png)

1. Markera kryssrutan bredvid **[!UICONTROL Make available to all your projects and add to your component list.]**
1. Klicka på **[!UICONTROL Save]**.
1. Filtret visas nu i filterkomponentlistan för alla dina projekt.
1. Du kan också [dela filtret](/help/components/filters/manage-filters.md) med andra i organisationen.

## Vad är filter som endast är projektbaserade? {#project-only}

Endast projektfilter är filter som bara gäller för det aktuella projektet som de skapades i. De är inte tillgängliga i andra projekt och kan inte delas med andra användare. De är avsedda för att snabbt kunna utforska dina data utan att du behöver skapa och spara ett filter i den vänstra listen. Du kan skapa filter som bara innehåller projekt i panelens släppzon med snabbfilter eller [ad hoc-filter](/help/components/filters/ad-hoc-filters.md).

Om du öppnar ett projektfilter i [!UICONTROL Filter Builder]visas ett meddelande om att projektet bara är öppet. Om du inte markerar &quot;Gör det här filtret tillgängligt..&quot; och klicka **[!UICONTROL APPLY]** förblir segmentet ett projektbaserat filter.

>[!NOTE]
>
>Om du använder ett snabbfilter från filterverktyget kan det inte längre öppnas i [!UICONTROL Quick Filter Builder].

![Endast projektet är omarkerat](assets/project-only-unchecked.png)

Om du markerar &quot;Gör det här filtret tillgängligt..&quot; och klicka **[!UICONTROL SAVE]** blir filtret tillgängligt i den vänstra listan över komponenter i rälsen för användning i andra projekt. Den kan också delas med andra användare från Filterhanteraren.

![Endast projektet är markerat](assets/project-only-checked.png)

