---
description: En panel är en samling tabeller och visualiseringar
title: Översikt över paneler
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 1%

---

# Översikt över paneler

En [!UICONTROL panel] är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i Workspace eller en [tom panel](/help/analysis-workspace/c-panels/blank-panel.md). Paneler är användbara när du vill ordna dina projekt efter tidsperioder, datavyer eller användningsfall för analyser. Följande paneltyper är tillgängliga i Analysis Workspace:

| Panelnamn | Beskrivning |
| --- | --- |
| [Tom panel](/help/analysis-workspace/c-panels/blank-panel.md) | Välj bland tillgängliga paneler och visualiseringar för att starta analysen. |
| [Panelen Snabbinsikter](quickinsight.md) | Bygg snabbt ett frihandsbord och en medföljande visualisering för att analysera och hitta insikter snabbare. |
| [Panelen Attribution](attribution.md) | Jämför och visualisera snabbt valfritt antal attribueringsmodeller med alla mått och konverteringsvärden. |
| [Frihandspanel](freeform-panel.md) | Utför obegränsade jämförelser och uppdelningar och lägg sedan till visualiseringar för att berätta en utförlig databerättelse. |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights],  [!UICONTROL Blank] och  [!UICONTROL Freeform] paneler är bra platser för att starta analysen, medan  [!UICONTROL Analytics for Target],  [!UICONTROL Attribution IQ]och  [!UICONTROL Media Concurrent Viewers]   [!UICONTROL Segment Comparison] ge sig ut på mer avancerade analyser. En `"+"`-knapp är tillgänglig i projekt, så du kan när som helst lägga till tomma paneler.

Standardstartpanelen är panelen [!UICONTROL Freeform], men du kan göra den tomma panelen](/help/analysis-workspace/c-panels/blank-panel.md) till standard.[

## Kalender {#calendar}

Panelkalendern styr rapporteringsintervallet för tabeller och visualiseringar inom en panel.

Obs! Om en (lila) datumintervallkomponent används i en tabell, visualisering eller paneldropzon åsidosätts panelkalendern.

![](assets/panel-calendar.png)

## Dropzone {#dropzone}

Med panelens listruta kan du tillämpa segment- och listrutefilter på alla tabeller och visualiseringar i en panel. Du kan använda ett eller flera filter på en panel. Titeln ovanför varje filter kan ändras genom att du klickar på redigeringspennan eller så kan du högerklicka för att ta bort den helt.

### Segmentfilter

Dra och släpp eventuella filter från den vänstra listen i panelens släppzon för att börja filtrera panelen.

![](assets/segment-filter.png)

### Ad hoc-filter

Komponenter som inte tillhör segment kan också dras direkt till dropzone för att skapa ad hoc-filter, vilket sparar tid och arbete med att gå till Filter Builder. Filter som skapas på det här sättet definieras automatiskt som träffnivåfilter. Du kan ändra den här definitionen genom att klicka på informationsikonen (i) bredvid filtret, sedan den pennformade redigeringsikonen och redigera den i Filterverktyget.

Ad-hoc-filter är lokala för projektet och visas inte i den vänstra listen om du inte gör dem offentliga.

![](assets/adhoc-segment-filter.png)

### Nedrullningsbara filter {#dropdown-filter}

Förutom segmentfilter kan du med hjälp av nedrullningsbara filter interagera med data på ett kontrollerat sätt. Du kan t.ex. lägga till ett nedrullningsbart filter för mobila enhetstyper så att du kan segmentera panelen via Surfplatta, Mobiltelefon eller Skrivbord.

Nedrullningsbara filter kan även användas för att konsolidera flera projekt till ett. Om du till exempel har många versioner av samma projekt med olika landssegment tillämpade, kan du konsolidera alla versioner till ett enda projekt och lägga till ett nedrullningsbart landsfilter.

![](assets/dropdown-filter-intro.png)

Så här skapar du nedrullningsbara filter:

1. Om du vill skapa ett nedrullningsbart filter med [!UICONTROL Dimension items], t.ex. värden inom dimensionen [!UICONTROL Marketing Channel], klickar du på högerpilsikonen bredvid dimensionen i den vänstra listen. Då visas alla tillgängliga objekt. Markera ett eller flera komponentobjekt i den vänstra listen och släpp dem i panelens dropzon **samtidigt som du håller ned Skift-tangenten**. Komponenterna blir då ett nedrullningsbart filter i stället för ett enda segment.
1. Om du vill skapa ett nedrullningsbart filter med hjälp av andra komponenter, som mått, segment eller datumintervall, väljer du en komponenttyp i den vänstra listen och släpper i panelens listruta **samtidigt som du håller ned Skift-tangenten**.
1. Välj ett av alternativen i listrutan om du vill ändra data på panelen. Du kan också välja att inte filtrera paneldata genom att välja **[!UICONTROL No filter]**.

![](assets/create-dropdown.png)

[Titta på ](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) videon och lär dig mer om hur du lägger till nedrullningsbara filter i ditt projekt.

## Högerklicka på menyn {#right-click}

Ytterligare funktioner för en panel är tillgängliga genom att högerklicka på panelhuvudet.

![](assets/right-click-menu.png)

Följande inställningar är tillgängliga:

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Insert Copied Panel/Visualization] | Gör att du kan klistra in (&quot;infoga&quot;) en kopierad panel eller visualisering på en annan plats i projektet, eller i ett helt annat projekt. |
| [!UICONTROL Copy Panel] | Högerklicka och kopiera en panel så att du kan infoga den på en annan plats i projektet eller i ett helt annat projekt. |
| [!UICONTROL Duplicate Panel] | Skapar en exakt kopia av den aktuella panelen, som du sedan kan ändra. |
| [!UICONTROL Collapse/Expand all Panels] | Komprimerar och utökar alla projektpaneler. |
| [!UICONTROL Collapse/Expand all Visualizations in Panel] | Komprimerar och utökar alla visualiseringar i den aktuella panelen. |
| [!UICONTROL Edit Description] | Lägg till (eller redigera) en textbeskrivning för panelen. |
| [!UICONTROL Get Panel Link] | Du kan dirigera någon till en viss panel i ett projekt. När användaren klickar på länken måste mottagaren logga in innan han eller hon dirigeras till just den panel som är länkad till. |
