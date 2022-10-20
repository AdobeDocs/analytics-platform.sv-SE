---
description: Skapa ett Adobe Analytics-styrkort
title: Skapa ett styrkort
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: 0922faf4476e52e05a8b7b0c4eb00aa38fbbf057
workflow-type: tm+mt
source-wordcount: '1700'
ht-degree: 0%

---

# Skapa ett mobilstyrkort

Följande information beskriver för chefer av Adobe Analytics-data hur man konfigurerar och presenterar kontrollpaneler för chefsanvändare. Börja med att titta på videon Adobe Analytics dashboards Scorecard Builder:

>[!VIDEO](https://video.tv.adobe.com/v/343458)

>[!NOTE]
>Styrkortsskärmbilder för den här sidan har tagits från Adobe Analytics-gränssnittet, inte från CJA. Gränssnitten är nästan identiska.

Ett Adobe Analytics-styrkort visar viktiga datavisualiseringar för chefsanvändare i en sidindelad layout, vilket visas nedan:

![Exempelstyrkort](assets/intro_scorecard.png)

Som kurator för det här styrkortet kan du använda styrkortsverktyget för att konfigurera vilka rutor som ska visas på styrkortet för den verkställande konsumenten. Du kan också konfigurera hur detaljerade vyer, eller delningarna, kan justeras när användaren trycker på plattorna. Gränssnittet i Scorecard Builder visas nedan:

![Styrkortbyggaren](assets/scorecard_builder.png)

Om du vill skapa styrkortet måste du göra följande:

1. Öppna [!UICONTROL Blank Mobile Scorecard] mall.
2. Konfigurera styrkortet med data och spara det.

## Öppna [!UICONTROL Blank Mobile Scorecard] mall {#template}

Du kommer åt [!UICONTROL Blank Mobile Scorecard] mall antingen genom att skapa ett nytt projekt eller från Verktyg-menyn.

### Skapa ett nytt projekt {#create}

1. Öppna Adobe Analytics och klicka på **[!UICONTROL Workspace]** -fliken.
1. Klicka **[!UICONTROL Create project]** och väljer **[!UICONTROL Blank mobile scorecard]** projektmall.
1. Klicka på **[!UICONTROL Create]**.

![Styrkortsmall](assets/new_template.png)

### Verktyg-menyn

1. Från **[!UICONTROL Tools]** meny, välja **[!UICONTROL Analytics dashboards (Mobile App)]**.
1. På nästa skärm klickar du på **[!UICONTROL Create new scorecard]**.

## Konfigurera styrkortet med data och spara det {#configure}

Så här implementerar du styrkortsmallen:

1. Under **[!UICONTROL Properties]** (i den högra listen), ange en **[!UICONTROL Project report suite]** som du vill använda data från. Rapportsviter är datavyer i CJA.

   ![Val av rapportsvit](assets/properties_save.png)

1. Om du vill lägga till en ny platta i styrkortet drar du ett mått från den vänstra panelen och släpper det i **[!UICONTROL Drag and Drop Metrics Here]** zon. Du kan också infoga ett mätvärde mellan två rutor med ett liknande arbetsflöde.

   ![Lägg till rutor](assets/build_list.png)


1. Från varje ruta kan du visa en detaljerad vy som visar ytterligare information om måttet, till exempel de översta objekten för en lista med relaterade dimensioner.

## Lägg till mått eller mätvärden {#dimsmetrics}

Om du vill lägga till en relaterad dimension till ett mått drar du det från den vänstra panelen och släpper det på en platta.

Du kan till exempel lägga till lämpliga dimensioner (som **[!DNL Marketing Channel]**, i det här exemplet) till **[!UICONTROL Unique Visitors]** genom att dra och släppa det på plattan. Dimensioner visas under [!UICONTROL Drill Ins] (uppdelning) i den rutspecifika delen **[!UICONTROL Properties]**. Du kan lägga till flera dimensioner till varje platta.

![Lägg till dimensioner](assets/layer_dimensions.png)

## Använda filter {#filters}

Om du vill använda filter på enskilda plattor drar du ett filter (segment är filter i CJA) från den vänstra panelen och släpper det direkt ovanpå plattan.

Om du vill använda filtret på alla rutor i styrkortet släpper du rutan ovanpå styrkortet. Du kan också använda filter genom att välja filter på filtermenyn under datumintervallen. Du [konfigurera och använda filter för styrkort](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) på samma sätt som i Adobe Analytics Workspace.

![Skapa filter](assets/segment_ui.png)

## Lägg till datumintervall {#dates}

Lägg till och ta bort datumintervallkombinationer som kan väljas i styrkortet genom att markera listrutan för datumintervall.

![Nytt poängkort](assets/new_score_card.png)

Varje nytt styrkort börjar med 6 kombinationer av datumintervall som fokuserar på data från idag och igår. Du kan ta bort onödiga datumintervall genom att klicka på x eller redigera varje datumintervallkombination genom att klicka på pennan.

![Nytt poängkort2](assets/new_score_card2.png)

Om du vill skapa eller ändra ett primärt datum använder du listrutan för att välja bland tillgängliga datumintervall eller drar och släpper en datumkomponent från den högra listen i släppzonen.

![Nytt poängkort3](assets/new_score_card3.png)

Om du vill skapa ett jämförelsedatum kan du välja bland praktiska förinställningar för vanliga tidsjämförelser i listrutan. Du kan också dra och släppa en datumkomponent från den högra listen.

![Nytt poängkort4](assets/new_score_card4.png)

Om det datumintervall du vill använda inte har skapats ännu kan du skapa ett nytt genom att klicka på kalenderikonen.

![Nytt poängkort5](assets/new_score_card5.png)

Du kommer då till datumintervallsverktyget där du kan skapa och spara en ny datumintervallkomponent.

## Använd visualiseringar {#viz}

Kontrollpanelerna för analyser erbjuder fyra visualiseringar som ger er insikt i dimensionsobjekt och mätvärden. Byt till en annan visualisering genom att ändra [!UICONTROL chart type] av en bricka [!UICONTROL Properties]. Markera bara den högra rutan och ändra sedan diagramtypen.

![Egenskaper för rutor](assets/properties.png)

Eller klicka på [!UICONTROL Visualizations] ikonen i den vänstra listen och dra och släpp den högra visualiseringen på plattan:

![Visualiseringar](assets/vizs.png)

### [!UICONTROL Summary Number]

Använd visualisering av sammanfattningsnummer för att markera ett stort tal som är viktigt i ett projekt.

![Sammanfattningsnummer](assets/summary-number.png)

### [!UICONTROL Donut]

På samma sätt som ett cirkeldiagram visar den här visualiseringen data som en del av en helhet. Använd ett mundiagram när du jämför procentandelar av en summa. Låt oss till exempel säga att du vill se vilken annonsplattform som har bidragit till det totala antalet unika besökare:

![Visualisering av ring](assets/donut-viz.png)

### [!UICONTROL Line]

Radvisualiseringen representerar mätvärden som använder en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram visar måtten över tiden men fungerar med alla visualiseringar. Du visualiserar produktkategoridimensionen i det här exemplet.

![Radvisualisering](assets/line.png)

### [!UICONTROL Horizontal Bar]

Den här visualiseringen visar vågräta staplar som representerar olika värden för ett eller flera mätvärden. Om du till exempel vill se vad dina bästa produkter är kan du använda [!UICONTROL Horizontal Bar] för din egen visualisering.

![vågrätt streck](assets/horizontal.png)

### Ta bort [!UICONTROL Unspecified] dimensionsuppgift

Om du vill ta bort [!UICONTROL Unspecified] dimensionsobjekt från dina data, gör följande:

1. Välj rätt platta.
1. I rätt spår, under **[!UICONTROL Drill ins]** markerar du högerpilen bredvid dimensionsobjektet vars **[!UICONTROL Unspecified]** objekt som du vill ta bort.

   ![ospecificerad](assets/unspecified.png)

1. Klicka på ikonen bredvid **[!UICONTROL Unspecified]** för att ta bort ospecificerade data från din rapportering. (Du kan även ta bort andra dimensionsobjekt.)

## Visa och konfigurera egenskaper för paneler {#tiles}

När du klickar på en platta i Styrkortbyggaren visas egenskaperna och egenskaperna för plattan och dess detaljbild i den högra listen. På den här listen kan du ange en ny **Titel** för plattan och konfigurera plattan genom att använda filter. Segment är filter i CJA.

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

Om du vill ta bort en komponent som har tillämpats på hela styrkortet klickar du var som helst på styrkortet utanför rutorna och tar sedan bort den genom att klicka på **x** som visas när du hovrar över komponenten, som visas nedan för **Första gången du besöker**:

![Remove_components](assets/new_remove.png)

## Styrkort för förhandsgranskning {#preview}

Du kan förhandsgranska hur styrkortet kommer att se ut och fungera när det har publicerats i kontrollpanelsappen för Analytics.

1. Klicka **[!UICONTROL Preview]** i skärmens övre högra hörn.

   ![Preview_scorecards](assets/preview.png)

1. Om du vill visa hur styrkortet kommer att se ut på olika enheter väljer du en enhet på menyn [!UICONTROL Device preview] nedrullningsbar meny.

   ![Device_preview](assets/device-preview.png)

1. Om du vill interagera med förhandsgranskningen kan du:

   * Vänsterklicka för att simulera knackning på telefonskärmen.

   * Använd datorns rullningsfunktion för att simulera rullning av telefonskärmen med fingret.

   * Klicka och håll ned för att simulera att du trycker och håller fingret på telefonskärmen. Detta är användbart när du vill interagera med visualiseringarna i den detaljerade vyn.

## Namnge ett styrkort {#name}

Om du vill namnge styrkortet klickar du på namnutrymmet längst upp till vänster på skärmen och skriver det nya namnet.

![Naming_Scorecards](assets/new_name.png)

## Dela ett styrkort {#share}

Så här delar du styrkortet med en verkställande användare:

1. Klicka på **[!UICONTROL Share]** meny och välj **[!UICONTROL Share scorecard]**.

1. I **[!UICONTROL Share mobile scorecard]** fylla i fälten med:

   * Ange namnet på styrkortet
   * Ange en beskrivning av styrkortet
   * Lägga till relevanta taggar
   * Ange mottagare för styrkortet

1. Klicka på **[!UICONTROL Share]**.

![Dela_styrkort](assets/new_share.png)

När du har delat ett styrkort kan mottagarna komma åt det på sina kontrollpaneler i Analytics. Om du gör senare ändringar i styrkortet i Styrkortbyggaren uppdateras de automatiskt i det delade styrkortet. Chefsanvändare ser sedan ändringarna när styrkortet har uppdaterats i sin app.

Om du uppdaterar styrkortet genom att lägga till nya komponenter kanske du vill dela styrkortet igen (och kontrollera **[!UICONTROL Share embedded components]** för att se till att dina chefsanvändare har tillgång till dessa ändringar.
