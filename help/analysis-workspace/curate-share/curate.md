---
description: Med kurering kan du begränsa komponenter innan du delar ett projekt.
keywords: Analysis Workspace curation
title: Kuratera arbetsyteprojekt
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---


# Kuratera arbetsyteprojekt

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Med kurering kan du begränsa komponenterna (mått, mått, segment, datumintervall) innan du delar ett projekt. När en mottagare öppnar projektet visas en begränsad uppsättning komponenter som du har valt för dem. Kurering är ett valfritt men rekommenderas innan du delar ett projekt.

>[!NOTE]
> Produktprofiler är den primära mekanismen som styr vilka komponenter en användare kan se. De hanteras via Adobe Experience Cloud Admin Console. Curation är ett sekundärt filter.

## Använd projektstrukturering

1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
De komponenter som används i projektet läggs automatiskt till.
   **Obs**: Om ett projekt har flera rapportsviter visas ett kuratefält för varje rapportserie i projektet.
1. (Valfritt) Om du vill lägga till fler komponenter drar du de komponenter du vill dela från den vänstra listen till [!UICONTROL Curate Components] fältet.
1. Klicka på **[!UICONTROL Done]**.

Du kan också använda Kursion på [!UICONTROL Share] menyn genom att klicka **[!UICONTROL Curate and Share]**. Med det här alternativet kurformas projektet automatiskt till de komponenter som används i projektet. Du kan lägga till ytterligare komponenter enligt stegen ovan.

![](assets/curation-field.png)

## Kuraterad projektvy

När en mottagare öppnar ett välstrukturerat projekt visas endast den urval av komponenter som du har definierat:

![](assets/curate-project.png)

## Ta bort projekturval

Så här tar du bort projektstrukturering och återställer alla komponenter i den vänstra listen:
1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Klicka på **[!UICONTROL Remove Curation]**.
1. Klicka på **[!UICONTROL Done]**.

## VRS-kuration (Virtual Report Suite)

Om du vill använda kurering på rapportsvitnivå, så att den gäller för många projekt samtidigt, kan du [strukturera komponenter i en Virtual Report-serie (VRS)](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html).

>[!NOTE]
> VRS-kurering används alltid före projektkurering. Detta innebär att även om ditt kuraterade projekt innehåller vissa komponenter, kommer de att filtreras bort om det aktuella VRS inte innehåller dem.

## Visa alla komponenter, alternativ

I ett välstrukturerat projekt (VRS) får mottagaren möjlighet att välja **[!UICONTROL Show All]** komponenter i den vänstra listen. [!UICONTROL Show All] visar olika uppsättningar av komponenter, beroende på:

* Användarens behörighetsnivå (admin eller icke-admin)
* Projektroll (ägare/redigerare eller inte)
* Typ av kuration som används (VRS eller projekt)

| Kurvtyp | Administratörer | Projektägare eller redigeringsroll som inte är administratör | Duplicera eller visa roll som inte är administratör |
|---|---|---|---|
| Kuraterad VRS | Alla VRS-komponenter som inte är kuraterade | Icke-förvaltade VRS-komponenter som den här rollen äger eller som har delats med dem | Icke-förvaltade VRS-komponenter som den här rollen äger eller som har delats med dem |
| Kuraterat projekt | Alla projektkomponenter som inte är kuraterade | Alla projektkomponenter som inte är kuraterade | Ej förvaltade projektkomponenter som den här rollen äger eller som har delats med dem |
| Kuraterat projekt i ett kuraterat VRS | Alla icke-förvaltade komponenter, visas under **[!UICONTROL Non-Curated Project Components]** och **[!UICONTROL Non-Curated VRS Components]** | Alla icke-förvaltade projektkomponenter OCH icke-förvaltade VRS-komponenter som den här rollen äger eller som har delats med dem | Icke-förvaltat VRS och projektkomponenter som den här rollen äger eller har delats med dem |
