---
title: Dimensioner med mycket hög kardinalitet i Customer Journey Analytics
description: Beskriver de bästa sätten att hantera högkardinalitetsmått i Customer Journey Analytics
translation-type: tm+mt
source-git-commit: be423e0fd298ed3ea9d6efa272f865882406b811
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---


# Dimensioner med mycket hög kardinalitet

Customer Journey Analytics (CJA) sätter inga gränser för antalet unika värden eller dimensionsposter som kan rapporteras inom en enda dimension. I vissa fall kan dock dimensioner med ett mycket stort antal unika poster - även kallade högkardinalitetsmått - påverka vad som kan rapporteras.

## Begränsningar

Beroende på antalet händelser i en viss CJA-anslutning kan följande två begränsningar förekomma i kombination med dimensioner med hög kardinalitet:

### 1. Radantalet kanske inte är exakt rapporteringsbart

Radantal vid höga kardinalitetsmått kanske inte kan rapporteras exakt. När detta inträffar kommer friformstabeller att ge en indikation som visas nedan:

![](assets/high-cardinality.png)

### 2. Beräknade mått kan returnera uppskattningar

Vid användning med stora kardinaldimensioner kan vissa beräkningsmått returnera uppskattningar, inklusive: Kolumnmaximum, Kolumngräns, Radantal, Medel, Medel, Percentile, Kvartpunkt, Standardavvikelse, Varians, Regressionsfunktioner samt T- och Z-funktioner.

Dessutom kan sortering av en tabellkolumn med ett beräknat mått baseras på en uppskattning och kanske inte alltid återspeglar den exakta sorteringsordningen. Ett varningsmeddelande visas som varnar dig om att uppskattningar kan ha använts.

Observera att även om beräknade värden ibland kan returnera uppskattningar är kolumnsummorna alltid korrekta och baseras aldrig på uppskattningar. När du använder standardvärden används heller aldrig uppskattningar för att sortera en kolumn och återspeglar alltid exakt sorteringsordning.

## Om alla dimensionsvärden beaktas

Även om det finns begränsningar för vissa beräknade värden och dimensionsradantal bör du vara medveten om att följande funktioner alltid tar hänsyn till alla unika värden i alla dimensioner. De ser dem oavsett om en dimension är mycket kardinal eller inte:

* Måttattribuering och dimensionsallokering
* Sökningar efter radobjekt som har tillämpats på en frihandsritabell
* Filter som använder dimensioner eller dimensionsobjekt
* Den ungefärliga distinkta funktionen för antal i beräknade värden
* Inkludera/exkludera logik som tillämpas på alla mått och dimensioner i en datavy
* Sök efter datauppsättningar som har lagts till i en anslutning

## Bästa tillvägagångssätt för arbete med stora kardinaldimensioner

För att eliminera varningar och uppskattningar som kan förekomma när du använder dimensioner med hög kardinalitet, rekommenderar vi att du minskar antalet rader som tas med i rapporten med någon av följande metoder:

* Lägg till ett filter i kolumnen eller panelen som påverkas.
* Använd en sökning i din frihandstabell.
* Använd en uppdelning på intressanta rader eller använd den högkardinala dimensionen som en detaljdimension.
* Lägg till inkluderings-/exkluderingskriterier i dimensionens datavykonfiguration för att begränsa antalet unika värden som finns i dimensionen.

Om du använder dessa tekniker kan du ofta eliminera oönskade uppskattningar eller varningar när du använder höga kardinaldimensioner.
