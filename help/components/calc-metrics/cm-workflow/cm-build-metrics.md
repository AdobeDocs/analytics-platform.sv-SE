---
description: I verktyget Calculated Metrics Builder finns en arbetsyta där du kan dra och släppa Dimensioner, mått, filter och funktioner för att skapa anpassade mått baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla beräknade mätvärden eller komplexa avancerade beräknade mätvärden.
title: Bygg mått
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: cdab5d8b674527a1c3f950284daac65d0ab01900
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 0%

---

# Bygg mätvärden

Customer Journey Analytics har en arbetsyta där du kan dra och släppa dimensioner, mått, filter och funktioner för att skapa anpassade mått baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla beräknade mätvärden eller komplexa avancerade beräknade mätvärden.

## Börja skapa ett beräknat mått

Du kan använda verktyget för beräknade mätvärden för att skapa beräknade mätvärden. När de skapas på det här sättet är beräknade värden tillgängliga i komponentlistan och kan sedan användas i projekt i hela organisationen. Du kan också skapa ett snabbt beräknat mått enligt beskrivningen i [Skapa beräknade värden för ett enskilt projekt](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) i [Metrisk](/help/components/apply-create-metrics.md).

Gå till verktyget för beräknade värden för att börja skapa ett beräknat mått som är tillgängligt i komponentlistan.

1. Använd verktyget för beräknade värden på något av följande sätt:

   * Öppna ett projekt i Analysis Workspace och välj sedan **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
   * Öppna ett projekt i Analysis Workspace och välj sedan ikonen **Plus** bredvid avsnittet [!UICONTROL **Metrisk**] i den vänstra listen.
   * I [!DNL Customer Journey Analytics] går du till **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]** och väljer sedan **[!UICONTROL + Add]** högst upp på sidan Beräknade mått.

1. Fortsätt med [Områden i det beräknade måttverktyget](#areas-of-the-calculated-metrics-builder).

## Områden för verktyget för beräknade mätvärden

I följande bild och medföljande tabell förklaras några av huvudområdena och funktionerna i verktyget för beräkning av mätvärden.

![Nytt fönster med beräknade mått som visar de huvudområden och funktioner som beskrivs i det här avsnittet.](assets/cm_builder_ui.png)

| Fält | Beskrivning |
| --- | --- |
| Titel | Det är obligatoriskt att namnge måttet. Du kan inte spara måttet om det inte har ett namn. |
| Beskrivning | Ge den en användarvänlig beskrivning för att visa vad den används för och skilja den från liknande. <p>Beskrivningen visas också i en rapport. Det är bäst att INTE placera formeln i beskrivningen. Beskriv i stället vad det här måttet ska och inte ska användas för. (Formeln genereras när du bygger måttet, under rubriken Sammanfattning. Därför behöver du inte lägga till formeln i beskrivningen.) </p> |
| Format | Du kan välja Decimal, Time, Percent och Currency. |
| Decimaler | Visar hur många decimaler som ska visas i rapporten. Det maximala antalet decimaler som du kan ange är 10. |
| Visa uppåttrend som.. | Den här inställningen för metrisk polaritet visar om Analytics bör ta hänsyn till en uppåtgående trend i mätvärdet som god (grön) eller dålig (röd). Därför visas rapportens diagram som grönt eller rött när det går upp. |
| Valuta | Basvalutan för den här datavyn. |
| Taggar | Taggning är ett bra sätt att ordna mätvärden. Alla användare kan skapa taggar och använda en eller flera taggar i ett mätresultat. Men du kan bara se taggar för de filter som du äger eller som har delats med dig. Vilka typer av taggar ska du skapa? Här följer några förslag på användbara taggar:<ul><li>**Teamnamn**, till exempel Social Marketing, Mobile Marketing.</li><li>**Projekt** (analystaggar), t.ex. Sidanalys.</li><li>**Kategorier**, till exempel Kvinnors, Geografi.</li><li>**Arbetsflöden**, till exempel Att godkännas; Kuraterat för (en specifik affärsenhet)</li></ul> |
| Sammanfattning | <p>Sammanfattningsformeln uppdateras varje gång du ändrar måttdefinitionen. Formeln visas också i måttfältet till vänster när du håller muspekaren över ett mätresultat och klickar på <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />-ikon. </p> |
| Definition | Här drar du i mått/beräknade mått, filter och/eller funktioner för att skapa det beräknade måttet. <ul><li>Om du drar i ett beräknat mått expanderas måttdefinitionen automatiskt. </li> <li>Du kan kapsla definitioner med behållare. Till skillnad från filterbehållare fungerar dessa behållare som ett matematiskt uttryck och avgör ordningen på åtgärderna. </li> </ul> |
| Operator | dividerat med ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) är standardoperatorn och det finns operatorerna +, - och x. |
| Förhandsgranska | Ger en snabb läsning av eventuella fel. Förhandsvisningen täcker de senaste 90 dagarna. Det här är ett sätt att först mäta om du har valt rätt komponenter för måttet. Ett oväntat resultat skulle innebära att du måste ta en andra titt på måttdefinitionen. |
| Produktkompatibilitet | För beräknade värden som du skapar i Customer Journey Analytics visas det här värdet alltid som [!UICONTROL **fullständigt bearbetade data**]. Beräknade mått kan bara innehålla data från händelsedatamängder. |
| Lägg till | För alla typer av beräknade värden kan du lägga till behållare och statiska tal i definitionen. För avancerade beräknade mätvärden kan du även lägga till filter och funktioner.<ul><li>Behållare fungerar som ett matematiskt uttryck och avgör ordningen på operationerna. Allt i en behållare bearbetas alltså före nästa åtgärd.</li><li>När du drar ett filter till en behållare filtreras allt i behållaren. (Endast avancerade beräknade mätvärden)</li><li>Du kan stapla flera filter i en behållare.</li></ul> |
| Kugghjulsikon (Mättyp, Attribution) | Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange mät- och attribueringsmodeller. <p>**Obs!** Tänk på följande när du uppdaterar en komponents attribuering till en icke-standardattribueringsmodell:</p><ul><li>**När komponenten används i en rapport med *en enda dimension*:** Komponentens attribuering ignorerar allokeringsmodellen när en icke-standardattribueringsmodell används.</li><li>**När komponenten används i en rapport med *flera dimensioner*:** Komponentens attribuering behåller allokeringsmodellen när en icke-standardattribueringsmodell används.</li><li>Flera dimensioner är bara tillgängliga när [exporterar data till molnet](/help/analysis-workspace/export/export-cloud.md).</li></ul> <p>Mer information om allokering finns i [Inställningar för Persistence-komponent](/help/data-views/component-settings/persistence.md).</p> |
| Plustecken (+), ikon | Gör att du kan skapa en ny komponent, till exempel ett nytt filter (som tar dig till filterverktyget .) |
| Sökkomponenter | Med det här sökfältet kan du söka efter dimensioner, mått, filter (endast avancerade beräknade värden) och funktioner (endast avancerade beräknade värden). |
| Lista över Dimensioner | I stället för att lämna det beräknade måttverktyget för att skapa ett enkelt filter (i filterverktyget), t.ex. &quot;Page = Homepage&quot;, kan du dra sidan och välja Hemsida direkt från det beräknade måttverktyget. Detta resulterar i ett mycket effektivare arbetsflöde för att skapa filtrerade beräknade mätvärden. |
| Lista över mått | Mätvärden finns i tre kategorier:<ul><li>Standardmått</li><li>Beräknade mått</li><li>Mätmallar - längst ned i listan.</li></ul>När du hovrar över ett mätresultat visas ikonen Info till höger om det. Om du klickar på den här ikonen visas följande information:<ul><li>Formeln för hur den beräknas.</li><li>En förgranskningstrend för måttet.</li><li>En redigeringsikon (penna) längst upp till höger som tar dig till verktyget för beräknade mätvärden där du kan redigera det här beräknade måttet.</li></ul> |
| Lista med filter | (Endast avancerade beräknade värden) Som administratör visar den här listan alla filter som har skapats i ditt inloggningsföretag. Om du inte är administratör visas de filter som du äger och de som delas med dig. |
| Lista över funktioner | (Endast avancerade beräknade mätvärden) Funktionerna är uppdelade i två listor: Grundläggande (används oftast) och Avancerat. |
| Datavyväljare | Med den här väljaren (längst upp till höger) kan du växla till en annan datavy. |
