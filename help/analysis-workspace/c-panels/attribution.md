---
title: Panelen Attribution
description: Använda och tolka attribueringspanelen i Analysis Workspace.
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---

# Panelen Attribution

Panelen [!UICONTROL Attribution] är ett enkelt sätt att skapa en analys som jämför olika attribueringsmodeller. Det är en funktion i [Attribution IQ](../attribution/overview.md) som ger dig en dedikerad arbetsyta för att använda och jämföra attribueringsmodeller.

## Skapa en attribueringspanel

1. Klicka på panelikonen till vänster.
1. Dra panelen [!UICONTROL Attribution] till ditt Analysis Workspace-projekt.

   ![Ny attribueringspanel](assets/Attribution_Panel_1.png)

1. Lägg till ett mätvärde som du vill attributera och lägg till en dimension till attributet mot. Exempel är marknadskanaler eller anpassade dimensioner, som interna kampanjer.

   ![Välj dimension och mått](assets/attribution_panel2.png)

1. Välj de [attribueringsmodeller och uppslagsfönster](../attribution/models.md) som du vill jämföra.

1. Attributpanelen returnerar en mängd data och visualiseringar som jämför attribuering för den valda dimensionen och måttet.

   ![Attributionsvisualiseringar](assets/attr_panel_vizs.png)

## Attributionsvisualiseringar

* **Totalt mått**: Det totala antalet konverteringar som inträffade under rapporttidsperioden. Detta är de konverteringar som tilldelas för den dimension som du har valt.
* **Attribution Comparison Bar**: Jämför de tilldelade konverteringarna visuellt för var och en av dimensionsobjekten från den valda dimensionen. Varje stapelfärg representerar en distinkt attribueringsmodell.
* **Attributjämförelsetabell**: Visar samma data som stapeldiagrammet, som en tabell. Om du markerar olika kolumner eller rader i den här tabellen filtreras stapeldiagrammet och flera andra visualiseringar i panelen. Den här tabellen fungerar på ungefär samma sätt som andra frihandstabeller i arbetsytan, vilket gör att du kan lägga till komponenter som mått, filter och uppdelningar.
* **Överlappningsdiagram**: Ett Venndiagram som visar de tre viktigaste dimensionsobjekten och hur ofta de deltar tillsammans i en konvertering. Storleken på bubbelöverlappningen anger till exempel hur ofta konverteringar inträffade när en besökare exponerades för båda dimensionsobjekten. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Prestandainformation**: Gör att du kan jämföra upp till tre attribueringsmodeller visuellt med en punktdiagram.
* **Trendprestanda**: Visar trenden för allokerade konverteringar för den översta dimensionsobjektet. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Flöde**: Gör att du kan se vilka kanaler som interagerar med de flesta, och i vilken ordning, på en besökares resa.
