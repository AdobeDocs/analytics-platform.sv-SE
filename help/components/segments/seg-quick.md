---
description: Lär dig använda snabbsegment i Analysis Workspace.
title: Snabbsegment
feature: Workspace Basics, Filters, Segments
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 0%

---

# Snabbsegment

Med snabbsegment kan du snabbt utforska data i ett Workspace-projekt, utan att behöva skapa ett segment i [Segment Builder](/help/components/segments/seg-create.md).



>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Snabbsegment i Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


Observera följande när du vill använda snabbsegment:

* Snabbsegment skapas direkt i ett Workspace-projekt. Det innebär att ett snabbsegment bara gäller för det Workspace-projekt där du skapar snabbsegmentet. Snabbsegmenten i ditt Workspace-projekt är inte tillgängliga i andra projekt och kan inte delas med andra användare.
* Du kan bara ange tre villkor som en del av ett snabbsegment.
* Snabbsegment har inte stöd för kapslade behållare eller sekventiella villkor.
* Du kan redigera snabbsegment i ett delat Workspace-projekt. Andra användare kan alltså redigera snabbsegmenten i ett Workspace-projekt som du har delat med dessa användare.

## Skapa

Snabbsegment gäller för paneler. Du kan skapa ett eller flera snabbsegment för alla paneler i ditt Workspace-projekt. Alla användare i Analysis Workspace kan skapa snabbsegment.

Så här skapar du ett snabbsegment:

* Välj ![SegmentAdd](/help/assets/icons/FilterAdd.svg) längst upp på panelen. <br/>Redigera sedan segmentet direkt i [snabbsegmentsverktyget](#quick-segment-builder).
* Dra en komponent från komponentpanelen till segmentets släppzon i panelhuvudet. Håll markören över segmentet och välj ![Redigera](/help/assets/icons/Edit.svg) för att redigera segmentet i [snabbsegmentsverktyget](#quick-segment-builder) när det släppts.

När du skapar ett snabbt segment med dra och släpp bör du tänka på följande:

* Alla komponenttyper stöds inte. Beräknade mätvärden stöds inte, och endast mått och mätvärden från vilka du kan skapa segment stöds.
* För mått och måttkomponenter skapar [snabbsegmentsverktyget](#quick-segment-builder) automatiskt ett `exists` -villkor. Om du till exempel drar och släpper **[!UICONTROL City]** skapas villkoret **[!UICONTROL City]** **[!UICONTROL exists]**.
* För dimensionsvärden skapar [snabbsegmentsverktyget](#quick-segment-builder) automatiskt ett **[!UICONTROL equals]**-villkor. Om du till exempel drar och släpper **[!UICONTROL Amsterdam]** från dimensionslistan **[!UICONTROL City]** skapas villkoret **[!UICONTROL City]** **[!UICONTROL equals]** `Amsterdam`.
* Om du drar och släpper **[!UICONTROL unspecified]** eller **[!UICONTROL none]** skapar [snabbsegmentsverktyget](#quick-segment-builder) automatiskt ett **[!UICONTROL does not exist]**-villkor.

Snabbsegment som du skapar visas högst upp på panelen. Snabbsegment har ett ljusblått tunt fält till vänster. När ett snabbsegment är i redigeringsläge med hjälp av [snabbsegmentsverktyget](#quick-segment-builder) är bakgrunden i snabbsegmentet ljusblå.

Resultatet av de snabbsegment du skapar på en panel används (med AND-logik) på alla visualiseringar som är en del av panelen.


## Hantera

Håll pekaren över **[!UICONTROL Quick segment]** om du vill hantera ett snabbsegment.

* Välj ![Redigera](/help/assets/icons/Edit.svg) för att öppna [snabbsegmentsverktyget](#quick-segment-builder) och redigera snabbsegmentet.
* Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg) för att öppna ett popup-fönster. I popup-fönstret visas information om segmentet. Du kan välja **[!UICONTROL Make available to all projects and add to your component list]** om du vill lägga till segmentet i komponentlistan ![ Segment](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** på komponentpanelen. Du ser en **[!UICONTROL Save quick segment]**-dialogruta där du uppmanas att ange ett namn för segmentet. Välj **[!UICONTROL Save]** om du vill fortsätta. [!UICONTROL Quick segment] blir en **[!UICONTROL Segment]**. Du kan inte längre redigera segmentet med [snabbsegmentsverktyget](#quick-segment-builder). I stället måste du redigera segmentet som ett vanligt segment med hjälp av [segmentverktyget](seg-builder.md).

## Bygg snabbt segment

Nedan finns ett exempel på snabbsegmentsverktyget. I exemplet öppnas byggaren för ett snabbsegment med namnet `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Båda snabbsegmenten längst upp gäller för panelen **[!UICONTROL Average Order Value Dashboard]** och alla visualiseringar i den, till exempel friformstabellen [!UICONTROL Average Order Value Per Country].

![Skapa snabbsegment](assets/quick-filter-builder.png)

Snabbsegmentsverktyget består av följande områden och knappar.

### Sidhuvudsområde

Rubrikområdet bestämmer snabbsegmentets namn, typ och omfång. Den visar också en visuell information om resultatet av snabbsegmentet.

| Element | Beskrivning |
|---|---|
| **[!UICONTROL Name]** | Namnet hämtas automatiskt från snabbsegmentsdefinitionen. |
| **[!UICONTROL People]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alert](/help/assets/icons/Alert.svg) | Förhandsvisa visuella data som är resultatet av snabbsegmentet. En stapel och ett procenttal ger insikt i hur mycket av de totala data som är en del av resultatet av snabbsegmentet. En ![varning](/help/assets/icons/AlertRed.svg) signalerar att snabbsegmentet inte returnerar data. |
| **[!UICONTROL Include]**<br/>**[!UICONTROL Exclude]** | Välj i listrutan ![ChevronDown](/help/assets/icons/ChevronDown.svg) om du vill ta med eller exkludera resultatet av snabbsegmentet från data på panelen. |
| **[!UICONTROL Event]**<br/>**[!UICONTROL Session]**<br/>**[!UICONTROL Person]** | Välj snabbsegmentets omfång på den nedrullningsbara menyn ![SparronDown](/help/assets/icons/ChevronDown.svg). |

### Villkorsområde

Villkorsområdet anger villkoren (upp till högst tre). För varje villkor kan du ange följande:

| Element | Beskrivning |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metric]**<br/>**[!UICONTROL Date range]** | Välj i listrutan ![ChevronDown](/help/assets/icons/ChevronDown.svg) om du vill ange ett villkor för en dimension, ett mått eller ett datumintervall. |
| **[!UICONTROL *komponent *]** | Komponentfältet för villkoret. Du kan [!UICONTROL *Typ om du vill lägga till*] en komponent, markera en komponent i listan eller dra och släppa en komponent från komponentpanelen. Du kan bara släppa liknande komponenter i komponentfältet för villkoret. Du kan t.ex. bara släppa en dimensionskomponent från komponentpanelen på ett dimensionsvillkor. <br/>Du kan också dra och släppa för att ersätta en befintlig komponent.<br/>Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort komponenten från komponentfältet. |
| **[!UICONTROL *operator *]** | Komponentens operator. Mer information finns i [Operatorer](seg-operators.md). Endast tillgängligt för mått och mätvärden. |
| **[!UICONTROL *värde *]** | Värdet för villkoret. Beroende på vilken operator som är vald kan värdet väljas från en lista eller så anger du ett värde. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Välj det här alternativet om du vill ta bort ett villkor från snabbsegmentet. |

### Knappar

| Knapp | Beskrivning |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Endast tillgängligt när du definierar mer än ett villkor. Välj i listrutan ![SparrrDown](/help/assets/icons/ChevronDown.svg) mellan villkoren. Markeringen avgör den booleska logiken för snabbsegmentet. Du kan inte blanda logik när du har tre villkor. Den booleska logiken är antingen **[!UICONTROL AND]** eller **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Lägger till ytterligare ett villkor i ditt snabbsegment. Den här knappen är bara tillgänglig när du har definierat ett eller två villkor för snabbsegmentet. |
| **[!UICONTROL Apply]** | Använd ändringarna på snabbsegmentet. |
| **[!UICONTROL Open builder]** | Du uppmanas att bekräfta med en **[!UICONTROL Are your sure?]**-dialogruta. Om du väljer **[!UICONTROL OK]** kan du inte längre ändra ditt segment i [snabbsegmentsverktyget](#quick-segment-builder). Snabbsegmentets namn ändras till **[!UICONTROL Segment]** och har nu ett mörkare blått tunt fält till vänster.<br/>Det vanliga [segmentverktyget](seg-builder.md) öppnas med alternativet **[!UICONTROL Make this segment available to all your projects and add it to your component list]**. <ul><li>Om du väljer det här alternativet och väljer **[!UICONTROL Apply]** läggs segmentet till i komponentlistan ![ Segment](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]** på komponentpanelen.</li><li>Om du inte markerar det här alternativet och väljer **[!UICONTROL Apply]** förblir segmentet bara för Workspace-projekt.</li></ul> |
| **[!UICONTROL Cancel]** | Välj det här alternativet om du vill avbryta skapandet eller redigeringen av ett snabbsegment. |

## Snabbsegment kontra segment

Snabbsegment är precis vad de namnges. Du kan skapa och redigera snabbsegment snabbt och direkt i panelen.

Segment har följande fördelar jämfört med snabbsegment.

* Segment kan göras tillgängliga i alla dina Workspace-projekt
* Segment har stöd för större komplexitet med kapslade och hierarkiska [behållare](seg-builder.md#containers) och sekvenser (med [sekventiella segment](seg-sequential-build.md)).


