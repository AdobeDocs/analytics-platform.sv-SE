---
description: I verktyget Calculated Metrics Builder finns en arbetsyta där du kan dra och släppa Dimensioner, mått, filter och funktioner för att skapa anpassade mått baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla beräknade mätvärden eller komplexa avancerade beräknade mätvärden.
title: Skapa mätvärden
source-git-commit: a747a7e7def6f55fd350406125581e631af9e208
workflow-type: tm+mt
source-wordcount: '917'
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

## UI-komponenter {#ui-components}

| Fält | Beskrivning |
| --- | --- |
| Titel | Det är obligatoriskt att namnge måttet. Du kan inte spara måttet om det inte har ett namn. |
| Beskrivning | Ge den en användarvänlig beskrivning för att visa vad den används för och skilja den från liknande. Beskrivningen visas också i en rapport. Det är bäst att INTE placera formeln i beskrivningen. Beskriv i stället vad det här måttet ska och inte ska användas för. (Formeln genereras när du bygger måttet, under rubriken Sammanfattning. Därför behöver du inte lägga till formeln i beskrivningen.) |
| Format | Du kan välja Decimal, Time, Percent och Currency. |
| Decimaler | Visar hur många decimaler som ska visas i rapporten. Det maximala antalet decimaler som du kan ange är 10. |
| Visa uppåttrend som.. | Den här inställningen för metrisk polaritet visar om Analytics bör ta hänsyn till en uppåtgående trend i mätvärdet som god (grön) eller dålig (röd). Därför visas rapportens diagram som grönt eller rött när det går upp. |
| Valuta | Basvalutan för den här datavyn. |
| Taggar | Taggning är ett bra sätt att ordna mätvärden. Alla användare kan skapa taggar och använda en eller flera taggar i ett mätresultat. Men du kan bara se taggar för de segment som du äger eller som har delats med dig. Vilka typer av taggar ska du skapa? Här följer några förslag på användbara taggar:<ul><li>Taggar baserade på teamnamn, som Social Marketing och Mobile Marketing.</li><li>Projekttaggar (analystaggar), t.ex. Sidanalys.</li><li>Kategoritaggar: Män geografi.</li><li>Arbetsflödestaggar: För godkännande. Kuraterad för (en specifik affärsenhet)</li></ul> |
| Sammanfattning | The [!UICONTROL Summary] formeln uppdateras varje gång du ändrar måttdefinitionen. Formeln visas också i måttfältet till vänster när du håller muspekaren över ett mätresultat och klickar på ikonen. |
| Definition | Här drar du i mått/beräknade mått, filter och/eller funktioner för att skapa det beräknade måttet. Om du drar i ett beräknat mått expanderas måttdefinitionen automatiskt. Du kan kapsla definitioner med behållare. Till skillnad från segmentbehållare fungerar dessa behållare som ett matematiskt uttryck och avgör ordningen på åtgärderna. |
| Operator | [!UICONTROL Divided by] är standardoperatorn, plus operatorerna +, - och x. |
| Förhandsgranska | Ger en snabb läsning av eventuella fel. Förhandsvisningen täcker de senaste 90 dagarna. Det här är ett sätt att först mäta om du har valt rätt komponenter för måttet. Ett oväntat resultat skulle innebära att du måste ta en andra titt på måttdefinitionen. |
| Produktkompatibilitet | Produktkompatibiliteten visar om mätvärdena är kompatibla med fullständigt bearbetade data. |
| Lägg till | För alla typer av beräknade värden kan du lägga till behållare och statiska tal i definitionen. För avancerade beräknade mätvärden kan du även lägga till filter och funktioner.<ul><li>Behållare fungerar som ett matematiskt uttryck och avgör ordningen på operationerna. Allt i en behållare bearbetas alltså före nästa åtgärd.</li><li>När du drar ett segment till en behållare segmenteras allt i behållaren. (Endast avancerade beräknade värden)</li><li>Du kan stapla flera filter i en behållare.</li></ul> |
| Kugghjulsikon (Mättyp, Attribution) | Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange mät- och attribueringsmodeller. |
| + Ny | Gör att du kan skapa en ny komponent, till exempel ett nytt filter (som tar dig till filterverktyget .) |
| Sökkomponenter | Med det här sökfältet kan du söka efter dimensioner, mått, segment (endast avancerade beräknade värden) och funktioner (endast avancerade beräknade värden). |
| Lista över Dimensioner | Istället för att lämna verktyget Beräknad metrisk Builder för att skapa ett enkelt filter (i Filter Builder), t.ex. &quot;Page = Homepage&quot; kan du dra i Page och välja Homepage direkt från Calculated Metric Builder. Detta ger ett mycket effektivare arbetsflöde för att skapa filtrerade beräknade mätvärden. |
| Lista över mått | Mätvärden finns i tre kategorier:<ul><li>Standardmått</li><li>Beräknade värden</li><li>Mätmallar - längst ned i listan.</li></ul>När du hovrar över ett mätresultat visas ikonen Info till höger om det. Om du klickar på den här ikonen visas följande information:<ul><li>Formeln för hur den beräknas.</li><li>En förgranskningstrend för måttet.</li><li>En redigeringsikon (penna) längst upp till höger som tar dig till verktyget Beräknade mått där du kan redigera det beräknade måttet.</li></ul> |
| Lista med filter | (Endast avancerade beräknade värden) Som administratör visar den här listan alla filter som har skapats i ditt inloggningsföretag. Om du inte är administratör visas de filter som du äger och de som delas med dig. |
| Lista över funktioner | (Endast avancerade beräknade mätvärden) Funktionerna är uppdelade i två listor: Grundläggande (används oftast) och Avancerat. |
| Datavyväljare | Med den här väljaren (längst upp till höger) kan du växla till en annan datavy. |

