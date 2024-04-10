---
description: Visa och hantera styrkort för kontrollpaneler i Analytics
title: Hantera styrkort
feature: Analytics Dashboards
role: User, Admin
solution: Customer Journey Analytics
exl-id: 6a0de7db-689d-448d-b8e0-90af4a5ee325
source-git-commit: 6149d2cf23eb31f0aaa37546d3150017e155053c
workflow-type: tm+mt
source-wordcount: '1768'
ht-degree: 0%

---

# Hantera styrkort

I det här avsnittet lär du dig att visa och hantera styrkortselement för Customer Journey Analytics.

## Visa och konfigurera egenskaper för paneler {#tiles}

När du klickar på en platta i styrkortsverktyget visas egenskaperna och egenskaperna för plattan och dess detaljbild i den högra listen. På den här listen kan du ange en ny **Titel** för plattan och konfigurera plattan genom att använda filter. Segment är filter i Customer Journey Analytics.

![Egenskapspanelen](assets/properties-tile-new.png)

## Visa detaljbilder {#view-detail-slides}

När du klickar på paneler visas i ett dynamiskt popup-fönster hur detaljbilden visas för den verkställande användaren i appen. Du kan lägga till dimensioner för att dela upp dina data efter dina specifika behov. Om en dimension inte har tillämpats, kommer uppdelningsdimensionen att **timme** eller **dagar**, beroende på standarddatumintervallet.

Uppdelningar förfinar analysen genom att dela upp mätvärden efter dimensionsobjekt som exempelvis följande:

* Unika besökarvärden uppdelade efter annonsplattform (AMO-ID)
* Besök uppdelade efter produktkategori (detaljhandel)
* Total intäkt uppdelad efter produktnamn

![Brytningsvy](assets/break_view.png)

Varje dimension som läggs till i rutan visas i en nedrullningsbar lista i appens detaljerade vy. Den verkställande användaren kan sedan välja bland alternativen i listrutan.

## Anpassa detaljbilder {#customize-detail-slide}

Med skräddarsydda detaljbilder kan ni målinrikta er ännu mer om vilken information ni delar med er målgrupp.

>[!VIDEO](https://video.tv.adobe.com/v/3410002)

Du kan ändra layouten för varje detaljbild och lägga till text som bättre förklarar vad slutanvändaren kan se i informationen. Du kan också ändra diagramtyp med hjälp av den nedrullningsbara menyn.

![Anpassad detaljbild](assets/custom-detail-slide.png)

### Ändra bildrutelayout

Ändra bildrutelayouten så att den fokuserar på den viktigaste informationen. Du kan till exempel ändra layouten så att bara ett diagram eller en tabell visas. Om du vill ändra bildrutelayouten väljer du ett av de fördesignade formaten.

![Bildlayout](assets/layout.png)

Du kan också ändra bildrutelayouten genom att dra och släppa visualiseringskomponenter från den vänstra listen på arbetsytan. Varje detaljbild kan endast innehålla två visualiseringar åt gången.

![Ändra bildlayout](assets/slide-layout-change.png)

### Lägga till beskrivande text i en bildruta

Du kan lägga till text för att ge meningsfull information om vad som finns i diagrammen eller nyanserna om data.

Om du vill lägga till text i en detaljbildruta väljer du en layout som visar `T` eller dra och släpp textvisualiseringskomponenten från den vänstra listen. Textredigeraren öppnas automatiskt när du lägger till en ny textvisualisering eller väljer en bildlayout med text. I textredigeraren finns alla standardalternativ för formatering av texten. Du kan använda textformat som stycke, rubriker och underrubriker och använda fet och kursiv stil. Du kan justera text, lägga till punktlistor och numrerade listor samt lägga till länkar. När du är klar med redigeringen klickar du på minimeringsknappen i det övre högra hörnet av textredigeraren för att stänga den. Om du vill redigera text som du redan har lagt till väljer du pennikonen och öppnar textredigeraren igen.

![Ändra bildlayout](assets/add-descriptive-text.png)

## Ta bort komponenter {#remove}

Om du vill ta bort en komponent som används på hela styrkortet klickar du var som helst på styrkortet utanför plattorna och tar sedan bort den genom att klicka på **x** som visas när du hovrar över komponenten, som visas nedan för **Första gången du besöker**:

![Remove_components](assets/new_remove.png)

## Skapa dataartiklar {#create-data-story}

En databerättelse är en samling datapunkter, kontext och relaterade mått som bygger på ett centralt tema eller mätvärden.

Om du till exempel fokuserar på webbtrafik kan det vara dina viktigaste mätvärden, men du kanske också är intresserad av nya personer, unika personer, och du kanske vill se data uppdelade efter webbsida eller efter vilken typ av enhet som trafiken kommer från. Med hjälp av datarubriker i mobilstyrningsprojekt kan du placera dina viktigaste mätvärden i centrum samtidigt som du berättar hela artikeln bakom mätvärdena med flera detaljbilder.

Titta på videon och lär dig mer om hur du skapar databerättelser i mobilstyrkortsprojekt i Analysis Workspace.

>[!VIDEO](https://video.tv.adobe.com/v/3416392/?quality=12&learn=on)

**Skapa en dataartikel** {#data-story-create}

Bygg din databerättelse genom att lägga till flera detaljbilder i en ruta.

1. Börja med ett mobilstyrningsprojekt.
1. Välj en platta som du vill skapa en artikel från.
   ![Skapa en dataartikel](assets/data-story1.png)
   ![Skapa ikoner för databerättelse](assets/create-data-story.png){width=".50%"}
1. Lägg till bilder för att skapa din databerättelse. Den första bilden genereras som standard.
Om du vill lägga till nya bildrutor håller du markören över eller klickar på en bildruta och väljer sedan bland de tillgängliga alternativen:
   * Tryck på +-tecknet för att skapa en ny bildruta.
   * Tryck på ikonen Duplicera om du vill duplicera den befintliga bildrutan.
1. Om du skapar en tom bildruta drar och släpper du komponenter från den vänstra listen, eller väljer en layout som automatiskt fyller bildrutan med data från den.
   ![Skapa en dataartikel](assets/data-story2.png)
Om du vill ta bort en bildruta trycker du på papperskorgsikonen.

### Anpassa en dataartikel {#customize-data-story}

Med hjälp av dataartiklar kan du anpassa allt så att du kan dela information som du vill dela och utesluta allt som du inte behöver. Du kan anpassa plattor och enskilda bildrutor för att lägga till filter, visa uppdelningar, ändra layout och ändra visualiseringar.

**Anpassa rutor**

1. Tryck på en platta. Den markerade plattan visas med blå konturer och den högra panelen visar rutans egenskaper.
1. Ändra alternativ för rubrik, diagramtyp och annan ruta.
1. Dra en komponent till plattan.
   ![Skapa en dataartikel](assets/data-story3.png)
När du drar och släpper en komponent, t.ex. en visualisering, på en platta används komponenten på alla bilder i en dataartikel.
1. Om du bara vill ändra titeln håller du ned Skift-tangenten för att tillämpa ändringen.
   ![Skapa en dataartikel](assets/data-story4.png)

>[!NOTE]
>Bilder ärver komponenter från plattan, men rutor ärver inte komponenter från bildrutor.

**Anpassa enskilda bildrutor**

Du kan ändra visualiseringen för enskilda bilder i en dataartikel. Du kan till exempel ändra ett vågrätt fält till ett ringdiagram för en viss bildruta. Du kan också ändra layouten. Se [Anpassa detaljbilder](#customize-detail-slide).

### Förhandsgranska en dataartikel {#preview-data-story}

När du har skapat en dataartikel använder du **Förhandsgranska** för att visa och interagera med en databerättelse som om du var en appanvändare. Mer information om hur du förhandsgranskar din dataartikel finns i [Förhandsgranska ett styrkort](#preview)

### Navigera mellan rutor och bilder {#navigate-tiles-slides}

I navigeringsfältet visas ikoner som representerar vad som finns på varje bildruta. Navigeringsfältet gör det enkelt att navigera till en viss bildruta om du har många bildrutor.

Om du vill flytta mellan plattan och bildrutorna trycker du på navigeringsfältet.
![Skapa en dataartikel](assets/data-story5.png)
![Skapa en dataartikel](assets/data-story-nav.png){width="45%"}

Du kan också navigera fram och tillbaka genom att använda pilarna på tangentbordet eller genom att markera en komponent och hålla den till vänster eller höger på skärmen för att rulla.

## Förhandsgranska styrkort {#preview}

Du kan förhandsgranska hur styrkortet kommer att se ut och fungera när det har publicerats i appen Adobe Analytics dashboards.

1. Klicka **[!UICONTROL Preview]** i skärmens övre högra hörn.

   ![Preview_scorecards](assets/preview.png)

1. Om du vill visa hur styrkortet kommer att se ut på olika enheter väljer du en enhet på menyn [!UICONTROL Device preview] listruta.

   ![Device_preview](assets/device-preview.png)

1. Om du vill interagera med förhandsgranskningen kan du:

   * Vänsterklicka för att simulera knackning på telefonskärmen.

   * Använd datorns rullningsfunktion för att simulera rullning av telefonskärmen med fingret.

   * Klicka och håll ned för att simulera att du trycker och håller fingret på telefonskärmen. Detta är användbart när du vill interagera med visualiseringarna i den detaljerade vyn.

## Dela styrkort {#share}

Så här delar du styrkortet med en verkställande användare:

1. Klicka på **[!UICONTROL Share]** meny och välj **[!UICONTROL Share scorecard]**.

1. I **[!UICONTROL Share Mobile Scorecard]** fylla i fälten med:

   * Ange namnet på styrkortet
   * Ange en beskrivning av styrkortet
   * Lägga till relevanta taggar
   * Ange mottagare för styrkortet

1. Klicka på **[!UICONTROL Share]**.

![Dela_styrkort](assets/new_share.png)

När du har delat ett styrkort kan mottagarna komma åt det på sina kontrollpaneler i Analytics. Om du gör efterföljande ändringar av styrkortet i styrkortsverktyget uppdateras de automatiskt i det delade styrkortet. Chefsanvändare ser sedan ändringarna när de har uppdaterat styrkortet i sin app.

Om du uppdaterar styrkortet genom att lägga till nya komponenter kanske du vill dela styrkortet igen (och kontrollera **[!UICONTROL Share embedded components]** för att se till att dina chefsanvändare har tillgång till dessa ändringar.

### Dela styrkort med hjälp av en delbar länk

Genom att använda en delbar länk är det enkelt att dela ett styrkort i ett e-postprogram, dokument eller textmeddelandeprogram. Med den delbara länken kan mottagarna öppna styrkortet på sina datorer eller i kontrollpanelernas mobilapp. Enkel, djup länkning gör det ännu enklare att dela projekt och öka engagemanget med era intressenter.

Dela ett styrkort med hjälp av en delbar länk

1. Klicka på **[!UICONTROL Share]** meny och välj **[!UICONTROL Share scorecard]**.

   ![Dela_styrkort](assets/share-scorecard.png)

1. Kopiera länken och klistra in den i ett e-postmeddelande, dokument eller en snabbmeddelandeapp.

   När en mottagare använder ett datorprogram eller en webbläsare för att öppna länken öppnas projektet i Workspace.

   När en mottagare öppnar länken på en mobil enhet öppnas styrkortet direkt i Adobe Analytics-appen för instrumentpaneler.

   Om en mottagare inte har laddat ned mobilappen dirigeras han/hon till applistan i App Store eller Google Play Store där han/hon kan ladda ned den.


## Ta bort [!UICONTROL Unspecified] dimensionsuppgift {#remove-dims}

Om du vill ta bort [!UICONTROL Unspecified] dimensionsobjekt från dina data, gör följande:

1. Välj rätt platta.
1. I rätt spår, under **[!UICONTROL Drill ins]** markerar du högerpilen bredvid dimensionsobjektet vars **[!UICONTROL Unspecified]** objekt som du vill ta bort.

   ![Egenskaper med pil som pekar mot högerpilen bredvid dimensionsnamnet.](assets/unspecified.png)

1. Klicka på ikonen bredvid **[!UICONTROL Unspecified]** för att ta bort ospecificerade data från din rapportering. (Du kan även ta bort andra dimensionsobjekt.)

## Visa intelligenta bildtexter i styrkort {#captions}

Intelligenta bildtexter kan hjälpa icke-analytiker att förstå sina data bättre utan hjälp av analytiker. Intelligenta bildtexter använder avancerad maskininlärning och generativ AI för att ge värdefulla insikter på naturspråket för visualiseringar.

Dessa bildtexter bygger på viktiga statistiska insikter i data och formulerar dem på naturligt språk, vilket hjälper icke-analytikerna att utveckla sin datakunskap.

Intelligent bildtext finns för alla visualiseringar i mobilappen, inklusive Line, Donut, Bar Chart och Summary Number.

Så här visar du intelligenta bildtexter i ett mobilstyrkort:

1. Klicka i ett styrkort i en ruta. I det här styrkortet klickar du till exempel i linjediagrammet längst ned.

   ![Styrkort med linjevisualisering](assets/caption1.png)

1. Tryck på den blå ikonen längst upp till höger för att generera bildtexterna. Bildtexterna visas under linjediagrammet.

   ![Intelligent bildtext i linjvisualisering](assets/caption2.png)

1. Svep åt höger för att visa alla intelligenta bildtexter.

   Intelligenta bildtexter kan peka på datatoppar, avvikelser, trender, minskningar, korrelationer och andra fenomen.

1. Tryck på den svarta flaggan i en bildtext för att rapportera ett problem, till exempel skadligt eller olagligt innehåll.

   ![Rapportera problem med bildtext](assets/caption-report.png)

1. Klicka på X för att avsluta **[!UICONTROL Report results]** -dialogrutan.
