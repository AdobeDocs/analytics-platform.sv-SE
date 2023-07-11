---
title: Aktiv
description: Mät tillväxten hos era användare.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: 14c7aa342649afbe9923b0086947e5a0adeefff2
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%

---

# Aktiv

{{release-limited-testing}}

The **Aktiv** vytypen ger insikter om användarnas tillväxt och förvärv under en viss period. Den vågräta axeln är alltid en tidshalaritet, medan den lodräta axeln alltid är ett mått på användaren. Användarna analyseras från början av datumintervallet och delas in i fyra kategorier:

* **Nytt**: Användaren var aktiv under den aktuella datapunkten och har inte visats i några tidigare datapunkter. Hovra över[!UICONTROL New users]&#39; i diagrammets förklaring för att se hur långt rapporten ser ut tillbaka för att bestämma en ny användare. Det här datumet väljs dynamiskt baserat på datumintervallets längd och granularitet.
* **Upprepa**: Användaren visades i den omedelbart föregående datapunkten och den aktuella datapunkten.
* **Retur**: Användaren visades inte i den omedelbart föregående datapunkten, men är inte en ny användare.
* **Vilande**: Användaren visades inte i den aktuella datapunkten, utan i den omedelbart föregående datapunkten. Vilande användare räknas inte med i det totala antalet aktiva användare.

Alla aktiva användare (nya + upprepning + retur) visas som en provton ovanför den vågräta axeln, medan alla vilande användare visas orangefärgade under den vågräta axeln.

Exempel:

* **Bevarande och bortfall av användare:** Ger en tydlig visualisering runt perioder med hög eller låg användarlojalitet. Genom att känna igen dessa perioder av hög eller låg lojalitet kan du fatta produktbeslut för att öka kundlojaliteten eller hjälpa till att minimera bortfallet.
* **Kampanjbedömning**: Att visa en viss kampanj kan hjälpa er att förstå inte bara hur mycket trafik den genererade, utan även hur väl kampanjen hjälpte användarna att hålla sig engagerade.
* **Livscykelanalys för användare**: Genom att analysera aktiv användartillväxt under hela användarlivscykeln kan man identifiera specifika faser där användarengagemanget minskar. Om det till exempel finns ett stort antal vilande användare för dem som befinner sig på introduktionsstadiet, kan det tyda på användbarhetsproblem eller ett behov av bättre produktvägledning.

[Skärmbild av användartillväxt]

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Händelser**: Händelsen som du vill mäta. Eftersom den här vytypen är användarbaserad kan en användare peka på händelsen en gång inom den angivna datumgranulariteten för att räknas som en aktiv användare. Du kan bara inkludera en händelse i en fråga.
* **Folk**: Det segment som du vill mäta. Du kan bara inkludera ett segment i en fråga.

## Diagraminställningar

Den här vytypen har följande diagraminställningar. Du kan justera diagraminställningarna på menyn mellan vytypen och kalenderväljaren.

* **Mått**: Det mått som du vill mäta. Alternativen är Antal användare och Procent av användare.
* **Diagramtyp**: Den typ av visualisering som du vill använda. Alternativen är Staplad liggande och Staplad yta.

## Använd tidsjämförelse

{{apply-time-comparison}}

## Datumintervall

Det önskade datumintervallet. Den här inställningen har två viktiga komponenter:

* **Intervall**: Datumgranulariteten som du vill visa data i. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **Datum**: Start- och slutdatumet. Det finns förinställningar för datumintervall tillgängliga, eller så kan du använda kalenderväljaren för att ange exakt önskat datum.
