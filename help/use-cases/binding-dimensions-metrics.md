---
title: Använda bindningsdimensioner och mätvärden i CJA
description: Attributdimensioner till objektarrayer för komplex beständighetsanalys.
source-git-commit: b93809c9af02227295c9dd66565f04675236c393
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---


# Använda bindningsdimensioner och mätvärden i CJA

Customer Journey Analytics erbjuder flera sätt att behålla dimensionsvärden efter den träff som de är inställda på. En av de beständighetsmetoder som Adobe erbjuder kallas bindning. I tidigare versioner av Adobe Analytics kallades detta koncept försäljning.

Även om du kan använda bindningsdimensioner med händelsedata på den översta nivån är detta koncept bäst när du arbetar med [Arrayer med objekt](object-arrays.md). Du kan tilldela en dimension till en del av en objektarray utan att använda den på alla attribut i en viss händelse. Du kan t.ex. tilldela en sökterm till en produkt i kundvagnens objektmatris utan att binda söktermen till hela händelsen.

## Exempel 2: Använda bindningsmått för att koppla söktermen till ett produktköp

En av de vanligaste försäljningsmetoderna i Adobe Analytics har varit att binda en sökterm till en produkt så att varje sökterm får erkännande för den produkt som passar bäst. Tänk på följande kundresa:

1. En besökare kommer till er webbplats och söker efter &quot;boxingshandskar&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. De hittar ett par handskar som de gillar och lägger till dem i kundvagnen.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. Besökaren söker sedan efter &quot;tennisracket&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. De hittar ett racket de gillar och lägger det i kundvagnen.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. Besökaren söker en tredje gång efter &quot;skor&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. De hittar ett par skor de gillar och lägger till dem i kundvagnen.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. Besökaren går igenom utcheckningsprocessen och köper dessa tre artiklar.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

Om du använder en traditionell allokeringsmodell med sökord, tilldelar alla tre produkterna intäkter till endast ett sökord. Om du till exempel använde första allokeringen med söktermsdimensionen:

| search_term | intäkt |
| --- | --- |
| boxingshandskar | $204.97 |

Om du använde den senaste allokeringen med söktermdimensionen tilldelar alla tre produkterna fortfarande intäkter till en enda sökterm:

| search_term | intäkt |
| --- | --- |
| skor | $204.97 |

Det här exemplet innehåller bara en besökare, men många besökare som söker efter olika saker kan feltilldela söktermer till olika produkter, vilket gör det svårt att avgöra vilka sökresultat som är bäst.

Med en bindningsdimension noterar Adobe vilken dimensionsartikel den är bunden till. När samma bindningsvärde visas i en efterföljande händelse, förs dimensionsobjektet över så att du kan tilldela det önskade måttet till det. I det här exemplet kan vi ange bindningsdimensionen för search_term till produktnamn:

![Bindningsdimension](assets/binding-dimension.png)

När vi anger den här dimensionen i Data View Manager måste vi också ange ett bindningsmått eftersom bindningsdimensionen finns i en objektmatris. Ett bindningsmått fungerar som en utlösare för en bindningsdimension, så det binder sig bara till händelser där det finns ett bindningsmått. I den här exempelimplementeringen innehåller sökresultatsidan alltid en sökterm och ett sökmått. Vi kan binda söktermer till produktnamn när sökstatistiken finns.

![Bindningsmått](assets/binding-metric.png)

Om du ställer in söktermsdimensionen på den här beständiga modellen körs följande logik:

* När search_term är i en händelse, kontrollera om det finns något produktnamn.
* Om produktnamnet inte finns där, gör ingenting.
* Om det finns ett produktnamn kontrollerar du om det finns något sökmått.
* Om sökstatistiken inte finns där, gör ingenting.
* Om sökstatistiken finns där binder du söktermen till alla produktnamn. Det fungerar som om det vore på samma nivå som produktnamnet för den händelsen. I det här exemplet behandlas det som product.search_term.
* Om samma produktnamn visas i en efterföljande händelse finns den bundna söktermen också där.

I Analysis Workspace ser resultatet ut ungefär så här:

| search_term | intäkt |
| --- | --- |
| boxingshandskar | 89,99 USD |
| tennisracket | 34,99 USD |
| skor | 79,99 USD |
