---
description: Med kurering kan du begränsa komponenter innan du delar ett projekt.
keywords: Analysis Workspace kurser
title: Kuratprojekt
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Kuratprojekt

Med kurering kan du begränsa komponenterna (mått, mått, segment, datumintervall) innan du delar ett projekt. När en mottagare öppnar projektet visas en begränsad uppsättning komponenter som du har valt för dem. Kurering är ett valfritt men rekommenderat steg innan du delar ett projekt.

>[!NOTE]
> Produktprofiler är den primära mekanismen som styr vilka komponenter en användare kan se. De hanteras via [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=sv-SE). Kuration är ett sekundärt segment.

## Använd projektstrukturering

1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
De komponenter som används i projektet läggs automatiskt till.
1. (Valfritt) Om du vill lägga till fler komponenter drar du de komponenter du vill dela från den vänstra panelen till fältet [!UICONTROL Curate Components].
1. Klicka på **[!UICONTROL Done]**.

Du kan också använda kurering från menyn [!UICONTROL Share] genom att klicka på **[!UICONTROL Curate and Share]**. Med det här alternativet kurformas projektet automatiskt till de komponenter som används i projektet. Du kan lägga till ytterligare komponenter enligt stegen ovan.

![Fönstret Kuratkomponenter visar de komponenter som används i projektet.](assets/curation-field.png)

## Kuraterad projektvy

När en mottagare öppnar ett välstrukturerat projekt visas endast den urval av komponenter som du har definierat:

![Ett delat kuraterat projekt med komponenter som du har definierat.](assets/curate-project.png)

## Ta bort projektstrukturering

Så här tar du bort projektstrukturering och återställer alla komponenter i den vänstra panelen:

1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Klicka på **[!UICONTROL Remove Curation]**.
1. Klicka på **[!UICONTROL Done]**.

## Alternativ för komponenturval

I ett välstrukturerat projekt kommer mottagaren att få alternativet **[!UICONTROL Show All]** komponenter i den vänstra panelen. [!UICONTROL Show All] visar olika uppsättningar av komponenter, beroende på:

* Användarens behörighetsnivå (admin eller icke-admin)
* Projektroll (ägare/redigerare eller inte)
* Typ av kuration som används (på projektnivå)

| Kurvtyp | Administratören kan se | Projektägaren (eller redigeringsrollen) som inte är administratör kan se | Dubblettroll som inte är administratör kan se |
| --- | --- | --- | --- |
| **Komponenter &quot;dolda&quot; från en datavy** | Alla datavykomponenter som är tillgängliga för rapportering (dolda komponenter kräver att du klickar på Visa alla) | Ej tillgängligt för rapportering | Ej tillgängligt för rapportering |
| **Komponenter som har lagts till eller tagits bort från en datavy** | Endast komponenter som har lagts till i datavyn (dolda eller inte dolda). Administratörer kan inte rapportera fält eller komponenter som inte har definierats i datavyn. | Endast komponenter som har lagts till i datavyn, eller komponenter som ägs eller delas med användaren. Dolda komponenter är inte tillgängliga (som VD). | Endast komponenter som lagts till i DV-filen är inte dolda och har inkluderats i projektkurationen. |
| **Kuraterade komponenter i ett projekt** | Alla datavykomponenter som är tillgängliga för rapportering (dolda komponenter kräver att du klickar på Visa alla) | Alla icke-dolda datavykomponenter (kräver att du klickar på Visa alla) | Endast förvaltade komponenter, plus eventuella komponenter som ägs eller delas med användaren |
| **Kuraterat projekt med en datavy med dolda komponenter** | Alla datakomponenter som är tillgängliga för rapportering (dolda och icke-förvaltade komponenter kräver att du klickar på Visa alla) | Alla icke-förvaltade projektkomponenter, alla icke-dolda datavykomponenter och alla komponenter som ägs eller delas med användaren | Endast förvaltade komponenter, plus alla komponenter som ägs eller delas med användaren |
