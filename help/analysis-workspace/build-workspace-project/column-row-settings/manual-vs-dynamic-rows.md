---
title: Dynamiska eller statiska dimensionsvärden
description: Hur man interagerar med dynamiska och statiska dimensionsvärden i tabeller.
translation-type: tm+mt
source-git-commit: 0477302df92ccab30d9f3a45cc7b22f2112a0c70
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 2%

---


# Dynamiska eller statiska dimensionsvärden i frihandstabeller

>[!NOTE] Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

I frihandstabeller kan raderna och kolumnerna innehålla olika komponentvärden. Dessa värden kan vara dynamiska (ändras med tid) eller statiska (ändras inte med tid), beroende på vilken analys du vill skapa.

## Dynamiska dimensionsvärden

Dynamiska dimensionsvärden ändras med tiden och är beroende av vilket mått som sorteras i friformstabellen. Dynamiska dimensionsvärden är att föredra när du vill analysera de översta artiklarna för en given tidsperiod.

När du släpper en dimension i en frihandstabell returneras dynamiska rader. De representerar de översta artiklarna som motsvarar dimensionen för ett givet mätvärde och en viss tidsperiod. Du kan också släppa en dimension i tabellkolumner på fri hand, och dimensionen utökas automatiskt till de fem övre dimensionsvärdena.

När du t.ex. drar dimensionen Webbläsartyp till tabellen visas de översta dimensionerna för Webbläsartyp (t.ex. Microsoft, Apple, Google) Återgå dynamiskt till tabellraderna. Om de utelämnas i en kolumn returneras dimensionerna för de fem vanligaste webbläsartyperna dynamiskt.

Dynamiska dimensionsvärden har radfilteralternativet och har **inga** lås- och X-ikoner.

## Statiska dimensionsvärden

Statiska dimensionsvärden ändras inte med tiden. de är fasta komponenter som alltid returneras i en frihandstabell. Statiska dimensionsvärden är att föredra när du alltid vill analysera samma artikel, oavsett om det är specifika kampanjer eller specifika dagar i veckan.

Varje gång du manuellt markerar och släpper specifika komponentvärden (mått, mått, segment, datumintervall) i en tabell blir resultatet en statisk lista med rader eller kolumner. Statiska dimensionsvärden kan också skapas om du väljer att:

* Högerklicka från rader > [!UICONTROL Display only selected rows]
* Högerklicka från kolumner > [!UICONTROL Make item static]

Om du t.ex. drar över vissa objekt i webbläsartypen, t.ex. Microsoft och Apple, hämtas dessa två objekt alltid till tabellen.

Statiska dimensionsvärden har **inte** radfilteralternativet. Istället visas lås- och X-ikoner för varje objekt. Klicka på X-ikonen för att ta bort det måttvärdet från tabellen.

## Blandade dimensionsvärden

Dimensionsvärden från olika dimensioner kan läggas till i samma tabell. Radhuvudet säger&quot;Blandade dimensioner&quot; i dessa fall. Dessa dimensionsvärden är statiska. Du kan till exempel lägga till specifika dimensionsvärden från dimensionen Webbläsartyp och andra dimensionsvärden från dimensionen Webbläsare.

## Frihandsrader

Dynamiska och statiska rader fungerar på olika sätt i den totala frihandsraden. Som standard:

* Dynamiska rader summeras på serversidan och dubblettvärden som besök och besökare tas bort
* Statiska rader summeras på klientsidan och dubbletter tas **inte** bort.

[Läs mer om alternativen för total](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) arbetsyta för dynamiska och statiska rader.
