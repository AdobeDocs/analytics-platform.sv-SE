---
title: Åtagandevy
description: Förstå bredden och bredden av funktionsengagemang.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 0%

---

# [!UICONTROL Engagement] visa

The **[!UICONTROL Engagement]** ger insikt i hur ofta en funktion används jämfört med hur många som använder den. Den här analysen fungerar bäst när flera funktioner jämförs.

Funktioner som pekar mot början av den här visualiseringen visar att den besöks ofta bland de personer som använder den. Funktioner som ritar åt höger om den här visualiseringen indikerar att den största andelen användare som använder funktionen är aktiva. Medianvärdet för hur många gånger en funktion används dividerar diagrammet vågrätt. Medianprocenten för aktiva användare dagligen delar diagrammet lodrätt.

* Funktionerna längst upp till vänster i matrisen innebär att en funktion inte används i någon större utsträckning. Men bland de personer som använder programmet använder de det ofta.
* Funktionerna i matrisens övre högra hörn innebär att en funktion används både ofta och ofta.
* Funktionerna längst ned till höger i matrisen innebär att en funktion används ofta, men inte ofta.
* Funktionerna längst ned till vänster i matrisen innebär att en funktion inte används i någon större utsträckning och inte heller används ofta.

## Användningsexempel

Exempel:

* **Engagemang efter funktion**: Du kan fastställa ett direkt samband mellan engagemang och användning av en viss funktion. Att förstå vilka funktioner som används mest kan hjälpa till att avgöra vilka funktioner som ska prioriteras.
* **Upptäck underutnyttjade funktioner**: Funktioner med låga dagliga aktiva användare men hög användning kan tyda på en dold men värdefull funktion. Överväg att exponera den här typen av funktioner för fler användare.
* **Förbättra populära funktioner**: Funktioner med aktiva användare men låg användning kan tyda på att en funktion är efterfrågad men underanvänd. Överväg att investera i förbättringar av dessa funktioner så att de används oftare.
* **Skapa funktionsbaserade segment**: Analysera hur ofta en funktion används mot hur många användare använder den för att avgöra vilka typer av användare som använder en viss funktion. Du kan skapa segment baserat på användare som använder en funktion ofta eller baserat på användare som använder den funktionen ofta.
* **A/B-testning av nya funktioner**: Jämför användningen av flera funktioner med hjälp av segment. Lägg till segmenten för varje kohort i frågespelaren för att enkelt avgöra skillnaden i funktionsanvändning.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Events]**: De händelser som du vill mäta. Dessa händelser representerar vanligtvis användningen av en viss funktion. Varje markering representeras som en punkt i matrisen. Du kan inkludera upp till tio händelser.
* **[!UICONTROL Counted as]**: Bestäm hur x-axeln räknar användare. Du kan mäta den genomsnittliga procentandelen aktiva användare varje dag, vecka, månad eller kvartal. Y-axeln justerar automatiskt genomsnittstiden per användare baserat på x-axelns markering.
* **[!UICONTROL Segments]**: De segment som du vill mäta. Varje markerat segment dubblerar antalet plottade punkter i diagrammet och raderna i tabellen. Du kan inkludera upp till tre segment.

## Diagraminställningar

The [!UICONTROL Engagement] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Medians]**: Avgör var medianinjerna visas och hur de plottade punkterna relaterar till medianerna.
   * **[!UICONTROL Standard]**: Visa det absoluta värdet av användning och engagemang.
   * **[!UICONTROL Normalized]**: Visa relativa ändringar från varje median.
* **[!UICONTROL Top events overlay]**: Se hur dina händelser fungerar jämfört med de vanligaste händelserna.

## Tidsjämförelse

{{apply-time-comparison}}

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa trenddata efter. Den här vytypen behandlar [!UICONTROL Interval] liknar [!UICONTROL Counted as] i frågefältet. Timvis aktiva användare stöds inte.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
