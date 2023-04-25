---
description: En panel är en samling tabeller och visualiseringar
title: Översikt över paneler
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
source-git-commit: 15e83ab3c828b6fd91a3f729001ec4f22f24f9ec
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 1%

---

# Översikt över paneler

A [!UICONTROL panel] är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i Workspace eller en [tom panel](/help/analysis-workspace/c-panels/blank-panel.md). Paneler är användbara när du vill ordna dina projekt efter tidsperioder, datavyer eller användningsfall för analyser.

## Paneltyper

Följande paneltyper är tillgängliga i Analysis Workspace för [!UICONTROL Customer Journey Analytics]:

| Panelnamn | Beskrivning |
| --- | --- |
| [Tom panel](/help/analysis-workspace/c-panels/blank-panel.md) | Välj bland tillgängliga paneler och visualiseringar för att starta analysen. |
| [Panelen Snabbinsikter](quickinsight.md) | Bygg snabbt ett frihandsbord och en medföljande visualisering för att analysera och hitta insikter snabbare. |
| [Panelen Attribution](attribution.md) | Jämför och visualisera snabbt valfritt antal attribueringsmodeller med alla mått och konverteringsvärden. |
| [Frihandspanel](freeform-panel.md) | Utför obegränsade jämförelser och uppdelningar och lägg sedan till visualiseringar för att berätta en utförlig databerättelse. |
| [Panelen för samtidiga medieanvändare](media-concurrent-viewers.md) | Analysera samtidiga tittare över tid, med information om maximal samtidighet och möjlighet att dela upp och jämföra. |
| [Panelen Medieuppspelning - tidsfördröjning](media-playback-timespent/media-playback-time-spent.md) | Analysera den uppspelningstid som använts för att förstå var maximal samtidighet inträffade eller var bortfall inträffade. |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights], [!UICONTROL Blank] och [!UICONTROL Freeform] paneler är bra att använda för att starta analysen, medan [!UICONTROL Attribution IQ] ger sig själv till mer avancerade analyser. A `"+"` -knappen är tillgänglig i projekt så att du kan lägga till tomma paneler när som helst.

Standardstartpanelen är [!UICONTROL Freeform] men du kan göra [tom panel](/help/analysis-workspace/c-panels/blank-panel.md) även din standard.

## Kalender {#calendar}

Panelkalendern styr rapporteringsintervallet för tabeller och visualiseringar inom en panel.

Obs! Om en (lila) datumintervallkomponent används i en tabell, visualisering eller paneldropzon åsidosätts panelkalendern.

![](assets/panel-calendar.png)

Du kan använda ett datumintervall på minutnivå under de avancerade inställningarna i panelkalendern. Om du rapporterar i ett datumintervall som sträcker sig över många dagar, gäller starttiden den första dagen och sluttiden den sista dagen i intervallet.

## Dropzon {#dropzone}

Med panelens dropzone kan du använda filter och nedrullningsbara filter på alla tabeller och visualiseringar i en panel. Du kan använda ett eller flera filter på en panel. Titeln ovanför varje filter kan ändras genom att du klickar på redigeringspennan eller så kan du högerklicka för att ta bort den helt.

### Filter

Dra och släpp eventuella filter från den vänstra listen i panelens släppzon för att börja filtrera panelen.

![](assets/segment-filter.png)

### Ad hoc-filter

Komponenter som inte är filterkomponenter kan också dras direkt till dropzone för att skapa ad hoc-filter, vilket sparar tid och arbete med att gå till Filter Builder. Filter som skapas på det här sättet definieras automatiskt som träffnivåfilter. Du kan ändra den här definitionen genom att klicka på informationsikonen (i) bredvid filtret, sedan den pennformade redigeringsikonen och redigera den i Filterverktyget.

Ad hoc-filter är en typ av snabbfilter och är lokala för projektet. De visas inte i den vänstra listen om du inte gör dem offentliga.

Mer information finns i [Snabbfilter](/help/components/filters/quick-filters.md).

![](assets/adhoc-segment-filter.png)

### Statiska nedrullningsbara filter

Med nedrullningsbara filter kan du interagera med data på ett kontrollerat sätt. Du kan till exempel lägga till ett nedrullningsbart filter för mobila enhetstyper så att du kan filtrera panelen efter Surfplatta, Mobiltelefon eller Skrivbord.

Nedrullningsbara filter kan även användas för att konsolidera flera projekt till ett. Om du t.ex. har många versioner av samma projekt med olika landsfilter kan du konsolidera alla versioner till ett enda projekt och lägga till ett nedrullningsbart landsfilter.

![](assets/dropdown-filter-intro.png)

Så här skapar du ett statiskt nedrullningsbart filter:

* För nedrullningsbara filter som använder dimensionsobjekt klickar du på högerpilsikonen bredvid önskad dimension i den vänstra listen. Den här åtgärden visar alla tillgängliga dimensionsobjekt. Välj flera dimensionsobjekt från den här listan med `[Shift + Click]` eller `[Ctrl + Click]`och sedan släppa dem i panelens dropzone **medan du håller`[Shift]`**.
* För nedrullningsbara filter som använder andra komponenter som mått, filter eller datumintervall väljer du flera komponenter med `[Shift + Click]` eller `[Ctrl + Click]`. Släpp markeringen i panelens dropzone **medan du håller`[Shift]`**. Alla komponenttyper behandlas som filter i den här kontexten.
* Ett enda nedrullningsbart filter kan bara innehålla en enda komponenttyp. Om du inkluderar flera komponenttyper i markeringen skapas ett separat nedrullningsbart filter per komponenttyp. Om du till exempel inkluderar både mått och dimensionsobjekt i markeringen skapas två separata nedrullningsbara filter. Ett nedrullningsbart filter innehåller dimensionsobjekt och det andra innehåller mått.

Välj ett av alternativen i listrutan om du vill ändra data på panelen. Du kan också välja att inte filtrera paneldata genom att markera **[!UICONTROL No filter]**.

![](assets/create-dropdown.png)

Om du högerklickar på ett nedrullningsbart filter finns följande alternativ:

* **[!UICONTROL Add label]**: När du lägger till ett nedrullningsbart filter i ett projekt ställs en etikett automatiskt in på komponentnamnet. Om du tar bort etiketten kan du lägga till den igen med det här alternativet.
* **[!UICONTROL Delete label]**: Ta bort texten ovanför ett nedrullningsbart filter.
* **[!UICONTROL Delete drop-down filter]**: Tar bort nedrullningsfiltret från panelen.

[Se videon](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) om du vill veta mer om hur du lägger till nedrullningsbara filter i ett projekt.

### Dynamiska nedrullningsbara filter

Med dynamiska nedrullningsbara filter kan du bestämma tillgängliga värden baserat på data i panelens rapporteringsintervall och värden i andra nedrullningsbara filter. Du kan t.ex. skapa två dynamiska listrutor med dimensionen Länder och Städer. När du väljer ett land i listrutan UICONTROL-länder justeras listrutan Städer dynamiskt så att den bara visar städer i det landet.

Samma koncept gäller för alla dimensioner. endast dimensionsobjekt som visas inom panelens datumintervall och markerade filter visas. De Dimensioner som markeras i statiska nedrullningsbara filter påverkar tillgängliga värden i dynamiska nedrullningsbara filter. Inversen är dock inte sann; De Dimensioner som markeras i dynamiska nedrullningsbara filter påverkar inte tillgängliga värden i statiska nedrullningsbara filter.

Manuellt urval av dimensionsobjekt är tillgängligt om du förväntar dig att en viss dimensionsobjekt ska samlas in i framtiden. Du kan även rensa ett dynamiskt nedrullningsbart filter så att det inte innehåller något värde, vilket innebär att andra dynamiska nedrullningsbara filter kan innehålla fler värden. Välj **[!UICONTROL Clear All]** för att ta bort markeringen från alla nedrullningsbara filter för den panelen.

Så här skapar du ett dynamiskt nedrullningsbart filter:

* Dra och släpp en dimension till panelens dropzone **medan du håller`[Shift]`**.
* Dynamiska nedrullningsbara filter är inte tillgängliga för mått, filter eller datumintervall.
* Högerklicka på ett nedrullningsbart filter och välj **[!UICONTROL Delete filter]** för att ta bort den.

Om du högerklickar på ett dynamiskt nedrullningsbart filter finns samma alternativ som för statiska nedrullningsbara filter.

## Högerklicka på menyn {#right-click}

Ytterligare funktioner för en panel är tillgängliga genom att högerklicka på panelhuvudet.

![](assets/right-click-menu.png)

Följande inställningar är tillgängliga:

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Insert Copied Panel/Visualization] | Gör att du kan klistra in (&quot;infoga&quot;) en kopierad panel eller visualisering på en annan plats i projektet, eller i ett annat projekt. |
| [!UICONTROL Copy Panel] | Högerklicka och kopiera en panel så att du kan infoga den på en annan plats i projektet eller i ett annat projekt. |
| [!UICONTROL Duplicate Panel] | Skapar en exakt kopia av den aktuella panelen, som du sedan kan ändra. |
| [!UICONTROL Collapse/Expand all Panels] | Komprimerar och utökar alla projektpaneler. |
| [!UICONTROL Collapse/Expand all Visualizations in Panel] | Komprimerar och utökar alla visualiseringar i den aktuella panelen. |
| [!UICONTROL Edit Description] | Lägg till (eller redigera) en textbeskrivning för panelen. |
| [!UICONTROL Get Panel Link] | Du kan dirigera någon till en viss panel i ett projekt. När användaren klickar på länken måste mottagaren logga in innan han eller hon dirigeras till just den panel som är länkad till. |
