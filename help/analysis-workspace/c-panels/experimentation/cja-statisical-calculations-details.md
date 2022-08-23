---
source-git-commit: c95e01a80f3f3ddcabfee171ee357a5cf9e81e53
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---
# Statistiska beräkningar i CJA:s expertpanel: Detaljer

På den här sidan visas detaljerade statistiska beräkningar som används i CJA:s Experimentation Panel. Det är avsett för tekniska användare.


## Konverteringsgrad

konverteringsgraden eller **medelvärde**, *μ<sub>ν</sub>* för varje variant *ν* i en expert definieras som förhållandet mellan summan av mätvärdet och antalet enheter som tilldelats mätvärdet, *N<sub>ν</sub>*:
<p style="text-align:center;"><img width="15%" src="img/mean_definition.png" alt="metrisk-medelvärde"></p>
Här,

- *Y<sub>iν</sub>* är värdet för måttet för varje enhet, *i*, som har tilldelats en viss variant *ν*.
- Summan över enheter *i* är beroende av valet av normalisering av mätvärden.
   - If *Folk* är normaliseringsmåtten, är varje enhet en unik person/profil.
   - If *Sessioner* är normaliseringsmåtten, är varje enhet en unik session.
   - If *Händelser* är normaliseringsmåtten, är varje enhet en unik händelse.

I allmänhet bör detta normaliseringsmått väljas så att det motsvarar din oberoende enhet, dvs. om beteendet hos en användare i en session är oberoende av deras beteende i en annan session, är sessionerna ett rimligt normaliseringsmått.

Vid behov används samplingens standardavvikelse, med uttrycket


<p style="text-align:center;"><img width="30%" src="img/stdev_definition.png" alt="metrisk-medelvärde"></p>


## Lyft

Lyften mellan en variant  *ν* och kontrollvarianten  *ν<sub>0</sub>* är relativ delta i konverteringsgrader, definierat som
<p style="text-align:center;"><img width="15%" src="img/lift_definition.png" alt="metrisk-medelvärde"></p>
där de enskilda konverteringssatserna är de som anges ovan.


## Konfidenssekvenser

Konfidenssekvensen för en enskild variant visas inte på CJA-panelen Experimentation *ν* är en central del i den statistiska metod som används av Adobe och definieras därför här (återges från [Waudiby-Smith et al.](https://doi.org/10.48550/arXiv.2103.06476)).

> Anta att någon är intresserad av att beräkna en målparameter *ψ* (som konverteringsgraden för en variant i en expert). Dichotomin mellan en sekvens med&quot;fasta&quot; konfidensintervall (CIs) och en tidsenhetlig konfidenssekvens (CS) kan sedan sammanfattas enligt följande:
<p style="text-align:center;"><img width="60%" src="img/ci_vs_cs.png" alt="metrisk-medelvärde"></p>

Med andra ord - för ett regelbundet konfidensintervall är sannolikhetsgarantin att målparametern ligger inom intervallet för värden *Ċ<sub>t</sub>* är endast giltigt till ett fast värde av *n* (där *n* är antalet prov). Omvänt för en tillförlitlig sekvens garanteras vi att alla värden i samplingsstorleken alltid/ *t*&#x200B;är &quot;true&quot;-värdet för parametern med intresse inom gränserna *<SPAN STYLE="text-decoration:overline">C</SPAN><sub>t</sub>*.

Detta har några viktiga konsekvenser som är mycket viktiga för onlinetestning:
- CS kan uppdateras när nya data blir tillgängliga.
- Experimenten kan övervakas kontinuerligt, stoppas eller fortsätta.
- Type-I-felet kontrolleras vid alla stopptider, inklusive databeroende tider.

Adobe använder asymptotisk konfidenssekvens, som för en enskild variant med medelskattning *μ* har formuläret

<p style="text-align:center;"><img width="45%" src="img/confidence_sequence_individual.png" alt="metrisk-medelvärde"></p>

Var:
- *N* är antalet enheter för varianten.
- *σ* är en uppskattning av standardavvikelsen (definierad tidigare).
- *α* är den önskade nivån av typ I-fel (eller sannolikhet för feltäckning).
- *ρ*<sup> 2</sup> är en konstant som justerar den samplingsstorlek där CS är tätast. Adobe har valt det universella värdet *ρ*<sup> 2</sup> = 10<sup>-2.8</sup>, vilket är lämpligt för de typer av konverteringsgrader som förekommer i online-experiment.


## Förtroende

Den konfidensgrad som används av Adobe är en&quot; alltid giltig&quot; konfidensgrad, som erhålls genom att invertera konfidenssekvensen för den genomsnittliga behandlingseffekten.

För att vara exakt noterar vi att i ett tvåprov *t* test för skillnaden i medelvärde mellan två varianter, det finns en 1:1-mappning mellan *p*-värde för detta test och konfidensintervallet för skillnaden i medel. I analogi med detta kan en *p*-värde kan erhållas genom att invertera (när som helst giltig) konfidenssekvensen för den genomsnittliga uppskattningen av behandlingseffekten:
<p style="text-align:center;"><img width="22%" src="img/ate_definition.png" alt="metrisk-medelvärde"></p>

Den uppskattade faktor som vi använder är en IPW-uppskattare. Överväg *N = N<sub>0</sub>* + *N<sub>1</sub>* enheter, varianttilldelningarna för varje enhet $i$ märkta med *A<sub>i</sub>=0,1* om enheten tilldelas variant ν=0,1. Om användarna har tilldelats en fast sannolikhet (benägenhet) *π<sub>0</sub>, (1-π<sub>0</sub>)*, och deras resultatmått är *Y<sub>i</sub>*&#x200B;är IPW-uppskattaren
<p style="text-align:center;"><img width="45%" src="img/ipw_definition.png" alt="metrisk-medelvärde"></p>

Observera att *f* är influensfunktionen, Waudiby-Smith et al. visade att tävlingssekvensen för den här uppskattaren är:
<p style="text-align:center;"><img width="55%" src="img/cs_ate_definition1.png" alt="metrisk-medelvärde"></p>

Ersätta sannolikhet för tilldelning med dess empiriska uppskattningar: *π<sub>0</sub> = N<sub>0</sub>/N* kan varianstermen uttryckas som medelvärden av enskilda stickprov.  *μ<sub>{0,1}</sub>* och uppskattningar av standardavvikelser,  *σ<sub>{0,1}</sub>* as:

<p style="text-align:center;"><img width="55%" src="img/cs_ate_var.png" alt="metrisk-medelvärde"></p>


Påminn om att för en regelbunden provning av en hypotes med provningsstatistik *z = (μ<sub>1</sub> - μ<sub>0</sub>)/σ<sub>p</sub>*, finns det en korrespondens mellan $p$-värden och konfidensintervall:

<p style="text-align:center;"><img width="55%" src="img/pvalue_ci_correspondence.png" alt="metrisk-medelvärde"></p>

där *Φ* är den kumulativa fördelningen av standardnormalvärdena. För alla tidpunkter *p*-värden, med tanke på konfidenssekvensen för den genomsnittliga behandlingseffekt som definieras ovan, kan vi invertera detta förhållande:
<p style="text-align:center;"><img width="75%" src="img/anytimevalid-pvalue.png" alt="metrisk-medelvärde"></p>

Slutligen **alltid giltig *tilltro*** är
<p style="text-align:center;"><img width="22%" src="img/anytimevalid-confidence.png" alt="metrisk-medelvärde"></p>


## Förklaring av en expert till slutsats

För en expert med två armar visas ett meddelande på panelen CJA Experimentation om att en Experiment är **slående** när ett giltigt konfidensintervall överstiger 95 % (dvs. när som helst giltigt *p*-value är under 5 %).

När det finns fler än två varianter tillämpas Bonferonni-korrigeringen. För ett experiment med *K* behandlingar och en enstaka baseline (kontrollbehandling) finns *K-1* oberoende hypotesstest. Korrigeringen av Bonferonni innebär att vi avvisar den nollhypotes som kontrollen och en given variant har samma medel, om *p*-value är under tröskelvärdet 0,05/(K-1).


## Högpresterande arm

När ett försök har förklarats slutgiltigt visas den arm som har bäst prestanda. Detta är armen med bästa prestanda (högsta medelvärde eller konverteringsgrad), bland uppsättningen som innehåller kontrollen och alla armar som har en *p*-värde som är under Bonferonni-tröskeln.