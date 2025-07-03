---
title: Hög kardinalnivå
description: Förklara hur Customer Journey Analytics hanterar dimensioner med många unika värden.
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 0%

---

# Höga kardinaldimensioner

När du använder en dimension som innehåller många unika värden kan den resulterande rapporten innehålla för många unika dimensionsobjekt för att visas eller beräknas. Resultaten trunkeras genom att dimensionsartiklar som anses vara minst viktiga tas bort. Dessa optimeringar görs för att bibehålla projekt- och produktprestanda.

När du begär en rapport med för många unika värden visar Analysis Workspace en indikator i dimensionshuvudet som anger att inte alla dimensionsobjekt inkluderas. Exempel: **[!UICONTROL Rows: 1-50 of more than 22,343,156]**. Nyckelordet **[!UICONTROL more than]** indikerar att viss optimering har tillämpats på rapporten för att returnera de viktigaste dimensionsobjekten.

![Frihandstabell i Workspace som visar nyckelordet &quot;mer än&quot; för att visa 1-50 av mer än 22 343 156](assets/high-cardinality.png)

## Bestämma vilka dimensionsobjekt som ska visas

Customer Journey Analytics bearbetar rapporter när de körs och distribuerar den kombinerade datauppsättningen till flera servrar. Data per bearbetningsserver grupperas efter person-ID, vilket innebär att en enda bearbetningsserver innehåller alla data för en viss person. När en server har bearbetat klart överför den sin deluppsättning av bearbetade data till en aggregeringsserver. Alla datadeluppsättningar kombineras och returneras i form av en Workspace-rapport.

Om någon enskild server bearbetar data som överskrider ett unikt tröskelvärde trunkeras resultaten innan den bearbetade datadeluppsättningen returneras. Trunkerade dimensionsobjekt bestäms utifrån det mätvärde som används för sortering.

Om sorteringsmåttet är ett beräknat mått, använder servern måtten i det beräknade måttet för att avgöra vilka dimensionsobjekt som ska trunkeras. Eftersom beräknade mätvärden kan innehålla flera mätvärden av varierande betydelse kan resultaten bli mindre exakta. Vid beräkningen av&quot;Intäkt per person&quot; returneras till exempel det totala inkomstbeloppet och det totala antalet personer och aggregeras innan indelningen görs. Därför väljer varje enskild bearbetningsserver vilka objekt som ska tas bort utan att veta hur resultatet påverkar den övergripande sorteringen.

Även om vissa enskilda dimensionsobjekt saknas i kardinalrapporterna är kolumnsummorna korrekta och inte baserade på trunkerade data. Funktionen Antal distinkt i beräknade mått påverkas inte heller av trunkerade dimensionsobjekt.

## Bästa tillvägagångssätt för höga kardinalitetsmått

Det bästa sättet att hantera stora kardinalitetsmått är att begränsa antalet dimensionsobjekt som en rapport behandlar. Eftersom alla rapporter bearbetas när de begärs kan du justera rapportparametrarna för att få omedelbara resultat. Adobe rekommenderar någon av följande optimeringar av kardinalitetsdimensioner:

* Använd ett [segment](/help/components/segments/seg-create.md). Segmenten tillämpas när varje server bearbetar en delmängd av data.
* Använd en sökning. Dimension-objekt som utesluts från söktermen tas bort från rapportresultaten, vilket gör det lättare att se de önskade dimensionsobjekten.
* Använd en dimension för uppslagsdatauppsättning. Dimensionerna för uppslagsdatauppsättningen kombinerar dimensionsobjekt för händelsedatamängd, som begränsar antalet unika värden som returneras.
* Använd komponentinställningen [Inkludera/exkludera](/help/data-views/component-settings/include-exclude-values.md) i datavyhanteraren.
* Förkorta datumintervallet för begäran. Om många unika värden ackumuleras över tid kan en förkortning av datumintervallet i Workspace-rapporten begränsa antalet unika värden som servrar kan bearbeta.
* Använd [Fullständig tabellexport](/help/analysis-workspace/export/export-cloud.md) om du vill returnera alla rader i tabellen.
