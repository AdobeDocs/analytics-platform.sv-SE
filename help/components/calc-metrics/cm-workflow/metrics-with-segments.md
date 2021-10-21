---
description: 'Genom att segmentera enskilda mätvärden kan ni göra mätjämförelser inom samma rapport. '
title: Segmenterade mätvärden
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 0865c318c1390f2ad6d9864915254a7b8f68030f
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Filtrerade mätvärden

I verktyget Beräknade mätvärden kan du använda filter i måttdefinitionen. Detta är praktiskt om du vill ta fram nya mätvärden som ska användas i din analys. Tänk på att filterdefinitioner kan uppdateras med hjälp av filterverktyget. Om ändringar görs uppdateras filtret automatiskt varhelst det används, inklusive om det ingår i en beräknad metrisk definition.

![](assets/german-visitors.png)

## Skapa ett filtrerat mått {#create}

Låt oss säga att du vill jämföra olika aspekter av ett&quot;tyska besökare&quot;-filter med ett&quot;Internationella besökare&quot;-filter. Du kan skapa mätvärden som ger dig insikter som:

* Hur fungerar innehållssökning jämfört med de två grupperna? (Ett annat exempel är: Hur är konverteringsgraden jämfört mellan de två filtren?)
* Hur många tyska besökare surfar på vissa sidor jämfört med internationella besökare som en procentandel av det totala antalet besökare?
* Var är de största skillnaderna när det gäller vilket innehåll som nås av de olika filtren?

1. Om du inte har något liknande filter kan du skapa ett ad hoc-segment i Calculated Metric Builder som heter&quot;Tyska besökare&quot;, där&quot;Länder&quot; är lika med&quot;Tyskland&quot;. Dra bara dimensionen Länder till arbetsytan Definition och välj Tyskland som värde:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Du kan även göra det här i dialogrutan [Filter Builder](/help/components/filters/create-filters.md)men vi har förenklat arbetsflödet genom att göra dimensionerna tillgängliga i verktyget för beräkning av mått. &quot;Adhoc&quot; innebär att segmentet inte är synligt i **[!UICONTROL Filters]** listan i den vänstra listen. Du kan emellertid göra den offentlig genom att hålla markören över ikonen&quot;i&quot; bredvid den och klicka på **[!UICONTROL Make public]**.

1. Om du inte har något jämförbart filter skapar du ett filter som kallas &quot;Internationella besökare&quot; där &quot;Länder&quot; inte är lika med &quot;Tyskland&quot;.
1. Bygg och spara ett mätvärde som kallas&quot;tyska besökare&quot; genom att dra tyskt filter till arbetsytan Definition och dra det unika besökarmåttet i det:

   ![](assets/german-visitors.png)

1. Upprepa steg 3 med segmentet Internationell besökare och mätvärdet Unik besökare för att skapa ett internationellt besökarmått.
1. I Analysis Workspace drar du **[!UICONTROL Page]** Dimension till en frihandstabell och dra de två nya beräknade måtten intill varandra högst upp:

   ![](assets/workspace-pages.png)

Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Procent av totala mätvärden {#percent-total}

Du kan ta exemplet ovan ett steg längre genom att jämföra filtret med en total population. Det gör du genom att skapa två nya mätvärden, &quot;% av totalt antal tyska besökare&quot; och &quot;% av totalt antal internationella besökare&quot;:

1. Släpp filtret för tyska (eller internationella) besökare på arbetsytan.
1. Släpp ett annat filter för tyska (eller internationella) besökare nedan. Men den här gången klickar du på konfigurationsikonen (kugghjulsikonen) för att välja måtttypen &quot;Totalt&quot;. Formatet ska vara &quot;Procent&quot;. Operatorn ska delas med. Resultatet blir den här måttdefinitionen:

   ![](assets/cm_metric_total.png)

1. Använd följande mått i ditt projekt:

   ![](assets/cm_percent_total.png)
