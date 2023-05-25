---
title: Använd bindningsdimensioner och mätvärden i CJA
description: Attributdimensioner till objektarrayer för komplex beständighetsanalys.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 71c633f259b25f30d474ab19f714935b074dfc0c
workflow-type: tm+mt
source-wordcount: '1328'
ht-degree: 1%

---


# Använd bindningsdimensioner och mätvärden i CJA

Customer Journey Analytics erbjuder flera sätt att behålla dimensionsvärden efter den träff som de är inställda på. En av de beständighetsmetoder som Adobe erbjuder kallas bindning. I tidigare versioner av Adobe Analytics kallades detta koncept försäljning.

Även om du kan använda bindningsdimensioner med händelsedata på den översta nivån är detta koncept bäst när du arbetar med [Arrayer med objekt](/help/use-cases/object-arrays.md). Du kan tilldela en dimension till en del av en objektarray utan att använda den på alla attribut i en viss händelse. Du kan t.ex. tilldela en sökterm till en produkt i kundvagnens objektmatris utan att binda söktermen till hela händelsen.

## Exempel 1: Använd bindningsdimensioner för att tilldela ytterligare produktattribut till ett inköp

Du kan binda dimensionsobjekt inom en objektarray till en annan dimension. När den bundna dimensionsobjektet visas, kommer CJA tillbaka den bundna dimensionen och inkluderar den i händelsen för dig. Tänk på följande kundresa:

1. En besökare ser en produktsida på en tvättmaskin.

   ```json
   {
       "PersonID": "1",
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. Besökaren visar sedan en produktsida på en torktumlare.

   ```json
   {
       "PersonID": "1",
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. I slutändan handlar de om ett inköp. Färgen på varje produkt ingick inte i köphändelsen.

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

Om du vill se intäkt per färg utan en bindande dimension, dimensionen `product.color` Bevaras och attribuerar felaktigt tillgodoräknande av torktumlarens färg:

| product.color | intäkt |
| --- | --- |
| neon orange | 2099 |

Du kan gå till datavyhanteraren och binda produktfärg till produktnamn:

![Bindningsdimension](../assets/binding-dimension.png)

När du anger den här beständighetsmodellen tar CJA hänsyn till produktnamnet när produktfärgen anges. När den känner igen samma produktnamn i en efterföljande händelse för den här personen, hämtas även produktfärgen. Samma data skulle se ut ungefär så här när du binder produktfärg till produktnamn:

| product.color | intäkt |
| --- | --- |
| vit | 1600 |
| neon orange | 499 |

## Exempel 2: Använd bindningsmått för att koppla söktermen till ett produktköp

En av de vanligaste försäljningsmetoderna i Adobe Analytics har varit att binda en sökterm till en produkt så att varje sökterm får erkännande för den produkt som passar bäst. Tänk på följande kundresa:

1. En besökare kommer till er webbplats och söker efter &quot;boxingshandskar&quot;. Sökmåtten stegvis ökas med ett och de tre översta sökresultaten visas.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
           },
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Professional gloves",
           }
       ]
   }
   ```

2. De hittar ett par handskar som de gillar och lägger till dem i kundvagnen.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           }
       ]
   }
   ```

3. Besökaren söker sedan efter &quot;tennisracket&quot;. Sökmåtten stegvis ökas med ett och de tre översta sökresultaten visas.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Women's open racket",
           },
           {
               "name": "Extreme racket",
           }
       ]
   }
   ```

4. De hittar ett racket de gillar och lägger det i kundvagnen.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           }
       ]
   }
   ```

5. Besökaren söker en tredje gång efter &quot;skor&quot;. Sökmåtten stegvis ökas med ett och de tre översta sökresultaten visas.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
           },
           {
               "name": "Tennis shoes",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

6. De hittar ett par skor de gillar och lägger till dem i kundvagnen.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

7. Besökaren går igenom utcheckningsprocessen och köper dessa tre artiklar.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "price": "79.99"
           }
       ]
   }
   ```

Om du använder en allokeringsmodell som inte innehåller någon bindningsdimension med söktermen, tilldelar alla tre produkterna intäkter endast till en enda sökterm. Om du till exempel använde [!UICONTROL Original] allokering med söktermdimensionen:

| search_term | intäkt |
| --- | --- |
| boxingshandskar | $204.97 |

Om du använt [!UICONTROL Most Recent] allokering med söktermsdimensionen tilldelar alla tre produkterna fortfarande intäkter till en enda sökterm:

| search_term | intäkt |
| --- | --- |
| skor | $204.97 |

Det här exemplet innehåller bara en person, men många som söker efter olika saker kan feltilldela söktermer till olika produkter, vilket gör det svårt att avgöra vilka sökresultat som är bäst.

Du kan binda söktermer till produktnamn när sökningsmåttet finns för att korrekt tilldela söktermer intäkter.

![Bindningsmått](../assets/binding-metric.png)

I Analysis Workspace ser resultatet ut ungefär så här:

| search_term | intäkt |
| --- | --- |
| boxingshandskar | $89.99 |
| tennisracket | $34.99 |
| skor | $79.99 |

CJA identifierar automatiskt relationen mellan den valda dimensionen och bindningsdimensionen. Om bindningsdimensionen finns i en objektmatris när den valda dimensionen är på en högre nivå, krävs ett bindningsmått. Ett bindningsmått fungerar som en utlösare för en bindningsdimension, så det binder sig bara till händelser där det finns ett bindningsmått. I ovanstående exempel innehåller sökresultatsidan alltid en sökterm och ett sökmått.

Om du ställer in söktermsdimensionen på den här beständiga modellen körs följande logik:

* När söktermdimensionen är inställd kontrollerar du om det finns något produktnamn.
* Om produktnamnet inte finns där, gör ingenting.
* Om det finns ett produktnamn kontrollerar du om det finns något sökmått.
* Om sökstatistiken inte finns där, gör ingenting.
* Om sökstatistiken finns där binder du söktermen till alla produktnamn i den händelsen. Den kopierar sig själv till samma nivå som produktnamnet för händelsen. I det här exemplet behandlas det som product.search_term.
* Om samma produktnamn visas i en efterföljande händelse överförs den bundna söktermen även till den händelsen.

## Exempel 3: Bind söktermen för video till användarprofilen

Du kan binda en sökterm till en användarprofil så att persistensen mellan profiler förblir helt åtskild. Din organisation kör till exempel en direktuppspelningstjänst där ett övergripande konto kan ha flera profiler. Besökaren har en underordnad profil och en vuxenprofil.

1. Kontot loggar in under den underordnade profilen och söker efter ett barns TV-program. Observera att `"ProfileID"` är `2` som representerar den underordnade profilen.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "Searches": "1",
       "search_term": "kids show"
   }
   ```

1. De hittar programmet &quot;Orangey&quot; och spelar det så att deras barn kan se det.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

1. Senare den kvällen växlar den överordnade till sin profil och söker efter vuxeninnehåll att titta på. Observera att `"ProfileID"` är `1` som representerar vuxenprofilen. Båda profilerna tillhör samma konto, som representeras av samma `"PersonID"`.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "1",
       "Searches": "1",
       "search_term": "grownup movie"
   }
   ```

1. Filmen&quot;Analytics After Hours&quot; visas och njuter av sin kväll när de tittar på den.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "1",
       "ShowName": "Analytics After Hours",
       "VideoStarts": "1"
   }
   ```

1. Nästa dag fortsätter de att visa &quot;Orangey&quot; för sina barn. De behöver inte söka eftersom de nu redan är medvetna om programmet.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

Om du använder den senaste allokeringen med förfallodatum för person visas `"grownup movie"` söktermen är den sista vyn i barnshowen.

| Sökterm | Videon startar |
| --- | --- |
| gruppfilm | 2 |
| barnshow | 1 |

Om du binder `search_term` till `ProfileID`, skulle varje profils sökningar isoleras till sin egen profil, vilket tillskrivs de rätta visar att de söker efter.

![Besökarbindning](../assets/binding-visitor.png)

Analysis Workspace attribuerar det andra avsnittet av Orangey korrekt till söktermen `"kids show"` utan att ta hänsyn till sökningar från andra profiler.

| Sökterm | Videon startar |
| --- | --- |
| barnshow | 2 |
| gruppfilm | 1 |

## Exempel 4: Utvärdera webbläsarbeteende jämfört med sökbeteenden i en detaljhandelsinställning

Du kan binda värden till dimensioner som angetts för tidigare händelser. När du anger en variabel med en bindningsdimension, tar CJA hänsyn till det beständiga värdet. Om du inte vill använda det här beteendet kan du justera bindningsdimensionens beständighetsinställningar. Titta på följande exempel där `product_finding_method` anges för en händelse och binds sedan till Cart Adds-måttet för följande händelse.

1. En besökare söker efter `"camera"`. Observera att inga produkter har angetts på den här sidan.

   ```json
   {
       "search_term": "camera",
       "product_finding_method": "search"
   }
   ```

1. De klickar på en kamera de gillar och lägger in den i kundvagnen.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. Besökaren bläddrar sedan in i manskategorin utan att göra en sökning. Observera att inga produkter har angetts på den här sidan.

   ```json
   {
       "category": "Men's belts",
       "product_finding_method": "browse"
   }
   ```

1. De klickar på ett bälte de gillar och lägger till det i kundvagnen.

   ```json
   {
       "Product": [
           {
               "name": "Ratchet belt"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. De går igenom utcheckningsprocessen och köper dessa två artiklar.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera",
               "price": "399.99"
           },
           {
               "name": "Ratchet belt",
               "price": "19.99"
           }
       ],
       "Purchase": "1"
   }
   ```

Om beständighet anges till den senaste allokeringen utan någon bindande dimension, kommer alla intäkter på 419,98 USD att tillskrivas `browse` sökmetod.

| Produktsökningsmetod | Intäkter |
| --- | --- |
| bläddra | 419.98 |

Om beständighet anges med ursprunglig allokering utan en bindande dimension, fördelas alla 419,98 USD av intäkten på `search` sökmetod.

| Produktsökningsmetod | Intäkter |
| --- | --- |
| sök | 419.98 |

Men om du binder `product_finding_method` I Cart Adds-måttet kopplas varje produkt till rätt sökmetod.

| Produktsökningsmetod | Intäkter |
| --- | --- |
| sök | 399.99 |
| bläddra | 19.99 |
