---
title: Dynamiska jämfört med statiska dimensionsobjekt
description: Hur man interagerar med dynamiska och statiska dimensionsobjekt i tabeller.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 2%

---


# Dynamiska jämfört med statiska dimensionsobjekt i frihandstabeller

>[!NOTE] Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

I frihandstabeller kan raderna och kolumnerna innehålla olika komponentvärden. Dessa värden kan vara dynamiska (ändras med tid) eller statiska (ändras inte med tid), beroende på vilken analys du vill skapa.

## Dynamiska dimensionsobjekt

Objekt med dynamiska dimensioner ändras med tiden och är beroende av vilket mått som sorteras i friformstabellen. Dynamiska dimensionsobjekt föredras när du vill analysera de översta artiklarna för en given tidsperiod.

När du släpper en dimension i en frihandstabell returneras dynamiska rader. De representerar de översta artiklarna som motsvarar dimensionen för ett givet mätvärde och en viss tidsperiod. Du kan också släppa en dimension i tabellkolumner på fri hand, och dimensionen utökas automatiskt till de fem främsta dimensionsobjekten.

När du t.ex. drar dimensionen Webbläsartyp till tabellen visas dimensionsobjekten för webbläsartypen överst (t.ex. Microsoft, Apple, Google) Återgå dynamiskt till tabellraderna. Om de utelämnas i en kolumn returneras dimensionsobjekten för de fem vanligaste webbläsartyperna dynamiskt.

Objekt med dynamiska dimensioner har alternativet radfilter och har **inga** lås- och X-ikoner.

## Statiska dimensionsobjekt

Statiska dimensionsobjekt ändras inte med tiden. de är fasta komponenter som alltid returneras i en frihandstabell. Statiska dimensionsobjekt föredras när du alltid vill analysera samma objekt, oavsett om det är specifika kampanjer eller specifika dagar i veckan.

Varje gång du manuellt markerar och släpper specifika komponentvärden (mått, mått, segment, datumintervall) i en tabell blir resultatet en statisk lista med rader eller kolumner. Statiska dimensionsobjekt kan också skapas om du väljer att:

* Högerklicka från rader > [!UICONTROL Display only selected rows]
* Högerklicka från kolumner > [!UICONTROL Make item static]

Om du t.ex. drar över vissa objekt i webbläsartypen, t.ex. Microsoft och Apple, hämtas dessa två objekt alltid till tabellen.

Statiska dimensionsobjekt har **inte** alternativet radfilter. Istället visas lås- och X-ikoner för varje objekt. Klicka på X-ikonen för att ta bort dimensionsobjektet från tabellen.

## Blandade dimensionsobjekt

Dimensionsobjekt från olika dimensioner kan läggas till i samma register. Radhuvudet säger&quot;Blandade dimensioner&quot; i dessa fall. Dessa dimensionsobjekt är statiska. Du kan till exempel lägga till specifika dimensionsobjekt från dimensionen Webbläsartyp och andra dimensionsobjekt från dimensionen Webbläsare.

## Frihandsrader

Dynamiska och statiska rader fungerar på olika sätt i den totala frihandsraden. Som standard:

* Dynamiska rader summeras på serversidan och dubblettvärden som besök och besökare tas bort
* Statiska rader summeras på klientsidan och dubbletter tas **inte** bort.

[Läs mer om alternativen för total](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) arbetsyta för dynamiska och statiska rader.
