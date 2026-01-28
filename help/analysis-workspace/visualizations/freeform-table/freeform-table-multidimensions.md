---
title: Inkludera flera dimensioner i en frihandstabell
description: Lär dig hur du inkluderar flera dimensioner i en frihandstabell
feature: Visualizations
role: User
source-git-commit: 696bd0db44949162307d8ce7d2debed351a76cd6
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 0%

---

# Inkludera flera dimensionskolumner i en frihandstabell

{{release-limited-testing}}

Du kan inkludera upp till 5 dimensionskolumner i en frihandstabell, så att du kan visa flera dimensionsobjekt sida vid sida. Varje rad med dimensionsobjekt fungerar som en enda sammanfogad dimensionspost.

Du kan använda filter, sortering, uppdelningar med mera i frihandstabeller med flera dimensionskolumner för att skapa en djupare och mer anpassad analys.

## Sammanfogade dimensionsobjekt

När du [lägger till flera dimensionskolumner i en friformstabell](#add-multiple-dimension-columns) fungerar varje rad med dimensionsobjekt som ett enda sammanfogat dimensionsobjekt. Med den här funktionen kan du se mätdata för specifika kombinationer av dimensioner.

Ta till exempel en frihandstabell där dimensionskolumnerna är _City_, _Device Type_ och _Day of Month_ och måttet är _Events_. De tre dimensionsobjekten i den första raden i tabellen blir en enda sammanfogad dimensionspost som visar att det var 2 056 händelser som ägde rum i Mumbai från mobiltelefoner den 30:e i månaden.

| Dimension: Ort | Dimension: Enhetstyp | Dimension: Dag i månaden | Mått: Händelser |
|---------|----------|---------|---------|
| Mumbai | Mobiltelefon | 30 | 2 056 |
| New York | Tablet | 31 | 1 761 |
| Bangalore | Skrivbord | 1 | 1 666 |
| Delhi | Mobiltelefon | 14 | 1 396 |

Så här visas tabellen i Analysis Workspace:

![Exempel på flera dimensioner](assets/multi-dim-example.png)

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

1. Visa varje rad i tabellen som en enskild dimensionspost. Mer information finns i [Sammanfogade dimensionsobjekt](#concatenated-dimension-items).

## Filtrera och ordna tabeller

Du kan använda filtrering och sortering på kolumner i en friformstabell. Du kan sortera data i en frihandstabell efter kolumner, oavsett om de är dimensioner eller mått. Du kan till och med sortera efter flera kolumner samtidigt.

Mer information finns i [Filtrera och sortera tabeller på frihand](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

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

* Dela upp ett dimensionsobjekt i friformstabellen med en andra dimension. Du kan visa upp till 400 dimensionsobjekt för den sekundära dimensionen.

### Lägga till uppdelningar i en tabell med flera dimensionskolumner

När du lägger till en uppdelning i en tabell som har flera dimensionskolumner, gäller uppdelningen den sammanfogade dimensionsposten (för alla dimensionskolumner) på raden där du lägger till den.

![exempel på flersortering](assets/dimensions-multiple-sort-breakdown.png)

Dessutom kan du lägga till flera dimensionskolumner i en uppdelning. Varje rad med dimensionsposter i uppdelningen fungerar också som en enda sammanfogad dimensionspost.

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

Mer information om hur du lägger till en brytning finns i [Bryt ned dimensioner](/help/components/dimensions/t-breakdown-fa.md).

## Skapa ett segment baserat på en dimensionspost som sträcker sig över flera dimensionskolumner

När du skapar ett segment baserat på en dimensionspost som sträcker sig över flera dimensionskolumner, inkluderas varje dimensionspost i segmentdefinitionen, och operatorerna And förenar dem.

Mer information om hur du skapar ett segment finns i [Skapa segment](/help/components/segments/seg-create.md).

## Dimensioner som inte stöds {#unsupported}

Följande dimensionskombinationer stöds inte och Analysis Workspace tillåter inte att de läggs till eller visar ett felmeddelande när de har lagts till:

* Flera dimensioner från fält som refererar till olika [arrayer av objekt](/help/use-cases/object-arrays.md) som används tillsammans i samma friformstabell.

  Flera dimensioner tillåts tillsammans i samma friformstabell om de refererar till samma objektmatris.

