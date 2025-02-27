---
description: Översikt över arbetsytan Resa
title: Reseduk
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 51a6341734163fdd6b994ae9cec53ef034959896
workflow-type: tm+mt
source-wordcount: '1893'
ht-degree: 0%

---

# Översikt över arbetsytan Resa {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="Reseduk"
>abstract="Visar hur personer går igenom eller faller bort från en serie kontaktytor. Använd för resor med flera ingångspunkter och sökvägar, eller för att analysera resor som skapats i Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="Reseduk"
>abstract="Analysera hur människor går igenom eller faller bort från en definierad resa. Skapa analyser av användarresor genom att skapa ett flexibelt diagram över noder och pilar som representerar en kombination av händelser, dimensionsobjekt och filter. Dra noder på arbetsytan för att ändra ordningen på händelser och villkor för resan. Data uppdateras i takt med att du gör det. <br/><br/>Kunder med tillgång till Adobe Journey Optimizer kan analysera befintliga Journey Optimizer-resor"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button"
>title="Reseduk"
>abstract="Visar hur personer går igenom eller faller bort från en serie kontaktytor. Använd för resor med flera ingångspunkter och sökvägar, eller för att analysera resor som skapats i Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel"
>title="Reseduk"
>abstract="Analysera hur människor går igenom eller faller bort från en definierad resa. Skapa analyser av användarresor genom att skapa ett flexibelt diagram över noder och pilar som representerar en kombination av händelser, dimensionsobjekt och filter. Dra noder på arbetsytan för att ändra ordningen på händelser och villkor för resan. Data uppdateras i takt med att du gör det. <br/><br/>Kunder med tillgång till Adobe Journey Optimizer kan analysera befintliga Journey Optimizer-resor"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_I den här artikeln dokumenteras visualiseringen av arbetsytan på resan i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**.<br/>Det finns ingen motsvarande visualisering i **Adobe Analytics**._

>[!ENDSHADEBOX]

Med visualiseringen av arbetsytan på resande fot kan ni analysera och få djupgående insikter om de resor som ni erbjuder era användare och kunder. Du kan definiera en resa från scratch eller visa en resa från Journey Optimizer och sedan se hur människor lämnade (föll ut) eller fortsatte igenom (föll igenom) resan.

Du kan [skapa analyser av användarresor](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) genom att använda valfri kombination av händelser, dimensionsobjekt, filter och datumintervall för att skapa resednoder. Koppla ihop noderna för att skapa resans flöde och inkludera flera vägar och beslutspunkter. Dra noder på arbetsytan för att ändra ordningen på händelser och villkor för resan. Datauppdateringar uppdateras i realtid när du gör ändringar.

[Noderna är anslutna](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) som en&quot;slutgiltig sökväg&quot;, vilket betyder att besökare räknas så länge de så småningom förflyttar sig från en nod till en annan, oavsett händelser som inträffar mellan de två noderna. Den tid som användarna får förflytta sig längs banan bestäms av behållarinställningen.

![Researbetsyta](assets/journey-canvas.png)

## Viktiga funktioner

Viktiga funktioner för visualisering av arbetsytan på resan är:

* Djupgående analys av bortfall och genombrott som passar de mest komplexa kundresorna.

* En arbetsyta för att mappa och visualisera de olika startpunkterna, noderna och sökvägarna i en användarresa.

* Dra och släpp-interaktioner för att lägga till komponenter på arbetsytan och för att flytta befintliga noder.

* Möjlighet att skapa analyser av användarresor på arbetsytan på resan eller att skapa dem automatiskt baserat på Journey Optimizer resor.

## Potentiella insikter

Researbetsytan ger användbara insikter för de mest komplexa resorna.

### Bana med högsta konverteringsgrad {#conversion-rate-caption}

Den mest framträdande insikten på arbetsytan i Journey visas som en bildtext högst upp på själva arbetsytan.

Den här beskrivningen sammanfattar vilken av alla vägar som hade den högsta konverteringsgraden.

När resan innehåller flera startnoder ser bildtexten ut så här:

![Insiktsbildtext för arbetsytan på resan](assets/journey-canvas-caption.png)

När resan innehåller en enda startnod ser bildtexten ut så här:

![En startnod för insiktsbildtext på arbetsytan på resan](assets/journey-canvas-caption-singlestart.png)

Tänk på följande när du tolkar den här bildtexten:

* En _sökväg_ definieras som en startnod som ansluts med pilar till en slutnod, med valfritt antal noder anslutna mellan dem.

* Beräkningen av konverteringsgraden beror på typen av resa (antalet startnoder och slutnoder som ingår i resan och huruvida vägarna korsar dem mellan dem).

  I följande tabell beskrivs hur konverteringsgraden beräknas baserat på resetypen:

  | Resetyp | Beräkning av konverteringssats | Exempel |
  |---------|----------|---------|
  | **En enda startnod och en enda slutnod** | Konverteringsgraden beräknas genom att antalet slutnoder divideras med antalet för startnoden. | ![Resa med flera starter som konvergerar till en gemensam nod](assets/journey-canvas-single-path.png) |
  | **En enskild startnod och flera slutnoder** | Konverteringsgraden beräknas genom att hitta slutnoden med det högsta talet och dividera talet med startnodens. | ![Resa med flera starter som konvergerar till en gemensam nod](assets/journey-canvas-singlestart-multiend.png) |
  | **Flera fristående sökvägar, där varje sökväg innehåller en enda startnod och en enda slutnod** | Konverteringsgraden beräknas genom att antalet slutnoder divideras med antalet för startnoden. Sökvägen med den högsta konverteringsgraden beskrivs i bildtexten. | ![Resa med flera starter som konvergerar till en gemensam nod](assets/journey-canvas-multi-start-separate.png) |
  | **Flera startnoder som vid någon tidpunkt under resan konvergerar till en gemensam nod** | Konverteringsgraden beräknas genom att hitta slutnoden med det högsta talet och dividera talet med startnodens med det lägsta talet. | ![Resa med flera starter som konvergerar till en gemensam nod](assets/journey-canvas-multi-start-converge.png) |

### Fallthrough, Fallout, and more

Nedan följer några exempel på andra insikter som Journey Canvas kan ge. Du kan välja om dessa insikter ska baseras på alla personer i datavyn, alla personer som påbörjade resan eller alla personer från den föregående noden på resan.

#### Fallthrough

* Antalet och procentandelen personer som slutförde resan (anlänt till den avslutande noden)

* Antalet och procentandelen personer som anlände till en viss nod på resan

* Det vanligaste steget efter eller före en viss nod på resan

#### Utfall

* Nod på resan där människor oftast föll utanför resan (aldrig anlände till någon av de närmaste noderna)

#### Ytterligare data för varje nod

* Lägg till en detaljdimension på valfri nod i resan för att visa ytterligare data för den specifika noden

## Välj mellan visualiseringar för arbetsyta, bortfall eller flöde i resan

Visualiseringen av arbetsytan på resan har likheter med [Utfallsvisualisering](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) och [Flödesvisualisering](/help/analysis-workspace/visualizations/c-flow/flow.md), men med viktiga skillnader.

### Förstå skillnaderna

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### När du ska använda Resans arbetsyta

Reseduken är oumbärlig för

* Bortfallsanalys som omfattar resor med flera ingångspunkter och sökvägar.

* Icke-linjära resor med flera ingångspunkter och sökvägar, med en fördefinierad sidsekvens.

* Förberedande ad hoc-analys som bygger på en fördefinierad resa.

* Analys som kräver ett primärt mått som inte är Session, Person eller Förekomster.

* Djupgående analyser av resor med ursprung i Adobe Journey Optimizer.

Använd [tabellen ovan](#understand-the-differences) för att förstå skillnaderna mellan visualiseringar av arbetsyta, utfall och flöde för resan.

## Analysera Journey Optimizer resor

>[!NOTE]
>
>Om din organisation inte har tillgång till Journey Optimizer kan du ändå [skapa analyser på arbetsytan ](#build-analyses-in-customer-journey-analytics).

Analyser av Journey Optimizer resor på arbetsytan i Journey ger djupgående, användbara insikter om hur människor interagerar med en resa.

När du analyserar en Journey Optimizer-resa på en arbetsyta visas resan med samma ordning, sekvens och struktur som i Journey Optimizer. Om du gör betydande ändringar i en resa på en arbetsyta i en resa synkroniseras inte längre [ändringar från Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Fördelar med att analysera Journey Optimizer resor med arbetsytan i Journey

Resans arbetsyta ger djupgående, grundliga analyser som inte är möjliga i Journey Optimizer.

Att använda Journey Canvas för att analysera resor som skapats i Journey Optimizer ger flera fördelar:

* Skapa händelser genom att använda Customer Journey Analytics mått, mätvärden, filter eller datumintervall.

  I Journey Optimizer måste en teknisk användare skapa en händelse innan den kan läggas till på en resa.

* Skapa målgrupper baserat på en anpassad nod som du skapar (startar Customer Journey Analytics målgruppsbyggare).

  I Journey Optimizer kan du bara skapa målgrupper för fördefinierade aktiviteter.

* Analysera genomgång och utfall

* Dela upp händelser oavsett dimension

* Kombinera händelser

* Connect-händelser

* Byta namn på och ta bort händelser

* Mycket mer

### Synkronisering mellan Journey Optimizer och arbetsytan på resan

När du har skapat en analys av en Journey Optimizer-resa på arbetsytan i Journey synkroniseras data endast i en riktning, från Journey Optimizer till arbetsytan i Journey. Det innebär att ändringar som görs på en resa på arbetsytan i Journey aldrig återspeglas i Journey Optimizer.

Dessutom synkroniseras ändringar som gjorts på en resa i Journey Optimizer med arbetsytan [endast om resan inte har ändrats avsevärt på arbetsytan ](#differences-after-modifying-a-journey-in-journey-canvas). När du har ändrat en resa på en arbetsyta på en resa på en arbetsyta på en resa, återspeglas inte de ändringar du gör på resan i Journey Optimizer på arbetsytan på resan. Om du vill se ändringarna återspeglas i arbetsytan på resan kan du ta bort och [återskapa resan på arbetsytan på resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Skillnader efter ändring av en resa på arbetsytan i en resa {#differences-after-modifying}

När du har ändrat en Journey Optimizer-resa på arbetsytan kan databearbetning, tillgängliga funktioner och synkroniseringsbeteende ändras.

Om du gör en betydande ändring av en Journey Optimizer-resa på arbetsytan kan ändringar göras i databearbetning, tillgängliga funktioner och synkroniseringsbeteende. En betydande ändring innefattar något av följande:

* Lägga till eller ta bort en nod

* Lägga till eller ta bort en pil mellan noder

* Ändra komponenterna på en nod

Om du gör andra ändringar av en Journey Optimizer-resa på arbetsytan för en resa, som att dra en nod eller lägga till en uppdelning, gäller inte de skillnader som beskrivs i följande avsnitt.

>[!NOTE]
>
>Om du vill återställa resan till det ursprungliga läget kan du trycka på Ctrl+Z när du har gjort den första ändringen på arbetsytan för resan. Eller så kan du ta bort och [återskapa resan på arbetsytan för resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Skillnader i databehandling

När du har ändrat en Journey Optimizer-resa på en arbetsyta i resan kan du lägga märke till att data ändras om resan innehåller mätvärden som inte har standardattribueringsmodeller.

Det beror på att du, till skillnad från Journey Optimizer, kan använda flera olika dimensioner på en resa med en arbetsyta från Journey. Den här funktionen innebär att [metrisk attribuering](/help/data-views/component-settings/attribution.md) inte stöds.

#### Skillnader i funktioner

När du har ändrat en Journey Optimizer-resa på arbetsytan för en resa ändras de alternativ som är tillgängliga i listrutan [!UICONTROL **Pilinställningar**], beroende på dina ändringar. Mer information finns i [Konfigurera inställningar](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Fältet [!UICONTROL **Nodtyp**] är bara tillgängligt i Journey Optimizer. Den är inte tillgänglig när du visar en Journey Optimizer-resa på en arbetsyta i en resa, oavsett om du gör ändringar på resan på arbetsytan i en resa i Europa eller inte.

#### Synkroniseringsskillnader

Ändringar som görs i en resa i Journey Optimizer synkroniseras endast till arbetsytan på resan om resan inte ändras på arbetsytan på resan.

När du har ändrat en Journey Optimizer-resa på arbetsytan i Journey återspeglas inte de ändringar du gör på resan i Journey Optimizer på arbetsytan i Journey. Om du vill se ändringarna återspeglas i arbetsytan på resan kan du ta bort och [återskapa resan på arbetsytan på resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Terminologiska skillnader mellan Journey Optimizer och Customer Journey Analytics

Vissa termer som betyder något i Journey Optimizer betyder något annat i Customer Journey Analytics. När du använder en arbetsyta på en resa används Customer Journey Analytics-termerna.

| Term | Reseduk | Journey Optimizer |
|---------|----------|---------|
| **Händelse** | En av flera standardvärden som är tillgängliga i Customer Journey Analytics. Det här måttet räknar t.ex. intäkter, prenumerationer eller genererade leads. | Den aktivitetskategori som utlöser en personaliserad resa, till exempel ett onlineköp. |

### Analysera en Journey Optimizer-resa på arbetsytan i Journey

Mer information om hur du analyserar en Journey Optimizer-resa på en arbetsyta för en resa finns i [Konfigurera en visualisering av en arbetsyta för en resa](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Skapa analyser på arbetsytan i Journey

Ni kan skapa analyser på arbetsytan i Journey som baseras på de dimensioner och mätvärden som finns i Analysis Workspace. Eller så kan du analysera resor som gjorts i Journey Optimizer. Mer information finns i [Konfigurera en visualisering av en arbetsyta på resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


>[!MORELIKETHIS]
>
> * [A Guide to Journey Canvas Visualization in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

