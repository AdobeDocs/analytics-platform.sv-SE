---
description: Lär dig hur du skapar en visuell karta över alla mätvärden i Analysis Workspace.
title: Mappa
translation-type: tm+mt
source-git-commit: ab1ea4c75c4c28f196c6793a819ce4dbe656d52c
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---


# Mappa

## Översikt {#section_19F740FAF08D47B1AF1EF239A74FC75C}

The Map Visualization in Analysis Workspace

* Gör att du kan skapa en visuell karta över alla mått (inklusive beräknade värden).
* Är användbart för att identifiera och jämföra mätdata för olika geografiska regioner.
* Kan hantera två datakällor: latitud/longitud från mobilanvändning eller geografisk dimension för webbanvändning.
* Stöd för PDF-export.
* Använder WebGL för bildvisning. Om grafikdrivrutinerna inte har stöd för WebGL-återgivning kan du behöva uppdatera drivrutinerna.

## Skapa en kartvisualisering {#section_61BBFA3A7BFD48DA8D305A69D9416299}

1. Dra **[!UICONTROL Map]** från listan över visualiseringar till en friformspanel:

   ![](assets/map-viz1.png)

1. Dra ett mätvärde från listan med mätvärden (inklusive beräknade värden).
1. Ange den datakälla som du vill rita från. (Den här dialogrutan visas bara om du har platsspårning aktiverad för mobilappsdata.)

<table id="table_CD54B433464B4282A7524FB187016C47"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Mobile Lat/Long</b> </p> </td> 
   <td colname="col2"> <p>Det här alternativet representerar mobilappsdata. </p> <p>Det här alternativet visas bara om du har aktiverat det för din rapportsserie i <span class="ignoretag"> <span class="uicontrol"> Analytics </span> &gt; <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Report Suites </span> &gt; <span class="uicontrol"> &lt;select report suite&gt; </span> &gt; <span class="uicontrol"> Redigera inställningar </span> &gt; &lt;a1 1/&gt; Mobile Management </span> &gt; <span class="uicontrol"> Enable Location Tracking </span> </span>.<span class="uicontrol"> </span></p> <p>Det här är standardinställningen (om platsspårning är aktiverat). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Geografisk Dimension  </b> </p> </td> 
   <td colname="col2"> <p>Det här alternativet representerar geosegmenteringsdata om besökarens plats baserat på besökarens IP-adress. Dessa data omvandlas till Land, Region och Stad. Observera att det inte går till DMA- eller Zip-kodnivån. </p> <p>Nästan alla rapportsviter har den här dimensionen aktiverad. Om du inte har det kontaktar du Adobe kundtjänst för att aktivera geografiska rapporter. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Klicka på **[!UICONTROL Build]**.

   Den första vyn som du ser är en World View med en bubbelkarta som liknar den här.

   ![](assets/bubble-world-view.png)

1. Nu kan du

   * **Zooma** in på kartan för att förstora vissa områden genom att dubbelklicka på kartan eller använda rullningshjulet. Kartan zoomas enligt var du har placerat markören. Genom zoominteraktion uppdateras den nödvändiga dimensionen (land > stat > stad) automatiskt utifrån zoomnivån.
   * **Jämför** två eller flera mappningsvisualiseringar i samma projekt genom att placera dem sida vid sida.
   * **Visa jämförelser** för perioden över perioden (t.ex. år över år):

      * Visa negativa tal: Om du till exempel ritar upp ett årligt mått kan kartan visa -33 % över New York.
      * Med mätvärden av typen procent beräknar klustring det genomsnittliga procentvärdet.
      * Ett grönt/rött färgschema: Positiv/negativ
   * **Rotera kartan** i 2D eller 3D genom att hålla ned  [!UICONTROL Ctrl] tangenten och flytta kartan.

   * **Växla** till en annan vy, t.ex. värmekartan, med de  [](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) inställningar som beskrivs nedan. Observera att bubbelvyn är standardinställningen.


1. **** Spara projektet för att spara alla kartinställningar (koordinater, zoomning, rotation).
1. Tabellen på frihand, nedanför visualiseringen, kan fyllas med genom att du drar i platsdimensioner och mått från den vänstra listen:

   ![](assets/location-dimensions.png)

## Inställningar för mappningsvisualisering {#section_5F89C620A6AA42BC8E0955478B3A427E}

Det finns två uppsättningar inställningar för kartan:

**skiftnyckelsikonen** längst upp till höger återställer den inledande dialogrutan där du kan ändra måttet och datakällan:

![](assets/map-wrench.png)

Om du klickar på **kugghjulsikonen** visas dessa visualiseringsinställningar:

| Inställning | Beskrivning |
|--- |--- |
| Bubblor | Ritar händelser med bubblor. Ett bubbeldiagram är ett diagram med flera variabler och som är ett kors mellan ett punktdiagram och ett proportionellt ytdiagram. Det här är standardvyn. |
| Heatmap | Ritar händelser med hjälp av en heatmap. En heatmap är en grafisk representation av data där de enskilda värdena i en matris representeras som färger. |
| Format: Färgtema | Visar färgschemat för värmekartan och bubblorna. Du kan välja mellan Coral, Reds, Green eller Blues. Standardvärdet är Koral. |
| Format: Kartstil | Du kan välja mellan Basic, Streets, Bright, Light, Dark och Satellite. |
| Klusterradie | Grupperar datapunkter som ligger inom det angivna antalet pixlar. Standardvärdet är 50. |
| Anpassat maxvärde | Gör att du kan ändra tröskelvärdet för det högsta värdet för kartan. Om du justerar det här värdet justeras skalan för värdena för bubblor/heatmap (färg och storlek) i förhållande till det anpassade maxvärdet. |
