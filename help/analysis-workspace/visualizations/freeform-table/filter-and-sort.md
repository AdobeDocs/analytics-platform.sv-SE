---
description: Lär dig filtrera och sortera frihandstabeller i Analysis Workspace.
title: Filtrera och ordna
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '1536'
ht-degree: 0%

---

# Filtrera och sortera tabeller på frihand

Frihandstabeller i Analysis Workspace är grunden för interaktiv dataanalys. De kan därför innehålla tusentals rader med information. Filtrering och sortering av data kan vara en viktig del av att effektivt kunna hitta den viktigaste informationen.


## Filtrera tabeller

Med filter i Analysis Workspace hittar du den viktigaste informationen.

>[!NOTE]
>
> Endast dynamiska dimensionsobjekt kan filtreras enligt beskrivningen i det här avsnittet. Statiska dimensionsobjekt kan inte filtreras. Mer information finns i [Dynamiska och statiska dimensionsobjekt i frihandstabeller](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Du kan använda flera metoder för att filtrera rader från en frihandstabell.

* Exkludera specifika rader från en tabell
* Använda filter på en tabell
* Använd målgruppssegment

Läs om hur varje metod påverkar [frihandstabellsummor](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Exkludera specifika rader från en tabell

Du kan snabbt utesluta vissa rader från tabellen utan att behöva använda ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]**.

>[!NOTE]
>
>När du utelämnar rader enligt beskrivningen i det här avsnittet läggs en [!UICONTROL Always exclude items]-regel till automatiskt i filterdialogrutan [!UICONTROL Advanced]. Du kan visa den använda regeln genom att välja filterikonen ![Filter](/help/assets/icons/Filter.svg) och sedan [**[!UICONTROL Show advanced]**](#apply-a-simple-or-advanced-filter-to-a-table) .

Så här exkluderar du vissa rader från en frihandstabell:

1. Håll pekaren över raden som du vill utesluta och välj sedan ![Stäng](/help/assets/icons/Close.svg).

   Håll ned tangenten ***Skift*** om du vill markera flera rader, eller håll ned tangenten ***Kommando*** (i Mac) eller tangenten ***Ctrl*** (i Windows) om du vill markera flera rader.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Använda enkel eller avancerad filtrering i en tabell

Så här filtrerar du data i frihandstabeller:

1. Håll markören över den kolumn som innehåller de data som du vill filtrera. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Välj ![Filter](/help/assets/icons/Filter.svg) **Filter** när det visas.

   ![Frihandstabell som markerar ikonen Filter.](assets/table-filter-icon.png)

   Följande alternativ är tillgängliga i dialogrutan **[!UICONTROL Search]**:

   ![Filtrera enkelt](assets/filter-simple.png){width="500"}

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Inkludera &quot;Inget värde&quot;**] | Välj det här alternativet om du vill visa en **[!UICONTROL No value]**-rad i tabellen för data som inte har något värde för den valda dimensionen. Avmarkera det här alternativet om du vill dölja **[!UICONTROL No value]** rader.<!-- Add at multi dim GA: When tables include multiple dimension columns, you can deselect this option to show data only when it applies to each dimension column in the table.--> |
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

### Inkludera filtervillkor i trenddata i miniatyrbilder och linjevisualiseringar {#include-filter-criteria}

Alla sökfiltervillkor som tillämpas på tabelldimensionen i en frihandstabell tas alltid med i miniatyrbilder.

Förutom miniatyrbilder kan du konfigurera filtervillkor som ska inkluderas i visningen av anslutna rader. (Som standard inkluderas inte filtervillkor i radvisualiseringar. Radvisualiseringar visar data för raden som är markerad i den anslutna tabellen. Om ingen rad är markerad visas endast data för den första dimensionen i den anslutna tabellen.)

Mer information om miniatyrdiagram och linjevisualiseringar finns i [Visa trenddata för en frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).

#### Konfigurera radvisualiseringar för att inkludera filtervillkor

1. Markera miniatyrdiagrammet i kolumnrubriken för mått.

   När miniatyrdiagramcellen är markerad visas den som mörkgrå. Detta anger att filtervillkor ingår i den anslutna linjens visualisering. Filtervillkoren används som ett segment i kolumnen. <!--show how to see it? Show what the segment looks like when it's applied? -->

   ![miniatyrdiagram markerat](assets/table-sparkline-selected.png)

#### Förstå när kolumnsummor kan vara felaktiga

Kolumnsummorna kanske inte är exakta i följande scenarier:

* När statiska komponenter används i den vänstra kolumnen och [kolumnsummor beräknas som summan av raderna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)

  Om radobjekt innehåller överlappande data i det här scenariot blir kolumnsummorna felaktiga.

  Om du till exempel lägger till statiska segment i den vänstra kolumnen och sedan lägger till Användare som ett mått i den högra kolumnen, kan vissa av dessa användare ingå i mer än ett av de statiska segmenten. I det här fallet deduplicerar inte Workspace användarna för varje statiskt segment. Detta kan leda till ett större antal användare, eftersom vissa användare kan räknas mer än en gång.

* När flervärdesdimensioner används

>[!NOTE]
>
>Miniatyrdiagrammet och linjediagrammet återspeglar fortfarande de exakta summorna i dessa scenarier.

### Använd målgruppssegment

Mer information finns i [Segmenteringsöversikt](/help/components/segments/seg-overview.md).

## Sortera tabeller

I Analysis Workspace kan du sortera data i en frihandstabell efter kolumner, oavsett om de är dimensioner eller mått. Du kan till och med sortera efter flera kolumner samtidigt.

Som standard sorteras dimensionerna i stigande ordning och måtten sorteras i fallande ordning.

### Sortera tabeller efter en kolumn

När du sorterar data för en enskild kolumn enligt beskrivningen i det här avsnittet, tas all [avancerad sortering](#sort-tables-by-multiple-columns-advanced-sorting) som tillämpas på tabellen bort.

Så här sorterar du data i tabeller efter en kolumn:

1. För musen över rubriken för den kolumn som du vill sortera och markera sedan ikonen **Sortera** ![Sortera](/help/assets/icons/SortOrderDown.svg) när den visas.

   ![Listrutan Sortera](assets/sort-dropdown-menu.png)

1. Välj **[!UICONTROL Ascending]** eller **[!UICONTROL Descending]**.

   Sorteringsikonen är fortfarande synlig när sortering används på kolumnen. En pil anger hur data sorteras (![Sortera](/help/assets/icons/SortOrderUp.svg) för stigande eller ![Sortera](/help/assets/icons/SortOrderDown.svg) för fallande).

### Sortera tabeller efter flera kolumner (avancerad sortering)

{{release-limited-testing-section}}

#### Använda sortering på flera kolumner

Så här sorterar du data i tabeller efter flera kolumner:

1. För musen över rubriken för den kolumn som du vill sortera och markera sedan ikonen **Sortera** ![Sortera](/help/assets/icons/SortOrderDown.svg) när den visas.

   ![Listrutan Sortera](assets/sort-dropdown-menu.png)

1. Välj **[!UICONTROL Advanced sorting]**.

   ![Dialogrutan Avancerad sortering](assets/sort-advanced-dialog.png)

1. Gör något av följande i dialogrutan Avancerad sortering:

   * Lägg till kolumner som ännu inte är sorterade genom att markera knappen **[!UICONTROL Add sort column]**.

   * Ta bort kolumner som du inte längre vill sortera genom att markera ikonen **Ta bort** ![Ta bort](/help/assets/icons/Close.svg).

   * Justera sorteringsprioriteten genom att dra kolumnerna uppåt eller nedåt i listan.

     Mer information finns i [Sorteringsprioritet](#sort-priority).

   * Ändra sorteringsvärdet genom att välja **[!UICONTROL Ascending]** eller **[!UICONTROL Descending]** i listrutan.

   * Välj en annan kolumn genom att välja den nedrullningsbara menyn för kolumnnamn.

1. Välj **[!UICONTROL Apply]**.

Sorteringsikonen är fortfarande synlig när sortering används på en kolumn. En pil anger hur data sorteras (![Sortera](/help/assets/icons/SortOrderUp.svg) för stigande eller ![Sortera](/help/assets/icons/SortOrderDown.svg) för fallande).

![exempel på flera sorteringar](assets/dimensions-multiple-sort.png)

#### Sorteringsprioritet

När du sorterar data för flera kolumner sorteras data efter den prioritet som du tilldelar varje kolumn. Prioritetsnumrering visas bredvid sorteringsikonen ![SortOrderDown](/help/assets/icons/SortOrderDown.svg)<sup>➊</sup>.

Kolumnen med den primära prioriteten bestämmer huvudordningen. Kolumnen med den sekundära prioriteten bestämmer ordningen när raderna har samma värde i den primära kolumnen. Kolumnen med den högre prioriteten bestämmer ordningen när raderna har samma värde i de primära och sekundära kolumnerna och så vidare.

Ta till exempel en tabell med följande kolumner:

* Dag i månaden (dimension)

* Dagens timme (dimension)

* Händelser (mått)

Du kan tilldela sorteringsprioritet till varje kolumn enligt följande:

| Kolumnnamn (komponent) | Komponenttyp | Sorteringsprioritet |
|---------|----------|---------|
| Dag i månaden | Dimension | 1 |
| Timme på dagen | Dimension | 2 |
| Händelser | Mått | 3 |

Genom att tilldela varje kolumn en sorteringsprioritet kan du styra exakt hur data visas i tabellen. I det här exemplet sorteras informationen först efter dag i månaden, sedan efter timme på dagen och slutligen efter händelser.

![exempel på flera sorteringar](assets/dimensions-multiple-sort.png)
