---
description: Översikt över arbetsytan Resa
title: Reseduk
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 2f42c64443cc5798388287e6f84b125fb8694812
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 0%

---

# Översikt över arbetsytan Resa

{{release-limited-testing}}

Med visualiseringen av arbetsytan på resande fot kan ni analysera och få djupgående insikter om de resor som ni erbjuder era användare och kunder. Du kan definiera en resa från scratch eller visa en resa från Journey Optimizer och sedan se hur människor lämnade (föll ut) eller fortsatte igenom (föll igenom) resan.

Du kan [skapa analyser av användarresor](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) genom att använda valfri kombination av händelser, dimensionsobjekt, filter och datumintervall för att skapa resednoder. Koppla ihop noderna för att skapa resans flöde och inkludera flera vägar och beslutspunkter. Dra noder på arbetsytan för att ändra ordningen på händelser och villkor för resan. Datauppdateringar i realtid när du gör ändringar.

## Viktiga funktioner

Viktiga funktioner för visualisering av arbetsytan på resan är:

* Djupgående analys av bortfall och genombrott som passar de mest komplexa kundresorna.

* En arbetsyta för att mappa och visualisera de olika startpunkterna, noderna och sökvägarna i en användarresa.

* Dra och släpp-interaktioner för att lägga till komponenter på arbetsytan och för att flytta befintliga noder.

* Möjlighet att skapa analyser av användarresor på arbetsytan i Journey eller att automatiskt skapa dem baserat på Journey Optimizer resor.

## Potentiella insikter

Nedan följer några exempel på vilka typer av insikter som Journey Canvas kan ge. Du kan välja om dessa insikter ska baseras på alla personer i datavyn eller på alla personer som påbörjade resan.

**Genomströmning**

* Antalet och procentandelen personer som slutförde resan (anlänt till den avslutande noden)

* Antalet och procentandelen personer som anlänt till en viss punkt (nod) på resan

* Det vanligaste steget efter eller före en viss punkt (nod) på resan

**Utfall**

* Poängen (noderna) på resan där de flesta människor föll utanför resan

**Annan**

* Ytterligare data för alla noder i resan (genom att lägga till en detaljdimension för noden)


## Välj mellan visualiseringar av arbetsytan på resan och utfall

Visualiseringar av arbetsytan på resan liknar [Utfallsvisualiseringar](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), eftersom båda visualiseringarna visar var personer lämnade (föll ut) och fortsatte igenom (föll igenom) en fördefinierad sekvens med sidor.

Det finns dock viktiga skillnader.

### Förstå skillnaderna

I följande tabell visas de typer av analyser som stöds i arbetsytevisualiseringen på resans yta och i utfallsvisualiseringen:

| Funktion | Visualisering av arbetsyta på resans yta | Utfallsvisualisering |
|---------|----------|---------|
| Linjära resor | Ja | Ja |
| Icke-linjära resor med flera ingångspunkter och sökvägar | Ja | Nej |
| Adobe Journey Optimizer resor | Ja | Nej |
| Primärt mått | Alla mått, inklusive beräknade värden | Kan endast använda mät för session eller användare |
| Sekundärt mått | Ja<p>Alla mått, inklusive beräknade värden</p> | Nej |
| Jämför filter | Nej | Ja<p>Jämför ett [obegränsat antal filter](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### Välj vilken visualisering som ska användas

Innan du väljer mellan att använda arbetsytan för resan eller Bortfall måste du [förstå skillnaderna mellan de två](#understand-the-differences).

Om din bortfallsanalys endast omfattar en linjär resa som har en enda känd början och slut bör du använda en [utfallsvisualisering](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) som ett enklare alternativ för de här mer enkla användarresorna.

Resans arbetsyta är avgörande för bortfallsanalys som omfattar resor med flera ingångspunkter och sökvägar, eller för analys av resor som har skapats i Journey Optimizer.

## Analysera Journey Optimizer resor

>[!NOTE]
>
>Om din organisation inte har tillgång till Journey Optimizer kan du ändå [skapa analyser på arbetsytan ](#build-analyses-in-customer-journey-analytics).

Analyser av Journey Optimizer resor på arbetsytan i Journey ger djupgående, användbara insikter om hur människor interagerar med en resa.

När du analyserar en Journey Optimizer-resa på en arbetsyta visas resan med samma ordning, sekvens och struktur som i Journey Optimizer. Om du kan göra ändringar i en resa på en arbetsyta i en resa synkroniseras inte längre [ändringar från Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Fördelar med att analysera Journey Optimizer resor med arbetsytan i Journey

Resans arbetsyta ger djupgående, grundliga analyser som inte är möjliga i Journey Optimizer.

Att använda Journey Canvas för att analysera resor som skapats i Journey Optimizer ger flera fördelar:

* Skapa händelser genom att använda mått, mätvärden, filter eller datumintervall i Customer Journey Analytics.

  I Journey Optimizer måste en teknisk användare skapa en händelse innan den kan läggas till på en resa.

* Skapa målgrupper baserat på en anpassad nod som du skapar (startar målgruppsverktyget i Customer Journey Analytics).

  I Journey Optimizer kan du bara skapa målgrupper för fördefinierade aktiviteter.

* Analysera genomgång och utfall

* Dela upp händelser oavsett dimension

* Kombinera händelser

* Connect-händelser

* Byta namn på och ta bort händelser

* Mycket mer

### Synkronisering mellan Journey Optimizer och arbetsytan på resan

När du har skapat en analys av en Journey Optimizer-resa på arbetsytan i Journey synkroniseras data endast i en riktning, från Journey Optimizer till arbetsytan i Journey. Det innebär att ändringar som görs på en resa på arbetsytan i Journey aldrig återspeglas i Journey Optimizer.

Dessutom synkroniseras ändringar som görs på en resa i Journey Optimizer endast med arbetsytan på resan om resan inte ändras på arbetsytan på resan. När du har ändrat en resa på en arbetsyta på en resa på en arbetsyta på en resa, återspeglas inte de ändringar du gör på resan i Journey Optimizer på arbetsytan på resan. Om du vill se ändringarna återspeglas i arbetsytan på resan kan du ta bort och [återskapa resan på arbetsytan på resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Skillnader efter ändring av en resa på arbetsytan i en resa {#differences-after-modifying}

När du har ändrat en Journey Optimizer-resa på arbetsytan kan databearbetning, tillgängliga funktioner och synkroniseringsbeteende ändras.

>[!NOTE]
>
>Om du vill återställa resan till det ursprungliga läget kan du trycka på Ctrl+Z när du har gjort den första ändringen på arbetsytan för resan. Eller så kan du ta bort och [återskapa resan på arbetsytan för resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Skillnader i databehandling

När du har ändrat en Journey Optimizer-resa på en arbetsyta i resan kan du lägga märke till att data ändras om resan innehåller mätvärden som inte har standardattribueringsmodeller.

Det beror på att du, till skillnad från Journey Optimizer, kan använda flera olika dimensioner på en resa med en arbetsyta från Journey. Den här funktionen innebär att [metrisk attribuering](/help/data-views/component-settings/attribution.md) inte stöds.

#### Skillnader i funktioner

När du har ändrat en Journey Optimizer-resa på en arbetsyta i resan är listrutan [!UICONTROL **Nodtyp**] inte längre tillgänglig.

Mer information om det här fältet finns i [Konfigurera inställningar](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

#### Synkroniseringsskillnader

Ändringar som görs i en resa i Journey Optimizer synkroniseras endast till arbetsytan på resan om resan inte ändras på arbetsytan på resan.

När du har ändrat en Journey Optimizer-resa på arbetsytan i Journey återspeglas inte de ändringar du gör på resan i Journey Optimizer på arbetsytan i Journey. Om du vill se ändringarna återspeglas i arbetsytan på resan kan du ta bort och [återskapa resan på arbetsytan på resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Skillnader i terminologi mellan Journey Optimizer och Customer Journey Analytics

Vissa termer som betyder något i Journey Optimizer betyder något annat i Customer Journey Analytics. När du använder en arbetsyta på en resa används termerna Customer Journey Analytics.

| Term | Reseduk | Journey Optimizer |
|---------|----------|---------|
| **Händelse** | En av flera standardvärden som är tillgängliga i Customer Journey Analytics. Det här måttet räknar t.ex. intäkter, prenumerationer eller genererade leads. | Den aktivitetskategori som utlöser en personaliserad resa, till exempel ett onlineköp. |

### Analysera en Journey Optimizer-resa på arbetsytan i Journey

Mer information om hur du analyserar en Journey Optimizer-resa på en arbetsyta för en resa finns i [Konfigurera en visualisering av en arbetsyta för en resa](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Skapa analyser på arbetsytan i Journey

Ni kan skapa analyser på arbetsytan i Journey som baseras på de dimensioner och mätvärden som finns i Analysis Workspace. Eller så kan du analysera resor som gjorts i Journey Optimizer. Mer information finns i [Konfigurera en visualisering av en arbetsyta på resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
