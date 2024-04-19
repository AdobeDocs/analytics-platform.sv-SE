---
description: Lär dig hur du kan analysera resultaten av A/B-tester på panelen Experimentation i Customer Journey Analytics.
title: Panelen Experimentation
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 68289e274c8ea985b6d07bca228f5e6654e05aa4
workflow-type: tm+mt
source-wordcount: '1842'
ht-degree: 0%

---

# Panelen Experimentation

The **[!UICONTROL Experimentation]** kan analytiker jämföra olika varianter av användarupplevelser, marknadsföring och meddelanden för att avgöra vilket som är bäst för att uppnå ett visst resultat. Ni kan utvärdera lyften och förtroendet för alla A/B-experiment från vilken experimentplattform som helst - online, offline, från Adobe-lösningar, Adobe Journey Optimizer och till och med från BYO (ta fram egna)-data.

Läs mer om [integrering mellan Adobe Customer Journey Analytics och Adobe Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja4t/cja4t).

## Åtkomstkontroll {#access}

Experimentationspanelen kan användas av alla Customer Journey Analytics-användare. Inga administratörsrättigheter eller andra behörigheter krävs. Installationen (steg 1 och 2 nedan) kräver åtgärder som bara administratörer kan utföra.

## Nya funktioner i Beräknade värden {#functions}

Två nya avancerade funktioner har lagts till: [!UICONTROL Lift] och [!UICONTROL Confidence]. Mer information finns i [Referens - avancerade funktioner](/help/components/calc-metrics/cm-adv-functions.md).

## Steg 1: Skapa en anslutning för att experimentera med datauppsättningar {#connection}

Det rekommenderade dataschemat är att experimentdata ska finnas i en [Objektarray](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/array.html) som innehåller experimentella data och variantdata i två olika dimensioner. Båda dimensionerna måste vara i ett **enkel** objektarray. Om du har experimenterat med data i en enda dimension med experiment- och variantdata i en avgränsad sträng kan du använda [delsträng](/help/data-views/component-settings/substring.md) ange i datavyer för att dela upp dem i två för användning på panelen.

Efter att dina experimentdata har [inkapslad](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html) till Adobe Experience Platform, [skapa en anslutning i Customer Journey Analytics](/help/connections/create-connection.md) till en eller flera experimentdata.

## Steg 2: Lägga till kontextetiketter i datavyer {#context-labels}

Administratörer kan lägga till datavyinställningar i Customer Journey Analytics [kontextetiketter](/help/data-views/component-settings/overview.md) till mått eller mätvärden och Customer Journey Analytics [!UICONTROL Experimentation] panelen kan använda dessa etiketter för sina ändamål. Två fördefinierade etiketter används för panelen Experimentation:

* [!UICONTROL Experimentation Experiment]
* [!UICONTROL Experimentation Variant]

I datavyn som innehåller experimentella data väljer du två dimensioner, en med experimentella data och en med variantdata. Ge sedan måtten etiketten med **[!UICONTROL Experiment]** och **[!UICONTROL Variant]** etiketter.

![Alternativ för sammanhangsetikett för Experimentation and Experimentation Variant.](assets/context-label.png)

Utan dessa etiketter fungerar inte Experimentpanelen eftersom det inte finns några experiment att arbeta med.

## Steg 3: Konfigurera panelen Experimentera {#configure}

1. Dra panelen Experimentation till ett projekt i arbetsytan Customer Journey Analytics.

![Experimenteringspanelen dras till ett projekt.](assets/experiment.png)

>[!IMPORTANT]
>Om de nödvändiga inställningarna i datavyer i Customer Journey Analytics inte har slutförts får du det här meddelandet innan du kan fortsätta: &quot;[!UICONTROL Please configure the experiment and variant dimensions in Data Views]&quot;.

1. Konfigurera panelens indatainställningar.

   | Inställning | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | En uppsättning variationer för en upplevelse som exponerats för slutanvändare för att avgöra vilken som är bäst att behålla för all framtid. Ett experiment består av två eller flera varianter, varav en betraktas som kontrollvariant. Den här inställningen är förifylld med de dimensioner som har märkts med  **[!UICONTROL Experiment]** i datavyer och de tre senaste månadernas experimentdata. |
   | **[!UICONTROL Control Variant]** | En av två eller flera förändringar i en slutanvändares upplevelse som jämförs i syfte att identifiera det bättre alternativet. En variant måste väljas som kontroll och endast en variant kan anses vara kontrollvariant. Den här inställningen är förifylld med de dimensioner som har märkts med  **[!UICONTROL Variant]** etikett i datavyer. Den här inställningen hämtar upp de variantdata som är associerade med det här experimentet. |
   | **[!UICONTROL Success Metrics]** | Mätvärden eller mätvärden som en användare jämför varianter med. Den variant som har det mest önskade resultatet för konverteringsmåttet (oavsett om det är högst eller lägst) deklareras som den&quot;bästa varianten&quot; i ett experiment. Du kan lägga till upp till 5 mätvärden. |
   | **[!UICONTROL Normalizing Metric]** | Grunden ([!UICONTROL People], [!UICONTROL Sessions], eller [!UICONTROL Events]) som testet ska köras på. Ett test kan t.ex. jämföra konverteringsgraden för flera variationer där **[!UICONTROL Conversion rate]** beräknas som **[!UICONTROL Conversions per session]** eller **[!UICONTROL Conversions per person]**. |
   | **[!UICONTROL Date Range]** | Datumintervallet anges automatiskt baserat på den första händelsen som togs emot i Customer Journey Analytics för det valda experimentet. Du kan begränsa eller utöka datumintervallet till en mer specifik tidsram om det behövs. |

1. Klicka på **[!UICONTROL Build]**.

## Steg 4: Visa panelutdata {#view}

Experimentationspanelen returnerar en mängd data och visualiseringar som hjälper dig att förstå hur dina experiment fungerar bättre. Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt. Du kan när som helst redigera panelen genom att klicka på redigeringspennan längst upp till höger.

Du får också en textsammanfattning som anger om experimentet är slutgiltigt eller inte och som sammanfattar resultatet. Slutsatsen baseras på statistisk signifikans. (Se Statistisk metod nedan.) Du kan se sammanfattningsnummer för den mest högpresterande varianten med högsta lyft och självförtroende.

För varje framgångsmått som du har valt visas en frihandstabell och en konverteringsgrad.

![Experimentationsresultatet visar en friformstabell och en konverteringsgrad.](assets/exp-output1.png)

The [!UICONTROL Line] diagrammet ger dig [!UICONTROL Control] kontra [!UICONTROL Control Variant] prestanda:

![Linjediagrammets utdata med kontrollen jämfört med kontrollvariantens prestanda.](assets/exp-output2.png)

>[!NOTE]
>
>Den här panelen stöder för närvarande inte analys av A/A-tester.

## Steg 5: Tolka resultaten {#interpret}

1. **Experiment är slutprodukt**: Varje gång du tittar på experimentrapporten analyserar Adobe de data som har samlats in fram till den här tidpunkten och deklarerar ett experiment som&quot;slutgiltigt&quot; när det giltiga förtroendet överskrider ett tröskelvärde på 95 % för *minst en* av varianterna (med en Benjamini-Hochberg-korrigering tillämpad när det finns mer än två armar, för att korrigera för multipla hypotestester).

2. **Best Performance Variant**: När ett experiment har förklarats vara slutgiltigt, benämns varianten med den högsta konverteringsgraden som&quot;varianten med bästa resultat&quot;. Observera att denna variant antingen måste vara kontroll- eller baslinjevarianten, eller en av varianterna som korsar det 95% som gäller vid varje tidpunkt (med korrigeringar av Benjamini-Hochberg tillämpade).

3. **Konverteringsgrad**: Den konverteringsgrad som visas är en kvot mellan det framgångsmått och det normaliserande måttvärdet. Observera att detta ibland kan vara större än 1 om mätvärdet inte är binärt (1 eller 0 för varje enhet i experimentet)

4. **Lyft**: Sammanfattningen av expertrapporten visar Lyft över baslinjen, som är ett mått på den procentuella förbättringen av konverteringsgraden för en viss variant över baslinjen. Definierat exakt är det skillnaden i prestanda mellan en given variant och baslinjen, dividerat med baslinjens prestanda, uttryckt i procent.

5. **Förtroende**: Den Anytime Valid Confidence som visas är ett sannolikhetsmått på hur mycket det finns bevis för att en viss variant är densamma som kontrollvarianten. Ett högre förtroende tyder inte på att kontrollvarianten och icke-kontrollvarianten har samma prestanda. Mer exakt är den säkerhet som visas en sannolikhet (uttryckt i procent) att vi skulle ha observerat en mindre skillnad i konverteringsgraden mellan en viss variant och kontrollen, om det i själva verket inte finns någon skillnad i den verkliga underliggande konverteringsgraden. När det gäller *p*-values, the trust displayed is 1 - *p*-value.

>[!NOTE]
>
>En fullständig beskrivning av resultaten bör beakta alla tillgängliga bevis (dvs. experimentdesign, provstorlekar, konverteringsgrader, konfidensgrad osv.), och inte bara försäkran om att resultatet är slutgiltigt eller inte. Även om ett resultat ännu inte är &quot;entydigt&quot; kan det fortfarande finnas övertygande bevis för att en variant skiljer sig från en annan (t.ex. att konfidensintervallen nästan inte överlappar varandra). I idealfallet bör beslutsfattandet kompletteras med all statistik, tolkad på ett kontinuerligt spektrum.

## Adobe statistisk metod {#statistics}

Adobe har antagit en statistisk metod som bygger på [Sekvenser för alltid giltiga förtroenden](https://doi.org/10.48550/arXiv.2103.06476).

En konfidenssekvens är en sekventiell analog till ett konfidensintervall. För att förstå vad en konfidenssekvens är kan du föreställa dig att du upprepar dina experiment hundra gånger och beräknar en uppskattning av medelvärdet för affärsmätningen (t.ex. öppningsfrekvensen för ett e-postmeddelande) och dess associerade 95 %-konfidenssekvens för *alla nya användare* som kommer in i experimentet.

En 95-procentig konfidenssekvens kommer att innehålla det &quot;sanna&quot; värdet för affärsmåttet i 95 av de 100 experiment som du utförde. (Ett 95-procentigt konfidensintervall kunde endast beräknas en gång per experiment för att ge samma 95-procentiga täckningsgaranti, inte för varje enskild ny användare). Med Confidence Sequences kan du därför kontinuerligt övervaka experiment utan att öka andelen falskt positiva fel, dvs. de tillåter&quot;sökning&quot; vid resultat.

## Tolka icke-slumpmässiga dimensioner {#non-randomized}

Med Customer Journey Analytics kan analytiker välja vilken dimension som helst som&quot;experiment&quot;. Men hur tolkar man en analys där den dimension som väljs som försöksprodukt inte är en som är slumpmässig?

Ta till exempel en annons som en person ser. Du kan vara intresserad av att mäta förändringen i vissa mätvärden (t.ex. genomsnittliga intäkter) om du bestämmer dig för att visa personer&quot;och B&quot; i stället för&quot;och A&quot;. Orsakseffekten av att visa annonser B i stället för annons A är av central betydelse för att fatta ett beslut om marknadsföring. Denna orsakseffekt kan mätas som de genomsnittliga intäkterna för hela befolkningen om vi ersatte status quo för att visa och A med den alternativa strategin att visa och B.

A/B-tester är den guldbaserade standarden inom branschen för att objektivt mäta effekterna av sådana ingrepp. Den kritiska orsaken till varför ett A/B-test ger upphov till en uppskattning av orsakssamband beror på slumpgenereringen av personer för att få en av de möjliga varianterna.

Tänk nu på en dimension som inte uppnås genom slumpgenerering, till exempel USA:s tillstånd för personen. Låt oss säga att våra personer främst kommer från två delstater, New York och Kalifornien. De genomsnittliga intäkterna från försäljningen av ett vinterklädmärke kan vara olika i de två delstaterna på grund av skillnaderna i det regionala vädret. I en sådan situation kan vädret vara den verkliga orsaken till försäljningen av kläder på vintern, och inte det faktum att personernas geografiska läge är olika.

Experimenteringspanelen i Customer Journey Analytics gör att du kan analysera data som genomsnittliga intäktsskillnader mellan personlägena. I en sådan situation har produktionen ingen orsaksmässig tolkning. En sådan analys kan dock fortfarande vara av intresse. Den ger en uppskattning (tillsammans med mått på osäkerhet) av skillnaden i de genomsnittliga intäkterna för delstaterna. Detta kallas även för &quot;Statistisk hypotestestning&quot;. Resultatet av denna analys kan vara intressant, men inte nödvändigtvis åtgärdbart, eftersom vi inte har gjort det och ibland inte kan göra någon slumpgenerering av personer till ett av de möjliga värdena i dimensionen.

Följande bild kontrasterar dessa situationer:

![Ett diagram som visar observationsdata och en slumpmässig studie.](assets/randomize.png)

När du vill mäta effekten av intervention X på resultatet Y, är det möjligt att den verkliga orsaken till båda är den förvirrande faktorn C. Om data inte uppnås genom slumpgenerering av personer på X, är effekten svårare att mäta, och analysen kommer uttryckligen att ta hänsyn till C. Slumpgenereringen bryter beroendet av X på C, vilket gör att vi kan mäta X:s effekt på Y utan att behöva oroa oss för andra variabler.

## Använda beräknade värden på panelen Experimentera

Läs det här blogginlägget för mer information om [använda härledda värden i panelen Experimentation](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
