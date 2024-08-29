---
description: Konfigurera en visualisering av en arbetsyta på resan
title: Reseduk
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: 707bfbf6d34d999bc1b275b24cd6a78b8ef65e74
workflow-type: tm+mt
source-wordcount: '4276'
ht-degree: 0%

---

# Konfigurera en visualisering av en arbetsyta på resan

{{release-limited-testing}}

Med visualiseringen av arbetsytan på resande fot kan ni analysera och få djupgående insikter om de resor som ni erbjuder era användare och kunder.

## Översikt över arbetsytan Resa

Se [Översikt över arbetsytan på resan](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) om du vill veta mer om arbetsytan på resan, inklusive:

* Viktiga funktioner

* Potentiella insikter

* Skillnader mellan arbetsyta för resan och utfall

* Information om hur man analyserar Journey Optimizer resor

* Och mer

## Börja bygga en visualisering av en arbetsyta i resan

1. Lägg till en tom panel i projektet, markera ikonen [!UICONTROL **Visualiseringar**] i den vänstra listen och dra sedan visualiseringen [!UICONTROL **Resursytan**] till panelen.

   eller

   Lägg till en visualisering av arbetsytan på resan på något av de sätt som beskrivs i avsnittet [Lägg till visualiseringar i en panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) i [Översikt över visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Ange följande grundläggande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Primärt mått**] | Det primära måttet påverkar följande aspekter av visualiseringen av arbetsytan på resan:  <ul><li>Definierar hur människor rör sig genom resan.</li><li>Det totala antalet som visas på varje nod.<p>Om Personer till exempel är det primära måttet visar varje nod antalet personer som har nått den noden under resan.</p></li><li>Procentandelen som visas på varje nod. (När visualiseringen har skapats kan du välja att visa antingen procentandelen av totalvärdet eller startnoden.)</li><p>Om Personer till exempel är det primära måttet visar varje nod den procentandel personer som nått den noden i resan (antingen procentandelen av det totala antalet eller startnoden).</p></li><li>När en dimension läggs till i visualiseringen läggs de tre viktigaste noderna i visualiseringen till, baserat på det primära måttet.</li></ul> |
   | [!UICONTROL **Sekundärt mått**] | Det sekundära måttet är valfritt. När en nod är markerad visas följande information på varje nod under det primära måttet: <ul><li>Det totala talet<p>Om sessioner till exempel är det sekundära måttet visar varje nod antalet sessioner som nått den noden under resan.</p></li><li>Procentandelen (när visualiseringen har skapats kan du välja att visa antingen procentandelen av den totala eller startnoden.)</li><p>Om sessioner till exempel är det sekundära måttet visar varje nod hur många sessioner som nått den noden under resan (antingen procentandelen av den totala eller startnoden).</p></li></ul> |
   | [!UICONTROL **Journey Optimizer resa**]<!-- name? --> | Välj den Journey Optimizer-resa som du vill använda som bas för din analys på arbetsytan i Journey. (Du kan också lämna det här alternativet tomt om du vill ha en tom arbetsyta som du kan använda för att skapa analyser i Analysis Workspace.)</p> <p>När du analyserar en Journey Optimizer-resa på en arbetsyta visas resan med samma ordning, sekvens och struktur som i Journey Optimizer. Mer information finns i [Analysera Journey Optimizer-resor](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) i [Översikt över arbetsytan på resan](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Obs!**: Det här alternativet visas bara när Journey Optimizer-data identifieras i datavyn som är markerad på den Analysis Workspace-panel där du lägger till visualiseringen. Mer information om hur du ändrar datavyn på en panel i Analysis Workspace finns i [Analysis Workspace - översikt](/help/analysis-workspace/home.md).</p> |

1. (Valfritt) Välj [!UICONTROL **Visa avancerade inställningar**] och ange sedan följande information:

   | Fält | Funktion |
   |---------|----------|
   | [!UICONTROL **Researbetsytebehållare**] | Välj den behållare som du vill fokusera på under hela resan. Behållaren som du väljer avgör vilken statistik som visas i visualiseringen. (Om behållarnamnen skiljer sig från standardnamnen som visas nedan anpassades de i datavyn.)<ul><li>**Sessioner:** Begränsar statistiken för visualiseringen så att den hamnar inom en enda definierad session för en viss person. Det innebär att de tal och procenttal som visas på varje nod (som baseras på primär- och sekundärstatistik) måste förekomma i en enda session för varje person.</li><li>**Personer:** Tillåter att statistiken för visualiseringen sträcker sig över flera sessioner för en viss person. Det innebär att de siffror och procenttal som visas på varje nod (som baseras på primär- och sekundärstatistik) kan förekomma i alla sessioner, så länge sessionerna tillhör samma person. Det här är standardinställningen.</li></ul> |

1. Välj [!UICONTROL **Skapa**].

   Om du har Journey Optimizer och valt en Journey Optimizer-resa visas resan med samma ordning, sekvens och struktur som i Journey Optimizer.

   <!-- add screen shot -->

   Om du inte har Journey Optimizer eller om du inte har valt någon Journey Optimizer-resa visas en tom arbetsyta där du kan börja fylla resan.

   <!-- add screen shot -->

1. Oavsett om du skapar en ny analys från en tom arbetsyta eller analyserar en Journey Optimizer-resa, kan du konfigurera resan så som beskrivs i [Konfigurera en visualisering av en arbetsyta ](#begin-building-a-journey-canvas-visualization).


## Konfigurera en visualisering av en arbetsyta på resan

Du måste [börja skapa en visualisering av en arbetsyta på resan](#begin-building-a-journey-canvas-visualization) innan du kan konfigurera den enligt beskrivningen i följande avsnitt.

### Konfigurera inställningar

1. Öppna en befintlig visualisering av en arbetsyta för resan i Analysis Workspace eller [börja skapa en ny](#begin-building-a-journey-canvas-visualization).

1. Konfigurera någon av följande inställningar som visas högst upp i visualiseringen:

   | Inställning | Funktion |
   |---------|----------|
   | [!UICONTROL **Nodtyp**] | Gör att du kan konfigurera vilka nodtyper som visas i visualiseringen. Om du vill dölja en nodtyp i visualiseringen markerar du (x) bredvid nodtypen eller avmarkerar den i listrutan. Om du vill visa en dold nodtyp väljer du den i listrutan. <p>Beroende på innehållet i din visualisering kan följande typer av noder förekomma:</p><ul><li>[!UICONTROL **Lässegment**]</li><li>[!UICONTROL **Slut**]</li><li>[!UICONTROL **Dimension**]</li><li>[!UICONTROL **Mått**]</li></ul><p>**Obs!** Tänk på följande när du använder det här fältet:</p><ul><li>Det här alternativet visas bara när Journey Optimizer-data identifieras i den datavy som är markerad på den Analysis Workspace-panel där du lägger till visualiseringen. Mer information om hur du ändrar datavyn på en panel i Analysis Workspace finns i [Analysis Workspace - översikt](/help/analysis-workspace/home.md).</li><li>När du har ändrat en Journey Optimizer-resa på en arbetsyta för resan är det här alternativet inte längre tillgängligt. Mer information finns i [Visuella skillnader efter att en resa på arbetsytan för en resa har ändrats](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#visual-differences-after-modifying-a-journey-in-journey-canvas)</li></ul></p> |
   | [!UICONTROL **Procentvärde**] | Välj bland följande alternativ: <ul><li>[!UICONTROL **Procent av totalt**]: Procentandel av alla personer som ingår i datavyn i panelens datumintervall.</li><li>[!UICONTROL **Procent av startnod**]: Procentandel av alla personer som ingår i datavyn i panelens datumintervall och som också uppfyller villkoren för kundens startnod. (Det här alternativet är endast tillgängligt på resor med en enda startnod. Det är inaktiverat på resor med flera startnoder. En startnod definieras som en nod som inte har någon anslutning som kommer in i den.)</li></ul> |
   | [!UICONTROL **Pilinställningar**] | Välj bland följande alternativ:<ul><li>[!UICONTROL **Ingen**]: </li><li>[!UICONTROL **Villkor**]: </li><li>[!UICONTROL **Alla etiketter**]: </li></ul><p>**Obs!**: Det här alternativet visas bara när Journey Optimizer-data identifieras i datavyn som är markerad på den Analysis Workspace-panel där du lägger till visualiseringen. Mer information om hur du ändrar datavyn på en panel i Analysis Workspace finns i [Analysis Workspace - översikt](/help/analysis-workspace/home.md).</p> |
   | [!UICONTROL **Visa utfall**] | Visa utfallsdata för varje nod. Detta visar antalet och procentandelen personer som avbrutit resan vid en viss nod. <p>Personer som faller bort från resan kan ha utfört andra åtgärder på webbplatsen, men de uppfyller aldrig kriterierna för nästa nod på resan.</p> |

1. Fortsätt med [Lägg till en nod](#add-a-node).

### Lägg till en nod

Noder i en visualisering av en arbetsyta i en resa representerar händelser eller åtgärder som rör en användarresa. Du skapar noder genom att dra Workspace-komponenter från den vänstra listen till arbetsytan.

Så här lägger du till en nod i en visualisering av en arbetsyta:

1. Öppna en befintlig visualisering av en arbetsyta för resan i Analysis Workspace eller [börja skapa en ny](#begin-building-a-journey-canvas-visualization).

1. Dra mått, dimensioner, dimensionsobjekt, filter eller datumintervall från den vänstra listen till arbetsytan. Mätvärden som baseras på ett [härlett fält](/help/data-views/derived-fields/derived-fields.md) stöds. Beräknade mått, liksom alla mått och mått som baseras på en [sammanfattningsdatamängd](/help/data-views/summary-data.md), stöds inte.

   Du kan markera flera komponenter i den vänstra listen genom att hålla ned Skift eller genom att hålla ned Kommando (Mac) eller Ctrl (Windows).

   Visualiseringen uppdateras enligt följande, beroende på komponenttypen och det område på arbetsytan där du monterar den:

   | Komponenttyp | Placering av komponent | Visualiseringsuppdateringar när noden har lagts till |
   |---------|----------|----------|
   | Mått | Tomt område på arbetsytan | Noden visar var komponenten släpptes, utan anslutning till några befintliga noder. |
   | Mått | En befintlig nod | Komponenten kombineras automatiskt med den befintliga noden. (Mer information finns i [Kombinera noder](#combine-nodes).)</p> |
   | Mått | En pil mellan två befintliga noder | Noden visas mellan de två befintliga noderna där komponenten släpptes och är ansluten till båda befintliga noder. (Mer information finns i [Anslut noder](#connect-nodes).)</p> |
   | Dimension | Tomt område på arbetsytan | 3 noder skapas för de tre översta dimensionsobjekten där komponenten släpptes, utan anslutning till några befintliga noder. (**Obs!** Om bara 1 eller 2 noder visas betyder det att data endast är tillgängliga för 1 eller 2 av dimensionsobjekten. Om inga noder visas betyder det att data inte är tillgängliga för någon av dimensionsobjekten. I det här fallet kan du försöka lägga till den på en annan punkt av resan, justera visualiseringens datumintervall eller välja en annan dimension.)<p>Håll ned Skift-tangenten när du släpper dimensionen på arbetsytan för att lägga till den som en enda nod med tre dimensionsobjekt.</p><p></p> |
   | Dimension | En befintlig nod | En uppdelning används automatiskt på noden med de fem översta dimensionsobjekten visade.<!--what happens if you hold Shift?--> |
   | Dimension | En pil som ansluter två befintliga noder | 3 noder skapas för de tre främsta dimensionsobjekten som följer efter den första händelsen efter den första noden (för personer/sessioner som till slut kommer till den andra noden). Noderna visas mellan de två befintliga noderna där komponenten släpptes och varje nod är ansluten till båda befintliga noder. (**Obs!** Om bara 1 eller 2 noder visas betyder det att data endast är tillgängliga för 1 eller 2 av dimensionsobjekten. Om inga noder visas betyder det att data inte är tillgängliga för någon av dimensionsobjekten. I det här fallet kan du försöka lägga till den på en annan punkt av resan, justera visualiseringens datumintervall eller välja en annan dimension.)<p>Håll ned Skift-tangenten när du släpper dimensionen på arbetsytan för att lägga till den som en enda nod med tre dimensionsobjekt. (Mer information finns i [Anslut noder](#connect-nodes).)</p> |
   | Dimension | Tomt område på arbetsytan | Noden visar var komponenten släpptes, utan anslutning till några befintliga noder. |
   | Dimension | En befintlig nod | Komponenten kombineras automatiskt med den befintliga noden. |
   | Dimension | En pil som ansluter två befintliga noder | Noden visas mellan de två befintliga noderna där komponenten släpptes och är ansluten till båda befintliga noder. (Mer information finns i [Anslut noder](#connect-nodes).)</p> |
   | Filter | Tomt område på arbetsytan | Noden visar var komponenten släpptes utan anslutning till några andra noder.<p>Antalet och procentandelen som visas på noden omfattar summan av det primära måttet, filtrerat efter filtret som du valde.</p> <p>Om du t.ex. väljer Personer som det primära måttet för resan och sedan lägger till filtret Dagar i ett tomt område på arbetsytan visas alla personer som har haft en händelse idag.</p> |
   | Filter | En befintlig nod | Använder filtret på den befintliga noden. |
   | Filter | En pil som ansluter två noder | Noden visas mellan de två befintliga noderna där komponenten släpptes och är ansluten till båda befintliga noder. (Mer information finns i [Anslut noder](#connect-nodes).)</p><p>Använder filtret på den punkt på banan där komponenten släpptes.</p> |
   | Datumintervall | Tomt område på arbetsytan | Noden visar var komponenten släpptes, utan anslutning till några andra noder.<p>Antalet och procentandelen som visas på noden inkluderar summan av det primära måttet, filtrerat efter det datumintervall du valde.</p> <p>Om du till exempel väljer Personer som det primära måttet för resan och sedan lägger till datumintervallet Den här månaden i ett tomt område på arbetsytan, visas alla personer som har haft en händelse under den aktuella månaden.</p> |
   | Datumintervall | En befintlig nod | Använder datumintervallet på den befintliga noden. |
   | Datumintervall | En pil som ansluter två noder | Noden visas mellan de två befintliga noderna där komponenten släpptes och är ansluten till båda befintliga noder. (Mer information finns i [Anslut noder](#connect-nodes).)</p><p>Tillämpar datumintervallet på den punkt på banan där komponenten släpptes.</p> |
   | Flera komponenter | Ett tomt område på arbetsytan | **Om ingen av komponenterna är dimensioner:**<p>Varje komponent visas som en separat nod där komponenterna släpptes, utan anslutning till några befintliga noder.</p><p>Håll ned Skift-tangenten när du släpper komponenterna på arbetsytan för att lägga till dem som en kombinerad nod. </p><p>**Om någon av de komponenter du lägger till är dimensioner:**</p><p>Varje komponent visas som en separat nod där komponenterna släpptes, utan anslutning till några befintliga noder.</p><p>Endast en dimension kan läggas till åt gången, och 3 noder skapas för de tre översta dimensionsobjekten där komponenten släpptes.</p><p>Håll ned Skift-tangenten när du släpper komponenterna på arbetsytan för att lägga till dem som en kombinerad nod. De tre översta dimensionsobjekten kombineras med varje nod. (Mer information finns i [Kombinera noder](#combine-nodes).)</p> |
   | Flera komponenter | En befintlig nod | Alla komponenter kombineras med den befintliga noden.<p>Om någon av de komponenter du lägger till är dimensioner kombineras de tre översta dimensionsobjekten med noden.</p> <p>Det går bara att lägga till en dimension åt gången.</p> |
   | Flera komponenter | En pil som ansluter två befintliga noder | **Om ingen av komponenterna är dimensioner:**<p>Varje komponent visas som en separat nod där komponenterna släpptes och varje nod är ansluten till båda befintliga noder. (Mer information finns i [Anslut noder](#connect-nodes).)</p><p>Håll ned Skift-tangenten när du släpper komponenterna på arbetsytan för att lägga till dem som en kombinerad nod. (Komponenter måste vara av samma typ för att kunna kombineras till en enda nod.) (Mer information finns i [Kombinera noder](#combine-nodes).)</p><p>**Om någon av de komponenter du lägger till är dimensioner:**</p><p>Varje komponent visas som en separat nod där komponenterna släpptes och varje nod är ansluten till båda befintliga noder.</p><p>Endast en dimension kan läggas till åt gången, och 3 noder skapas för dimensionens tre främsta objekt som följer den första händelsen efter den första noden (för personer/sessioner som till slut kommer till den andra noden). Varje nod är ansluten till båda befintliga noder. (Mer information finns i [Anslut noder](#connect-nodes).)</p><p>Håll ned Skift-tangenten när du släpper komponenterna på arbetsytan för att lägga till dem som en kombinerad nod. De tre översta dimensionsobjekten kombineras med varje nod och varje nod är ansluten till båda befintliga noder. (Mer information finns i [Kombinera noder](#combine-nodes).)</p> |

   Noderna visas som en rektangulär ruta med följande information:

   * Komponentnamn

   * Komponenttypen (till exempel mått eller dimension)

   * Statistik för primärt mått (summa och procent)

   * Statistik för sekundära mätvärden (summa och procent)

1. Upprepa den här processen om du vill fortsätta lägga till noder för att bygga ut din resa.

1. Fortsätt att anpassa resan enligt beskrivningen i avsnitten nedan. Du kan ansluta noder, byta namn på noder, tillämpa uppdelningar, skapa målgrupper, lägga till tidsbegränsningar och mycket mer.

### Lägg till de översta noderna baserat på befintliga noder

Du kan automatiskt lägga till de översta noderna baserat på de noder som redan finns på arbetsytan.

Det här alternativet är tillgängligt för följande objekt på arbetsytan:

* Enskilda noder

* Pilen mellan noder

#### Lägga till översta noder efter en befintlig nod

Du kan välja en nod och lägga till de tre noder som kommer efter den på resan.

1. Högerklicka på noden där du vill lägga till de tre noderna som kommer efter den på resan.

   Den här noden kan inte ha några befintliga noder som leder ut från den under resan.

1. Välj [!UICONTROL **Lägg till översta noder efter den här noden**].

   De tre toppnoderna som kommer efter den här noden i resan läggs till och de ansluts till den nod du valde som en separat gren.

#### Lägga till översta noder före en befintlig nod

Du kan lägga till de tre viktigaste noderna som kommer före en befintlig nod på resan.

1. Högerklicka på noden där du vill lägga till de tre noderna som kommer före den på resan.

   Den här noden kan inte ha några befintliga noder på resan.

1. Välj [!UICONTROL **Lägg till översta noder före den här noden**].

   De tre toppnoderna som kommer före den här noden i resan läggs till och de är anslutna till den nod som du har valt som en separat gren.

#### Lägga till översta noder mellan befintliga noder

Du kan lägga till de tre viktigaste noderna som finns mellan två befintliga noder:

1. Högerklicka på pilen mellan de två noderna där du vill lägga till de tre viktigaste noderna på resan.

1. Välj [!UICONTROL **Lägg till översta noder**].<!-- I don't think this should have the word "next" in the UI option, because it's both next and previous. It's in between. Just "Get top nodes" sounds better to me.-->

   De tre översta noderna läggs till mellan de två befintliga noderna och de är anslutna som separata grenar.

### Ordna om noder

Resor på arbetsytan i resan består av ett flexibelt diagram över noder och pilar som representerar en kombination av händelser, dimensionsobjekt och filter.

Du kan dra noder på arbetsytan för att ändra ordningen på händelser och villkor för resan. Data uppdateras i takt med att du gör det.

### Kombinera noder

En kombinerad nod på arbetsytan i Journey är en enda punkt i användarresan (nod) som innehåller två eller flera komponenter som förenas via logik.

#### Skapa kombinerade noder

Du kan göra något av följande om du vill skapa en kombinerad nod på arbetsytan i Journey:

* Dra en komponent från den vänstra listen till en nod på arbetsytan.

* Dra flera komponenter samtidigt från den vänstra listen till en nod på arbetsytan.

* Dra flera komponenter samtidigt från den vänstra listen till ett tomt område på arbetsytan samtidigt som du håller ned Skift.

* Markera de noder du vill kombinera på arbetsytan, högerklicka på någon av de markerade noderna och välj sedan **Kombinera**.<!--Is there a limit on how many you can combine? -->

#### Logisk när noder kombineras

Den logik som tillämpas på noder när de kombineras varierar beroende på vilka komponenttyper du kombinerar, enligt följande:

>[!TIP]
>
>Du kan visa logiken för en kombinerad nod genom att högerklicka på noden och sedan välja [!UICONTROL **Skapa filter från nod**]. Logiken visas i avsnittet [!UICONTROL **Definition**].


| Komponenttyper som ska kombineras | Använd logik (operator) |
|---------|----------|
| Mått + Mått | Kopplad med OR |
| DIMENSION + DIMENSION | Kopplad med OR |
| Filter + filter | Kopplad med AND |
| Dimension + mått, datumintervall eller filter | Kopplad med AND |
| Datumintervall + Mått, Filter eller Dimension | Kopplad med AND |
| Filter + mått, datumintervall eller Dimension | Kopplad med AND |

### Anslut noder

Du kan ansluta noder som redan finns på arbetsytan eller ansluta en nod när du lägger till den på arbetsytan.

#### Pilar mellan noder

Noderna ansluts av en pil. Både pilens riktning och bredd har betydelse:

* **Riktning**: Anger sekvensen med händelser för resan

* **Bredd**: Anger procentvolym från en nod till en annan

#### Logisk vid anslutning av noder

När du ansluter noder på en arbetsyta i Journey ansluts de med hjälp av operatorn THEN. Detta kallas även [sekventiell filtrering](/help/components/filters/seg-sequential-build.md).

Noderna är sammankopplade som en&quot;slutgiltig sökväg&quot;, vilket innebär att besökare räknas så länge de så småningom går från en nod till en annan, oavsett händelser som inträffar mellan de två noderna.

Du kan visa logiken för anslutna noder genom att högerklicka på noden och sedan välja [!UICONTROL **Skapa filter från nod**]. Logiken visas i avsnittet [!UICONTROL **Definition**].

#### Anslut befintliga noder

Resorna kan inte vara cirkelformade, de måste gå tillbaka till tidigare anslutna noder.

Så här ansluter du noder på arbetsytan Resor:

1. På arbetsytan för du pekaren över den nod som kommer först i den färdssekvens som du vill ansluta till en annan nod.

   4 blå punkter visas på var sida om den markerade noden.

1. Dra någon av de fyra blå punkterna till någon av de fyra sidorna i noden som du vill ansluta till.

   En pil visas som förbinder de två noderna. Mer information finns i [Pilar mellan noder](#arrows-between-nodes).

#### Anslut noder när du lägger till en nod

När du lägger till en nod på arbetsytan kan du placera den mellan två anslutna noder. Noden läggs till i resan mellan de två befintliga noderna.

Mer information finns i [Lägg till en nod](#add-a-node).

### Ändra färgen på en nod eller pil

Du kan anpassa en resa visuellt genom att ändra färgen på en nod eller pil på arbetsytan. Du kan till exempel justera en färg för att ange en önskvärd eller oönskad händelse.

Alternativet att ändra färgen är tillgängligt för följande objekt på arbetsytan:

* Enskilda noder

* Pilen mellan noder

Så här ändrar du färg på en nod eller pil:

1. Högerklicka på den nod eller pil vars färg du vill ändra.

1. Välj [!UICONTROL **Ändra färg**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Välj önskad färg.

   Följande färger är tillgängliga: <!--look into this interaction and color list-->

### Byta namn på en nod eller pil

När du drar en komponent till en visualisering av en arbetsyta på resan skapas en nod med samma namn som komponentnamnet. Du kan byta namn på noden så att den bättre motsvarar det steg i resan som noden representerar.

Alternativet att byta namn är tillgängligt för följande objekt på arbetsytan:

* Enskilda noder

* Pilen mellan noder

Så här byter du namn på en nod:

1. Högerklicka på noden som du vill byta namn på.

1. Välj [!UICONTROL **Byt namn**].

1. Ange ett nytt namn och tryck sedan på Retur.<!--is that right?-->

### Använda en uppdelning

Alternativet att använda en uppdelning av data är tillgängligt för följande objekt på arbetsytan:

* Enskilda noder

* Flera noder

* Pilen mellan noder

* Flera pilar mellan noder

### Använda en uppdelning på en eller flera noder eller pilar

1. Markera en eller flera noder där du vill dela upp och högerklicka sedan på en av de markerade noderna.

   eller

   Markera en eller flera pilar mellan två noder där du vill tillämpa nedbrytningen och högerklicka sedan på en av de markerade pilarna.

1. Välj [!UICONTROL **Uppdelning**].

### Tillämpa en uppdelning på en enskild nod

Du kan dra en dimension från den vänstra listen till den nod på arbetsytan där du vill tillämpa nedbrytningen.

Mer information finns i [Lägg till en nod](#add-a-node).

### Skapa en målgrupp

Alternativet att skapa en målgrupp är tillgängligt för följande objekt på arbetsytan:

* Enskilda noder

* Flera noder

* Pilen mellan noder

* Flera pilar mellan noder

Så här skapar du en publik:

1. Markera en eller flera noder där du vill skapa en målgrupp och högerklicka sedan på en av de markerade noderna.

   eller

   Markera en eller flera pilar mellan två noder där du vill skapa en målgrupp och högerklicka sedan på en av de markerade pilarna.

1. Välj [!UICONTROL **Skapa målgrupp**].

1. Fortsätt skapa och publicera målgruppen enligt beskrivningen i [Skapa och publicera målgrupper](/help/components/audiences/publish.md).

### Visa trenddata

Du kan visa trenddata i ett linjediagram för objekt på arbetsytan på resan. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

Alternativet att trender är tillgängligt för följande objekt på arbetsytan:

* Enskilda noder

* Flera noder

* Pilarna mellan noder

* Flera pilar mellan noder

Så här visar du trenddata:

1. Markera en eller flera noder som du vill visa trenddata för och högerklicka sedan på en av de markerade noderna.

   eller

   Markera en eller flera pilar mellan två noder som du vill visa trenddata för och högerklicka sedan på en av de markerade pilarna.

1. Välj [!UICONTROL **Trend**].

### Duplicera noder

Alternativet att duplicera är tillgängligt för följande objekt på arbetsytan:

* Flera noder

Så här duplicerar du noder:

1. Markera flera noder som du vill duplicera.

1. Högerklicka på en av de markerade noderna och välj sedan [!UICONTROL **Duplicera**].


### Lägga till en tidsbegränsning mellan noder

Du kan ange en tidsbegränsning mellan noder. När en person följer den definierade resan men tar längre tid än den angivna tidsperioden att förflytta sig mellan noderna, anses de ha lämnat resan.

Alternativet att lägga till en tidsbegränsning är tillgängligt för följande objekt på arbetsytan:

* Pilen mellan noder

Så här lägger du till en tidsbegränsning:

1. Högerklicka på pilen mellan två noder och välj sedan [!UICONTROL **Lägg till tidsbegränsning**].

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

### Skapa ett filter baserat på en nod eller pil

Du kan skapa ett nytt filter baserat på en nod eller pil i en resa. När filtret har skapats kan du använda det var som helst i Analysis Workspace.

Filter som skapas från arbetsytan i Resenstid använder [sekventiell filtrering](/help/components/filters/seg-sequential-build.md). Det innebär att filtret använder operatorn THEN för att länka ihop sekvensen av händelser (dvs. resan) som människor flödade igenom, vilket leder upp till den valda noden eller pilen. Alla händelser som matchar den valda noden eller pilen inkluderas i filtret.

Om du skapar ett filter baserat på en nod som har flera banor som flödar in i den, inkluderas alla banor i filtret. Separata banor förenas med operatorn OR.

Så här skapar du ett filter:

1. Högerklicka på den nod eller pil på arbetsytan som du vill använda för att skapa filtret.

1. Välj [!UICONTROL **Skapa filter från nod**] eller [!UICONTROL **Skapa filter från pil**].

   Filterverktyget visas. I avsnittet [!UICONTROL **Definition**] skapas filterdefinitionen baserat på noden eller pilen som du valde och dess kontext inom resan.

1. Ange en titel för filtret och gör eventuella andra ändringar. Mer information om hur du skapar ett filter finns i [Filterverktyget](/help/components/filters/filter-builder.md).

1. Välj [!UICONTROL **Spara**] om du vill spara filtret.

### Ta bort noder

Du kan ta bort en eller flera noder i taget under en resa. När du tar bort en nod som är ansluten mellan två noder under resan kopplas de två återstående noderna direkt samman.

Så här tar du bort noder på arbetsytan för Resor:

1. Markera en eller flera noder som du vill ta bort och högerklicka sedan på någon av de markerade noderna.

1. Välj [!UICONTROL **Ta bort**].

### Ta bort pilar mellan noder

Du kan ta bort en eller flera pilar åt gången under en resa. När du tar bort en pil mellan två noder är noderna inte längre anslutna. Om pilen var en del av en längre bana kopplas banan från.

Så här tar du bort pilar mellan noder på arbetsytan för Resor:

1. Markera en eller flera pilar mellan två noder som du vill ta bort och högerklicka sedan på en av de markerade pilarna.

1. Välj [!UICONTROL **Ta bort**].


<!-- Delete this after I decide I don't want to do it this way. Will probably use sections like I hav above.

### Manage existing nodes

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Right-click an **individual node** on the canvas, then select any of the following options:
   
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Create segment**] | B1 |
   | [!UICONTROL **Publish audience**] | B2 |
   | [!UICONTROL **Trend**] | B3 | 
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Get top next ...**] | B2 |
   | [!UICONTROL **Change color**] | B2 |
   | [!UICONTROL **Rename**] | B2 |
   | [!UICONTROL **Delete**] | B2 |

1. Select **multiple nodes** on the canvas, right-click one of the selected nodes, then select any of the following options:

   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Combine**] | B1 |
   | [!UICONTROL **Delete**] | B2 |
   | [!UICONTROL **Duplicate**] | B3 | 
   | [!UICONTROL **Trend**] | B2 |
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Create segment**] | B2 |
   | [!UICONTROL **Publish audience**] | B2 |

   -->


## Öppna en resa från Journey Optimizer


Öppna den resa du vill analysera på arbetsytan i Journey Optimizer.

1. Välj [!UICONTROL **Analysera i CJA**]. <!-- ?? -->
