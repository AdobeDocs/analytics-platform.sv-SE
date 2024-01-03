---
description: Visa dina data i Analysis Workspace.
keywords: Analysis Workspace
title: Visualiseringar - översikt
feature: Visualizations
exl-id: ca9e0561-7a54-487a-9fdc-3bcf34f9bdb1
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1314'
ht-degree: 1%

---

# Visualiseringar - översikt

Workspace erbjuder ett antal visualiseringar som gör att du kan generera visuella representationer av dina data, t.ex. stapeldiagram, dondiagram, histogram, linjediagram, kartor, punktdiagram med mera. De flesta visualiseringstyper är välbekanta för dig om du använder Customer Journey Analytics. Men Analysis Workspace har visualiseringsinställningar och många nya eller unika visualiseringstyper med interaktiva funktioner.

## Visualiseringstyper

Följande visualiseringstyper finns i Analysis Workspace:

| Visualiseringsnamn | Beskrivning |
| --- | --- | 
| [Område](/help/analysis-workspace/visualizations/area.md)<p>![Ikon för område](assets/Smock_GraphArea_18_N.svg)</p> | Som ett linjediagram, men med ett färgat område under linjen. Använd ett ytdiagram när du har flera mätvärden och vill visualisera området som uttrycks genom skärningspunkten för två eller flera mätvärden. | Svar: <ul><li> |
| [Liggande](/help/analysis-workspace/visualizations/bar.md) <p>![Ikon för stapel](assets/Smock_GraphBarVertical_18_N.svg)</p> | Visar lodräta staplar som representerar olika värden för ett eller flera mätvärden. |
| [Punktdiagram](/help/analysis-workspace/visualizations/bullet-graph.md) <p>![Punktlikon](assets/Smock_GraphBullet_18_N.svg)</p> | Visar hur ett värde som du är intresserad av jämförs med eller mäter mot andra prestandaintervall (mål). |
| [Kohortabell](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)<p>![Kohortabellikon](assets/Smock_TextNumbered_18_N.svg)</p> | A *`cohort`* är en grupp personer som delar gemensamma egenskaper under en angiven period. Kohortanalys är användbart för analys av kvarhållande, bortfall eller fördröjning. |
| [Ringdiagram](/help/analysis-workspace/visualizations/donut.md) <p>![Ringformsikon](assets/Smock_GraphDonut_18_N.svg)</p> | På samma sätt som ett cirkeldiagram visar den här visualiseringen data som delar eller filter av en helhet. |
| [Utfall](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)<p>![Utfallsikon](assets/Smock_ConversionFunnel_18_N.svg)</p> | Utfallsrapporter visar var personer lämnade (föll ut) och fortsatte igenom (föll igenom) en fördefinierad sidsekvens. Kan anges till sekvenser av typen slutlig eller exakt |
| [Flöde](/help/analysis-workspace/visualizations/c-flow/flow.md)<p>![Flödesikon](assets/flow-icon.png)</p> | Visar exakta kundvägar via era webbplatser och appar. |
| [Frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)<p>![Ikon för frihandstabell](assets/Smock_ViewTable_18_N.svg)</p> | En friformstabell är inte bara en datatabell, utan också en interaktiv visualisering. Det är grunden för dataanalys i Workspace. |
| [Histogram](/help/analysis-workspace/visualizations/histogram.md)<p>![Histogram, ikon](assets/Smock_GraphHistogram_18_N.svg)</p> | Ett histogram spänner över personer, besök eller händelser i grupper baserat på en mätvolym. |
| [Vågrätt fält](/help/analysis-workspace/visualizations/horizontal-bar.md)<p>![Ikon för vågrätt fält](assets//Smock_GraphBarHorizontal_18_N.svg)</p> | Visar vågräta staplar som representerar olika värden för ett eller flera mätvärden. |
| [Linjediagram](/help/analysis-workspace/visualizations/line.md)<p>![Linjeikon](assets/Smock_GraphTrend_18_N.svg)</p> | Representerar mätvärden med hjälp av en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram använder tid längs x-axeln. |
| [Spridningsdiagram](/help/analysis-workspace/visualizations/scatterplot.md) <p>![Scatplot, ikon](assets/Smock_GraphScatter_18_N.svg)</p> | Visar relationen mellan dimensionsobjekt och upp till tre mätvärden. |
| [Sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md)<p>![Ikon för summeringsnummer](assets/summary-number-icon.png)</p> | Visar den markerade cellen som ett stort tal. |
| [Sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md)<p>![Ikon för ändring av sammanfattning](assets/summary-change-icon.png)</p> | Visar ändringen mellan de markerade cellerna som ett stort tal/procent. |
| [Text](/help/analysis-workspace/visualizations/text.md)<p>![Scatplot, ikon](assets/Smock_Text_18_N.svg)</p> | Gör att du kan lägga till användardefinierad text på arbetsytan. Användbar för att lägga till ytterligare kontext till analyser och insikter, utöver att utnyttja beskrivningar av paneler/visualisering |
| [Treemap-diagram](/help/analysis-workspace/visualizations/treemap.md)<p>![Treemap, ikon](assets/Smock_GraphTree_18_N.svg)</p> | Visar hierarkiska (trädstrukturerade) data som en uppsättning kapslade rektanglar. |
| [Venn](/help/analysis-workspace/visualizations/venn.md)<p>![Vennikon](assets/venn-icon.png)</p> | Använder cirklar för att beskriva måttöverlappningen för upp till 3 filter. |

## Lägga till visualiseringar i en panel

1. Öppna det Analysis Workspace-projekt där du vill lägga till en visualisering.

1. Använd någon av följande metoder för att lägga till visualiseringen:

   * I den vänstra listen väljer du **Visualiseringar** icon <!-- add icon -->och sedan dra en visualisering till panelen där du vill lägga till den.

     ![Panelen Visualiseringar](assets/viz-rail.png)

   * På panelen där du vill lägga till visualiseringen väljer du **Plus** väljer du sedan den ikon som representerar den visualisering som du vill lägga till. Håll pekaren över ikonen för varje visualisering för att se dess namn.

     ![Knapp för att lägga till en visualisering](assets/visualization-add-to-panel.png)

   * Lägg till en [tom panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html)väljer du sedan den visualisering som du vill lägga till.

     ![Tom panel](assets/blank_panel.png)

   * Högerklicka på en befintlig panel i ditt Analysis Workspace-projekt och välj sedan [!UICONTROL **Duplicera visualisering**] eller [!UICONTROL **Kopiera visualisering**].

## Anpassa visualiseringsinställningar

Du kan anpassa visualiseringsinställningar för en enskild visualisering eller för alla visualiseringar som du skapar.

### Anpassa visualiseringsinställningar för en enda visualisering

För åtkomst [!UICONTROL Visualization Settings] för en enskild visualisering:

1. I Analysis Workspace håller du muspekaren över den visualisering vars inställningar du vill anpassa.

1. Klicka på kugghjulet.

   Varje typ av visualisering har unika inställningar som du kan anpassa. Mer information om tillgängliga inställningar finns i [Inställningar](#settings).

### Anpassa visualiseringsinställningar för alla visualiseringar du skapar

Du kan anpassa inställningarna för alla visualiseringar som du skapar. Mer information finns i [Användarinställningar](/help/analysis-workspace/user-preferences.md).

## Inställningar {#settings}

Varje visualisering har sina egna inställningar som du kan hantera. För åtkomst [!UICONTROL Visualization Settings]klickar du på [!UICONTROL Visualization Settings] kugghjulsikon.

![Visualiseringsinställningar som visar de inställningsalternativ som beskrivs i nästa avsnitt.](assets/settings.png)

| Inställning | Beskrivning |
| --- | --- |
| Visualiseringstyp | Ändra den typ av visuell information som används för att avbilda data. |
| Kornighet | För trendvisualiseringar kan du ändra tidshalten (dag, vecka, månad osv.) från den här listrutan. Den här ändringen gäller även för datakälltabellen. |
| Procenttal | Visar värden i procent. |
| 100 % staplad | Den här inställningen för staplade ytor, staplade staplade staplar eller vågräta staplade visualiseringar gör att diagrammet blir en&quot;100 % staplade&quot; visualisering. Exempel: ![Ett stapeldiagram som visar vyn Staplad 100 %.](assets/stacked_100_percent.png) |
| Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för visualiseringen av Sammanfattningsnummer/Sammanfattningsändring. |
| Begränsa maximalt antal objekt | Gör att du kan begränsa antalet objekt som visas i en visualisering. |
| Fästpunkt Y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll, kommer diagrammets standardvärde att göra den nedre delen av y-axeln ICKE-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |
| Normalisering | Tvingar måtten att ha samma proportioner. Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
| Visa dubbel axel | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
| Visa kantlinjer | Förbättrar linjediagram och frihandstabeller genom att visa avvikelseidentifiering. Analysidentifiering i linjevisualiseringar inkluderar ett förväntat värde (streckad linje) och ett förväntat intervall (skuggat band). |

## Förklaring {#legend}

En visualiseringsförklaring hjälper dig att relatera datum i en källtabell till plottade serier i visualiseringen. Förklaringen är interaktiv - du kan klicka på ett förklaringsobjekt om du vill visa/dölja en serie i visualiseringen. Detta är praktiskt om du vill förenkla de data som visualiseras.

Dessutom kan du byta namn på förklaringsetiketter så att det blir lättare att använda bilderna. Obs! Förklaringsredigering gör det **not** gäller för: Treemap, Bullet, Summary Change/Number, Text, Frihand, Histogram, Kohort eller Flödesvisualiseringar.

Så här redigerar du en förklaringsetikett:

1. Högerklicka på någon av förklaringsetiketterna.
1. Klicka på **[!UICONTROL Edit Label]**.

   ![En förklaringsetikett och alternativet Redigera etikett.](assets/edit-label.png)

1. Ange den nya etikettexten.
1. Tryck **[!UICONTROL Enter]** att spara.

## Högerklicka på menyn {#right-click}

Ytterligare funktioner för en visualisering är tillgängliga genom att högerklicka på rubriken för visualisering. Inställningarna varierar beroende på visualisering. Några av de tillgängliga inställningarna är:

![Ytterligare visualiseringsinställningar med alternativen för högerklick. Alternativen beskrivs i nästa avsnitt.](assets/right-click.png)

| Inställning | Beskrivning |
| --- | --- |
| Infoga kopierad panel/visualisering | Gör att du kan klistra in (&quot;infoga&quot;) en kopierad panel eller visualisering på en annan plats i projektet, eller i ett helt annat projekt. |
| Kopiera visualisering | Högerklicka och kopiera en visualisering så att du kan infoga den på en annan plats i projektet eller i ett helt annat projekt. |
| [Hämta projektdata](/help/analysis-workspace/export/download-send.md) | Hämta upp till 50 000 dimensionsobjekt för den valda dimensionen som en CSV-fil. |
| [Hämta projektdata](/help/analysis-workspace/export/download-send.md) | Hämta en datakälla för visualisering som en CSV-fil. |
| Duplicera visualisering | Skapar en exakt kopia av den aktuella visualiseringen, som du sedan kan ändra. |
| Redigera beskrivning | Lägg till (eller redigera) en textbeskrivning för visualiseringen. |
| Hämta visualiseringslänk | Gör att du kan dirigera någon till en viss visualisering i ett projekt. När användaren klickar på länken måste mottagaren logga in innan den dirigeras till den exakta visualisering som är länkad till den. |
| Börja om | (Works for Flow, Venn, Histogram) Tar bort konfigurationen för den aktuella visualiseringen så att du kan konfigurera om den från början. |

## Ikonen Skapa visuell {#quick-viz}

Om du är osäker på vilken visualisering du ska välja klickar du på **[!UICONTROL Create Visual]** -ikonen i valfri tabellrad (tillgänglig vid hovring). Det här är det snabbaste sättet att lägga till en visualisering. När du klickar på den uppmanas Analysis Workspace att göra en kvalificerad gissning där visualiseringen bäst passar dina data. Om du till exempel har markerat 1 rad skapas ett linjediagram. Om du har markerat tre filterrader skapas ett Venndiagram.

![Snabb visualisering](assets/quick-viz.png)
