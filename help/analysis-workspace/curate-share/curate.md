---
description: Med kurering kan du begränsa komponenterna innan du delar ett projekt.
keywords: Analysis Workspace curation
title: Kurva arbetsyteprojekt
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---


# Kurva arbetsyteprojekt

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Med kurering kan du begränsa komponenterna (dimensioner, mått, segment, datumintervall) innan du delar ett projekt. När en mottagare öppnar projektet visas en begränsad uppsättning komponenter som du har kursat för dem. Kursion är ett valfritt men rekommenderat steg innan du delar ett projekt.

>[!NOTE]
> Produktprofiler är den primära mekanismen som styr vilka komponenter en användare kan se. De hanteras via Adobe Experience Cloud Admin Console. Kursion är ett sekundärt filter.

## Använd projektkursion

1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
Komponenterna som används i projektet läggs automatiskt till.
   **Anteckning**: Om ett projekt har flera rapportuppsättningar visas ett kursfält för varje rapportsvit i projektet.
1. (Valfritt) Om du vill lägga till fler komponenter drar du de komponenter som du vill dela från vänster räl till vänster [!UICONTROL Curate Components] fält.
1. Klicka på **[!UICONTROL Done]**.

Kursion kan också användas från [!UICONTROL Share] meny genom att klicka på **[!UICONTROL Curate and Share]**. Med det här alternativet bollar du projektet automatiskt till de komponenter som används i projektet. Du kan lägga till ytterligare komponenter enligt stegen ovan.

![](assets/curation-field.png)

## Aktuell projektvy

När en mottagare öppnar ett aktuellt projekt visas endast den aktuella uppsättning komponenter som du har definierat:

![](assets/curate-project.png)

## Ta bort projektkursion

Så här tar du bort projektkurvorna och återställer hela uppsättningen komponenter i den vänstra rälen:
1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Klicka på **[!UICONTROL Remove Curation]**.
1. Klicka på **[!UICONTROL Done]**.

## VRS-kursion (Virtual Report Suite)

Om du vill använda kursion på rapportsvitnivå, så att den gäller för många projekt samtidigt, kan du [Kurvera komponenter i ett virtuellt rapportpaket (VRS)](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html).

>[!NOTE]
> VRS-kurering används alltid före projektkurering. Detta innebär att även om ditt aktuella projekt innehåller vissa komponenter filtreras de ut om det aktuella VRS inte innehåller dem.

## Alternativet Visa alla komponenter

I ett aktuellt projekt eller VRS kommer mottagaren att få möjlighet att **[!UICONTROL Show All]** Komponenter i vänster räl. [!UICONTROL Show All] visar olika komponentuppsättningar, beroende på:

* Användarens behörighetsnivå (administratör eller annan än administratör)
* Projektroll (ägare/redaktör eller ej)
* Typ av kuration som används (VRS eller projekt)

| Kurstyp | Administratörer | Projektägare som inte är administratör eller redigeringsroll | Dubblett eller visningsroll som inte är administratör |
|---|---|---|---|
| Kursiverat VRS | Alla icke-kurderade VRS-komponenter | Icke-aktuella VRS-komponenter som den här rollen äger eller som har delats med dem | Icke-aktuella VRS-komponenter som den här rollen äger eller som har delats med dem |
| Aktuellt projekt | Alla projektkomponenter som inte är aktuella | Alla projektkomponenter som inte är aktuella | Icke-aktuella projektkomponenter som den här rollen äger eller som har delats med dem |
| Kursiverat projekt i ett kursiverat VRS | Alla komponenter som inte är kursiverade, visas under **[!UICONTROL Non-Curated Project Components]** och **[!UICONTROL Non-Curated VRS Components]** | Alla projektkomponenter som inte är kursiverade OCH ej kursiverade VRS-komponenter som den här rollen äger eller som har delats med dem | Icke-curated VRS och projektkomponenter som den här rollen äger eller som har delats med dem |
