---
title: Dynamiska och statiska Dimension-objekt
description: Lär dig hur du använder dynamiska och statiska dimensionsobjekt i frihandstabeller i Analysis Workspace.
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 0%

---

# Dynamiska och statiska dimensionsobjekt

I frihandstabeller kan raderna och kolumnerna innehålla olika komponentvärden. Dessa värden kan vara dynamiska (ändras över tid) eller statiska (ändras inte över tid), beroende på vilken analys du vill bygga.

## Dynamiska dimensionsobjekt

Objekt med dynamiska dimensioner ändras över tid och är beroende av det mått som sorteras i friformstabellen. Dynamiska dimensionsobjekt föredras när du vill analysera de översta artiklarna för en given tidsperiod.

När du släpper en dimension i en frihandstabell returneras dynamiska rader. Dynamiska rader representerar de översta objekten som motsvarar dimensionen för ett givet mått och en viss tidsperiod. Du kan också släppa en dimension i tabellkolumner på fri hand, och dimensionen utökas automatiskt till de fem främsta dimensionsobjekten.

När du t.ex. drar dimensionen Webbläsartyp till tabellen, återgår de översta textobjekten (t.ex. Microsoft, Apple, Google) dynamiskt till tabellraderna. Om de utelämnas i en kolumn returneras dimensionsobjekten för de fem vanligaste webbläsartyperna dynamiskt.

Dynamiska dimensionsobjekt har radfilteralternativet ![Filter](/help/assets/icons/Filter.svg) och ![Close](/help/assets/icons/Close.svg) och har **inte** låset ![LockClosed](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> När du klickar på ![Stäng](/help/assets/icons/Close.svg) bredvid ett dynamiskt dimensionsobjekt tillämpas ett filter automatiskt. Mer information om hur du tillämpar filter på tabeller finns i [Filtrera och sortera tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![En friformstabell som markerar filterikonen.](assets/dynamic-items.png)

## Statiska dimensionsobjekt

Statiska dimensionsobjekt ändras inte med tiden. De är fasta komponenter som alltid returneras i en friformstabell. Statiska dimensionsobjekt föredras när du alltid vill analysera samma objekt, oavsett om det är specifika kampanjer eller specifika dagar i veckan.

Varje gång du manuellt markerar och släpper specifika komponentvärden (mått, mått, segment, datumintervall) i en tabell blir resultatet en statisk lista med rader eller kolumner.

Om du till exempel drar över vissa objekt i webbläsartypen, som Microsoft och Apple, hämtas dessa två objekt alltid till tabellen.

Statiska dimensionsobjekt kan också skapas om du väljer **[!UICONTROL Display only selected rows]** på snabbmenyn för markerade rader.

Statiska dimensionsobjekt har **inte** alternativet radfilter. I stället finns en ![LockClosed](/help/assets/icons/LockClosed.svg) och ![Close](/help/assets/icons/Close.svg) för varje objekt. Välj ![Stäng](/help/assets/icons/Close.svg) om du vill ta bort dimensionsobjektet från tabellen.

![En friformstabell som visar webbläsartypen och Microsoft-raden med en låsikonanteckning: Dimensionsobjektet är statiskt och ändras inte med tiden.](assets/static-items.png)

## Blandade dimensionsobjekt

Dimension-objekt med olika dimensioner kan läggas till i samma tabell. Radhuvudet säger **[!UICONTROL Mixed Dimensions]** i dessa fall. Dessa dimensionsobjekt är statiska. Du kan till exempel lägga till specifika dimensionsobjekt från dimensionen Webbläsargrupp och andra dimensionsobjekt från dimensionen Webbläsarnamn.

![En friformstabell som markerar kolumnen Blandade dimensioner.](assets/mixed-dimensions.png)

## Frihandsrader

Dynamiska och statiska rader fungerar på olika sätt i den totala frihandsraden. Som standard:

* Dynamiska rader summeras på serversidan och dubblettmått som sessioner eller personer tas bort.
* Statiska rader summeras på klientsidan och deduplicerar **inte**-mått. Om du vill beräkna den totala radserversidan ändrar du radinställningen till **Visa totalsumman**. [Läs mer](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)
