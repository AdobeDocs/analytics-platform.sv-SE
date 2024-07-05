---
title: Attributionspanelen
description: Använda och tolka attribueringspanelen i Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: c89a28323c9d40a7265cd22994a0d1c484f4c7ee
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 14%

---

# Attributionspanelen {#attribution-panel}

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_button"
>title="Tillskrivning"
>abstract="Jämför och visualisera snabbt valfritt antal attribueringsmodeller med alla mått och konverteringsmått"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panelen Attribution IQ"

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_panel"
>title="Attributionspanelen"
>abstract="Jämför och visualisera snabbt valfritt antal attribueringsmodeller med alla mått och konverteringsvärden.<br/><br/>**Parametrar **<br/>**Kanal**<br/> Den dimension som ska attribut mot. Det kan vara marknadsföringskanaler, kampanjer eller andra dimensioner.<br/>**Models**<br/> Modellen avgör hur krediter tilldelas till kontaktytor.<br/>**Fönstret Lookback**<br/> Den här inställningen bestämmer fönstret för den dataattribuering som ska användas för varje konvertering."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panelen Attribution IQ"


The [!UICONTROL Attribution] är ett enkelt sätt att skapa en analys som jämför olika attribueringsmodeller. Det är en funktion som ger dig en dedikerad arbetsyta för att använda och jämföra attribueringsmodeller.

Customer Journey Analytics förbättrar attribueringen genom att låta dig:

* Definiera attribuering för mer än betalda medier: alla mått, mätvärden, kanaler och händelser kan användas i modellerna (till exempel intern sökning), inte bara marknadsföringskampanjer.
* Jämföra attribueringsmodeller utan begränsningar: jämför dynamiskt hur många modeller ni vill.
* Undvik implementeringsändringar: Med rapporttidsbearbetning och sammanhangsberoende sessioner kan kundens reskontext byggas in och tillämpas vid körning.
* Skapa den session som bäst matchar attribueringsscenariot.
* Dela upp attribuering med filter: Jämför enkelt resultatet i era marknadsföringskanaler i alla viktiga filter (t.ex. Nya kontra upprepade kunder, produkt X kontra produkt Y, lojalitetsnivå eller CLV).
* Granska analyser av kontaktytor och kanalbyten: använd venndiagram och histogram samt trendattribuering.
* Analysera viktiga marknadsföringssekvenser visuellt: utforska vägar som leder till konvertering visuellt med flernodsflöde och bortfallsvisualisering.
* Skapa beräknade värden: använd valfria metoder för attribueringstilldelning.

## Skapa en attribueringspanel

1. Klicka på panelikonen till vänster.
1. Dra [!UICONTROL Attribution] i Analysis Workspace Project.

   ![Fönstret Nytt projekt markerar panelen Attribution.](assets/Attribution_Panel_1.png)

1. Lägg till ett mätvärde som du vill attributera och lägg till en dimension till attributet mot. Exempel är marknadskanaler eller anpassade dimensioner, som interna kampanjer.

   ![Fönstret på panelen Attribution visar flera valda mått och mätvärden.](assets/attribution_panel2.png)

1. Välj de attribueringsmodeller och det uppslagsfönster som du vill jämföra.

1. Attributionspanelen returnerar en mängd data och visualiseringar som jämför attribuering för den valda dimensionen och det valda måttet.

   ![Attributpanelens visualiseringar som jämför valda mått och mått.](assets/attr_panel_vizs.png)

## Attributvisualiseringar

* **Totalt mått**: Det totala antalet konverteringar som inträffade under rapporttidsperioden. Detta är de konverteringar som tilldelas för den dimension som du har valt.
* **Attribution Comparison Bar**: Jämför visuellt de tilldelade konverteringarna för var och en av dimensionsobjekten från den valda dimensionen. Varje stapelfärg representerar en distinkt attribueringsmodell.
* **Jämförelsetabell för attribut**: Visar samma data som stapeldiagrammet, representerat som en tabell. Om du markerar olika kolumner eller rader i den här tabellen filtreras stapeldiagrammet och flera andra visualiseringar i panelen. Den här tabellen fungerar på ungefär samma sätt som andra frihandstabeller i Workspace, vilket gör att du kan lägga till komponenter som mått, filter och uppdelningar.
* **Överlappa diagram**: Ett Venndiagram som visar de tre viktigaste måttposterna och hur ofta de deltar tillsammans i en konvertering. Storleken på bubbelöverlappningen anger till exempel hur ofta konverteringar inträffade när en person exponerades för båda dimensionsobjekten. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Prestandainformation**: Gör att du kan jämföra upp till tre attribueringsmodeller visuellt med en punktdiagram.
* **Trendprestanda**: Visar trenden för konverteringar av attribut för den översta dimensionsobjektet. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Flöde**: Här kan du se vilka kanaler som interagerar med de vanligaste, och i vilken ordning, under en persons resa.
