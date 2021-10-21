---
description: I verktyget Calculated Metrics Builder finns en arbetsyta där du kan dra och släppa Dimensioner, mått, filter och funktioner för att skapa anpassade mått baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla beräknade mätvärden eller komplexa avancerade beräknade mätvärden.
title: Skapa mätvärden
source-git-commit: e50636784e406da84c986645ac380d68d9622bc6
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 1%

---

# Skapa mätvärden

I verktyget Calculated Metrics Builder finns en arbetsyta där du kan dra och släppa Dimensioner, mått, filter och funktioner för att skapa anpassade mått baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla beräknade mätvärden eller komplexa avancerade beräknade mätvärden.

Det finns flera sätt att komma åt verktyget för beräkning av mått:

* Öppna ett projekt i Analysis Workspace och klicka på  **[!UICONTROL + New]** > **[!UICONTROL Create Metric]** .
* I [!DNL Analytics], gå till **[!UICONTROL Components]** > **[!UICONTROL Calculated Metrics]**.

* Klicka **[!UICONTROL + Add]** högst upp på [Beräknad måtthanterare](/help/components/calc-metrics/cm-workflow/cm-manager.md), eller

* Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, öppna en rapport och klicka på Metrics-ikonen  ![](assets/metrics_icon.png) för att visa måttspåret och sedan klicka **[!UICONTROL Add]**.

![](assets/cm_builder_ui.png)

## UI-komponenter {#section_9382AEEBA4244DD6A9F6C1DD3F6D076B}

<table id="table_60A82936321047D1A335331BF83B0972"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Fält </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Titel </span> </td> 
   <td colname="col3"> <p>Det är obligatoriskt att namnge måttet. Du kan inte spara måttet om det inte har ett namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Beskrivning </span> </td> 
   <td colname="col3"> <p>Ge den en användarvänlig beskrivning för att visa vad den används för och skilja den från liknande. </p> <p>Beskrivningen visas också i en rapport. Det är bäst att INTE placera formeln i beskrivningen. Beskriv i stället vad det här måttet ska och inte ska användas för. (Formeln genereras när du bygger måttet, under rubriken Sammanfattning. Därför behöver du inte lägga till formeln i beskrivningen.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Format </span> </td> 
   <td colname="col3"> <p>Du kan välja Decimal, Time, Percent och Currency. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Decimaler </span> </td> 
   <td colname="col3"> <p>Visar hur många decimaler som ska visas i rapporten. Det maximala antalet decimaler som du kan ange är 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Visa uppåttrend som.. </span> </td> 
   <td colname="col3"> <p>Den här inställningen för metrisk polaritet visar om Analytics bör ta hänsyn till en uppåtgående trend i mätvärdet som god (grön) eller dålig (röd). Därför visas rapportens diagram som grönt eller rött när det går upp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Taggar </span> </td> 
   <td colname="col3"> <p>Taggning är ett bra sätt att ordna mätvärden. Alla användare kan skapa taggar och använda en eller flera taggar i ett mätresultat. Men du kan bara se taggar för de segment som du äger eller som har delats med dig. Vilka typer av taggar ska du skapa? Här följer några förslag på användbara taggar: 
     <ul id="ul_9A6CE5F179424687A39F2D5C1A953258"> 
      <li id="li_A8815F2D8D284874AD701A7B103D82A3">Taggar baserade på <b>gruppnamn</b>, som social marknadsföring, mobilmarknadsföring. </li> 
      <li id="li_A51A4515A541488E9D90296A955E9F4F"><b>Projekt</b> taggar (analystaggar), t.ex. analys på ingångssidan. </li> 
      <li id="li_B4605470A7094026AC168420B64BBCC3"><b>Kategori</b> taggar: Män geografi. </li> 
      <li id="li_B6EAB0F2A96C41209C4EC97B9E64390B"><b>Arbetsflöde</b> taggar: För godkännande. Kuraterad för (en specifik affärsenhet) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Sammanfattning </span> </td> 
   <td colname="col3"> <p>The <span class="uicontrol"> Sammanfattning </span> formeln uppdateras varje gång du ändrar måttdefinitionen. Formeln visas också i måttfältet till vänster när du håller muspekaren över ett mätresultat och klickar på <img placement="inline"  src="assets/i_icon.png" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> ikon. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Definition </span> </td> 
   <td colname="col3"> <p>Här drar du i mått/beräknade mått, segment och/eller funktioner för att skapa det beräknade måttet. </p> <p> 
     <ul id="ul_B13401A266354DC594C6176025DB61CB"> 
      <li id="li_01776C32C7C5440AA1F847096CBED92B">Om du drar i ett beräknat mått expanderas måttdefinitionen automatiskt. </li> 
      <li id="li_A483D352522E4572AB43042473053359">Du kan kapsla definitioner med behållare. Till skillnad från segmentbehållare fungerar dessa behållare som ett matematiskt uttryck och avgör ordningen på åtgärderna. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Operator </span> </td> 
   <td colname="col3"> <p>dividerat med ( <img placement="inline"  src="assets/divided_icon.png" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) är standardoperatorn och det finns operatorerna +, - och x. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Förhandsgranska </span> </td> 
   <td colname="col3"> <p>Ger en snabb läsning av eventuella fel. Förhandsvisningen täcker de senaste 90 dagarna. Det här är ett sätt att först mäta om du har valt rätt komponenter för måttet. Ett oväntat resultat skulle innebära att du måste ta en andra titt på måttdefinitionen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Lägg till </span> </td> 
   <td colname="col3"> <p>För alla typer av beräknade värden kan du lägga till behållare och statiska tal i definitionen. För avancerade beräknade mätvärden kan du även lägga till segment och funktioner. </p> <p> 
     <ul id="ul_607C1B303F334062BC620317667DE490"> 
      <li id="li_53462789B8AF4F1AA9B45565D37CF22B">Behållare fungerar som ett matematiskt uttryck och avgör ordningen på operationerna. Allt i en behållare bearbetas alltså före nästa åtgärd. </li> 
      <li id="li_401A9E0D8B3B468990289DBF66A06F63">När du drar ett segment till en behållare segmenteras allt i behållaren. (Endast avancerade beräknade värden) </li> 
      <li id="li_F191B200D7A944F9ADC0573A9A82A6DA">Du kan stapla flera segment i en behållare. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Kugghjulsikon ( <span class="uicontrol"> Mätningstyp </span>, <span class="uicontrol"> Attribut </span>) </td> 
   <td colname="col3"> <p>Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange <a href="/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md"  > metrisk typ och attribueringsmodeller </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> + Ny </span> </td> 
   <td colname="col3"> <p>Skapa en ny komponent, till exempel ett nytt filter (som tar dig till <a href="/help/components/filters/create-filters.md"  > Filter Builder </a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Sökkomponenter </p> </td> 
   <td colname="col3"> <p>Med det här sökfältet kan du söka efter dimensioner, mått, segment (endast avancerade beräknade värden) och funktioner (endast avancerade beräknade värden). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista över Dimensioner </p> </td> 
   <td colname="col3"> <p>Istället för att lämna beräkningsverktyget för att skapa ett enkelt segment (i segmentbyggaren), t.ex. "Page = Homepage" kan du dra i Page och välja Homepage direkt från Calculated Metric Builder. </p> <p>Detta ger ett mycket effektivare arbetsflöde för att skapa segmenterade beräknade mätvärden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista över mått </p> </td> 
   <td colname="col3"> <p>Mätvärden finns i tre kategorier: </p> 
    <ul id="ul_7BF50F4964EF45858FBA1634FBFA45CF"> 
     <li id="li_90F2312927A6499CA1CE04F8FFC912CF">Standardvärden ( <img placement="inline"  src="assets/met_icon.png" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li> 
     <li id="li_A3F59083E79B4AC780D6F8CEDFFD20C9">Beräknade värden ( <img placement="inline"  src="assets/calc_met_icon.png" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li> 
     <li id="li_8735E76637ED4C3F983731A66E04C93E">Mätningsmallar ( <img placement="inline"  src="assets/cm_template_icon.png" width="25px" id="image_D236601511CC4DD3828F223431E27E88" />) - längst ned i listan. </li> 
    </ul> <p>När du hovrar över ett mätresultat visas ikonen Info till höger om det: <img placement="inline"  src="assets/info.png" width="150px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Om du klickar på den här ikonen visas följande information: </p> 
    <ul id="ul_DF35DDB9FBFA40C8A93FA0F2286A0BBE"> 
     <li id="li_4215AA9BF93F4C8B941002A7A4D2F50B">Formeln för hur den beräknas. </li> 
     <li id="li_6A8E39EB6DCE4377B0B594B6D4FC0294">En förgranskningstrend för måttet. </li> 
     <li id="li_44C1595E4BE64ED69D1DB3BB6655ED55">En redigeringsikon (penna) längst upp till höger som tar dig till verktyget Beräknade mått där du kan redigera det beräknade måttet. </li> 
    </ul> <p><img placement="break" align="center"  src="assets/info2.png" width="200px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista med filter </p> </td> 
   <td colname="col3"> <p>(Endast avancerade beräknade värden) Som administratör visar den här listan alla filter som har skapats i ditt inloggningsföretag. Om du inte är administratör visas de filter som du äger och de som delas med dig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista över funktioner </p> </td> 
   <td colname="col3"> <p>(Endast avancerade beräknade mätvärden) Funktionerna är uppdelade i två listor: <a href="/help/components/calc-metrics/cm-functions.md"  > Grundläggande </a> (används oftast) och <a href="/help/components/calc-metrics/cm-adv-functions.md"  > Avancerat </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Datavyväljare </p> </td> 
   <td colname="col3"> <p>Växla till en annan datavy. </p> </td> 
  </tr> 
 </tbody> 
</table>
