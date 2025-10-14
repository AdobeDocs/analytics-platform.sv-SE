---
description: Lär dig hur du visar trenddata för en frihandstabell i Analysis Workspace.
title: Visa trenddata för en frihandstabell
feature: Freeform Tables
role: User, Admin
source-git-commit: 6ffc02c537a5e0b24edab34c87866d5c8413ae6f
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---

# Visa trenddata för en frihandstabell

Du kan visa trenden för data som ingår i en frihandstabell. Dessa trenddata visas inom följande områden i Analysis Workspace:

* [Miniatyrdiagram](#use-sparklines-to-view-trended-data)

* [Radvisualiseringar](#use-line-visualizations-to-view-trended-data)

## Använd miniatyrbilder för att visa trenddata

Miniatyrdiagram visas i kolumnrubriken för mått i frihandstabeller.

![miniatyrdiagram i frihandstabell](assets/table-sparkline.png)

Miniatyrdiagram innehåller alltid:

* Trenddata för alla data i kolumnen

* Alla sökfiltervillkor som tillämpas på registerdimensionen

  Mer information finns i [Filter och sortering](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Använd linjevisualiseringar för att visa trenddata

[Linjevisualiseringar](/help/analysis-workspace/visualizations/line.md) visar data i frihandstabellen som de är anslutna till.

### Koppla ihop en linjevisualisering till ett frihandsritbord

Beroende på hur och när linjevisualiseringen lades till i projektet kanske den redan är ansluten till den önskade friformstabellen. Följ de här stegen för att kontrollera eller ansluta manuellt:

1. Lägg till en radvisualisering i ett Analysis Workspace-projekt.

1. Markera punkten bredvid visualiseringsnamnet, välj fliken **[!UICONTROL Data source]** och markera sedan namnet på frihandstabellen som du vill ansluta till radvisualiseringen.

   ![linjevisualisering ansluten till frihandstabeller](assets/table-line-viz.png)

### Välj de data som ska inkluderas i radinvisualiseringen

Vilka data som inkluderas i visualiseringen av den anslutna linjen varierar beroende på vilken cell som är markerad i frihandstabellen.

Om du vill visa en trend för alla data i frihandstabellen markerar du miniatyrdiagramcellen i frihandstabellen.

När miniatyrdiagramcellen är markerad visas cellen som mörkgrå.

![miniatyrdiagram markerat](assets/table-sparkline-selected.png)

När miniatyrdiagramcellen i den anslutna tabellen är markerad innehåller linjevisualiseringar:

* Trenddata för alla data i kolumnen

* Alla sökfiltervillkor som tillämpas på registerdimensionen

  Mer information finns i [Filter och sortering](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

När miniatyrdiagrammet för den anslutna tabellen inte är markerat innehåller linjevisualiseringar:

* Data för raden som är markerad i den anslutna tabellen. Om ingen rad är markerad visas endast data för den första dimensionen i den anslutna tabellen.

* Alla sökfiltervillkor som tillämpas på tabelldimensionen ignoreras

  Mer information finns i [Filter och sortering](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


## Inkludera filtervillkor i visualiseringar av anslutna rader

Mer information om när filtervillkor ingår i visualiseringar av anslutna rader finns i [Inkludera filtervillkor i trenddata i miniatyrbilder och linjevisualiseringar](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#include-filter-criteria-in-trended-data-in-sparklines-and-line-visualizations)

