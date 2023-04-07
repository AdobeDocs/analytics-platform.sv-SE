---
title: Panelen Attribution
description: Använda och tolka attribueringspanelen i Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
source-git-commit: c21eb39e0af36ad54fd675c147e2f50b6b00711a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Panelen Attribution

The [!UICONTROL Attribution] är ett enkelt sätt att skapa en analys som jämför olika attribueringsmodeller. Det är en funktion som ger dig en dedikerad arbetsyta att använda och jämföra attribueringsmodeller.

Customer Journey Analytics förbättrar attribueringen genom att låta dig:

* Definiera attribuering för mer än betalda medier: alla mått, mätvärden, kanaler och händelser kan användas i modellerna (till exempel intern sökning), inte bara marknadsföringskampanjer.
* Jämföra attribueringsmodeller utan begränsningar: jämför dynamiskt hur många modeller ni vill.
* Undvika implementeringsändringar: med hjälp av rapporttidshantering och sammanhangsberoende sessioner kan kundresan byggas in och användas vid körning.
* Skapa den session som bäst matchar attribueringsscenariot.
* Dela upp attribuering med filter: Jämför enkelt resultatet i era marknadsföringskanaler i alla viktiga filter (t.ex. nya jämfört med upprepade kunder, produkt X jämfört med produkt Y, lojalitetsnivå eller CLV).
* Granska analyser av kontaktytor och kanalbyten: använd venndiagram och histogram samt trendattribuering.
* Analysera viktiga marknadsföringssekvenser visuellt: utforska vägar som leder till konvertering visuellt med flernodsflöde och bortfallsvisualisering.
* Skapa beräknade värden: använd valfria metoder för attribueringstilldelning.

## Skapa en attribueringspanel

1. Klicka på panelikonen till vänster.
1. Dra [!UICONTROL Attribution] i Analysis Workspace Project.

   ![Ny attribueringspanel](assets/Attribution_Panel_1.png)

1. Lägg till ett mätvärde som du vill attributera och lägg till en dimension till attributet mot. Exempel är marknadskanaler eller anpassade dimensioner, som interna kampanjer.

   ![Välj dimension och mått](assets/attribution_panel2.png)

1. Välj de attribueringsmodeller och det uppslagsfönster som du vill jämföra.

1. Attributpanelen returnerar en mängd data och visualiseringar som jämför attribuering för den valda dimensionen och måttet.

   ![Attributionsvisualiseringar](assets/attr_panel_vizs.png)

## Attributionsvisualiseringar

* **Totalt mått**: Det totala antalet konverteringar som inträffade under rapporttidsperioden. Detta är de konverteringar som tilldelas för den dimension som du har valt.
* **Attribution Comparison Bar**: Jämför de tilldelade konverteringarna visuellt för var och en av dimensionsobjekten från den valda dimensionen. Varje stapelfärg representerar en distinkt attribueringsmodell.
* **Jämförelsetabell för attribuering**: Visar samma data som stapeldiagrammet, som en tabell. Om du markerar olika kolumner eller rader i den här tabellen filtreras stapeldiagrammet och flera andra visualiseringar i panelen. Den här tabellen fungerar på ungefär samma sätt som andra frihandstabeller i arbetsytan, vilket gör att du kan lägga till komponenter som mått, filter och uppdelningar.
* **Överlappa diagram**: Ett Venndiagram som visar de tre viktigaste dimensionsobjekten och hur ofta de deltar tillsammans i en konvertering. Storleken på bubbelöverlappningen anger till exempel hur ofta konverteringar inträffade när en besökare exponerades för båda dimensionsobjekten. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Prestandainformation**: Gör att du kan jämföra upp till tre attribueringsmodeller visuellt med en punktdiagram.
* **Trendprestanda**: Visar trenden för allokerade konverteringar för den översta dimensionsobjektet. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Flöde**: Gör att du kan se vilka kanaler som interagerar med de flesta, och i vilken ordning, på en besökares resa.
