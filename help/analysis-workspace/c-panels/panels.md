---
description: En panel är en samling tabeller och visualiseringar
title: Paneler - översikt
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: e61368765dde35e6d9beed7713a7a28db0c2af98
workflow-type: tm+mt
source-wordcount: '2033'
ht-degree: 1%

---

# Paneler - översikt

En [!UICONTROL panel] är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i Workspace eller en [tom panel](/help/analysis-workspace/c-panels/blank-panel.md). Paneler är användbara när du vill ordna dina projekt efter tidsperioder, datavyer eller användningsfall för analyser.

## Paneltyper

Följande paneltyper är tillgängliga i Analysis Workspace för [!UICONTROL Customer Journey Analytics]:

| Panelnamn | Beskrivning |
| --- | --- |
| [Tom panel](/help/analysis-workspace/c-panels/blank-panel.md) | Välj bland tillgängliga paneler och visualiseringar för att starta analysen. |
| [Attribution](attribution.md) | Jämför och visualisera snabbt valfritt antal attribueringsmodeller med alla mått och konverteringsvärden. |
| [Experimentation](experimentation.md) | Jämför olika användarupplevelser, marknadsförings- och meddelandevarianter för att avgöra vilket som är bäst för att få fram ett visst resultat. |
| [Frihand](freeform-panel.md) | Utför obegränsade jämförelser och uppdelningar och lägg sedan till visualiseringar för att berätta en utförlig databerättelse. |
| [Medel - genomsnittlig minutpublik](average-minute-audience-panel.md) | Analysera den genomsnittliga minuten-publiken för ett visst innehåll eller under en anpassad tidsperiod. |
| [Medievisningsprogram för samtidig användning](media-concurrent-viewers.md) | Analysera samtidiga tittare över tid, med information om maximal samtidighet och möjlighet att dela upp och jämföra. |
| [Tidsåtgång för uppspelning av media](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | Analysera den uppspelningstid som används för att förstå var högfrekvenser förekommer eller var bortfall inträffar. |
| [Nästa eller föregående objekt](next-previous.md) | Visa nästa eller föregående sidor som andra går till. |
| [Snabba insikter](quickinsight.md) | Bygg snabbt ett frihandsbord och en medföljande visualisering för att analysera och hitta insikter snabbare. |


[!UICONTROL Quick insights]-, [!UICONTROL Blank]- och [!UICONTROL Freeform]-panelerna är bra platser att starta analysen på, medan [!UICONTROL Attribution] är intresserad av mer avancerade analyser. En ![AddCircle](/help/assets/icons/AddCircle.svg) finns längst ned på arbetsytan, så du kan när som helst lägga till tomma paneler.

Standardstartpanelen är panelen [!UICONTROL Freeform], men du kan göra den [tomma panelen](/help/analysis-workspace/c-panels/blank-panel.md) eller [snabbinsikterna](/help/analysis-workspace/c-panels/quickinsight.md) till standard. Se [Inställningar för projekt och analys](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences).


## Skapa en panel

Så här skapar du en panel:

* Dra och släpp en panel från den vänstra panelen på arbetsytan i **[!UICONTROL Panels]**.
* Välj en panel på panelen [Tom](blank-panel.md).
* Använd menyn **[!UICONTROL Insert]** i Workspace och markera panelen. Du kan också använda något av [kortkommandona](../build-workspace-project/fa-shortcut-keys.md) för att infoga en panel.

  ![Skapa en panel](assets/create-panel.png)

Ni kan:

* Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **i** en panel om du vill lägga till en annan visualisering. Ett popup-fönster visas där du kan välja en visualisering.

  ![Popup som visar möjliga visualiseringar](assets/blank-panel.png)

  | Välj.. | Skapa en.. |
  |---|---|
  | ![Tabell](/help/assets/icons/Table.svg) | [Frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![Linjediagram](/help/assets/icons/GraphTrend.svg) | [Linjediagram](/help/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Bar](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [Sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Text](/help/assets/icons/Text.svg) | [Text](/help/analysis-workspace/visualizations/text.md) |
  | ![ConversionTratt](/help/assets/icons/ConversionFunnel.svg) | [Utfall](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![Arbetsflöde](/help/assets/icons/GraphPathing.svg) | [Flöde](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStached](/help/assets/icons/GraphAreaStacked.svg) | [Område staplat](/help/analysis-workspace/visualizations/area.md) |
  | ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Kohortabell](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![GraphBullet](/help/assets/icons/GraphBullet.svg) | [Punkt](/help/analysis-workspace/visualizations/bullet-graph.md) |
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Ringdiagram](/help/analysis-workspace/visualizations/donut.md) |
  | ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Histogram](/help/assets/icons/Histogram.svg) | [Histogram](/help/analysis-workspace/visualizations/histogram.md) |
  | ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Spridning](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![Typ](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [Treemap-diagram](/help/analysis-workspace/visualizations/treemap.md) |

* Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **utanför** den sista panelen på arbetsytan för att lägga till ytterligare en [tom panel](blank-panel.md).


## Datavy

Varje panel är associerad med en [datavy](/help/data-views/data-views.md) som identifieras av ![Data](/help/assets/icons/Data.svg) **[!UICONTROL *namnet på datavyn *]**i listrutan längst upp till höger på panelen.

När du skapar ett tomt Workspace-projekt är standarddatavyn för den första panelen datavyn som du senast arbetade med i Customer Journey Analytics.

När du skapar en ny panel baseras standarddatavyn på datavyn för den panel du senast arbetade på i Workspace-projektet.

>[!IMPORTANT]
>
>Den valda datavyn avgör vilka dimensioner, mätvärden och filter som är tillgängliga för att skapa visualiseringar i en panel.
>
>
>När du växlar en datavy för en panel kanske vissa komponenter inte är tillgängliga i den nya datavyn. Ändringen kan göra att visualiseringen inte återges korrekt. Du kan se varningar som:
>
>* Den här panelen innehåller komponenter som inte är aktiverade i den markerade datavyn. Ändra datavyn eller aktivera de nödvändiga komponenterna i datavyn.
>* Det gick inte att återge visualisering: Kontrollera kolumnerna och raderna för att se om de innehåller giltiga komponenter.
>

## Kalender

Panelkalendern styr rapportens datumintervall för tabeller och visualiseringar inom en panel.

>[!NOTE]
>
>Om en ![kalender](/help/assets/icons/Calendar.svg)-datumintervallkomponent används i en visualisering eller panel (till exempel som ett filter) åsidosätter datumintervallkomponenten panelkalendern.
>


![Kalenderfönstret visar det valda datumintervallet.](assets/panel-calendar.png)

1. Välj ett datumintervall genom att först markera startdatumet och sedan slutdatumet.
Du kan också välja en **[!UICONTROL Preset]** i listrutan [!UICONTROL *Välj en förinställning*].

1. Du kan också välja **[!UICONTROL Show advanced settings]** för att:

   * Ange **[!UICONTROL Start time]** och **[!UICONTROL End time]** förutom standardvärdena `12:00 AM` (`0:00`) och `11:59 PM` (`23:59`). Sluttider omfattar alltid 59 sekunder. För ett datumintervall som sträcker sig över många dagar gäller starttiden den första dagen i datumintervallet och sluttiden gäller den sista dagen i datumintervallet. Använd **[!UICONTROL (Reset time values)]** om du vill återställa start- och sluttiden till standardvärdena.
   * **[!UICONTROL Make date range components relative to panel calendar]**. Om det är inaktiverat är de datumintervallkomponenter som används på panelen relativa till den aktuella tiden. Om det här alternativet är aktiverat är de datumintervallskomponenter som används på panelen relaterade till panelkalendern.
   * **[!UICONTROL Use rolling dates]**. Om det här alternativet är aktiverat uppdateras förinställda datumintervall som **[!UICONTROL Last 7 full days]** dynamiskt som aktuellt datum- och tidsförlopp. Om du avaktiverar det uppdateras inte dessa förinställningar när de har använts.

     ![Rullande datum](assets/calendar-rolling.png)

     Du kan markera texten inom hakparenteser (till exempel **[!UICONTROL fixed start - rolling daily]**) för att utöka panelen och ange information för **[!UICONTROL Start]** och **[!UICONTROL End]**.

      1. Välj **[!UICONTROL Start of]**, **[!UICONTROL End of]** eller **[!UICONTROL Fixed day]**.
      1. När du har valt **[!UICONTROL Start of]** eller **[!UICONTROL End of]** kan du skapa ett fullständigt uttryck. Till exempel: **[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**. Välj lämpligt värde för varje enskild del av uttrycket.
         * Välj ett värde för aktuell. Till exempel **[!UICONTROL current year]**.
         * Välj ett värde för ytterligare beräkning. Exempel: **[!UICONTROL plus]**.
         * När du har angett ytterligare beräkning anger du ett värde. Till exempel `1`.
         * När du har angett ytterligare beräkning väljer du den tidsperiod som ska användas för beräkningen. Till exempel **[!UICONTROL day]**.

     Välj **[!UICONTROL Hide details]** om du vill dölja informationen för beräkning av rullande datum.

1. Välj **[!UICONTROL Apply]** om du vill tillämpa datumintervallet på panelen som du anropade kalendern från.
Välj **[!UICONTROL Apply to all panels]** om du vill använda datumintervallet på alla paneler i Workspace-projektet.


## Släppzon {#dropzone}

Med panelens släppzon kan du använda filter och nedrullningsbara filter på alla tabeller och visualiseringar i en panel. Du kan använda ett eller flera filter på en panel.

### Filter

Dra och släpp eventuella filter från den vänstra panelen i panelens släppzon för att börja filtrera panelen. Upprepa den här processen om du vill lägga till fler filter på panelen. Filter visas sida vid sida högst upp på panelen.

![Den vänstra panelen visar tillgängliga mått och det mobila kundmåttet som dras till panelens släppzon.](assets/segment-filter.png)

#### Snabbfilter

Komponenter som inte är filterkomponenter kan också dras direkt till släppzonen för att skapa snabbfilter, vilket sparar tid och arbete med att gå till [filterverktyget](/help/components/filters/filter-builder.md). Filter som skapas på det här sättet definieras automatiskt som händelsenivåfilter. Du kan snabbt ändra den här definitionen genom att välja ![Redigera](/help/assets/icons/Edit.svg) bredvid filternamnet.


Mer information finns i [Snabbfilter](/help/components/filters/quick-filters.md).

![Ad hoc-filter som är offentliga och släppta i släppzonen](assets/adhoc-segment-filter.png)

### Nedrullningsbara filter

>[!VIDEO](https://video.tv.adobe.com/v/23877?quality=12&learn=on)

I den här videon demonstreras funktionaliteten med Adobe Analytics. Funktionen finns dock på liknande sätt i Customer Journey Analytics. Tänk på följande skillnader i terminologi.

| Adobe Analytics | Customer Journey Analytics |
| --- | --- |
| Segment | Filter |
| Besökare | Person |
| Besök | Session |
| Träff | Händelse |


#### Statiska nedrullningsbara filter

Med statiska nedrullningsbara filter kan du interagera med data på ett kontrollerat sätt. Du kan till exempel lägga till ett nedrullningsbart filter för Mobila enhetstyper så att du kan filtrera panelen efter Surfplatta, Mobiltelefon eller Skrivbord.

Statiska nedrullningsbara filter kan också användas för att konsolidera flera projekt till ett. Om du t.ex. har många versioner av samma projekt med olika landsfilter kan du konsolidera alla versioner till ett enda projekt och lägga till ett nedrullningsbart landsfilter.

![Statiska nedrullningsbara filter visar filtret &quot;Direkt&quot; för marknadskanalen markerat. ](assets/dropdown-filter-intro.png)

##### Skapa statiska listrutefilter

* För nedrullningsbara filter som använder dimensionsobjekt väljer du en dimension från den vänstra panelen och släpper dimensionen i panelens släppzon samtidigt som du håller ned ⇧ (*shift*). Den här åtgärden skapar ett nedrullningsbart filter med alla dimensionsobjekt som är associerade med den dimensionen.

  Eller om du vill att listrutefiltret bara ska innehålla vissa dimensionsobjekt som är kopplade till en dimension, markerar du högerpilsikonen bredvid önskad dimension på den vänstra panelen. Den här åtgärden visar alla tillgängliga dimensionsobjekt. Markera flera dimensionsobjekt i den här listan med ⇧+![Markera](/help/assets/icons/Select.svg) (*Skift* + *välj*) eller ^+![Markera](/help/assets/icons/Select.svg) (*kontroll* + *markera*) och släpp dem sedan i panelens släppzon **samtidigt som du håller ned** ⇧.

* För nedrullningsbara filter som använder en enda komponenttyp (t.ex. bara dimensioner, eller bara filter, eller endast mätvärden) väljer du flera objekt av samma typ på den vänstra panelen med ⇧+![Markera](/help/assets/icons/Select.svg) eller ^+![Markera](/help/assets/icons/Select.svg). Släpp sedan objekten i panelens släppzon **samtidigt som du håller ned** ⇧.

  Ett enda nedrullningsbart filter skapas med komponenter som du har valt.

* För nedrullningsbara filter som använder en blandning av komponenttyper (till exempel 2 mätvärden och 3 filter) väljer du flera komponenter med ⇧+![Markera](/help/assets/icons/Select.svg) eller ^+![Markera](/help/assets/icons/Select.svg). Släpp markeringen i panelens släppzon **medan du håller ned** ⇧. I det här sammanhanget behandlas alla komponenttyper som separata nedrullningsbara filter. Om du till exempel inkluderar både mått och dimensionsobjekt i markeringen skapas två separata nedrullningsbara filter: ett nedrullningsbart filter innehåller dimensionsobjekt och det andra innehåller mått.

Ett nedrullningsbart filter innehåller följande alternativ för snabbmenyer:

* **[!UICONTROL Delete drop-down]**: Tar bort nedrullningsfiltret från panelen.
* **[!UICONTROL Delete label]**: Ta bort texten som visas ovanför ett nedrullningsbart filter. Om du vill ändra etiketten håller du pekaren över etiketten och väljer ![Redigera etikett för nedrullningsbart filter](/help/assets/icons/Edit.svg).
* **[!UICONTROL Add label]**: När du lägger till ett nedrullningsbart filter i ett projekt ställs en etikett automatiskt in på komponentnamnet. Om du tar bort etiketten kan du lägga till den igen med det här alternativet.
* **[!UICONTROL Require selection]**: Kräver att ett filter är inställt på panelen.

##### Använda statiska nedrullningsbara filter

Användare kan använda den nedrullningsbara filtermenyn på något av följande sätt för att filtrera panelen:

* Använd ett enda filter på panelen genom att välja filtret i listrutan.

* Använd flera filter på panelen genom att markera mer än ett filter i listrutan. Panelen filtreras så att den innehåller något av de valda filtren.


#### Dynamiska nedrullningsbara filter

Med dynamiska nedrullningsbara filter kan du bestämma tillgängliga värden baserat på data i panelens rapporteringsintervall och värden i andra nedrullningsbara filter. Du kan till exempel skapa två dynamiska listrutor med en landsdimension och en stadsdimension. När du väljer ett land i listrutan **[!UICONTROL Countries]** justeras listrutan **[!UICONTROL Cities]** dynamiskt så att den bara visar städer i det landet.

Samma koncept gäller för alla dimensioner. Endast dimensionsobjekt som visas inom panelens datumintervall och markerade filter visas. De Dimensioner som markeras i statiska nedrullningsbara filter påverkar tillgängliga värden i dynamiska nedrullningsbara filter. Inverteringen är emellertid inte true. De Dimensioner som markeras i dynamiska listrutefilter påverkar inte tillgängliga värden i statiska listrutefilter.

Manuellt urval av dimensionsobjekt är tillgängligt om du förväntar dig att en viss dimensionsobjekt ska samlas in i framtiden. Du kan även rensa ett dynamiskt nedrullningsbart filter så att det inte innehåller något värde, vilket innebär att andra dynamiska nedrullningsbara filter kan innehålla fler värden. Välj **[!UICONTROL Reset all]** om du vill ta bort markeringen från alla nedrullningsbara filter för den panelen.

Så här skapar du ett dynamiskt nedrullningsbart filter:

* Dra och släpp en dimension i panelens släppzon **samtidigt som du håller ned** ⇧.

Observera att dynamiska nedrullningsbara filter inte är tillgängliga för mått, filter eller datumintervall.

Ett dynamiskt nedrullningsbart filter har samma alternativ för snabbmenyer som statiska nedrullningsbara filter.


## Snabbmeny

Ytterligare funktioner för en panel är tillgängliga via en snabbmeny (högerklicka) i panelhuvudet.

![Alternativ för högerklick för en panelrubrik.](assets/right-click-menu.png)

Följande alternativ är tillgängliga:

| Alternativ | Beskrivning |
| --- | --- |
| **[!UICONTROL Insert copied panel]** | Gör att du kan klistra in en kopierad panel på en annan plats i projektet eller i ett annat projekt. |
| **[!UICONTROL Insert copied visualization]** | Klistra in en kopierad visualisering på en annan plats i panelen, projektet eller i ett annat projekt. |
| **[!UICONTROL Apply Data view to all panels]** | Använd datavyn för den här panelen på alla andra paneler i projektet. |
| **[!UICONTROL Copy panel]** | Kopiera en panel så att du kan infoga den på en annan plats i projektet eller i ett annat projekt. |
| **[!UICONTROL Duplicate panel]** | Skapar en exakt kopia av den aktuella panelen, som du sedan kan ändra. |
| **[!UICONTROL Collapse all panels]** | Komprimera alla projektpaneler. |
| **[!UICONTROL Expand all panels]** | Expandera alla projektpaneler. |
| **[!UICONTROL Collapse all visualizations in panel]** | Komprimera alla visualiseringar i den aktuella panelen. |
| **[!UICONTROL Expand all visualizations in panel]** | Utöka alla visualiseringar i den aktuella panelen. |
| **[!UICONTROL Edit Description]** | Lägg till (eller redigera) en textbeskrivning för panelen. |
| **[!UICONTROL Get Panel Link]** | Dirigera någon till en viss panel i ett projekt. När länken är markerad måste mottagaren logga in innan han eller hon dirigeras till just den panel som är länkad till. |

## Konfiguration

Vissa paneler (som [!UICONTROL Attribution], [!UICONTROL Experimentation], [!UICONTROL Media average minute audience] och andra) har en konfigurationsdialogruta som hjälper dig att skapa visualiseringen. Använd ![Redigera](/help/assets/icons/Edit.svg) längst upp på panelen för att komma åt och ändra konfigurationen.

![Konfigurera en panel](/help/analysis-workspace/c-panels/assets/configure-panel.png)
