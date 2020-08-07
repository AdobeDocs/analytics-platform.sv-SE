---
title: Dynamiska kontra statiska dimensionsobjekt i friformstabeller
description: Så här interagerar du med dynamiska och statiska dimensionsobjekt i tabeller.
translation-type: tm+mt
source-git-commit: cee89d021e9cd034246fe9367bc8910dac7ca7cf
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 2%

---


# Dynamiska kontra statiska dimensionsobjekt i friformstabeller

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

I Freeform-tabeller kan raderna och kolumnerna innehålla olika komponentvärden i dem. Dessa värden kan vara dynamiska (ändras med tiden) eller statiska (ändra inte med tiden), beroende på vilken analys du vill skapa.

## Dynamiska dimensionsartiklar

Dynamiska dimensionsobjekt ändras med tiden och är beroende av att måttet sorteras av i frihandstabellen. Dynamiska dimensionsobjekt föredras när du vill analysera de översta objekten för en given tidsperiod.

När du släpper en dimension i en frihandstabell returneras dynamiska rader. De representerar de översta posterna som motsvarar dimensionen för en given metrisk period och tidsperiod. Du kan också släppa en dimension i frihandstabellkolumner och dimensionen utökas automatiskt till de fem översta dimensionsobjekten.

När du t.ex. drar dimensionen Webbläsartyp till tabellen visas dimensionsobjekt av typen översta webbläsare (t.ex. Microsoft, Apple, Google osv.) Gå tillbaka till tabellraderna dynamiskt. Om de släpps i en kolumn returneras dimensionsobjekten av den högsta webbläsartypen dynamiskt.

Alternativet Radfilter för dynamiska dimensionsobjekt används och gör det **inte** ha lås- och X-ikoner närvarande.

![](assets/dynamic-items.png)

## Statiska dimensionsartiklar

Statiska dimensionsposter ändras inte med tiden. De är fasta komponenter som alltid returneras i en frihandstabell. Statiska dimensionsobjekt föredras när du alltid vill analysera samma objekt, oavsett om det är specifika kampanjer eller specifika dagar i veckan.

När du manuellt markerar och släpper specifika komponentvärden (dimension, mått, segment, datumintervall) i en tabell blir resultatet en statisk lista med rader eller kolumner. Du kan också skapa statiska dimensionsobjekt om du väljer att:

* Högerklicka på > [!UICONTROL Display only selected rows]
* Från kolumner högerklickar du > [!UICONTROL Make item static]

När du t.ex. drar över specifika objekt av typen Webbläsare, t.ex. Microsoft och Apple, hämtas alltid dessa två specifika objekt till tabellen.

Statiska dimensionsobjekt gör det **inte** har alternativet radfilter. Istället finns lås- och X-ikoner på varje objekt. Klicka på ikonen X om du vill ta bort dimensionsobjektet från tabellen.

![](assets/static-items.png)

## Blandade dimensionsobjekt

Dimensionsobjekt med olika dimensioner kan läggas till i samma tabell. Radrubriken säger &quot;Blandade dimensioner&quot; i dessa fall. De här dimensionsobjekten är statiska. Du kan till exempel lägga till specifika dimensionsobjekt från dimensionen Webbläsartyp och andra dimensionsobjekt från dimensionen Webbläsare.

![](assets/mixed-dimensions.png)

## Frigör totala rader

Dynamiska och statiska rader beter sig annorlunda i den totala frihandsraden. Som standard:

* Dynamiska rader summeras på serversidan och dubbletter, t.ex. besök eller besökare
* Statiska rader summeras på klientsidan och gör **inte** avduplicerade mått. Om du vill beräkna den totala radserversidan ändrar du radinställningen till **Visa totalsumma**. [Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html)

