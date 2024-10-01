---
description: Använd snabbfilter i Analysis Workspace för Customer Journey Analytics
title: Snabbfilter
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 0%

---

# Snabbfilter

Med snabbfilter kan du snabbt utforska data i ett Workspace-projekt utan att behöva skapa ett filter i [Filter Builder](/help/components/filters/create-filters.md).


+++ I följande video visas hur du använder snabbfilter.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)


+++

När du vill använda snabbfilter bör du tänka på följande:

* Snabbfilter skapas direkt i ett Workspace-projekt. Det innebär att ett snabbfilter bara gäller för det Workspace-projekt där du skapar snabbfiltret. Snabbfiltren i ditt Workspace-projekt är inte tillgängliga i andra projekt och kan inte delas med andra användare.
* Du kan bara ange tre villkor som en del av ett snabbfilter.
* Snabbfilter stöder inte kapslade behållare eller sekventiella villkor.
* Du kan redigera snabbfilter i ett delat Workspace-projekt. Andra användare kan alltså redigera snabbfiltren i ett Workspace-projekt som du har delat med dessa användare.

## Skapa

Snabbfilter gäller för paneler. Du kan skapa ytterligare ett snabbfilter för alla paneler i Workspace-projektet. Alla användare i Analysis Workspace kan skapa snabbfilter.

Så här skapar du ett snabbfilter:

* Välj ![FilterAdd](/help/assets/icons/FilterAdd.svg) längst upp på panelen. <br/>Redigera sedan filtret direkt i [snabbfilterverktyget](#quick-filter-builder).
* Dra en komponent från komponentpanelen till filtersläppzonen i panelhuvudet. Håll pekaren över filtret när det tagits bort och välj ![Redigera](/help/assets/icons/Edit.svg) för att redigera filtret i [snabbfilterverktyget](#quick-filter-builder).

När du skapar ett snabbfilter med dra och släpp bör du tänka på följande:

* Alla komponenttyper stöds inte. Beräknade mätvärden stöds inte, och endast mått och mätvärden som du kan använda för att skapa filter stöds.
* För mått och måttkomponenter skapar [snabbfilterverktyget](#quick-filter-builder) automatiskt ett `exists` -villkor. Om du till exempel drar och släpper `City` skapas villkoret `City exists`.
* För dimensionsvärden skapar [snabbfilterverktyget](#quick-filter-builder) automatiskt ett `equals`-villkor. Om du till exempel drar och släpper `amsterdam` från dimensionen `City` skapas villkoret `City equals amsterdam`.
* Om du drar och släpper `unspecified` eller `none` skapar [snabbfilterverktyget](#quick-filter-builder) automatiskt ett `does not exist` -villkor.

Snabbfilter som du skapar visas högst upp på panelen. Snabbfilter har ett ljusblått tunt fält till vänster. När ett snabbfilter är i redigeringsläge med hjälp av [snabbfilterverktyget](#quick-filter-builder) är bakgrunden i snabbfiltret ljusblå.

Resultatet av de snabbfilter du skapar på en panel används (med AND-logik) på alla visualiseringar som är en del av panelen.


## Hantera

Håll pekaren över **[!UICONTROL Quick filter]** om du vill hantera ett snabbfilter.

* Välj ![Redigera](/help/assets/icons/Edit.svg) för att öppna [snabbfilterverktyget](#quick-filter-builder) och redigera snabbfiltret.
* Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg) för att öppna ett popup-fönster. I popup-fönstret visas information om filtret. Du kan välja **[!UICONTROL Make available to all projects and add to your component list]** om du vill lägga till filtret i komponentlistan ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** på komponentpanelen. Du ser en **[!UICONTROL Save quick filter]**-dialogruta där du uppmanas att ange ett namn för filtret. Välj **[!UICONTROL Save]** om du vill fortsätta. [!UICONTROL Quick filter] blir en **[!UICONTROL Filter]**. Du kan inte längre redigera filtret med [snabbfilterverktyget](#quick-filter-builder). I stället måste du redigera filtret som ett vanligt filter med hjälp av [filterverktyget](filter-builder.md).

## Snabbfilterverktyg

Nedan finns ett exempel på verktyget Snabbfilter. I exemplet öppnas verktyget för ett snabbfilter med namnet `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Båda snabbfiltren längst upp gäller panelen [!UICONTROL Average Order Value Dashboard] och alla visualiseringar i den, till exempel friformstabellen [!UICONTROL Average Order Value Per Country].

![Snabbfilterverktyg](assets/quick-filter-builder.png)

Snabbfilterverktyget består av följande områden och knappar.

### Sidhuvudsområde

Rubrikområdet bestämmer snabbfiltrets namn, typ och omfattning. Den visar också en visuell information om resultatet av snabbfiltret.

| Element | Beskrivning |
|---|---|
| **[!UICONTROL Name]** | Namnet hämtas automatiskt från snabbfilterdefinitionen. |
| **[!UICONTROL People]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alert](/help/assets/icons/Alert.svg) | Förhandsgranska visuella data från snabbfiltret. En stapel och ett procenttal ger insikt i hur mycket av de totala data som är en del av resultatet av snabbfiltret. En röd ![varning](/help/assets/icons/Alert.svg) signalerar att snabbfiltret inte returnerar data. |
| **[!UICONTROL Include]**<br/>**[!UICONTROL Exclude]** | Välj i listrutan ![SparronDown](/help/assets/icons/ChevronDown.svg) om du vill inkludera eller exkludera resultaten av snabbfiltret från data på panelen. |
| **[!UICONTROL Event]**<br/>**[!UICONTROL Session]**<br/>**[!UICONTROL Person]** | Välj snabbfiltrets omfång i listrutan ![SparronDown](/help/assets/icons/ChevronDown.svg). |

### Villkorsområde

Villkorsområdet anger villkoren (upp till högst tre). För varje villkor kan du ange följande:

| Element | Beskrivning |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metric]**<br/>**[!UICONTROL Date range]** | Välj i listrutan ![ChevronDown](/help/assets/icons/ChevronDown.svg) om du vill ange ett villkor för en dimension, ett mått eller ett datumintervall. |
| **[!UICONTROL *komponent *]** | Komponentfältet för villkoret. Du kan [!UICONTROL *Typ om du vill lägga till*] en komponent, markera en komponent i listan eller dra och släppa en komponent från komponentpanelen. Du kan bara släppa liknande komponenter i komponentfältet för villkoret. Du kan t.ex. bara släppa en dimensionskomponent från komponentpanelen på ett dimensionsvillkor. <br/>Du kan också dra och släppa för att ersätta en befintlig komponent.<br/>Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort komponenten från komponentfältet. |
| **[!UICONTROL *operator *]** | Komponentens operator. Mer information finns i [Operatorer](operators.md). Endast tillgängligt för mått och mätvärden. |
| **[!UICONTROL *värde *]** | Värdet för villkoret. Beroende på vilken operator som är vald kan värdet väljas från en lista eller så anger du ett värde. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Välj det här alternativet om du vill ta bort ett villkor från snabbfiltret. |

### Knappar

| Knapp | Beskrivning |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Endast tillgängligt när du definierar mer än ett villkor. Välj i listrutan ![ChevronDown](/help/assets/icons/ChevronDown.svg) mellan villkoren. Markeringen avgör snabbfiltrets booleska logik. Du kan inte blanda logik när du har tre villkor. Den booleska logiken är antingen **[!UICONTROL AND]** eller **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Lägger till ytterligare ett villkor i snabbfiltret. Den här knappen är bara tillgänglig när du har definierat ett eller två villkor för snabbfiltret. |
| **[!UICONTROL Apply]** | Använd ändringarna på snabbfiltret. |
| **[!UICONTROL Open builder]** | Du uppmanas att bekräfta med en **[!UICONTROL Are your sure?]**-dialogruta. Om du väljer **[!UICONTROL OK]** kan du inte längre ändra filtret i [snabbfilterverktyget](#quick-filter-builder). Snabbfiltret har bytt namn till **[!UICONTROL Filter]** och har nu ett mörkare blått tunt fält till vänster.<br/>Det vanliga [filterverktyget](filter-builder.md) öppnas med alternativet **[!UICONTROL Make this filter available to all your projects and add it to your component list]**. <ul><li>Om du väljer det här alternativet och väljer **[!UICONTROL Apply]** läggs filtret till i komponentlistan ![ Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** på komponentpanelen.</li><li>Om du inte markerar det här alternativet och väljer **[!UICONTROL Apply]** förblir filtret ett Workspace-projektfilter.</li></ul> |
| **[!UICONTROL Cancel]** | Välj det här alternativet om du vill avbryta skapandet eller redigeringen av ett snabbfilter. |

## Snabbfilter jämfört med filter

Snabbfilter är precis vad de namnges. Du kan skapa och redigera snabbfilter snabbt och se effekterna direkt i panelen.

Filter har följande fördelar jämfört med snabbfilter.

* Filter kan göras tillgängliga i alla dina Workspace-projekt
* Filter kan bli mer komplicerade med kapslade och hierarkiska behållare och sekvenser (med sekvensfilter).


