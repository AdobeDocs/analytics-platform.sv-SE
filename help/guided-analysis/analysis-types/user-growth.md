---
title: Användartillväxt
description: Håll koll på hur produktens användarbas växer.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
source-git-commit: c18ed01f899b7a521c67ed6a0008210099b858bf
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Användartillväxt

{{release-limited-testing}}

The **Användartillväxt** [Analystyp](overview.md) ger insikter om användarnas tillväxt och förvärv under en viss period. Den vågräta axeln är alltid en tidshalaritet, medan den lodräta axeln alltid är ett mått på användaren. Användarna analyseras från början av datumintervallet och delas in i fyra kategorier:

* **Nytt**: Det är användarens första gång i det angivna datumintervallet. Den första datapunkten är alltid 100 % nya användare, eftersom analysen inte ser ut utanför datumintervallet.
* **Upprepa**: Användaren visades i den omedelbart föregående datapunkten och den aktuella datapunkten.
* **Retur**: Användaren visades inte i den omedelbart föregående datapunkten, men är inte en ny användare. Returanvändare kan inte visas i den första eller andra datapunkten, eftersom de först måste visas som en ny användare och sedan som en vilande användare.
* **Vilande**: Användaren visades inte i den aktuella datapunkten, utan i den omedelbart föregående datapunkten. Vilande användare räknas inte med i det totala antalet aktiva användare.

Alla aktiva användare (nya + upprepning + retur) visas som en provton ovanför den vågräta axeln, medan alla vilande användare visas orangefärgade under den vågräta axeln.

Användningsexempel för den här analystypen är:

* **Resultatutvärdering**: Med användartillväxten kan du bedöma den övergripande prestandan för din produkt när det gäller att skaffa nya användare. Genom att följa tillväxttrender kan du bättre förstå om produkten lockar och behåller användare i önskad takt.
* **Bevarande och bortfall av användare:** Användartillväxten ger en tydlig visualisering runt perioder med hög eller låg användarlojalitet. Genom att känna igen dessa perioder av hög eller låg lojalitet kan du fatta produktbeslut för att öka kundlojaliteten eller hjälpa till att minimera bortfallet.
* **Kampanjbedömning**: Genom att se på användartillväxten kring en viss kampanj kan ni förstå inte bara hur mycket trafik den genererade, utan även hur väl kampanjen hjälpte användarna att förbli engagerade.

[Skärmbild av användartillväxt]

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Händelser**: Händelsen som du vill mäta. Eftersom den här analystypen är användarbaserad kan en användare peka på händelsen en gång inom den angivna datumgranulariteten för att räknas som en aktiv användare. Du kan bara inkludera en händelse i en fråga.
* **Folk**: Det segment som du vill mäta. Du kan bara inkludera ett segment i en fråga.

## Vytyper

Användartillväxt erbjuder följande vytyper. Du kan ändra vytyp med hjälp av listrutan högst upp till vänster i diagrammet.

* **Aktiv:** Mät tillväxten hos era användare.

## Diagraminställningar

Användartillväxt har följande diagraminställningar. Du kan justera diagraminställningarna på menyn mellan vytypen och kalenderväljaren.

* **Mått**: Det mått som du vill mäta. Alternativen är Antal användare och Procent av användare.
* **Diagramtyp**: Den typ av visualisering som du vill använda. Alternativen är Staplad liggande och Staplad yta.

## Datumintervall

Det önskade datumintervallet. Den här inställningen har två viktiga komponenter:

* **Intervall**: Datumgranulariteten som du vill visa data i. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **Datum**: Start- och slutdatumet. Det finns förinställningar för datumintervall tillgängliga, eller så kan du använda kalenderväljaren för att ange exakt önskat datum.
