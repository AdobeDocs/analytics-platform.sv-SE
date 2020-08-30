---
title: Panelen Attribution
description: Hur du använder och tolkar attributpanelen i Analysis Workspace.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---


# Panelen Attribution

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Tilldelningspanelen är ett enkelt sätt att skapa en analys som jämför olika tilldelningsmodeller. Det är en funktion i [Attribut-IQ](../attribution/overview.md) som ger dig en dedikerad arbetsyta att använda och jämföra attributmodeller.

## Skapa en attributpanel

1. Klicka på panelikonen till vänster.
1. Dra attributpanelen till Analysis Workspace-projektet.

   ![Ny attributpanel](assets/Attribution_Panel_1.png)

1. Lägg till ett mått som du vill tilldela och lägg till en dimension i attributet mot. Exempel är marknadsföringskanaler eller anpassade dimensioner, t.ex. interna befordringar.

   ![Välj dimension och mått](assets/attribution_panel2.png)

1. Välj [attributmodeller och granskningsfönster](../attribution/models.md) du vill jämföra.

1. Attributpanelen returnerar en rik uppsättning data och visualiseringar som jämför attribut för den valda dimensionen och måttet.

   ![Betygsvisualiseringar](assets/attr_panel_vizs.png)

## Betygsvisualiseringar

* **Totalt mått**: Det totala antalet konverteringar som inträffade under rapporttidsfönstret. Detta är konverteringarna som tilldelas för den valda dimensionen.
* **Diagram för jämförelse av metriska attribut**: Visuellt jämför de tilldelade konverteringarna för var och en av dimensionsobjekten från den valda dimensionen. Varje stapelfärg representerar en särskild attributmodell.
* **Freeform-tabell för måttattribut**: Visar samma data som stapeldiagrammet, representerat som en tabell. Om du markerar olika kolumner eller rader i den här tabellen filtreras stapeldiagrammet och flera av de andra visualiseringarna på panelen. Den här tabellen fungerar på samma sätt som alla andra frihandstabeller på arbetsytan. Du kan lägga till komponenter som mått, segment eller indelningar.
* **Delat diagram för dimension**: Ett Venndiagram som visar de tre viktigaste dimensionsobjekten och hur ofta de deltar tillsammans i en konvertering. Exempelvis anger storleken på bubbelöverlappningen hur ofta konverteringar inträffade när en besökare exponerades för båda dimensionsobjekten. Om du markerar andra rader i den angränsande Freeform-tabellen uppdateras visualiseringen så att den återspeglar ditt val.
* **Marknadsföringspunkter per resa**: Ett histogram som anger antalet beröringspunkter som besökaren hade i uppslagsfönstret. Detta är användbart om du vill se hur skadlig multipektilldelningen är för datauppsättningen. Om nästan alla besökare bara har en enda beröringspunkt visar olika tilldelningsmodeller troligen liknande data.
* **Information om kanalprestanda för marknadsföring**: Gör att du kan jämföra upp till tre attributmodeller visuellt med hjälp av en spridningspunkt.
* **Marknadsföringskanalflöde**: Gör att du kan se vilka kanaler som interagerar med oftast, och i vilken ordning över besökarens resa.
