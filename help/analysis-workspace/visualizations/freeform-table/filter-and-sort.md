---
description: Lär dig filtrera och sortera frihandstabeller i Analysis Workspace.
title: Filtrera och sortera tabeller
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# Filtrera och sortera tabeller på frihand

Frihandstabeller i Analysis Workspace är grunden för interaktiv dataanalys. De kan därför innehålla tusentals rader med information. Filtrering och sortering av data kan vara en viktig del av att effektivt kunna hitta den viktigaste informationen.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtrera tabeller

Med filter i Analysis Workspace hittar du den viktigaste informationen.

>[!NOTE]
>
> Endast dynamiska dimensionsobjekt kan filtreras enligt beskrivningen i det här avsnittet. Statiska dimensionsobjekt kan inte filtreras. Mer information finns i [Dynamiska och statiska dimensionsobjekt i frihandstabeller](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Du kan använda flera metoder för att filtrera rader från en frihandstabell.

- Exkludera specifika rader från en tabell
- Använda filter på en tabell
- Använd målgruppssegment

Läs om hur varje metod påverkar [registersummor för frihand](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Exkludera specifika rader från en tabell

Du kan snabbt utesluta vissa rader från tabellen utan att behöva använda ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]**.

>[!NOTE]
>
>När du utelämnar rader enligt beskrivningen i det här avsnittet läggs en [!UICONTROL Always exclude items]-regel till automatiskt i filterdialogrutan [!UICONTROL Advanced]. Du kan visa den använda regeln genom att välja filterikonen ![Filter](/help/assets/icons/Filter.svg) och sedan [**[!UICONTROL Show advanced]**](#apply-a-simple-or-advanced-filter-to-a-table) .

Så här exkluderar du specifika rader från en friformstabell:

1. Håll pekaren över raden som du vill utesluta och välj sedan ![Stäng](/help/assets/icons/Close.svg).

   Håll ned ***Skift*** om du vill markera ett radintervall eller håll ned ***cmd***-tangenten (på Mac) eller ***ctrl***-tangenten (på Windows) om du vill markera flera rader.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Använda ett enkelt eller avancerat filter på en tabell

Så här filtrerar du data i frihandstabeller:

1. Håll markören över den kolumn som innehåller de data som du vill filtrera. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Välj ![Filter](/help/assets/icons/Filter.svg) **Filter** när det visas.

   ![Frihandstabell som markerar ikonen Filter.](assets/table-filter-icon.png)

   Följande alternativ är tillgängliga i dialogrutan **[!UICONTROL Search]**:

   ![Filtrera enkelt](assets/filter-simple.png){width="500"}

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Inkludera &quot;Inget värde&quot;**] | Välj det här alternativet om du vill visa en **[!UICONTROL No value]**-rad i tabellen för data som inte har något värde för den valda dimensionen. Avmarkera alternativet om du vill dölja raden **[!UICONTROL No value]**. |
   | [!UICONTROL **Sök efter ord eller fras**] | Ange ett ord eller en fras som du vill filtrera efter. Endast rader som innehåller det angivna ordet eller den exakta frasen visas. |


1. (Valfritt) Om du vill filtrera efter olika villkor eller efter flera villkor väljer du [!UICONTROL **Visa avancerat**].

   Följande avancerade filteralternativ är tillgängliga:

   ![Filtrera enkelt](assets/filter-advanced.png){width=500}

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Inkludera &quot;Inget värde&quot;**] | Välj det här alternativet om du vill visa en **[!UICONTROL No value]**-rad i tabellen för data som inte har något värde för den valda dimensionen. Avmarkera alternativet om du vill dölja raden **[!UICONTROL No value]**. |
   | [!UICONTROL **Matcha**] | Välj [!UICONTROL **Om alla villkor uppfylls**] om du bara vill visa data som uppfyller alla villkor som du anger. Det här alternativet ger vanligtvis mer förfinade data.<br/><br/>Välj [!UICONTROL **Om något villkor uppfylls**] för att visa data som uppfyller något av de filtervillkor som du anger. Det här alternativet ger vanligtvis mindre förfinade data. |
   | [!UICONTROL **Villkor**] | Välj bland följande filteralternativ:<br/><ul><li>[!UICONTROL **Innehåller frasen**] (standard): Endast data som innehåller den exakta frasen som du anger inkluderas i de filtrerade resultaten. Ord måste finnas i den ordning som anges i fältet [!UICONTROL **Sök efter ord eller fras**].</li><li>[!UICONTROL **Innehåller valfri term**]: Endast data som innehåller ett eller flera ord från den fras du anger inkluderas i filtrerade resultat. </li><li>[!UICONTROL **Innehåller alla termer**]: Endast data som innehåller alla ord från frasen som du anger inkluderas i filtrerade resultat. Ord behöver inte vara i den ordning som anges i fältet [!UICONTROL **Sök efter ord eller fras**].</li><li>[!UICONTROL **Innehåller inte någon term**]: Endast data som inte innehåller något av orden från den fras du anger inkluderas i filtrerade resultat. </li><li>[!UICONTROL **Innehåller inte frasen**]: Endast data som inte innehåller den exakta frasen som du anger inkluderas i filtrerade resultat. Ord måste finnas i den ordning som anges i fältet [!UICONTROL **Sök efter ord eller fras**].</li><li>[!UICONTROL **Lika med**]: Endast data som exakt matchar den fras du anger inkluderas i filtrerade resultat. </li><li>[!UICONTROL **Är inte lika med**]: Endast data som inte exakt matchar frasen som du anger inkluderas i filtrerade resultat. </li><li>[!UICONTROL **Börjar med**]: Endast data som börjar med ordet eller den exakta frasen som du anger inkluderas i filtrerade resultat. </li><li>[!UICONTROL **Slutar med**]: Endast data som slutar med ordet eller den exakta frasen som du anger inkluderas i filtrerade resultat. </li></ul>Välj ![Lägg till](/help/assets/icons/Add.svg) [!UICONTROL **Lägg till rad**] om du vill lägga till flera filtervillkor. Det alternativ du väljer för [!UICONTROL **Matcha**] avgör **[!UICONTROL If all criteria are met]** eller **[!UICONTROL If any criteria are met]**. |
   | [!UICONTROL **Uteslut alltid objekt**] | Ange namnet på alla objekt som du vill utesluta från filtrerade data. |

1. Välj **[!UICONTROL Apply]** om du vill filtrera data. Välj **[!UICONTROL Clear]** om du vill rensa alla indata. Välj **[!UICONTROL Cancel]** om du vill avbryta och stänga dialogrutan. <br/>En färgad ![Filter](/help/assets/icons/FilterColored.svg) **Filter** -ikon anger och visar information när ett filter används i tabellen.

### Använd målgruppssegment

Mer information finns i [Segmenteringsöversikt](/help/components/segments/seg-overview.md).

## Sortera tabeller

Du kan sortera data i en Frihand-tabell efter en kolumn i Analysis Workspace som är en dimension eller ett mått. En pil visar hur data sorteras (**↓** för fallande eller **↑** för stigande).

![Sortering](assets/sorting.gif)
