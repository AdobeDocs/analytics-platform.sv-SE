---
description: Skapa ett projekt och lägg till komponenter (mått, mått, filter, datumintervall) på frihandspanelen.
keywords: Analysis Workspace
title: Skapa ett Workspace-projekt
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 15%

---


# Skapa ett Workspace-projekt

Skapa ett projekt och lägg till komponenter (mått, mått, filter, datumintervall) på frihandspanelen.

I den här artikeln får du information om Analysis Workspace gränssnittselement och hur du skapar ett projekt.

## Skapa ett projekt

1. Ange användarbehörighet för att skapa och strukturera projekt.

   Innan du skapar eller strukturerar ett Analysis Workspace-projekt måste administratörer lägga till dig i en grupp med behörigheten **[!UICONTROL Create / Curate Projects in Analysis Workspace]** aktiverad, eller i användargruppen **[!UICONTROL All Report Access]**. ( **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > [Grupper](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html)).

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** i [!DNL Experience Cloud].

   ![](assets/analysis_workspace_menu.png)

   Du kan också ange ett snedstreck (/) för att öppna rapportens sökfält och sedan skriva *`workspace`*.

   ![](assets/analysis-app-search.png)

1. Klicka på **[!UICONTROL Create New Project]**.

   Du kan välja om du vill skapa ett projekt från

* Ett tomt projekt (standard). Instruktioner finns nedan.
* En anpassad mall. De här mallarna skapas av användare med administratörsbehörighet.

   ![](assets/start_modal.png)

1. Om du vill skapa ett projekt från ett tomt projekt klickar du på **[!UICONTROL Blank Project]**.

   * Klicka sedan på **[!UICONTROL Create]** eller
   * Klicka bara på **[!UICONTROL Enter]**.

   Ett tomt projekt visas med en friformspanel och en datatabellvisualisering.

   ![](assets/fa_project_new.png)

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > Komponenter</a> </td> 
   <td colname="col2"> <p>Dimensioner, mätvärden, filter och datumintervall som du kan dra in i projekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualiseringar</a> </td> 
   <td colname="col2"> <p>Objekt som du kan dra till panelen eller projektområdena i gränssnittet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md"  > Frihandspanelen  </a> </td> 
   <td colname="col2"> <p>Arbetsytan eller arbetsytan som du interagerar med i Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Spara projektet. Ge projektet ett namn, ange en beskrivning (valfritt, men användbart) och tagga projektet (valfritt) och klicka sedan på **[!UICONTROL Save Project]**.

   ![](assets/save_project.png)

1. Du kan nu högerklicka och kopiera en visualisering eller panel och sedan klistra in (infoga) det kopierade elementet på en annan plats i projektet eller i ett annat projekt.

   Du kan använda den här funktionen för att skapa byggstenar – fördefinierade visualiseringar/paneler – som kan kopieras till andra projekt för att komma igång snabbare och med data som är specifika för ert företag.

   >[!NOTE]
   >
   >När du har kopierat/sparat som är länkar nu relativt till det projekt de bor i, inte det ursprungliga projektet som de kopierades från.

## Lägga till komponenter och visualiseringar {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. Bygg ditt projekt genom att dra *`components`* och *`visualizations`* till projektet.

   **Komponenter**

   I verktygsfältet Komponent visas sökbara mått, mått, filter och datumintervall som du använder oftast.

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komponent </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensioner (orange) </td> 
   <td colname="col2"> <p>Använd på projektnivå </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Prop#, eVar# och event# läggs till i dimensionsnamnen, och du kan söka efter dessa siffror. Exempel: "Internal Campaign" visas i det vänstra fältet som "Internal Campaign (evar2)". </p> <p> Observera att prop-, eVar- och händelsenumren inte visas i tabellen (för att hålla titlarna korta). </p> <p>Det finns en standardsorteringsordning för vissa färdiga dimensioner, när de dras till en friformstabell eller när de visas i den vänstra listen. När"Timme på dagen" släpps till exempel i ett bord eller visas i det vänstra fältet sorteras det från 12:00-11:00. Du kan fortfarande välja att sortera efter valfri mätvärdeskolumn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrisk (grön) </td> 
   <td colname="col2"> <p>Använd på projektnivå. </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> Förekomst </span> är datatabellens standardmått. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter (blå) </td> 
   <td colname="col2"> <p>Det går bara att dra på panelnivå, men du kan skapa textbundna filter i datatabellen. </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>Mer information finns i <a href="/help/analysis-workspace/components/t-freeform-project-segment.md"  >-filter </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datumintervall och detaljrikedom (lila) </td> 
   <td colname="col2"> <p>Kan endast dras på panelnivå. Du kan skapa ett projekt från kalendern när du konfigurerar ett datumintervall. </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[Visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

Panelen [!UICONTROL Visualizations] innehåller standarddiagram för analyser, diagram, donuts, datatabeller, [kohort](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)-tabeller, Venndiagram o.s.v. Du kan dra och släppa flera visualiseringar i ditt projekt.

![Stegresultat](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. Steg

## Använd högerklicksmenyn för att anpassa data {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

Med högerklicksmenyn kan du utföra följande åtgärder, beroende på vilken cell i en tabell du högerklickar på.

![Stegresultat](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Åtgärd </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Lägg till tidsperiodkolumn</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Jämför tidsperioder</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kopiera till Urklipp </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta bort markerade </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > Skapa avisering från markering</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > Uppdelningar</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">Mått </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">Mätvärden </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">Filter </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">Tid </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualisera</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/curate-share/download-send.md"  > Hämta som CSV</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/home.md"  > Trendval</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/t-freeform-project-segment.md"  > Skapa filter från markering</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visa endast markerade rader </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visa alla rader </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Mer information om hur du kopierar och markerar rader finns i [Interaktioner för tangentbord och mus i Analysis Workspace](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).
