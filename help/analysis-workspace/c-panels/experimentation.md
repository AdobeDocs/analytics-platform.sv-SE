---
description: Lär dig hur du kan analysera resultaten av A/B-tester på panelen Experimentation i Customer Journey Analytics.
title: Panelen Experimentation
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: e0cf556a094726edbee35b21bf71d5d1f227fcc7
workflow-type: tm+mt
source-wordcount: '1838'
ht-degree: 0%

---

# Panelen Experimentation

The **[!UICONTROL Experimentation]** kan analytiker jämföra olika varianter av användarupplevelser, marknadsföring och meddelanden för att avgöra vilket som är bäst för att uppnå ett visst resultat. Ni kan utvärdera lyften och förtroendet för alla A/B-experiment från vilken experimentplattform som helst - online, offline, från Adobe-lösningar som Target eller Journey Optimizer, och till och med från BYO (hämta in dina egna) data.

Läs mer om [integrering mellan Adobe Customer Journey Analytics och Adobe Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja).

## Åtkomstkontroll {#access}

Experimentationspanelen kan användas av alla Customer Journey Analytics-användare. Inga administratörsrättigheter eller andra behörigheter krävs. Installationen (steg 1 och 2 nedan) kräver åtgärder som bara administratörer kan utföra.

## Nya funktioner i Beräknade värden {#functions}

Två nya avancerade funktioner har lagts till: [!UICONTROL Lift] och [!UICONTROL Confidence]. Mer information finns i [Referens - avancerade funktioner](/help/components/calc-metrics/cm-adv-functions.md).

## Steg 1: Skapa en anslutning för att experimentera med datauppsättningar {#connection}

Det rekommenderade dataschemat är att experimentdata ska finnas i en [Objektarray](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array) som innehåller experimentella data och variantdata i två olika dimensioner. Båda dimensionerna måste vara i ett **enkel** objektarray. Om du har experimenterat med data i en enda dimension (med experimentella data och variantdata i en avgränsad sträng) kan du använda [delsträng](/help/data-views/component-settings/substring.md) ställa in i datavyer för att dela dimensionen i två för användning i panelen.

Efter att dina experimentdata har [inkapslad](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) till Adobe Experience Platform, [skapa en anslutning i Customer Journey Analytics](/help/connections/create-connection.md) till en eller flera experimentdata.

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
>
>Om de nödvändiga inställningarna i datavyer i Customer Journey Analytics inte har slutförts får du följande meddelande innan du kan fortsätta: &quot;[!UICONTROL Please configure the experiment and variant dimensions in Data Views]&quot;.
>

1. Konfigurera panelens indatainställningar.

   | Inställning | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | En uppsättning variationer för en upplevelse som exponerats för slutanvändarna för att avgöra vilken som är bäst att behålla för all framtid. Ett experiment består av två eller flera varianter, varav en betraktas som kontrollvariant. Den här inställningen är förifylld med de dimensioner som har märkts med  **[!UICONTROL Experiment]** i datavyer och de tre senaste månadernas experimentdata. |
   | **[!UICONTROL Control Variant]** | En av två eller flera förändringar i en slutanvändares upplevelse som jämförs i syfte att identifiera det bättre alternativet. En variant måste väljas som kontroll och endast en variant kan anses vara kontrollvariant. Den här inställningen är förifylld med de dimensioner som har märkts med  **[!UICONTROL Variant]** etikett i datavyer. Den här inställningen hämtar upp de variantdata som är associerade med det här experimentet. |
   | **[!UICONTROL Success Metrics]** | Mätvärden eller mätvärden som en användare jämför varianter med. Den variant som har det mest önskade resultatet för konverteringsmåttet (oavsett om det är högst eller lägst) deklareras som den&quot;bästa varianten&quot; i ett experiment. Du kan lägga till upp till 5 mätvärden. |
   | **[!UICONTROL Normalizing Metric]** | Grunden ([!UICONTROL People], [!UICONTROL Sessions], eller [!UICONTROL Events]) som testet körs på. Ett test kan t.ex. jämföra konverteringsgraden för flera variationer där **[!UICONTROL Conversion rate]** beräknas som **[!UICONTROL Conversions per session]** eller **[!UICONTROL Conversions per person]**. |
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

1. **Experiment är slutprodukt**: Varje gång du tittar på experimentrapporten analyseras de data som har samlats in i experimentet fram till nu. Och deklarerar att ett experiment är &quot;klart&quot; när ett giltigt konfidensintervall korsar ett tröskelvärde på 95 % för *minst en* av varianterna (med en Benjamini-Hochberg-korrigering tillämpad när det finns mer än två armar, för att korrigera för multipla hypotestester).

2. **Best Performance Variant**: När ett experiment har förklarats vara slutgiltigt, benämns varianten med den högsta konverteringsgraden som&quot;varianten med bästa resultat&quot;. Observera att denna variant antingen måste vara kontroll- eller baslinjevarianten, eller en av varianterna som korsar det 95% som gäller vid varje tidpunkt (med korrigeringar av Benjamini-Hochberg tillämpade).

3. **Konverteringsgrad**: Den konverteringsgrad som visas är en proportion mellan det framgångsrika mätvärdet och det normaliserande mätvärdet. Observera att det här värdet ibland kan vara större än 1 om mätvärdet inte är binärt (1 eller 0 för varje enhet i experimentet)

4. **Lyft**: Sammanfattningen av expertrapporten visar Lyft över baslinjen, som är ett mått på den procentuella förbättringen av konverteringsgraden för en viss variant över baslinjen. Definierat exakt är det skillnaden i prestanda mellan en given variant och baslinjen, dividerat med baslinjens prestanda, uttryckt i procent.

5. **Förtroende**: Det givna förtroendet som visas är ett sannolikhetsmått på hur mycket det finns bevis för att en viss variant är densamma som kontrollvarianten. Ett högre förtroende tyder inte på att kontrollvarianten och icke-kontrollvarianten har samma prestanda. Mer exakt är den sannolikhet som visas (uttryckt i procent) att du skulle ha observerat en mindre skillnad i konverteringsgraden mellan en viss variant och kontrollen, om det i själva verket inte finns någon skillnad i den verkliga underliggande konverteringsgraden. När det gäller *p*-values, the trust displayed is 1 - *p*-value.

>[!NOTE]
>
>En fullständig beskrivning av resultaten bör omfatta alla tillgängliga bevis (t.ex. experimentdesign, provstorlekar, konverteringsgrader, förtroende med mera), och inte bara en förklaring om huruvida resultatet är slutgiltigt eller inte. Även om resultatet ännu inte är entydigt kan det fortfarande finnas övertygande bevis för att en variant skiljer sig från en annan (t.ex. att konfidensintervallen nästan inte överlappar varandra). Helst bör alla statistiska uppgifter, tolkade på ett kontinuerligt spektrum, vara beslutsunderlag.

## Adobe statistisk metod {#statistics}

Adobe har antagit en statistisk metod som bygger på [Sekvenser för alltid giltiga förtroenden](https://arxiv.org/abs/2103.06476).

En konfidenssekvens är *sekventiell* analog för ett konfidensintervall. För att förstå vad en konfidenssekvens är kan du föreställa dig att du upprepar dina experiment hundra gånger och beräknar en uppskattning av medelvärdet för affärsmätningen (t.ex. en öppen frekvens för ett e-postmeddelande) och dess associerade 95-procentiga konfidenssekvens för *alla nya användare* som kommer in i experimentet.

En 95-procentig konfidenssekvens innehåller det &quot;sanna&quot; värdet av företagsmätningen i 95 av de 100 experiment som du utförde. (Ett 95-procentigt konfidensintervall kunde endast beräknas en gång per experiment för att ge samma 95-procentiga täckningsgaranti, inte för varje enskild ny användare). Med hjälp av förtroendesekvenser kan du därför övervaka försök kontinuerligt, utan att öka antalet falska positiva fel, det vill säga de tillåter&quot;sökning&quot; vid resultat.

## Tolka icke-slumpmässiga dimensioner {#non-randomized}

Med Customer Journey Analytics kan analytiker välja vilken dimension som helst som&quot;experiment&quot;. Men hur tolkar man en analys där den dimension som väljs som försöksprodukt inte är en som är slumpmässig?

Ta till exempel en annons som en person ser. Du kan vara intresserad av att mäta förändringen i vissa mätvärden (till exempel medelintäkter) om du bestämmer dig för att visa personer&quot;och B&quot; i stället för&quot;och A&quot;. Orsakseffekten av att visa annonser B i stället för annons A är av central betydelse för att fatta ett beslut om marknadsföring. Denna orsakseffekt kan mätas som de genomsnittliga intäkterna för hela befolkningen, om ni ersatte status quo för att visa och A med den alternativa strategin att visa och B.

A/B-tester är den guldbaserade standarden inom branschen för att objektivt mäta effekterna av sådana ingrepp. Den kritiska orsaken till varför ett A/B-test ger upphov till en uppskattning av orsakssamband beror på slumpgenereringen av personer för att få en av de möjliga varianterna.

Tänk på en dimension som inte uppnås genom slumpgenerering, till exempel USA:s tillstånd för personen. Låt oss säga att personer främst kommer från två delstater, New York och Kalifornien. De genomsnittliga intäkterna från försäljningen av ett vinterklädmärke kan vara olika i de två delstaterna på grund av skillnaderna i det regionala vädret. I en sådan situation kan vädret vara den verkliga orsaken till försäljningen av kläder på vintern, och inte det faktum att personernas geografiska läge är olika.

Experimenteringspanelen i Customer Journey Analytics gör att du kan analysera data som genomsnittliga intäktsskillnader mellan personlägena. I en sådan situation har produktionen ingen orsaksmässig tolkning. En sådan analys kan dock fortfarande vara av intresse. Den ger en uppskattning (tillsammans med mått på osäkerhet) av skillnaden i de genomsnittliga intäkterna för delstaterna.  Detta värde kallas även för &quot;Statistisk hypotestestning&quot;. Resultatet av den här analysen kan vara intressant, men inte nödvändigtvis åtgärdbart, eftersom du inte har gjort det och ibland inte kan göra personer slumpmässiga till ett av dimensionens möjliga värden.

Följande bild kontrasterar dessa situationer:

![Ett diagram som visar observationsdata och en slumpmässig studie.](assets/randomize.png)

När du vill mäta effekten av intervention X på resultatet Y, är det möjligt att den verkliga orsaken till båda är den förvirrande faktorn C. Om data inte uppnås genom slumpgenerering av personer på X är effekten svårare att mäta, och analysen redogör uttryckligen för C. Slumpmässigt bryter X beroendet av C, vilket gör att vi kan mäta X:s effekt på Y utan att behöva oroa oss för andra variabler.

## Använda beräknade värden på panelen Experimentera

Läs det här blogginlägget för mer information om [använda härledda värden i panelen Experimentation](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
