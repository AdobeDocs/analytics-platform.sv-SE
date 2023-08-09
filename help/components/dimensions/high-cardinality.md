---
title: Höga kardinaldimensioner
description: Beskriver hur Customer Journey Analytics hanterar dimensioner med många unika värden
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
source-git-commit: 8f64e0a31ed3bca7185674490fc36b78598f5b1c
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---

# Höga kardinaldimensioner

När du använder en dimension som innehåller många unika värden kan den resulterande rapporten innehålla för många unika dimensionsobjekt för att visas eller beräknas. Resultaten trunkeras genom att dimensionsartiklar som anses vara minst viktiga tas bort. Dessa optimeringar görs för att bibehålla projekt- och produktprestanda.

När du begär en rapport med för många unika värden visar Analysis Workspace en indikator i dimensionshuvudet som anger att inte alla dimensionsobjekt inkluderas. Exempel: &quot;Rader: 1-50 av mer än 22 343 156&quot;. Nyckelordet &quot;mer än&quot; indikerar att viss optimering har tillämpats på rapporten för att returnera de viktigaste dimensionsobjekten.

![Förhandsgranska arbetsyta](assets/high-cardinality.png)

## Bestämma vilka dimensionsobjekt som ska visas

Customer Journey Analytics bearbetar rapporter när de körs och distribuerar den kombinerade datauppsättningen till flera servrar. Data per bearbetningsserver grupperas efter person-ID, vilket innebär att en enda bearbetningsserver innehåller alla data för en viss person. När en server har bearbetat klart överför den sin deluppsättning av bearbetade data till en aggregeringsserver. Alla deluppsättningar av bearbetade data kombineras och returneras i form av en Workspace-rapport.

Om någon enskild server bearbetar data som överskrider ett unikt tröskelvärde trunkeras resultaten innan den bearbetade datadeluppsättningen returneras. Trunkerade dimensionsobjekt bestäms utifrån det mätvärde som används för sortering.

Om sorteringsmåttet är ett beräknat mått, använder servern måtten i det beräknade måttet för att avgöra vilka dimensionsobjekt som ska trunkeras. Eftersom beräknade mätvärden kan innehålla flera mätvärden av varierande betydelse kan resultaten bli mindre exakta. Vid beräkningen av&quot;Intäkt per person&quot; returneras till exempel det totala inkomstbeloppet och det totala antalet personer och aggregeras innan indelningen görs. Därför väljer varje enskild bearbetningsserver vilka objekt som ska tas bort utan att veta hur resultatet påverkar den övergripande sorteringen.

Även om vissa enskilda dimensionsobjekt saknas i kardinalrapporterna är kolumnsummorna korrekta och inte baserade på trunkerade data. Funktionen Antal distinkt i beräknade mått påverkas inte heller av trunkerade dimensionsobjekt.

## Bästa tillvägagångssätt för höga kardinalitetsmått

Det bästa sättet att hantera stora kardinalitetsmått är att begränsa antalet dimensionsobjekt som en rapport behandlar. Eftersom alla rapporter bearbetas när de begärs kan du justera rapportparametrarna för att få omedelbara resultat. Adobe rekommenderar någon av följande optimeringar av högkardinalitetsmått:

* Använd en [Filter](/help/components/filters/create-filters.md). Filter tillämpas när varje server bearbetar en delmängd av data.
* Använd en sökning. Dimensioner som utesluts från söktermen tas bort från rapportresultaten, vilket gör det lättare att se de önskade dimensionsobjekten.
* Använd en dimension för uppslagsdatauppsättning. Dimensionerna för uppslagsdatauppsättningen kombinerar dimensionsobjekt för händelsedatamängd, som begränsar antalet unika värden som returneras.
* Använd [Inkludera/exkludera](/help/data-views/component-settings/include-exclude-values.md) -komponentinställning i datavyhanteraren.
* Förkorta datumintervallet för begäran. Om många unika värden ackumuleras över tid kan ett kortare datumintervall i Workspace-rapporten begränsa antalet unika värden som servrar kan bearbeta.
