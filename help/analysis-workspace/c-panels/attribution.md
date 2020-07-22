---
title: Panelen Attribution
description: Använda och tolka attribueringspanelen i Analysis Workspace.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---


# Panelen Attribution

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

attribueringspanelen är ett enkelt sätt att skapa en analys som jämför olika attribueringsmodeller. Det är en funktion i [Attribution IQ](../attribution/overview.md) som ger dig en dedikerad arbetsyta för att använda och jämföra attribueringsmodeller.

## Skapa en attribueringspanel

1. Klicka på panelikonen till vänster.
1. Dra panelen Attribution till ditt Analysis Workspace-projekt.

   ![Ny attribueringspanel](assets/Attribution_Panel_1.png)

1. Lägg till ett mätvärde som du vill attributera och lägg till en dimension till attributet mot. Exempel är marknadskanaler eller anpassade dimensioner, som interna kampanjer.

   ![Välj dimension och mått](assets/attribution_panel2.png)

1. Välj de [attribueringsmodeller och det uppslagsfönster](../attribution/models.md) som du vill jämföra.

1. Attributionspanelen returnerar en mängd data och visualiseringar som jämför attribuering för den valda dimensionen och det valda måttet.

   ![Attributionsvisualiseringar](assets/attr_panel_vizs.png)

## Attributionsvisualiseringar

* **Totalt mått**: Det totala antalet konverteringar som inträffade under rapporttidsperioden. Detta är de konverteringar som tilldelas för den dimension som du har valt.
* **Jämförelsetabell** för måttattribut: Jämför de tilldelade konverteringarna visuellt för var och en av dimensionsobjekten från den valda dimensionen. Varje stapelfärg representerar en distinkt attribueringsmodell.
* **Friformstabell** för måttattribut: Visar samma data som stapeldiagrammet, som en tabell. Om du markerar olika kolumner eller rader i den här tabellen filtreras stapeldiagrammet och flera andra visualiseringar i panelen. Den här tabellen fungerar på ungefär samma sätt som andra frihandstabeller i arbetsytan, vilket gör att du kan lägga till komponenter som mått, segment och uppdelningar.
* **Dimensionsöverlappningsdiagram**: Ett Venndiagram som visar de tre viktigaste dimensionsobjekten och hur ofta de deltar tillsammans i en konvertering. Storleken på bubbelöverlappningen anger till exempel hur ofta konverteringar inträffade när en besökare exponerades för båda dimensionsobjekten. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Marknadsföringskontaktytor per resa**: Ett histogram som anger hur många kontaktytor en besökare har i uppslagsfönstret. Det här är användbart om du vill se hur effektfull multitouch-attribuering är för din datauppsättning. Om nästan alla besökare bara har en enda kontaktyta visar olika attribueringsmodeller troligen liknande data.
* **Prestandainformation** för marknadsföringskanal: Gör att du kan jämföra upp till tre attribueringsmodeller visuellt med en punktdiagram.
* **Marknadsföringskanalflöde**: Gör att du kan se vilka kanaler som interagerar med de flesta, och i vilken ordning, på en besökares resa.
