---
description: Med ett interdimensionellt flöde kan du undersöka användarsökvägar i olika dimensioner.
title: Intradimensionella flöden
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
source-git-commit: ab30cd4e884dbf92d4148e8f81a638a8ea0b63f3
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Intradimensionella flöden

Med ett interdimensionellt flöde kan du undersöka användarsökvägar i olika dimensioner.

En dimensionsetikett högst upp i varje Flow-kolumn gör det mer intuitivt att använda flera dimensioner i en flödesvisualisering:

![Ett interdimensionellt flöde som framhäver flera dimensioner inklusive produkt, sida, OS-version och använd tid.](assets/flow.png)

Vi ska titta på två användningsfall: ett exempel på appanvändning och ett exempel på webbanvändning.

## Använd fall ett: app

The [!UICONTROL Action Name] dimension lades till i flödet, med den översta returnerade artikeln [!UICONTROL ItemAdded]:

![Ett flöde som visar det tillagda objektet.](assets/multi-dimensional-flow.png)

Om du vill utforska interaktionen mellan skärmar/sidor och åtgärder i den här appen kan du dra siddimensionen till flera platser, beroende på vad du vill utforska:

* Dra den till valfri ände av släppzonen (inuti den svarta trimmade rektangulära zonen som visas) för att **ersätt** de främsta resultaten i slutet:

  ![Ett flöde som visar sidmåttet som dras till de olika områdena.](assets/multi-dimensional-flow2.png) ![Flödesdiagram som visar de objekt som dras.](assets/multi-dimensional-flow3.png)

* Dra den till det tomma utrymmet på slutet (lägg märke till den svarta parentesen) för att **lägg till i** visualisering:

  ![Ett flöde som visar sidmåttet som dras till det tomma utrymmet i slutet.](assets/multi-dimensional-flow4.png)

Här är resultatet om du bestämmer dig för att ersätta ItemScaled-objektet i den högra kolumnen med Page-dimensionen. Det översta resultatet ändras nu till det översta resultatet för siddimensionen:

![En fLow som visar siddimensionens resultat högst upp i listan.](assets/multi-dimensional-flow5.png)

Nu kan ni se hur kunderna rör sig genom åtgärder och sidor. Du kan utforska flödet ytterligare genom att klicka på olika noder:

![Ett flöde som visar objekt som lagts till, objekt som dragits och huvudvyn.](assets/multi-dimensional-flow6.png)

Detta är vad som händer om du lägger till en annan Action Name-dimension i slutet av visualiseringen:

![Ett flöde som visar åtgärdsnamnet som lagts till.](assets/multi-dimensional-flow7.png)

Detta ger vissa djupgående insikter och möjlighet att ändra appen som du analyserar.

## Använd fall två: webb

Det här användningsexemplet visar hur ni kan analysera vilka kampanjer som leder till flest poster på en webbplats.

Dra Campaign Name-dimensionen till ett nytt flöde:

![Ett flöde som visar dimensionen Kampanjnamn som dras till ett nytt flöde.](assets/multi-dimensional-flow8.png)

Nu vill jag se till vilka sidor dessa kampanjer genererar trafik, så jag drar siddimensionen åt höger om flödesresultaten för att lägga till ytterligare i visualiseringen:

![Ett flöde som visar siddimensionen som dras till höger om flödesresultaten.](assets/multi-dimensional-flow9.png)
