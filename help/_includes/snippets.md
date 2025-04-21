---
source-git-commit: be615a45a68b47f95517992cc4268a887ac1110a
workflow-type: tm+mt
source-wordcount: '3756'
ht-degree: 0%

---
# Fragment

## Begränsad testning av versionsfas {#release-limited-testing}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i den här artikeln är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Customer Journey Analytics funktionsreleaser](/help/release-notes/releases.md).

## Frisläppningsfas, begränsad testsektion {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Customer Journey Analytics funktionsreleaser](/help/release-notes/releases.md).

## Välj paket {#select-package}

>[!NOTE]
>
>Du måste ha paketet **Select** eller senare för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

## Prime package {#prime-package}

>[!NOTE]
>
>Du måste ha paketet **Prime** eller senare för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

## Ultimate package {#ultimate-package}

>[!NOTE]
>
>Du måste ha **Ultimate**-paketet för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

## Alternativ för komponentsortering {#components-sort-options}

| Alternativ | Funktion |
|---------|----------|
| **[!UICONTROL Recommended]** | Sortera komponenter för varje typ (mått, mått, segment och datumintervall) baserat på deras rekommendation. Komponenter som du eller andra i organisationen använder oftast och senast visas högst upp i varje lista. |
| **[!UICONTROL Last modified]** | Sortera komponenter för varje typ (dimension, mått, segment och datumintervall) baserat på deras senaste ändringsdatum. De senast ändrade komponenterna visas högre i varje lista. |
| **[!UICONTROL Alphabetical]** | Sortera komponenterna för varje typ (mått, mått, segment och datumintervall) i stigande alfabetisk ordning. |
| **[!UICONTROL Categorical]** | Sortera komponenterna för varje typ (dimension, mått, segment och datumintervall) baserat på deras kategori. Exempel: Kuraterade jämfört med Ej strukturerade datavykomponenter. |

{style="table-layout:auto"}

## Tidsjämförelse {#apply-time-comparison}

Du kan jämföra den aktuella tidsperioden med en tidigare tidsperiod. Om du väljer ett alternativ på den här menyn får alla datapunkter en motsvarande streckad motsvarighet i färg. Den här motsvarigheten representerar samma mått i det valda föregående datumintervallet. Om du anger det här alternativet dubbleras antalet objekt i diagrammet och raderna i tabellen.

Tillgängliga tidsjämförelsealternativ omfattar föregående period, 13 veckor före, 52 veckor före och ett anpassat datumintervall. Om du väljer Anpassat datumintervall visas ytterligare alternativ så att du kan välja antal och detaljrikedom. Om du väljer Ingen tas datumjämförelsen bort.


## Videodemonstration - Adobe Analytics {#videoaa}

*Den här videon demonstrerar funktionaliteten med Adobe Analytics. Funktionen finns dock på liknande sätt i Customer Journey Analytics. Observera skillnaderna i terminologi mellan Adobe Analytics och Customer Journey Analytics (t.ex.&quot;besök&quot; jämfört med&quot;sessioner&quot;).*


## Panelen Filter {#filterspanel}

1. Välj ![Filter](/help/assets/icons/Filter.svg) för att öppna panelen Filter. Om du behöver mer utrymme för filterlistan kan du stänga panelen genom att välja ![Filter](/help/assets/icons/Filter.svg) en gång till.
1. Välj filter från något av de tillgängliga filteravsnitten.


## Avsnittet Taggfilter {#tagfiltersection}

| Taggar | Beskrivning |
|---|---|
| ![Taggar](/help/assets/filter-tag.png){width="300"} | I avsnittet **[!UICONTROL Tags]** kan du filtrera efter taggar. <ul><li>Du kan ![söka efter ](/help/assets/icons/Search.svg) *söktaggar* om du vill söka efter taggar som du kan använda för att filtrera.</li><li>Du kan markera flera taggar. Vilka märkord som är tillgängliga beror på vilka markeringar du har gjort i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>**(1)**: Antalet markerade taggar (om en eller flera taggar har valts).</li><li>**2︎⃣**: Antalet tillgängliga taggar för objekten som är resultatet av det aktuella filtret.</li><li>7︎⃣: Antalet objekt som är associerade med den specifika taggen.</li></ul></li></ul> |


## Filteravsnitt för datavy {#dataviewfiltersection}

| Datavy | Beskrivning |
|---|---|
| ![Datavyer](/help/assets/filter-dataview.png){width="300"} | I avsnittet **[!UICONTROL Data view]** kan du filtrera på datavyer. <ul><li>Du kan ![söka](/help/assets/icons/Search.svg) *i datavyer* om du vill söka efter datavyer som du kan använda för att filtrera.</li><li>Du kan välja mer än en datavy. Vilka datavyer som är tillgängliga beror på vilka markeringar du har gjort i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>**(2)**: Antalet markerade datavyer (om en eller flera datavyer har valts).</li><li>**3︎⃣**: Antalet datavyer som är tillgängliga för objekten som är resultatet av det aktuella filtret.</li><li>4︎⃣: Antalet objekt som är associerade med den specifika datavyn.</li></ul></li></ul> |

## Aktiverat statusfilteravsnitt {#enabledstatusfiltersection}

| Aktiverad status | Beskrivning |
|---|---|
| ![Aktiverad status](/help/assets/filter-enabledstatus.png){width="300"} | I avsnittet **[!UICONTROL Enabled status]** kan du filtrera efter aktiverad status. <ul><li>Du kan välja mer än en status.</li><li>Siffrorna anger:<ul><li>**(2)**: Antalet markerade statusar (om en eller flera statusvärden har valts).</li><li>**2︎⃣**: Antalet statusar som är tillgängliga för objekten från det aktuella filtret.</li><li>1︎⃣: Antalet artiklar som är associerade med den specifika statusen.</li></ul></li></ul> |

## Textfilteravsnitt {#typefiltersection}

| Typ | Beskrivning |
|---|---|
| ![Typ](/help/assets/filter-type.png){width="300"} | I avsnittet **[!UICONTROL Type]** kan du filtrera efter typ. <ul><li>Du kan markera flera typer.</li><li>Siffrorna anger:<ul><li>**(2)**: Antalet valda typer (om en eller flera typer har valts).</li><li>**1︎⃣**: Antalet tillgängliga typer för objekten som är resultatet av det aktuella filtret.</li><li>3︎⃣: Antalet objekt som är associerade med den specifika typen.</li></ul></li></ul> |

## Ägarfilteravsnitt {#ownerfiltersection}

| Ägare | Beskrivning |
|---|---|
| ![Ägare](/help/assets/filter-owners.png){width="300"} | I avsnittet **[!UICONTROL Owner]** kan du filtrera efter ägare. <ul><li>Du kan ![söka](/help/assets/icons/Search.svg) *sökägare* om du vill söka efter ägare som du kan använda för att filtrera.</li><li>Du kan välja mer än en ägare. Vilka ägare som är tillgängliga beror på vad som har gjorts i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>**(2)**: Antalet valda ägare (om en eller flera ägare har valts).</li><li>**3︎⃣**: Antalet ägare som är tillgängliga för objekten som är resultatet av det aktuella filtret.</li><li>4︎⃣: Antalet objekt som är associerade med den specifika ägaren.</li></ul></li></ul> |

## Andra filteravsnitt {#otherfiltersfiltersection}

| Andra filter | Beskrivning |
|---|---|
| ![Andra filter](/help/assets/filter-other.png){width="300"} | I avsnittet **[!UICONTROL Other filters]** kan du filtrera på andra fördefinierade filter.<ul><li>Du kan välja ett eller flera av följande alternativ:<ul><li> **[!UICONTROL Show all]**</li><li>**[!UICONTROL Shared with me]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approved]**</li><li>**[!UICONTROL Favorites]**</li></ul> Vad du kan välja beror på din roll och dina behörigheter.</li><li>Du kan markera mer än ett annat filter. Vilka andra filter som är tillgängliga beror på vilka markeringar du har gjort i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>**(1)**: Antalet markerade andra filter (om ett eller flera andra filter har valts).</li><li>**5︎⃣**: Antalet andra filter som är tillgängliga för objekten från det aktuella filtret.</li><li>4︎⃣: Antalet objekt som är associerade med det specifika andra filtret.</li></ul></li></ul> |

## Filteravsnitt för datumintervall  {#daterangefiltersection}

| Tillämpat datumintervall | Beskrivning |
|---|---|
| ![Datumintervall](/help/assets/filter-daterange.png){width="300"} | I avsnittet Använt datumintervall kan du filtrera efter ett datumintervall som gäller för artiklarna.<ol><li>Välj ett datumintervall.</li><li>Ange ett datumintervall i kalenderpopup eller välj en av de tillgängliga förinställningarna.<br>Du kan också ange ett datumintervall direkt i datumintervallet på panelen Filter.</li></ol><ul><li>Siffrorna anger:<ul><li>**(1)**: Antalet ändrade datumintervall som har ändrats från standardförinställningar.</li><li>**5︎⃣**: Antalet datumintervall som är tillgängliga för objekten från det aktuella filtret.</li></ul> |


## Attributionsmodeller {#attribution-models-details}

En attribueringsmodell avgör vilka dimensionsobjekt som får kredit för ett mätresultat när flera värden visas i en metrisk sökningsfönster. Attributionsmodeller används bara när det finns flera dimensionsobjekt angivna i uppslagsfönstret. Om bara en enda dimensionsobjekt anges får den dimensionsobjektet 100 % kredit oavsett vilken attribueringsmodell som används.

| Ikon | Attributionsmodell | Definition |
| :---: | :--- | --- |
| ![Senaste beröring](/help/assets/icons/AttributeLastTouch.svg) | Senaste beröring | Ger 100 % uppskattning av den beröringspunkt som inträffade senast före konverteringen. Den här attribueringsmodellen är vanligtvis standardvärdet för alla mätvärden där ingen attributmodell har angetts på annat sätt. Organisationer använder vanligtvis den här modellen där tiden för konvertering är ganska kort, till exempel när interna söknyckelord analyseras. |
| ![Första beröring](/help/assets/icons/AttributeFirstTouch.svg) | Första beröring | Ger 100 % kredit till den beröringspunkt som först ses i attribueringssökningsfönstret. Organisationer använder vanligtvis den här modellen för att förstå varumärkesmedvetenhet och kundvärvning. |
| ![Linjär](/help/assets/icons/AttributeLinear.svg) | Linjär | Ger samma beröm till alla kontaktytor som leder till konvertering. Det är användbart när konverteringscyklerna är längre eller kräver mer frekvent kundengagemang. Organisationer använder vanligtvis den här attribueringsmodellen för att mäta hur effektiva mobilappsaviseringar är eller med prenumerationsbaserade produkter. |
| ![Deltagande](/help/assets/icons/AttributeParticipation.svg) | deltagande | Alla unika kontaktpunkter får 100 % beröm. Eftersom varje beröringspunkt får 100 % rabatt läggs måttdata vanligtvis till mer än 100 %. Om en dimensionspost visas flera gånger som leder till en konvertering, dupliceras värdena till 100 %. Den här attribueringsmodellen är perfekt i situationer där du vill förstå vilka kontaktpunkter kunderna exponeras mest för. Medieorganisationer använder vanligtvis den här modellen för att beräkna innehållets hastighet. Butiksorganisationer använder vanligtvis den här modellen för att förstå vilka delar av deras sajt som är avgörande för konverteringen. |
| ![Samma beröring](/help/assets/icons/AttributeSameTouch.svg) | Samma beröring | Ger 100 % kredit till samma händelse som konverteringen inträffade. Om en beröringspunkt inte inträffar för samma händelse som en konvertering, blockeras den under Ingen. Den här attribueringsmodellen är ibland lika med att inte ha någon attribueringsmodell alls. Det är värdefullt i scenarier där du inte vill ha värden från andra händelser som påverkar hur ett mätvärde ger kredit till dimensionsobjekt. Produkt- eller designteam kan använda den här modellen för att utvärdera hur effektiv en sida är där konverteringen sker. |
| ![U-form](/help/assets/icons/AttributeUShaped.svg) | U Shaped | Ger 40 % uppskattning av den första interaktionen, 40 % tack vare den sista interaktionen och delar de återstående 20 % på alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får båda 50 % rabatt. Den här attribueringsmodellen används bäst i scenarier där du värdesätter den första och den sista interaktionen mest, men inte helt vill avvisa ytterligare interaktioner däremellan. |
| ![J-kurva](/help/assets/icons/AttributeJCurve.svg) | J-kurva | Ger 60 % kreativitet till den senaste interaktionen, 20 % tack till den första interaktionen och delar de återstående 20 % på alla kontaktpunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får 75 % poäng för den senaste interaktionen och 25 % kredit ges till den första. I likhet med U-Shaped är den här attribueringsmodellen att föredra den första och sista interaktionen, men den är mer prioriterad än den sista interaktionen. |
| ![Omvänd J](/help/assets/icons/AttributeInverseJ.svg) | Inverterad J | Ger 60 % kredit till den första beröringspunkten, 20 % kredit till den sista beröringspunkten och delar de återstående 20 % till alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får 75 % kredit för den första interaktionen och 25 % kredit för den sista. I likhet med J-Shaped prioriterar den här attribueringsmodellen den första och sista interaktionen, men prioriterar den första interaktionen mer. |
| ![Tidsminskning](/help/assets/icons/AttributeTimeDecay.svg) | Tidsminskning | Följer en exponentiell minskning med en anpassad halveringsparameter, där standardvärdet är 7 dagar. Vikten för varje kanal beror på hur lång tid det tar mellan öppnandet av kontaktpunkten och den slutliga konverteringen. Formeln som används för att bestämma kredit är `2^(-t/halflife)`, där `t` är tiden mellan en kontaktpunkt och en konvertering. Alla beröringspunkter normaliseras sedan till 100 %. Perfekt för scenarier där du vill mäta attribuering mot en specifik och viktig händelse. Ju längre en konvertering sker efter den här händelsen, desto mindre kredit ges. |
| ![Anpassat](/help/assets/icons/AttributeCustom.svg) | Anpassad | Gör att du kan ange de vikter du vill ge den första beröringspunkten, den sista beröringspunkten och eventuella mellanliggande beröringspunkter. De angivna värdena normaliseras till 100 % även om de anpassade siffrorna inte läggs till i 100. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För interaktioner med två beröringspunkter ignoreras parametern middle. Den första och sista beröringspunkten normaliseras sedan till 100 % och krediteringen tilldelas därefter. Den här modellen är idealisk för analytiker som vill ha fullständig kontroll över sin attribueringsmodell och har särskilda behov som andra attribueringsmodeller inte uppfyller. |
| ![Algoritmisk](/help/assets/icons/AttributeAlgorithmic.svg) | Algoritmisk | Använder statistiska tekniker för att dynamiskt fastställa den optimala kreditfördelningen för det valda måttet. Den algoritm som används för attribuering bygger på Harsanyi Dividend från kooperativ spelteori. Harsanyi-utdelningen är en generalisering av Shapley-värdelösningen (som uppges efter Lloyd Shapley, en Nobel Laureate-ekonom) för att distribuera krediter bland spelarna i ett spel med olika bidrag till resultatet.<br>Vid en hög nivå beräknas attribueringen som en koalition av spelare till vilka ett överskott måste fördelas jämnt. Varje koalitions överskottsfördelning bestäms utifrån det överskott som tidigare skapades genom varje delkoalition (eller tidigare deltagande dimensionsposter) rekursivt. Mer information finns i John Harsanyis och Lloyd Shapley&#39;s original papers:<br>Shapley, Lloyd S. (1953). Ett värde för personliga spel. *Bidrag till spelets teori, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). En förenklad förhandlingsmodell för det personliga kooperativa spelet. *Internationell ekonomisk granskning 4(2)*, 194-220. |

{style="table-layout:auto"}

## Fönstret Tilldelningssökning {#attribution-lookback-window}

Ett uppslagsfönster är den tid som en konvertering bör titta tillbaka för att inkludera beröringspunkter. Om ett dimensionsobjekt anges utanför uppslagsfönstret inkluderas inte värdet i någon attribueringsberäkning.

* **14 dagar**: Kan synkroniseras upp till 14 dagar från när konverteringen gjordes.
* **30 dagar**: Kan synkroniseras upp till 30 dagar från när konverteringen gjordes.
* **60 dagar**: Kan synkroniseras upp till 60 dagar från när konverteringen gjordes.
* **90 dagar**: Återställer upp till 90 dagar från när konverteringen inträffade.
* **13 månader** [!BADGE B2B edition]{type=Informative}: Kan synkroniseras upp till 13 månader efter konverteringen.
* **Session**: Går tillbaka till början av sessionen där en konvertering inträffade. Sessionssökningsfönster respekterar den ändrade [Sessionstimeout](/help/data-views/create-dataview.md#session-settings) i en datavy.
* **Person (rapporteringsfönster)**: Alla besök kontrolleras fram till den första i månaden i det aktuella datumintervallet. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för personsökning 1 september - 30 september. Om du använder det här uppslagsfönstret kan du ibland se att dimensionsobjekt tilldelas till datum utanför rapportfönstret.
* **Global Account (Reporting Window)** [!BADGE B2B edition]{type=Informative}: Kontrollerar för alla globala konton fram till den första månaden i det aktuella datumintervallet. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för global kontosökning 1 september - 30 september. Om du använder det här uppslagsfönstret kan du ibland se att dimensionsobjekt tilldelas till datum utanför rapportfönstret.
* **Konton (rapporteringsfönster)** [!BADGE B2B edition]{type=Informative}: Kontrollerar för alla konton fram till den första månaden i det aktuella datumintervallet. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för kontosökning 1 september - 30 september. Om du använder det här uppslagsfönstret kan du ibland se att dimensionsobjekt tilldelas till datum utanför rapportfönstret.
* **Möjlighet (rapporteringsfönster)** [!BADGE B2B edition]{type=Informative}: Alla affärsmöjligheter kan säkerhetskopieras till den första månaden i det aktuella datumintervallet. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för affärsmöjlighetssökning 1 september - 30 september. Om du använder det här uppslagsfönstret kan du ibland se att dimensionsobjekt tilldelas till datum utanför rapportfönstret.
* **Köpgrupp (rapporteringsfönster)** [!BADGE B2B edition]{type=Informative}: Kontrollerar alla inköpsgrupper fram till den första i månaden i det aktuella datumintervallet. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för inköpsgruppens sökning 1 september - 30 september. Om du använder det här uppslagsfönstret kan du ibland se att dimensionsobjekt tilldelas till datum utanför rapportfönstret.
* **Anpassad tid:** Används för att ange ett anpassat uppslagsfönster från när en konvertering inträffade. Du kan ange antalet minuter, timmar, dagar, veckor, månader eller kvartal. Om en konvertering till exempel skedde den 20 februari skulle ett uppslagsfönster på fem dagar utvärdera alla dimensionskontaktytor från den 15 februari till den 20 februari i attribueringsmodellen.

## Attributionsexempel {#attribution-example}

Titta på följande exempel:

1. Den 15 september kommer en person till er webbplats via en betald sökannons, sedan går han/hon iväg.
1. Den 18 september kommer personen till er webbplats igen via en länk för sociala medier som de fått från en vän. De lägger till flera artiklar i kundvagnen, men köper ingenting.
1. Den 24 september skickar marknadsföringsteamet ett e-postmeddelande med en kupong för några av artiklarna i kundvagnen. De använder kupongen, men besöker flera andra sajter för att se om det finns några andra kuponger. De hittar en till genom en displayannons och gör sedan ett köp för 50 dollar.

Beroende på ditt uppslagsfönster och din attribueringsmodell får kanalerna olika krediter. Nedan följer några exempel:

* Med **första beröring** och ett **sessionsfönster** tittar attribueringen bara på det tredje besöket. Mellan e-post och visning var e-post först, så e-post får 100 % rabatt på 50 USD.

* Attribution söker efter alla tre besök med **första beröring** och ett **fönster för personsökning**. Betalsökning var först, så den får 100 % rabatt på 50 USD.

* Med **linjär** och ett **sessionsfönster** delas krediteringen mellan e-post och visning. Båda dessa kanaler får 25 krediter.
Med **linjär** och ett **personsökningsfönster** delas krediten in i betalsökning, sociala medier, e-post och visning. Varje kanal får 12,50 dollar i rabatt för detta inköp.

* Med **J-formad** och ett **personsökningsfönster** delas krediteringen mellan betalsökningar, sociala medier, e-post och visning.

   * 60 % kredit ges för 30 dollar.
   * 20 % kredit ges till betald sökning för 10 dollar.
   * De återstående 20 % är uppdelade i sociala medier och e-post, vilket ger 5 USD till var och en.

* Med **Time Decay** och ett **Personsökningsfönster** delas krediten in i betalsökning, sociala medier, e-post och visning. Använd standardhalveringstiden på 7 dagar:

   * Mellanrum på noll dagar mellan visning och konvertering. `2^(-0/7) = 1`
   * Mellanrum på noll dagar mellan e-postens kontaktpunkt och konvertering. `2^(-0/7) = 1`
   * Ett mellanrum på sex dagar mellan social kontaktyta och konvertering. `2^(-6/7) = 0.552`
   * Mellanrum på nio dagar mellan betald sökningspunkt och konvertering. `2^(-9/7) = 0.41`
   * Normalisering av dessa värden ger följande resultat:

      * Bildskärm: 33,8 %, får 16,88 USD
      * E-post: 33,8 % får 16,88 USD
      * Socialt: 18,6 %, får 9,32 USD
      * Betalsökning: 13,8 %, får 6,92 USD

Konverteringshändelser som vanligtvis har ett heltal delas om kredit tillhör fler än en kanal. Om till exempel två kanaler bidrar till en order med en linjär attribueringsmodell får båda kanalerna 0,5 av den ordningen. Dessa partiella mätvärden summeras för alla personer och avrundas sedan till närmaste heltal för rapportering.

## Jämförelser av resevisualisering {#journey-visualization-comparisons}

Olika visualiseringar i kundreseanalyser är utformade för att analysera de resor du erbjuder dina kunder.

Använd följande information för att välja den visualisering som bäst passar dina behov.

| Funktion | Reseduk | Utfall | Flöde |
|---------|----------|---------|---------|
| **Fördefinierad sidsekvens** | Ja</br>Kombinerar fördefinierad och undersökande analys. Den slutliga sökvägen används när fördefinierade noder används på banan (besökare räknas så länge de till slut går från en fördefinierad nod till en annan). Nästa nod som är direkt (inte slutgiltig) kan också visas genom att [visa de översta noderna baserat på befintliga noder](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#show-the-top-nodes-based-on-existing-nodes). | Ja</br>Sökvägen kan vara en slutlig sökväg eller begränsas till nästa kontaktyta | Nej |
| **Utforska sidsekvenser (ad hoc-analys)** | Ja</br>Kombinerar fördefinierad och undersökande analys. Den slutliga sökvägen används när fördefinierade noder används på banan (besökare räknas så länge de till slut går från en fördefinierad nod till en annan). Nästa nod som är direkt (inte slutgiltig) kan också visas genom att [visa de översta noderna baserat på befintliga noder](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#show-the-top-nodes-based-on-existing-nodes). | Begränsad</br>Du kan högerklicka och visa direkt utfall i en friformstabell. | Ja</br>Endast experimentell analys. Alltid inom en dimensionsinstans mellan noder. Det innebär att varje nod visar den omedelbara (inte slutliga) nästa kontaktyta längs banan. |
| **Visar var personer slutade (föll ut) och fortsatte igenom (gick igenom)** | Ja</br>Visar både fördefinierade och experimentella resor. | Ja</br>Visar fördefinierade resor | Ja</br>Visar för experimentella resor |
| **Linjära resor** | Ja | Ja | Nej |
| **Icke-linjära resor med flera startpunkter och sökvägar** | Ja | Nej | Ja |
| **Primärt mått** | Alla mätvärden, inklusive beräknade värden. | Endast session eller person | Endast förekomster (banvyer) |
| **Sekundärt mått** | Ja<p>Alla mätvärden, inklusive beräknade värden.</p> | Nej | Nej |
| **Komponentstöd i noder eller kontaktytor** | Mätvärden, dimensionsobjekt, segment och datumintervall. | Mätvärden, dimensionsobjekt, segment och datumintervall. | Endast dimensionsobjekt (utom start- och slutkontaktytan) |
| **Jämför segment** | Nej | Ja<p>Jämför två olika segment sida vid sida i samma rapport.</p> | Nej |
| **Komponentinteraktion genom att dra och släppa** | Ja | Ja | Nej |
| **Adobe Journey Optimizer-resor** | Ja</br>Öppna resor från Journey Optimizer för djupgående analyser och anpassningar. | Nej | Nej |

{style="table-layout:auto"}

## Uppgradera checklista {#upgrade-note}

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i Customer Journey Analytics uppgraderingshandbok. <br><br>Om du vill komma åt guiden från Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.

## Uppgradera checklista, anteckning efter steg {#upgrade-note-step}

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de rekommenderade uppgraderingsstegen (rekommenderas för de flesta organisationer) eller följa de steg som skapas dynamiskt för din organisation med Customer Journey Analytics Upgrade Guide. <ul><li>**Rekommenderade uppgraderingssteg** (rekommenderas för de flesta organisationer)<p>En serie steg som leder till en perfekt Customer Journey Analytics-implementering.</p><p>Mer information finns i [Uppgradera från Adobe Analytics till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide** (anpassade steg som är anpassade efter organisationens specifika behov)<p>Det finns en ny uppgraderingsguide som dynamiskt genererar uppgraderingssteg som är skräddarsydda för just er organisation och era unika omständigheter.</p><p>Om du vill få åtkomst till guiden från Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.</p></li></ul>

## Slutgiltigt steg för checklista för uppgradering {#upgrade-final-step}

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de dynamiskt genererade uppgraderingsstegen i Customer Journey Analytics Upgrade Guide. Om du vill få åtkomst till guiden från Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.


## Utkast till Content Analytics-dokumentation {#draft-aca}

>[!WARNING]
>
>Artikeln ingår i utkastet till Content Analytics-dokumentation. Alla utkast till Content Analytics-dokumentation kan fortfarande ändras och inga rättsliga skyldigheter kan härledas från den aktuella versionen av den här artikeln eller någon annan artikel som ingår i Content Analytics-dokumentationen.
>


## Utkast till Customer Journey Analytics B2B edition-dokumentation {#draft-b2b}

>[!AVAILABILITY]
>
>De funktioner som beskrivs i den här artikeln, och alla andra artiklar eller funktioner som har märkts med [!BADGE B2B edition]{type=Informative}, är i den begränsade testfasen och är kanske inte tillgängliga än i din miljö. <br/>Dessutom kan [!BADGE B2B edition]{type=Informative}-funktioner och dokumentation för [!BADGE B2B edition]{type=Informative}-funktioner ändras och inga juridiska skyldigheter härledas från dem.<br/>Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Customer Journey Analytics funktionsreleaser](/help/release-notes/releases.md).
>


## B2B edition {#b2b-edition}

>[!INFO]
>
>I den här dokumentationen markeras specifika B2B-artiklar eller funktioner, som bara är tillgängliga med Customer Journey Analytics B2B edition, med [!BADGE B2B edition]{type=Informative}.
