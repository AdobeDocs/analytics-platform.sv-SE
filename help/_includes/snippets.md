---
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '3624'
ht-degree: 0%

---
# Fragment

## Begränsad testning av versionsfas {#release-limited-testing}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i den här artikeln är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).

## Frisläppningsfas, begränsad testsektion {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).

## Välj paket {#select-package}

>[!NOTE]
>
>Du måste ha paketet **Select** eller senare för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

## Prime-paket {#prime-package}

>[!NOTE]
>
>Du måste ha paketet **Prime** eller senare för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

## Ultimat paket {#ultimate-package}

>[!NOTE]
>
>Du måste ha paketet **Ultimate** för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.


## Filtervillkor för dataordlista {#dd-filter-criteria}

1. (Valfritt) Markera ikonen **Filter** ![Datamordlistefilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) och välj sedan något av följande filteralternativ för att filtrera komponentlistan:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Godkänd**] | Visa endast komponenter som har markerats som Godkänd av en administratör. |
   | [!UICONTROL **Favoriter**] | Visa endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Komponentöversikt](/help/components/overview.md). |
   | [!UICONTROL **Dimensioner**] | Visa endast komponenter som är Dimensioner. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
   | [!UICONTROL **Mätvärden**] | Visa endast komponenter som är mätvärden. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
   | [!UICONTROL **Filter**] | Visa endast komponenter som är filter. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Datumintervall**] | Visa endast komponenter som är datumintervall. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
   | [!UICONTROL **Visa alla**] | Visa alla komponenter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Ej godkänt**] | Visa endast komponenter som ännu inte har markerats som Godkända av en administratör. Som administratör är detta användbart när du identifierar komponenter som kräver granskning och godkännande. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Beskrivning saknas**] | Visa endast komponenter som ännu inte har någon beskrivning i fältet Beskrivning. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Visa dubbletter**] | Visa bara komponenter som har antingen samma namn eller samma beskrivning som en annan komponent i den markerade datavyn. Detta omfattar både komponenter du skapar och de som tillhandahålls av Adobe. Namn eller beskrivningar måste vara exakta matchningar för att kunna visas som dubbletter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Inga senaste data**] | Visa endast komponenter som inte har samlat in några data under de senaste 90 dagarna. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Skapad av Adobe**] <!-- I don't see this option--> | Visa endast komponenter som har skapats av Adobe. Komponenter som har skapats av en administratör eller en annan användare i organisationen visas inte. |

   {style="table-layout:auto"}

## Komponentinformation för dataordlista {#dd-component-information}

| Alternativ | Funktion |
|---------|----------|
| [!UICONTROL **Godkänd**] | <p>Anger att komponenten har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **inte godkänna**]. Om du väljer det här alternativet markeras komponenten som&quot;Inte godkänd&quot; för användarna.</p> |
| [!UICONTROL **Inte godkänt**] | <p>Anger att komponenten ännu inte har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **godkänna**]. Om du väljer det här alternativet markeras komponenten som&quot;Godkänd&quot; för användare.</p> |
| [!UICONTROL **Beskrivning**] | Beskriver komponentens avsedda funktion. (Den här informationen läggs till av Analytics-administratören, enligt beskrivningen i [Lägg till komponentbeskrivningar](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Används ofta med**] | <p>Visar komponenter som används oftast med den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Filter och Datumintervall.</p><p>Listan baseras på data från de senaste 90 dagarna. Endast de komponenter som du har åtkomst till visas.</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**]. Innan du strukturerar de komponenter som visas för användarna måste du först tillämpa filtret **Visa alla** för att se om några komponenter som inte delas med dig har lagts till av en annan administratör.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Liknar**] | <p>Visar komponenter med liknande namn som den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Filter och Datumintervall.</p><p>Endast de komponenter som du har åtkomst till visas.</p><p>Alla dubblettkomponenter i datavyn visas här. Analysadministratörer bör identifiera och ta bort alla dubblettkomponenter, vilket beskrivs i [Övervaka dataordlistehälsa](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**]. Innan du strukturerar de komponenter som visas för användarna måste du först tillämpa filtret **Visa alla** för att se om några komponenter som inte delas med dig har lagts till av en annan administratör.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBS!** För närvarande innehåller avsnittet **Liknande** bara komponenter som du skapar och inte de som tillhandahålls av Adobe. Komponenter som tillhandahålls av Adobe kommer att läggas till i en framtida version.</p> |
| [!UICONTROL **Produktkompatibilitet**] | Anger var i Customer Journey Analytics det här beräknade måttet kan användas. <p>Möjliga värden är:</p><ul><li>[!UICONTROL **Överallt i Customer Journey Analytics**]: Det beräknade måttet kan användas i hela Customer Journey Analytics, inklusive i Analysis Workspace, Report Builder och så vidare.</li><li>[!UICONTROL **Överallt i Customer Journey Analytics (utom experiment)**]: Det beräknade måttet kan användas i hela Customer Journey Analytics, utom på panelen Experimentation.</li> <p>Mer information om villkoren som avgör om ett beräknat mätresultat kan användas för experimenterande finns i [Använd beräknade mätvärden på panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) i [panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| [!UICONTROL **Taggar**] | Visar alla taggar som har tillämpats på komponenten. Användare med administratörsbehörighet kan lägga till taggar när komponenten redigeras. |
| [!UICONTROL **Komponenttyp**] | Visar vilken typ av komponent det är, oavsett om det är en Dimension, ett mått, ett filter eller ett datumintervall. |
| [!UICONTROL **Skapad av**] | Visar namnet på den användare som skapade komponenten. |
| [!UICONTROL **Förhandsgranska**] | Visar en förhandsgranskning av hur komponenten ser ut i Analysis Workspace. |
| [!UICONTROL **Senast ändrad**] | Visar den dag som komponenten senast ändrades. Det här avsnittet visas när du visar filter, mått, beräknade värden och datumintervall. |

{style="table-layout:auto"}

## Alternativ för komponentsortering {#components-sort-options}

| Alternativ | Funktion |
|---------|----------|
| **[!UICONTROL Recommended]** | Sortera komponenter för varje typ (mått, mått, filter och datumintervall) baserat på deras rekommendation. Komponenter som du eller andra i organisationen använder oftast och senast visas högst upp i varje lista. |
| **[!UICONTROL Last modified]** | Sortera komponenter för varje typ (mått, mått, filter och datumintervall) baserat på deras senaste ändringsdatum. De senast ändrade komponenterna visas högre i varje lista. |
| **[!UICONTROL Alphabetical]** | Sortera komponenterna för varje typ (mått, mått, filter och datumintervall) i stigande alfabetisk ordning. |
| **[!UICONTROL Categorical]** | Sortera komponenter för varje typ (mått, mått, filter och datumintervall) baserat på deras kategori. Exempel: Kuraterade jämfört med Ej strukturerade datavykomponenter. |

{style="table-layout:auto"}

## Tidsjämförelse {#apply-time-comparison}

Du kan jämföra den aktuella tidsperioden med en tidigare tidsperiod. Om du väljer ett alternativ på den här menyn får alla datapunkter en motsvarande streckad motsvarighet i färg. Den här motsvarigheten representerar samma mått i det valda föregående datumintervallet. Om du anger det här alternativet dubbleras antalet objekt i diagrammet och raderna i tabellen.

Tillgängliga tidsjämförelsealternativ omfattar föregående period, 13 veckor före, 52 veckor före och ett anpassat datumintervall. Om du väljer Anpassat datumintervall visas ytterligare alternativ så att du kan välja antal och detaljrikedom. Om du väljer Ingen tas datumjämförelsen bort.


## Videodemonstration - Adobe Analytics {#videoaa}

>[!NOTE]
>
>I den här videon demonstreras funktionaliteten med Adobe Analytics. Funktionen finns dock på liknande sätt i Customer Journey Analytics. Tänk på följande skillnader i terminologi.
>
>
>| Adobe Analytics | Customer Journey Analytics |
>|:---:|:---:|
>| Segment | Filter |
>| Besökare | Person |
>| Besök | Session |
>| Träff | Händelse |
>

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
* **Session**: Går tillbaka till början av sessionen där en konvertering inträffade. Sessionssökningsfönster respekterar den ändrade [Sessionstimeout](/help/data-views/create-dataview.md#session-settings) i en datavy.
* **Person (rapporteringsfönster)**: Alla besök kontrolleras fram till den första i månaden i det aktuella datumintervallet. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för personsökning 1 september - 30 september. Om du använder det här uppslagsfönstret kan du ibland se att dimensionsobjekt tilldelas till datum utanför rapportfönstret.
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

