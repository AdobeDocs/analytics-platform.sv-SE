---
description: Med kurering kan du begränsa komponenter innan du delar ett projekt.
keywords: Analysis Workspace kurser
title: Kuratprojekt
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: f940e5cba11df0ff158093a503213ff1641b1c5d
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Kuratprojekt

Med kurering kan du begränsa komponenterna (mått, mått, segment, datumintervall) innan du delar ett projekt. När en mottagare öppnar projektet visas en begränsad uppsättning komponenter som du har valt för dem. Kurering är ett valfritt men rekommenderat steg innan du delar ett projekt.

>[!NOTE]
> Produktprofiler är den primära mekanismen som styr vilka komponenter en användare kan se. De hanteras via [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-tool-experience-cloud). Kuration är ett sekundärt segment.

## Använd projektstrukturering

1. Välj **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
Komponenterna som används i projektet läggs till automatiskt.
Om ett projekt har flera datavyer visas ett aktuellt släppmål för varje datavy i projektet.
1. (Valfritt) Om du vill lägga till fler komponenter drar du de komponenter du vill dela från den vänstra panelen till släppzonen **[!UICONTROL Curate components]** för datavyn.
1. Välj **[!UICONTROL Done]**.

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![Fönstret Kuratkomponenter visar de komponenter som används i projektet.](assets/curation-field.png)

När en mottagare öppnar ett välstrukturerat projekt visas endast den urval av komponenter som du har definierat:


## Ta bort projektstrukturering

Så här tar du bort projektstrukturering och återställer alla komponenter i den vänstra panelen:

1. Välj **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Välj **[!UICONTROL Remove Curation]**.
1. Välj **[!UICONTROL Done]**.

## Alternativ för komponenturval

I ett välstrukturerat projekt får mottagaren alternativet att **[!UICONTROL Show All]** komponenter i den vänstra panelen. [!UICONTROL Show All] visar olika uppsättningar av komponenter, beroende på:

* Användarens behörighetsnivå (admin eller icke-admin)
* Projektroll (ägare/redigerare eller inte)
* Typ av kuration som används (på projektnivå)

| Kurvtyp | Administratören kan se | Projektägaren (eller redigeringsrollen) som inte är administratör kan se | Dubblettroll som inte är administratör kan se |
| --- | --- | --- | --- |
| **Komponenter *dolda* från en datavy** | Alla datavykomponenter är tillgängliga för rapportering (dolda komponenter kräver att du väljer **[!UICONTROL Show all]**) | Ej tillgängligt för rapportering | Ej tillgängligt för rapportering |
| **Komponenter som har lagts till eller tagits bort från en datavy** | Endast komponenter som har lagts till i datavyn (dolda eller inte dolda). Administratörer kan inte rapportera fält eller komponenter som inte är definierade i datavyn. | Endast komponenter som har lagts till i datavyn, eller komponenter som ägs eller delas med användaren. Dolda komponenter är inte tillgängliga (som VD). | Det är bara komponenter som läggs till i datavyn som inte är dolda och som ingår i projekturval. |
| **Kuraterade komponenter i ett projekt** | Alla datavykomponenter som är tillgängliga för rapportering (dolda komponenter kräver att du väljer **[!UICONTROL Show all]**) | Alla icke-dolda datavykomponenter (kräver att du klickar på Visa alla) | Endast förvaltade komponenter, plus eventuella komponenter som ägs eller delas med användaren |
| **Kuraterat projekt med en datavy med dolda komponenter** | Alla datakomponenter som är tillgängliga för rapportering (dolda och icke-förvaltade komponenter kräver att du väljer **[!UICONTROL Show all]**) | Alla icke-förvaltade projektkomponenter, alla icke-dolda datavykomponenter och alla komponenter som ägs eller delas med användaren | Endast förvaltade komponenter, plus alla komponenter som ägs eller delas med användaren |
