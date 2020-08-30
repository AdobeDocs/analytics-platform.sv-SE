---
description: Läs mer om visualiseringar och visualiseringsinställningar i Analysis Workspace.
keywords: Analysis Workspace
title: Översikt över visualiseringar
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 4%

---


# Översikt över visualiseringar

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

På arbetsytan finns ett antal visualiseringar som du kan använda för att skapa visuella representationer av dina data, t.ex. stapeldiagram, ritdiagram, histogram, linjediagram, kartor, områden med flera. Varje visualisering har sina egna inställningar som du kan hantera. Klicka på namnet på visualiseringen om du vill ha mer detaljerad information.

YouTube-video: [Visualiseringstyper i Analysis Workspace](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) 2:57

| Visualiseringsnamn | Beskrivning |
|---|---|
| [Område](/help/analysis-workspace/visualizations/area.md) | som ett linjediagram, men med ett färgat område under linjen. Använd ett ytdiagram när du har flera mått och vill visualisera området som uttrycks genom skärningspunkten mellan två eller flera mått. |
| [Stapel](/help/analysis-workspace/visualizations/bar.md) | Visar lodräta staplar som representerar olika värden över ett eller flera mått. |
| [Punktdiagram](/help/analysis-workspace/visualizations/bullet-graph.md) | Visar hur ett värde du är intresserad av jämfört med eller mått i förhållande till andra prestandaområden (mål). |
| [Kohort-tabell](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | A *`cohort`* är en grupp personer som har gemensamma kännetecken under en viss period. Kohort Analysis är till exempel användbar när du vill lära dig hur en kohort hanterar ett varumärke. Du kan enkelt upptäcka förändringar i trender och sedan svara på lämpligt sätt. |
| [Ringdiagram](/help/analysis-workspace/visualizations/donut.md) | I likhet med ett cirkeldiagram visar den här visualiseringen data som delar eller segment av en helhet. |
| [Utfall](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | Rapporterna om utfall visar var besökarna lämnade (föll bort) och fortsatte igenom en fördefinierad sidsekvens. |
| [Flöde](/help/analysis-workspace/visualizations/c-flow/flow.md) | Visar kundsökvägar via dina webbplatser och appar. |
| [Frihandstabell](/help/analysis-workspace/visualizations/freeform-table.md) | En Freeform-tabell är inte bara en datatabell utan också en interaktiv visualisering. |
| [Histogram](/help/analysis-workspace/visualizations/histogram.md) | Ett histogram liknar ett stapeldiagram, men det grupperar numren i intervall (bucket). |
| [Vågrät stapel](/help/analysis-workspace/visualizations/horizontal-bar.md) | Visar vågräta staplar som representerar olika värden över ett eller flera mått. |
| [Linjediagram](/help/analysis-workspace/visualizations/line.md) | Representerar mått med hjälp av en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram kan bara användas när tiden används som dimension. |
| [Spridningsdiagram](/help/analysis-workspace/visualizations/scatterplot.md) | Visar förhållandet mellan dimensionsobjekt och upp till tre mått. |
| [Sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md) | Beroende på vilken cell som är markerad visas summor och sammanfattningar. |
| [Sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md) | Beroende på vilka celler som är markerade jämförs cellerna med varandra. |
| [Text](/help/analysis-workspace/visualizations/text.md) | Gör att du kan lägga till användardefinierad text på arbetsytan. |
| [Treemap-diagram](/help/analysis-workspace/visualizations/treemap.md) | Visar hierarkiska data (i trädstrukturer) som en uppsättning kapslade rektanglar. |
| [Venn](/help/analysis-workspace/visualizations/venn.md) | Gör att du kan dra upp till 3 segment (från Komponenter) och ett metriskt för att skapa ett Venndiagram. |

## Visualiseringspanelen {#section_DC07F032FBEF4046A40F7B95C28DA018}

Om du vill visa visualiseringspanelen klickar du på **[!UICONTROL Visualizations]** i sidopanelen.

![Stegresultat](assets/visualizations.png)

De flesta visualiseringstyper (t.ex. Area-, Bar-, Donut- och linjediagram) är bekant för dig om du använder Adobe Analytics. Analysis Workspace ger dock visualiseringsinställningar och många nya eller unika visualiseringstyper med interaktiva funktioner.

## Visualiseringsinställningar {#section_D3BB5042A92245D8BF6BCF072C66624B}

Åtkomst [!UICONTROL Visualization Settings], dra en visualisering till [!UICONTROL Freeform Panel]och klicka sedan på [!UICONTROL Visualization Settings] Växelikon.

>[!IMPORTANT]
>
>Vilka visualiseringsinställningar som visas beror på visualiseringen. Alla inställningar gäller inte för alla visualiseringar. Dessutom visas vissa avancerade inställningar **endast** för särskilda visualiseringar, t.ex. [Histograminställningar](/help/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477).

![](assets/visualization_settings.png)

| Inställning | Beskrivning |
|--- |--- |
| Procentsatser | Visar värden i procent. |
| 100 % staplad | Den här inställningen för ytstaplade eller staplade eller vågräta staplade visualiseringar gör att diagrammet blir en &quot;100 % staplad&quot; visualisering. Exempel: ![](assets/stacked_100_percent.png) |
| Förklaring synlig | Gör att du kan dölja filterinformationstexten för visualisering av sammanfattningsnummer/sammanfattning. |
| Begränsa maximalt antal objekt | Du kan begränsa antalet objekt som visualiseringen visar. |
| Ankra Y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll blir diagrammets standardvärde den nedre delen av Y-axeln NON-ZERO. Om du markerar den här rutan, tvingas y-axeln till noll (och diagrammet ritas om). |
| Normalisering | Tvingar måtten till samma proportioner. |
| Visa dubbel axel | Använd bara om du har två mått - du kan ha en y-axel till vänster (för ett mått) och till höger (för det andra måttet). |
| Visa anomalier | Förbättrar linjediagram och frihandstabeller för att visa dataavvikelser. |

## Skapa visuell ikon {#section_9C11D9DEDC42413AA53E69A71A509DFC}

Om du är osäker på vilken visualisering du vill välja klickar du på **[!UICONTROL Create Visual]** ikon i valfri tabellrad. Den här ikonen visas när du håller pekaren över tabellraden. Om du klickar på den uppmanas Analysis Workspace att ta en välutbildad gissning där visualisering passar dina data bäst. Om du t.ex. har markerat upp till tre segment skapas ett Venndiagram. För mer än tre segment skapas ett stapeldiagram. För andra typer av data kan det skapa ett linjediagram osv.

![](assets/create-visual.png)

## Högerklicka på visualisering/panelmeny {#section_05B7914D4C9E443F97E2BFFDEC70240C}

Du kan komma åt inställningar som är kontextuella för ett diagram när du högerklickar bredvid ett visualiserings- eller panelhuvud. Vissa eller alla följande inställningar är tillgängliga:

![](assets/right-click_menu.png)

| Inställning | Beskrivning |
|--- |--- |
| Infoga kopierad visualisering/panel | Gör att du kan klistra in (&quot;infoga&quot;) det kopierade elementet på en annan plats i projektet eller i ett helt annat projekt. |
| Kopiera visualisering/panel | Du kan högerklicka och kopiera en visualisering eller panel. |
| Dubblett av visualisering/panel | Gör en exakt dubblett av den aktuella visualiseringen, som du sedan kan ändra. |
| Dölj alla paneler | Komprimerar alla projektpaneler. |
| Dölj alla visualiseringar på panelen | Komprimerar alla visualiseringar i den här projektpanelen. |
| Expandera alla paneler | Expanderar alla projektpaneler. |
| Expandera alla visualiseringar på panelen | Expanderar alla visualiseringar i den här projektpanelen. |
| Redigera beskrivning | Lägg till (eller redigera) en textbeskrivning för visualiseringen/panelen. Beskrivningen visas i Projekt > Projektinformation och inställningar. |
| Länk till Hämta panel | Gör att du kan dirigera någon till en specifik panel i ett projekt. |
| Hämta visualiseringslänk | Gör att du kan kopiera och dela den här länken för att skicka andra direkt till den här visualiseringen. Användarna måste logga in. |
| Börja om | (Works for Flow, Venn, Histogram) Tar bort konfigurationen för den aktuella visualiseringen och öppnar en ny panel där du kan konfigurera om den. |

## Redigera förklaringsetiketter {#section_94F1988CB4B9434BA1D9C6034062C3DE}

Du kan byta namn på serienamn i visualiseringsteckenförklaringar (Utfall, Område, Stapel, Stapel, Stapel, Donut, Histogram, Vågrät stapel, Linje, Punktdiagram och Venndiagram) för att göra visualerna mer användbara.

Legenredigering gör **inte** tillämpas på Treemap, Punktuppställning, Sammanfattningsändring eller Nummer, Text, Frihand, Histogram, Kohort eller Flödesvisualiseringar.

Så här redigerar du t.ex. en förklaringsetikett i ett linjediagram

1. Högerklicka på en av förklaringsetiketterna.
1. Klicka på **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Ange den nya etiketttexten.
1. Tryck **[!UICONTROL Enter]** för att spara.

Här är en [länk till en video](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) om detta ämne.
