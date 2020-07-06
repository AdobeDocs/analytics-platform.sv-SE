---
description: Lär dig mer om visualiseringar och visualiseringsinställningar i Analysis Workspace.
keywords: Analysis Workspace
title: Översikt över visualiseringar
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 4%

---


# Översikt över visualiseringar

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Workspace erbjuder ett antal visualiseringar som gör att du kan generera visuella representationer av dina data, t.ex. stapeldiagram, dondiagram, histogram, linjediagram, kartor, punktdiagram med mera. Varje visualisering har sina egna inställningar som du kan hantera. Klicka på namnet på visualiseringen för mer detaljerad information.

YouTube Video: [Visualiseringstyper i Analysis Workspace](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (2:57)

| Visualiseringsnamn | Beskrivning |
|---|---|
| [Yta](/help/analysis-workspace/visualizations/area.md) | som ett linjediagram, men med ett färgat område under linjen. Använd ett ytdiagram när du har flera mätvärden och vill visualisera området som uttrycks genom skärningspunkten för två eller flera mätvärden. |
| [Liggande](/help/analysis-workspace/visualizations/bar.md) | Visar lodräta staplar som representerar olika värden för ett eller flera mätvärden. |
| [Punktdiagram](/help/analysis-workspace/visualizations/bullet-graph.md) | Visar hur ett värde som du är intresserad av jämförs med eller mäter mot andra prestandaintervall (mål). |
| [Kohortabell](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | A *`cohort`* is a group of people sharing common characteristics over a specified period. Kohortanalys är till exempel användbart när du vill veta hur en kohort interagerar med ett varumärke. Du kan enkelt upptäcka ändringar i trender och sedan svara på dem. |
| [Ringdiagram](/help/analysis-workspace/visualizations/donut.md) | På samma sätt som ett cirkeldiagram visar den här visualiseringen data som delar eller segment av en helhet. |
| [Utfall](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | Utfallsrapporter visar var besökarna lämnade (föll ned) och fortsatte igenom (föll igenom) en fördefinierad sidsekvens. |
| [Flöde](/help/analysis-workspace/visualizations/c-flow/flow.md) | Visar kundvägar via era webbplatser och appar. |
| [Frihandstabell](/help/analysis-workspace/visualizations/freeform-table.md) | En friformstabell är inte bara en datatabell, utan också en interaktiv visualisering. |
| [Histogram](/help/analysis-workspace/visualizations/histogram.md) | Ett histogram liknar ett stapeldiagram, men det grupperar nummer i intervall (intervall). |
| [Vågrätt fält](/help/analysis-workspace/visualizations/horizontal-bar.md) | Visar vågräta staplar som representerar olika värden för ett eller flera mätvärden. |
| [Linjediagram](/help/analysis-workspace/visualizations/line.md) | Representerar mätvärden med hjälp av en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram kan bara användas när tid används som dimension. |
| [Spridningsdiagram](/help/analysis-workspace/visualizations/scatterplot.md) | Visar relationen mellan dimensionsvärden och upp till tre mätvärden. |
| [Sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md) | Beroende på vilken cell som är markerad visar den här visualiseringen summor och sammanfattningar. |
| [Sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md) | Beroende på vilka celler som är markerade jämförs cellerna med varandra. |
| [Text](/help/analysis-workspace/visualizations/text.md) | Gör att du kan lägga till användardefinierad text på arbetsytan. |
| [Treemap-diagram](/help/analysis-workspace/visualizations/treemap.md) | Visar hierarkiska data (i trädstrukturer) som en uppsättning kapslade rektanglar. |
| [Venn](/help/analysis-workspace/visualizations/venn.md) | Gör att du kan dra i upp till tre segment (från komponenter) och ett mätvärde för att skapa ett Venndiagram. |

## Panelen Visualiseringar {#section_DC07F032FBEF4046A40F7B95C28DA018}

Om du vill visa visualiseringspanelen klickar du **[!UICONTROL Visualizations]** på sidopanelen.

![Stegresultat](assets/visualizations.png)

De flesta visualiseringstyper (till exempel Area-, Bar-, Donut- och Line-diagram) är välbekanta för dig om du använder Adobe Analytics. Analysis Workspace tillhandahåller dock visualiseringsinställningar och många nya eller unika visualiseringstyper med interaktiva funktioner.

## Visualiseringsinställningar {#section_D3BB5042A92245D8BF6BCF072C66624B}

Du öppnar [!UICONTROL Visualization Settings]genom att dra en visualisering till [!UICONTROL Freeform Panel]och sedan klicka på [!UICONTROL Visualization Settings] kugghjulsikonen.

>[!IMPORTANT]
>
>Vilka visualiseringsinställningar som visas beror på visualiseringen. Alla inställningar gäller inte för alla visualiseringar. Dessutom visas vissa avancerade inställningar **bara** för specifika visualiseringar, som [histograminställningarna](/help/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477).

![](assets/visualization_settings.png)

| Inställning | Beskrivning |
|--- |--- |
| Procenttal | Visar värden i procent. |
| 100 % staplad | Den här inställningen för staplade ytor, stolpdiagram eller skiktade vågräta staplar gör diagrammet till en&quot;100 % staplade&quot; visualisering. Exempel: ![](assets/stacked_100_percent.png) |
| Förklaring synlig | Gör att du kan dölja filterinformationstexten för visualiseringen av Sammanfattningsnummer/Sammanfattningsändring. |
| Begränsa maximalt antal objekt | Gör att du kan begränsa antalet objekt som visas i en visualisering. |
| Ankra Y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll, kommer diagrammets standardvärde att göra den nedre delen av y-axeln ICKE-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |
| Normalisering | Tvingar måtten att ha samma proportioner. |
| Visa dubbel axel | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). |
| Visa avvikelser | Förbättrar linjediagram och frihandstabeller för att visa dataavvikelser. |

## Ikonen Skapa visuell {#section_9C11D9DEDC42413AA53E69A71A509DFC}

Om du är osäker på vilken visualisering du ska välja klickar du på **[!UICONTROL Create Visual]** ikonen i valfri tabellrad. Den här ikonen visas när du hovrar över tabellraden. När du klickar på den uppmanas Analysis Workspace att göra en kvalificerad gissning där visualiseringen bäst passar dina data. Om du till exempel har markerat upp till tre segment skapas ett Venndiagram. För mer än tre segment skapas ett stapeldiagram. För andra typer av data kan det skapa ett linjediagram osv.

![](assets/create-visual.png)

## Högerklicka på visualisering/panelmeny {#section_05B7914D4C9E443F97E2BFFDEC70240C}

Inställningar som är sammanhangsbaserade för ett diagram kan nås när du högerklickar bredvid ett visualiserings- eller panelhuvud. Vissa eller alla av följande inställningar kommer att vara tillgängliga:

![](assets/right-click_menu.png)

| Inställning | Beskrivning |
|--- |--- |
| Infoga kopierad visualisering/panel | Gör att du kan klistra in (&quot;infoga&quot;) det kopierade elementet på en annan plats i projektet eller i ett helt annat projekt. |
| Kopiera visualisering/panel | Gör att du kan högerklicka och kopiera en visualisering eller panel. |
| Duplicera visualisering/panel | Skapar en exakt kopia av den aktuella visualiseringen, som du sedan kan ändra. |
| Komprimera alla paneler | Komprimerar alla projektpaneler. |
| Komprimera alla visualiseringar i panelen | Komprimerar alla visualiseringar i den här projektpanelen. |
| Expandera alla paneler | Expanderar alla projektpaneler. |
| Expandera alla visualiseringar i panelen | Utökar alla visualiseringar i den här projektpanelen. |
| Redigera beskrivning | Lägg till (eller redigera) en textbeskrivning för visualiseringen/panelen. Den här beskrivningen visas i Projekt > Projektinformation och inställningar . |
| Hämta panellänk | Du kan dirigera någon till en viss panel i ett projekt. |
| Hämta visualiseringslänk | Gör att du kan kopiera och dela den här länken för att skicka andra direkt till den här visualiseringen. Användarna måste logga in. |
| Börja om | (Works for Flow, Venn, Histogram) Tar bort konfigurationen för den aktuella visualiseringen och öppnar en ny panel där du kan konfigurera om den. |

## Redigera förklaringsetiketter {#section_94F1988CB4B9434BA1D9C6034062C3DE}

Du kan byta namn på serienamn i visualiseringsteckenförklaringar (Utfall, Område, Staplad, Stapel, Staplad liggande stapel, Donut, Histogram, Vågrät stapel, Staplad linje, Spridning och Venndiagram) för att göra bilderna mer konsumerbara.

Legend editing does **not** apply to: Treemap, Bullet, Summary Change or Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

Om du vill redigera en förklaringsetikett i ett linjediagram, till exempel

1. Högerklicka på någon av förklaringsetiketterna.
1. Klicka på **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Ange den nya etikettexten.
1. Tryck för **[!UICONTROL Enter]** att spara.

Här är en [länk till en video](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) om det här ämnet.
