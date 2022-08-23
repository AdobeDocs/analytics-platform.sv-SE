---
source-git-commit: 99b190e1afe7068d11fd9d53c5be72008958a9c2
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---
# Introduktion till statistisk metod i CJA:s expertpanel

I den här artikeln beskrivs de statistiska beräkningar som används av panelen Experimentation i CJA. CJA använder avancerade statistiska metoder för att beräkna **tilltro** som är giltigt när som helst, så att du kan köra dina experiment så länge du vill och övervaka resultatet kontinuerligt.

Den här artikeln beskriver hur A/B-tester fungerar och ger en intuitiv introduktion till Adobe ***Valfri tidsgiltig konfidenssekvens***. För expertanvändare inkluderas de tekniska detaljerna och referenserna i slutet.

## A/B-tester och orsakssamband

A/B-tester beskrivs ofta som en&quot;guldstandard&quot; för att utvärdera orsakssambandet hos någon typ av&quot;intervention&quot;. De är randomiserade testversioner, vilket i samband med onlinetestning innebär att vissa slumpmässigt utvalda användare exponeras för en viss variant av en webbplats, ett meddelande eller ett e-postmeddelande och en annan slumpmässigt utvald uppsättning användare för andra **variant** eller **behandling**. Efter exponering mäter vi sedan resultatet **mått** vi är intresserade av (t.ex. öppningar av e-post, prenumerationer eller inköp).

Som framgår av bilden nedan innebär det faktum att vi slumpmässigt tilldelade användare till varje variantgrupp att grupperna i genomsnitt har samma egenskaper. Alla skillnader i utfall kan alltså tolkas som att de beror på skillnader i de varianter som tas emot, dvs. vi kan fastställa en **orsakssamband** sambandet mellan våra insatser och de resultat vi är intresserade av. På så sätt kan ni fatta noggranna, förklarliga och datadrivna beslut för att optimera era era affärsmål, och A/B-tester är en grundläggande del av verktygslådan för alla moderna personaliseringsföretag.

<p style="text-align:center;"><img width="75%" src="img/causal-inference-cartoon.png" alt="kausal-inf"></p>


En viktig fråga är nu om observerade skillnader är &quot;verkliga effekter&quot; eller uppstår på grund av slumpmässighet. Intuitivt, om det bara finns en liten skillnad i resultatmåtten mellan grupper, skulle detta kunna ha observerats av en slump, medan större skillnader oftare är &quot;reella&quot;. Tekniktermen här är att våra mätningar är *uppskattningar* av de verkliga värdena för medelvärdet för varje variantgrupp. Statistisk härledning ger oss sätt att kvantifiera mängden osäkerhet i våra uppskattningar - det är här koncepten till **p-värden** och **Konfidensintervall** uppstår, men för att förstå detta bör vi först förstå statistiska fel.

## Statistisk testning och kontroll av fel

Många statistiska undersökningsmetoder är utformade för att kontrollera två typer av fel: **Falska positiva** (Type-I-fel) och **Falska negativ** (typ II-fel). Dessa illustreras i tabellen nedan.


<p style="text-align:center;"><img width="50%" src="img/contingency_table_stats_errors.png" alt="ContingencyTable"></p>


Falskt positivt är ett felaktigt avvisande av nollhypotesen, när det faktiskt är sant. När det gäller A/B-tester online innebär detta att vi (falskt) drar slutsatsen att affärsresultatet är annorlunda mellan olika armar, när det i själva verket var samma. Innan vi genomför experimentet väljer vi vanligtvis ett tröskelvärde *α*. När experimentet är klart *p*-value beräknas och vi avvisar null om *p &lt; α*. En vanlig tröskel är *α*= 0,05, vilket betyder att vi i längden förväntar oss att 5 av 100 experiment ska vara falska positiva.

Under tiden betyder False Negative att vi inte kan avvisa nollhypotesen när den i själva verket är falsk. För A/B-tester innebär detta att vi inte avvisar nollhypotesen (minns ni att nollhypotesen anger att affärsresultatet är detsamma mellan olika armar), när det faktiskt är annorlunda. För att kontrollera den här typen av fel måste vi i allmänhet ha tillräckligt många användare i vårt experiment för att garantera en viss **Strömförsörjning**, definierad som 1-*β* (dvs. ett minus sannolikheten för ett typ II-fel).

De flesta statistiska startmetoder kräver att du korrigerar provstorleken i förväg, baserat på den effektstorlek som du vill bestämma samt feltolerans (*α* och *β*) i förväg. Adobe metod är dock utformad för att du kontinuerligt ska kunna titta på dina resultat, oavsett provstorlek.



## Adobe Statistisk metod: _Sekvenser för alltid giltiga förtroenden_

Adobe har antagit en statistisk metod som bygger på [_Sekvenser för alltid giltiga förtroenden_](https://doi.org/10.48550/arXiv.2103.06476).

En konfidenssekvens är en sekventiell analog till ett konfidensintervall. För att förstå vad en konfidenssekvens är kan du föreställa dig att du upprepar dina experiment hundra gånger och beräknar en uppskattning av medelvärdet för affärsmätningen (t.ex. öppningsfrekvensen för ett e-postmeddelande) och dess associerade 95-procentiga konfidenssekvens för *alla nya användare* som kommer in i experimentet. En 95-procentig konfidenssekvens kommer att innehålla det &quot;sanna&quot; värdet för affärsmåttet i 95 av de 100 experiment som du utförde. (Ett 95-procentigt konfidensintervall kunde endast beräknas en gång per experiment för att ge samma 95-procentiga garanti. inte med alla nya användare). Med Confidence Sequences kan du därför kontinuerligt övervaka experiment utan att öka andelen falskt positiva fel, dvs. de tillåter&quot;sökning&quot; vid resultat.

Skillnaden mellan konfidenssekvenser och konfidensintervall för ett enskilt experiment visas i animeringen nedan:

<p style="text-align:center;"><img width="75%" src="img/confidence-sequence-evolution-comparison.gif" alt="CSGIF"></p>


Vi noterar att konfidenssekvenser flyttar fokus på A/B-tester till *uppskattning* snarare än att testa hypoteser, dvs. att fokusera på en korrekt uppskattning av skillnaden i medel mellan behandlingar, i stället för att avvisa en nollhypotes som baseras på ett tröskelvärde för statistisk signifikans.

På liknande sätt som för relationen mellan $p$-värden (eller konfidensintervall) och konfidensintervall finns det dock även en relation mellan konfidenssekvenser och varje gång giltiga $p$-värden (eller när som helst giltig konfidensnivå). Med tanke på hur välkända kvantiteter är, som Konfidensen, tillhandahåller CJA alltid giltighetsdata i sina rapporter.

Den teoretiska grunden för Confidence Sequences kommer från studien av sekvenser av slumpmässiga variabler som kallas martingales. Nedan finns några viktiga resultat för expertläsare, men teknikerna är tydliga:


> Konfidenssekvenser kan tolkas som &quot;säkra&quot; sekventiella analoger med konfidensintervall: kan du när som helst titta på och tolka data i A/B-testet och på ett säkert sätt stoppa eller fortsätta experimentera. Motsvarande Anytime Valid Confidence (eller *p*-value) är också säkert att tolka.

Det är viktigt att notera att eftersom den statistiska metoden är&quot;när som helst giltig&quot; kommer den att vara mer försiktig än en metod med en fast horisont som tillämpas med samma urvalsstorlek. Det innebär att&quot;när som helst giltig&quot; *p*-värden är i allmänhet större än motsvarande fasta horisont *p*-values (d.v.s. när giltig konfidensgrad är mindre)

## Tolka resultaten

1. **Experiment är slutprodukt**: Varje gång du tittar på experimentrapporten analyserar Adobe de data som har samlats in i experimentet fram till den här tidpunkten och deklarerar ett experiment som&quot;slutgiltigt&quot; när ett giltigt konfidensintervall överskrider ett tröskelvärde på 95 % för *minst en* av varianterna (med en Bonferonni-korrigering tillämpad när det finns mer än två armar, för att korrigera för multipla hypotesstester).

2. **Best Performance Variant**: När ett försök har förklarats vara avgörande betecknas varianten med den högsta konverteringsgraden som&quot;varianten med bästa resultat&quot;. Observera att denna variant antingen måste vara kontrollvarianten eller baslinjevarianten, eller en av varianterna som korsar det 95% som gäller vid varje tidpunkt (när Bonferonni korrigerar).

3. **Konverteringsgrad**: Den konverteringsgrad som visas är ett förhållande mellan framgångsmåttet och det normaliserande måttvärdet. Observera att detta ibland kan vara större än 1 om mätvärdet inte är binärt (1 eller 0 för varje enhet i experimentet)

4. **Lyft**: Sammanfattningen av expertrapporten visar Lyft över baslinjen, som är ett mått på den procentuella förbättringen av konverteringsgraden för en given variant över baslinjen. Definierat exakt är det skillnaden i prestanda mellan en given variant och baslinjen, dividerat med baslinjens prestanda, uttryckt i procent.

5. **Förtroende**: Den Anytime Valid Confidence som visas är ett sannolikhetsmått på hur mycket det finns bevis för att en viss variant är densamma som kontrollvarianten. Ett högre förtroende tyder inte på att kontrollvarianten och icke-kontrollvarianten har samma prestanda. Mer exakt är den säkerhet som visas en sannolikhet (uttryckt i procent) att vi skulle ha observerat en mindre skillnad i konverteringsgraden mellan en viss variant och kontrollen, om det i själva verket inte finns någon skillnad i den verkliga underliggande konverteringsgraden. När det gäller *p*-values, the trust displayed is 1 - *p*-value.

Observera dock att en fullständig beskrivning av resultaten bör beakta alla tillgängliga bevis (dvs. experimentutformning, provstorlekar, konverteringsgrader, konfidensgrad osv.), och inte bara deklarationen av huruvida det är slutgiltigt eller inte. Även om ett resultat ännu inte är &quot;entydigt&quot; kan det fortfarande finnas övertygande bevis för att en variant skiljer sig från en annan (t.ex. att konfidensintervallen nästan inte överlappar varandra). I idealfallet bör beslutsfattandet kompletteras med all statistik, tolkad på ett kontinuerligt spektrum.
