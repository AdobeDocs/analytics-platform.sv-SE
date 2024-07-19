---
title: Inställningar för attribueringskomponent
description: Gör att du kan ange standardattribuering för ett mätresultat.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 0%

---

# Inställningar för attribueringskomponent

Attribution låter dig anpassa hur dimensionsposter får kredit för lyckade händelser.

![Fönstret Datavyer där attributalternativet Ange markeras ](../assets/attribution-settings.png)

Exempel:

1. En person på din webbplats klickar på en betalsöklänk till en av dina produktsidor. De lägger produkten i varukorgen, men köper den inte.
2. Nästa dag ser de ett inlägg i sociala medier från en av deras vänner. De klickar på länken och slutför sedan köpet.

I vissa rapporter kanske du vill ha den beställning som är kopplad till betald sökning. I andra rapporter kanske du vill att ordern ska tillskrivas Social. Attribution låter dig styra den här aspekten av rapportering.

## Ange en komponents standardattribueringsmodell

Du kan ange en standardattribueringsmodell för ett givet mätresultat genom att uppdatera måttets inställning i datavyn. Om du gör det åsidosätts måttets attribueringsmodell när som helst när den används i Analysis Workspace.

>[!NOTE]
>
>Tänk på följande när du aktiverar attribuering för ett mätvärde:
>
>* **När komponenten används i en rapport med *en enda dimension*:** Komponentens attribuering ignorerar allokeringsmodellen när en icke-standardattribueringsmodell används.
>
>* **När komponenten används i en rapport med *flera dimensioner*:** Komponentens attribuering behåller allokeringsmodellen när en icke-standardattribueringsmodell används.
>
>   Flera dimensioner är bara tillgängliga när [exporterar data till molnet](/help/analysis-workspace/export/export-cloud.md).
>
> Mer information om allokering finns i [Inställningar för Persistence-komponent](/help/data-views/component-settings/persistence.md).

Så här uppdaterar du en komponents standardattribueringsmodell:

1. Gå till datavyn som innehåller komponenten vars standardattribueringsmodell du vill uppdatera.

1. Markera komponenten och expandera sedan avsnittet Attribution till höger på skärmen.

   ![Fönstret Datavyer där attributalternativet Ange markeras ](../assets/attribution-settings.png)

1. Välj [!UICONTROL **Ange attribuering**] och välj sedan attribueringsmodell i listrutan [!UICONTROL **Attributmodell**].

   Se [Attribution models](#attribution-models) om du vill veta mer om de olika attribueringsmodellerna.

1. Välj [!UICONTROL **Spara och fortsätt**].

>[!TIP]
>
>Om din organisation kräver att ett mätresultat har flera attribueringsinställningar kan du göra något av följande:
>
> * Kopiera måtten i datavyn med varje önskad attribueringsinställning. Du kan inkludera samma mätvärde flera gånger i en datavy och ge varje mätvärde en egen inställning. Se till att du märker varje mätvärde på rätt sätt så att analytikerna förstår skillnaden mellan dessa mätvärden när de skapar rapporter.
>
> * Åsidosätt måttet i Analysis Workspace. I måttets [kolumninställningar](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) väljer du **[!UICONTROL Use non-default attribution model]** om du vill ändra måttets attribueringsmodell och uppslagsfönster för den specifika rapporten.

## Attributionsmodeller

En attribueringsmodell avgör vilka dimensionsobjekt som får kredit för ett mätresultat när flera värden visas i en metrisk sökningsfönster. Attributionsmodeller används bara när det finns flera dimensionsobjekt angivna i uppslagsfönstret. Om bara en enda dimensionsobjekt anges får den dimensionsobjektet 100 % kredit oavsett vilken attribueringsmodell som används.

| Ikon | Attributionsmodell | Definition |
| :---: | :--- | --- |
| ![Senaste beröring](../assets/attribution-models/last_touch1.png) | Senaste beröring | Ger 100 % uppskattning av den beröringspunkt som inträffade senast före konverteringen. Den här attribueringsmodellen är vanligtvis standardvärdet för alla mätvärden där ingen attributmodell har angetts på annat sätt. Organisationer använder vanligtvis den här modellen där tiden för konvertering är ganska kort, till exempel när interna söknyckelord analyseras. |
| ![Första beröring](../assets/attribution-models/first_touch.png) | Första beröring | Ger 100 % kredit till den beröringspunkt som först ses i attribueringssökningsfönstret. Organisationer använder vanligtvis den här modellen för att förstå varumärkesmedvetenhet och kundvärvning. |
| ![Linjär](../assets/attribution-models/linear.png) | Linjär | Ger samma beröm till alla kontaktytor som leder till konvertering. Det är användbart när konverteringscyklerna är längre eller kräver mer frekvent kundengagemang. Organisationer använder vanligtvis den här attribueringsmodellen för att mäta hur effektiva mobilappsaviseringar är eller med prenumerationsbaserade produkter. |
| ![Deltagande](../assets/attribution-models/participation.png) | deltagande | Alla unika kontaktpunkter får 100 % beröm. Eftersom varje beröringspunkt får 100 % rabatt läggs måttdata vanligtvis till mer än 100 %. Om en dimensionspost visas flera gånger som leder till en konvertering, dupliceras värdena till 100 %. Den här attribueringsmodellen är perfekt i situationer där du vill förstå vilka kontaktpunkter kunderna exponeras mest för. Medieorganisationer använder vanligtvis den här modellen för att beräkna innehållets hastighet. Butiksorganisationer använder vanligtvis den här modellen för att förstå vilka delar av deras sajt som är avgörande för konverteringen. |
| ![Samma beröring](../assets/attribution-models/same_touch.png) | Samma beröring | Ger 100 % kredit till samma händelse som konverteringen inträffade. Om en beröringspunkt inte inträffar för samma händelse som en konvertering, blockeras den under Ingen. Den här attribueringsmodellen är ibland lika med att inte ha någon attribueringsmodell alls. Det är värdefullt i scenarier där du inte vill ha värden från andra händelser som påverkar hur ett mätvärde ger kredit till dimensionsobjekt. Produkt- eller designteam kan använda den här modellen för att utvärdera hur effektiv en sida är där konverteringen sker. |
| ![U-form](../assets/attribution-models/u_shaped.png) | U Shaped | Ger 40 % uppskattning av den första interaktionen, 40 % tack vare den sista interaktionen och delar de återstående 20 % på alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får båda 50 % rabatt. Den här attribueringsmodellen används bäst i scenarier där du värdesätter den första och den sista interaktionen mest, men inte helt vill avvisa ytterligare interaktioner däremellan. |
| ![J-kurva](../assets/attribution-models/j_shaped.png) | J-kurva | Ger 60 % kreativitet till den senaste interaktionen, 20 % tack till den första interaktionen och delar de återstående 20 % på alla kontaktpunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får 75 % poäng för den senaste interaktionen och 25 % kredit ges till den första. I likhet med U-Shaped är den här attribueringsmodellen att föredra den första och sista interaktionen, men den är mer prioriterad än den sista interaktionen. |
| ![Omvänd J](../assets/attribution-models/inverse_j.png) | Inverterad J | Ger 60 % kredit till den första beröringspunkten, 20 % kredit till den sista beröringspunkten och delar de återstående 20 % till alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får 75 % kredit för den första interaktionen och 25 % kredit för den sista. I likhet med J-Shaped prioriterar den här attribueringsmodellen den första och sista interaktionen, men prioriterar den första interaktionen mer. |
| ![Tidsminskning](../assets/attribution-models/time_decay.png) | Tidsminskning | Följer en exponentiell minskning med en anpassad halveringsparameter, där standardvärdet är 7 dagar. Vikten för varje kanal beror på hur lång tid det tar mellan öppnandet av kontaktpunkten och den slutliga konverteringen. Formeln som används för att bestämma kredit är `2^(-t/halflife)`, där `t` är tiden mellan en kontaktpunkt och en konvertering. Alla beröringspunkter normaliseras sedan till 100 %. Perfekt för scenarier där du vill mäta attribuering mot en specifik och viktig händelse. Ju längre en konvertering sker efter den här händelsen, desto mindre kredit ges. |
| ![Anpassat](../assets/attribution-models/custom.png) | Anpassad | Gör att du kan ange de vikter du vill ge den första beröringspunkten, den sista beröringspunkten och eventuella mellanliggande beröringspunkter. De angivna värdena normaliseras till 100 % även om de anpassade siffrorna inte läggs till i 100. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För interaktioner med två beröringspunkter ignoreras parametern middle. Den första och sista beröringspunkten normaliseras sedan till 100 % och krediteringen tilldelas därefter. Den här modellen är idealisk för analytiker som vill ha fullständig kontroll över sin attribueringsmodell och har särskilda behov som andra attribueringsmodeller inte uppfyller. |
| ![Algoritmisk](../assets/attribution-models/algorithmic.png) | Algoritmisk | Använder statistiska tekniker för att dynamiskt fastställa den optimala kreditfördelningen för det valda måttet. Den algoritm som används för attribuering bygger på Harsanyi Dividend från kooperativ spelteori. Harsanyi-utdelningen är en generalisering av Shapley-värdelösningen (som uppges efter Lloyd Shapley, en Nobel Laureate-ekonom) för att distribuera krediter bland spelarna i ett spel med olika bidrag till resultatet.<br>Vid en hög nivå beräknas attribueringen som en koalition av spelare till vilka ett överskott måste fördelas jämnt. Varje koalitions överskottsfördelning bestäms utifrån det överskott som tidigare skapades genom varje delkoalition (eller tidigare deltagande dimensionsposter) rekursivt. Mer information finns i John Harsanyis och Lloyd Shapley&#39;s original papers:<br>Shapley, Lloyd S. (1953). Ett värde för personliga spel. *Bidrag till spelets teori, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). En förenklad förhandlingsmodell för det personliga kooperativa spelet. *Internationell ekonomisk granskning 4(2)*, 194-220. |

{style="table-layout:auto"}

## Fönstret Lookback

Ett uppslagsfönster är den tid som en konvertering bör titta tillbaka för att inkludera beröringspunkter. Om ett dimensionsobjekt anges utanför uppslagsfönstret inkluderas inte värdet i någon attribueringsberäkning.

* **14 dagar**: Kan synkroniseras upp till 14 dagar från när konverteringen gjordes.
* **30 dagar**: Kan synkroniseras upp till 30 dagar från när konverteringen gjordes.
* **60 dagar**: Kan synkroniseras upp till 60 dagar från när konverteringen gjordes.
* **90 dagar**: Återställer upp till 90 dagar från när konverteringen inträffade.
* **Session**: Går tillbaka till början av sessionen där en konvertering inträffade. Sessionssökningsfönster respekterar den ändrade [Sessionstimeout](../create-dataview.md#session-settings).
* **Person (rapporteringsfönster)**: Alla besök kontrolleras fram till den första i månaden i det aktuella datumintervallet. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för personsökning 1 september - 30 september. Om du använder det här uppslagsfönstret kan du ibland se att dimensionsobjekt tilldelas till datum utanför rapportfönstret.
* **Anpassad tid:** Används för att ange ett anpassat uppslagsfönster från när en konvertering inträffade. Du kan ange antalet minuter, timmar, dagar, veckor, månader eller kvartal. Om en konvertering till exempel skedde den 20 februari skulle ett uppslagsfönster på fem dagar utvärdera alla dimensionskontaktytor från den 15 februari till den 20 februari i attribueringsmodellen.

## Exempel

Titta på följande exempel:

1. Den 15 september kommer en person till er webbplats via en betald sökannons, sedan går han/hon iväg.
2. Den 18 september kommer personen till er webbplats igen via en länk för sociala medier som de fått från en vän. De lägger till flera artiklar i kundvagnen, men köper ingenting.
3. Den 24 september skickar marknadsföringsteamet ett e-postmeddelande med en kupong för några av artiklarna i kundvagnen. De använder kupongen, men besöker flera andra sajter för att se om det finns några andra kuponger. De hittar en till genom en displayannons och gör sedan ett köp för 50 dollar.

Beroende på ditt uppslagsfönster och din attribueringsmodell får kanalerna olika krediter. Nedan följer några bra exempel:

* Med **första beröring** och ett **sessionsfönster** tittar attribueringen bara på det tredje besöket. Mellan e-post och visning var e-post först, så e-post får 100 % rabatt på 50 USD.
* Attribution söker efter alla tre besök med **första beröring** och ett **fönster för personsökning**. Betalsökning var först, så den får 100 % rabatt på 50 USD.
* Med **linjär** och ett **sessionsfönster** delas krediteringen mellan e-post och visning. Båda dessa kanaler får 25 krediter.
* Med **linjär** och ett **personsökningsfönster** delas krediten in i betalsökning, sociala medier, e-post och visning. Varje kanal får 12,50 dollar i rabatt för detta inköp.
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
