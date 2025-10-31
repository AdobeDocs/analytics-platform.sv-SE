---
title: Inkludera flera dimensioner i en frihandstabell
description: Lär dig hur du inkluderar flera dimensioner i en frihandstabell
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: ec07eb5dced013eac3d1088f2f49dcea23894395
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 0%

---

# Inkludera flera dimensionskolumner i en frihandstabell

{{release-limited-testing}}

Du kan inkludera upp till 5 dimensionskolumner i en frihandstabell, så att du kan visa flera dimensionsobjekt sida vid sida. Varje rad med dimensionsobjekt fungerar som en enda sammanfogad artikel.

Du kan använda filter, sortering, uppdelningar med mera på frihandstabeller med flera dimensionskolumner för att skapa en mer komplett och anpassad analys.

## Lägga till flera dimensionskolumner

Du kan lägga till flera dimensionskolumner en åt gången eller gruppvis.

1. Skapa en frihandstabell i Analysis Workspace.

   Mer information finns i [Lägga till visualiseringar i en panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) i [Översikt över visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Lägg till mått i frihandsritabellen. Du kan lägga till en dimension åt gången eller lägga till flera dimensioner samtidigt.

   * Dra måtten en en åt gången till frihandstabellen. Placera ytterligare dimensionskolumner till vänster eller höger om befintliga dimensionskolumner i tabellen. En blå lodrät **[!UICONTROL Add]**-rad visar var den nya kolumnen kommer att skapas.

     ![Dra enskilda dimensioner](assets/dimensions-add-individually.png)

   * Välj upp till 5 dimensioner på komponentmenyn och dra dem till frihandstabellen. Dimensioner läggs till i tabellen från vänster till höger i den ordning som du markerar dem.

     Om du vill markera flera dimensioner håller du ned tangenten ***Kommando*** (i Mac) eller tangenten ***Ctrl*** (i Windows).

     ![Dra flera dimensioner](assets/dimensions-add-multiple.png)

## Filtrera tabeller

Du kan använda filter på en eller flera dimensionskolumner i en frihandstabell.

Mer information om att filtrera tabeller finns i [Filtrera tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#filter-tables) i [Filtrera och sortera tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Sortera tabeller {#sort-tables}

<!--At GA, move this section into the "Filter and sort tables" article and replace the current "Sort tables" section. Change the "Filter tables" section above to "Filter and sort tables" and link to the other article. Also add row to Guardrails -->

Du kan sortera data i en frihandstabell efter kolumner i Analysis Workspace, oavsett om de är dimensioner eller mått.

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

När du sorterar data för flera kolumner sorteras data efter den prioritet som du tilldelar varje kolumn. Prioritetsnumrering visas bredvid sorteringsikonen ![sorteringsprioritet](assets/sort-priority-icon.png).

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

## Flera dimensionskolumner och uppdelningar

I Analysis Workspace finns följande sätt att lägga till flera dimensioner i en frihandstabell:

* Inkludera flera dimensionskolumner (enligt beskrivningen i den här artikeln)

* [Lägg till uppdelningar](/help/components/dimensions/t-breakdown-fa.md)

Båda dessa metoder gör att du kan analysera mått mot andra dimensioner. Det finns dock viktiga skillnader, och båda metoderna kan användas i samma tabell för en ännu djupare analys.

### Skillnader mellan dimensionskolumner och uppdelningar

Med flera dimensionskolumner kan du:

* Sammanfoga dimensionsobjekt i distinkta rader med data över flera dimensioner.

* Inkludera endast dimensionsposter i sammanfogade rader när dimensionsposter gäller för varje dimensionskolumn i tabellen. För att uppnå detta använder du kolumnfiltret för att avmarkera inställningen **[!UICONTROL Include "No value"]** för varje dimensionskolumn.

  Mer information finns i [Sortera tabeller efter flera kolumner (avancerad sortering)](#sort-tables-by-multiple-columns-advanced-sorting).

* Sortera data efter flera dimensioner och måttkolumner för att se mer anpassade data.

  Mer information finns i [Sortera tabeller efter flera kolumner (avancerad sortering)](#sort-tables-by-multiple-columns-advanced-sorting)

Med uppdelningar kan du:

* Dela upp ett dimensionsobjekt i friformstabellen med en andra dimension. Du kan visa upp till 200 dimensionsobjekt för den sekundära dimensionen.

### Lägga till uppdelningar i en tabell med flera dimensionskolumner

När du lägger till en uppdelning i en tabell som har flera dimensionskolumner, sträcker sig uppdelningen över alla dimensionsobjekt på raden där du lägger till den.

Du kan lägga till en uppdelning enligt beskrivningen i [Bryt ned dimensioner](/help/components/dimensions/t-breakdown-fa.md).

## Dimensioner som inte stöds {#unsupported}

Följande dimensionskombinationer stöds inte och Analysis Workspace tillåter inte att de läggs till eller visar ett felmeddelande när de har lagts till:

* Flera dimensioner från fält som refererar till olika [arrayer av objekt](/help/use-cases/object-arrays.md) som används tillsammans i samma friformstabell.

  Flera dimensioner tillåts tillsammans i samma friformstabell om de refererar till samma objektmatris.