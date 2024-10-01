---
description: Med funktioner kan du filtrera/sortera data och göra statistiska analyser.
title: Använd funktioner
feature: Calculated Metrics
exl-id: 7a41aa4e-90c6-4242-a801-2eef6b524cfe
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '4050'
ht-degree: 1%

---

# Använd funktioner

Med funktionerna kan du filtrera, sortera data och göra enkla och komplexa statistiska analyser.

En lista över alla funktioner finns i [Grundläggande funktioner](/help/components/calc-metrics/cm-functions.md) och [Avancerade funktioner](/help/components/calc-metrics/cm-adv-functions.md).


>[!NOTE]
>
>Där [!DNL metric] identifieras som ett argument i en funktion tillåts även andra uttryck för mätvärden. [!DNL MAXV(metrics)] tillåter till exempel även [!DNL MAXV(PageViews + Visits).]
>

>[!NOTE]
>
>När du inkluderar funktioner i Definitionen av verktyget för beräknade värden ska du alltid använda funktionen innan du drar i mått eller filter.
>

## Tabellfunktioner kontra radfunktioner

En tabellfunktion är en funktion där utdata är desamma för alla rader i tabellen. En radfunktion är en funktion där utdata är olika för alla rader i tabellen.

## Vad betyder parametern Include-Zeros?

Den anger om nollor ska inkluderas i beräkningen. Ibland betyder noll&quot;ingenting&quot;, men ibland är det viktigt.

Om du till exempel har ett intäktsmått och sedan lägger till ett sidvymått i rapporten finns det plötsligt fler rader för dina intäkter som alla är noll. Du vill antagligen inte att detta ska påverka MEAN, MIN, QUARTILE osv. beräkningar som du har i intäktskolumnen. I det här fallet kontrollerar du parametern include-zeros.

Å andra sidan, om du har två mätvärden som du är intresserad av, kan det vara svårt att säga att en har ett högre genomsnitt eller ett lägre värde, eftersom vissa av raderna var nollor, så du skulle inte kontrollera parametern så att den inkluderar nollorna.

<!-- This video is way too outdated and too much AA oriented to comfortably show as part of CJA functionality 

Watch this [video](https://youtu.be/SSyWvomnewI) to understand the use of functions.

-->

+++ Grundfunktioner


## Absolut värde (rad)

Returnerar det absoluta värdet av ett tal. Det absoluta värdet för ett tal är talet med ett positivt värde.

```
ABS(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det mått som du vill ha det absoluta värdet för. |

## Högsta kolumn

Returnerar det största värdet i en uppsättning dimensionselement för en måttkolumn. MAXV utvärderas lodrätt i en enda kolumn (mått) över dimensionselement.

```
MAXV(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Ett mått som du skulle vilja ha utvärderat. |

## Minsta kolumn

Returnerar det minsta värdet i en uppsättning dimensionselement för en måttkolumn. MINV utvärderas lodrätt i en enda kolumn (mått) över dimensionselement.

```
MINV(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Ett mått som du skulle vilja ha utvärderat. |

## Kolumnsumma

Lägger till alla numeriska värden för ett mått i en kolumn (över elementen i en dimension).

```
SUM(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det mått som du vill ha det totala värdet eller summan för. |

## Antal (tabell)

Returnerar antalet, eller antalet, värden som inte är noll för ett mätvärde i en kolumn (antalet unika element som rapporteras inom en dimension).

```
COUNT(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det mått som du vill räkna. |

## Exponent (rad)

Returnerar *e* upphöjt till ett angivet tal. Konstanten *e* är lika med 2.71828182845904, basen för den naturliga logaritmen. EXP är den inverterade LN, den naturliga logaritmen av ett tal.

```
EXP(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Exponenten som används på basen *e*. |

## Exponentiering

Strömoperator


pow(x,y) = x<sup>y</sup> = x *x* x*... (y gånger)


## Medel (tabell)

Returnerar det aritmetiska medelvärdet, eller medelvärdet, för ett mått i en kolumn.

```
MEAN(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det mätvärde som du vill ha medelvärdet för. |

## Median (tabell)

Returnerar medianvärdet för ett mått i en kolumn. Medianvärdet är talet i mitten av en uppsättning tal, det vill säga hälften av talen har värden som är större än eller lika med medianvärdet och hälften är mindre än eller lika med medianvärdet.

```
MEDIAN(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det mätvärde som du vill ha medianen för. |

## Modulo

Resten av col1 / col2, med division Euclidean.

Returnerar resten efter att x delats med y.

```
x = floor(x/y) + modulo(x,y)
```

Returvärdet har samma tecken som indata (eller är noll).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Använd om du alltid vill få ett positivt tal

```
modulo(modulo(x,y)+y,y)
```

## Procent (tabell)

Returnerar den n:te percentilen av värden för ett mätvärde. Du kan använda den här funktionen för att fastställa ett tröskelvärde för godkännande. Du kan t.ex. bestämma att undersöka dimensionselement som får en poäng över 90-percentilen.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metrisk</i> </td> 
   <td colname="col2"> Den måttkolumn som definierar relativ position. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> Procentvärdet i intervallet 0 till 100. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (tabell)

Returnerar kvartilen med värden för ett mått. Du kan till exempel använda kvartilarna för att hitta de 25 % av de bästa produkterna som genererar störst intäkter. MINV, MEDIAN och MAXV returnerar samma värde som QUARTILE när quart är lika med 0 (noll), 2 respektive 4.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metrisk</i> </td> 
   <td colname="col2"> Måttet som du vill ha kvartilsvärdet för. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Anger vilket *värde som ska returneras. </td> 
  </tr> 
 </tbody> 
</table>

&#42;Om *quart* = 0 returnerar QUARTILE minimivärdet. Om *quart* = 1 returnerar QUARTILE den första kvartilen (25 percentiler). Om *quart* = 2 returnerar QUARTILE den första kvartilen (50 percentiler). Om *quart* = 3 returnerar QUARTILE den första kvartilen (75 percentiler). Om *quart* = 4 returnerar QUARTILE det maximala värdet.

## Ansökningstillfälle

Returnerar närmaste heltal för ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har 569,34 USD, använder du formeln Round( *Revenue*) för att avrunda intäkten till närmaste dollar, eller 569 dollar. En produkt som rapporterar 569,51 USD avrundas till närmaste dollar, eller 570 USD.

```
ROUND(metric)
```

| Argument | Beskrivning |
|---|---|
| *number* | Det mätvärde som du vill runda av. |

Round without a digits parameter is the same as round with a digits parameter of 0, DVS. round to the leading integer. Med en sifferparameter returneras så många siffror till höger om decimaltecknet. Om siffrorna är negativa returneras 0 till vänster om decimaltecknet.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Antal rader

Returnerar antalet rader för en given kolumn (antalet unika element som rapporteras inom en dimension). &quot;Uniques beyond&quot; räknas som 1.

## Max rad

Det maximala antalet kolumner i varje rad.

## Min rad

Minimivärdet för kolumnerna i varje rad.

## Radsumma

Summan av kolumnerna på varje rad.

## Kvadratrot (rad)

Returnerar den positiva kvadratroten av ett tal. Kvadratroten av ett tal är värdet av talet upphöjt till 1/2.

```
SQRT(metric)
```

| Argument | Beskrivning |
|---|---|
| *number* | Måttet som du vill ha kvadratroten för. |

## Standardavvikelse (tabell)

Returnerar standardavvikelsen, eller kvadratroten av variansen, baserat på en exempelpopulation med data.

Ekvationen för STDEV är:

![](../assets/std_dev.png)

där x är samplingsmedelvärdet (*metric*) och *n* är samplingsstorleken.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> argument </b> </td> 
   <td> <b> Beskrivning</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metrisk </i> </b> </td> 
   <td> <p> Det mått som du vill använda för standardavvikelsen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varians (tabell)

Returnerar variansen baserat på en exempelpopulation med data.

Ekvationen för VARIANS är:

![](../assets/variance_eq.png)

där x är samplingsmedelvärdet, MEAN(*metric*) och *n* är samplingsstorleken.

```
VARIANCE(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det mått som du vill ha variansen för. |

För att kunna beräkna en varians tittar du på en hel sifferkolumn. Från den listan med tal beräknar du först medelvärdet. När du har fått medelvärdet går du igenom varje tävlingsbidrag och gör följande:

1. Subtrahera medelvärdet från talet.

2. Fyrkantiga resultatet.

3. Lägg till det till summan.

När du har itererat över hela kolumnen får du en totalsumma. Sedan dividerar du summan med antalet objekt i kolumnen. Talet är variansen för kolumnen. Det är ett enda tal. Den visas dock som en kolumn med siffror.

Om det är en kolumn med tre objekt:

1

2

3

Medelvärdet för den här kolumnen är 2. Variansen för kolumnen är ((1 - 2)<sup>2</sup> + (2 - 2)<sup></sup> + (3 - 2)<sup> </sup>/3 = 2/3.

+++

+++ Avancerade funktioner


## OCH

Returnerar värdet för dess argument. Använd NOT för att kontrollera att ett värde inte är lika med ett visst värde.

>[!NOTE]
>
>0 (noll) betyder False och alla andra värden är True.

```
AND(logical_test1,[logical_test2],...)
```

| Argument | Beskrivning |
|---|---|
| *logical_test1* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE. |
| *logical_test2* | Valfritt. Ytterligare villkor som du vill utvärdera som TRUE eller FALSE |

## Ungefärlig distinkt (dimension)

Returnerar det ungefärliga distinkta antalet dimensionsobjekt för den valda dimensionen. Funktionen använder HyperLogLog-metoden (HLL) för att beräkna distinkta antal.  Den är konfigurerad för att garantera att värdet ligger inom 5 % av det faktiska värdet 95 % av tiden.

```
Approximate Count Distinct (dimension)
```

| Argument |  |
|---|---|
| *dimension* | Dimensionen som du vill ha det ungefärliga distinkta artikelantalet för. |

### Exempel på användningsfall

Approximate Count Distinct (kundens ID-eVar) är ett vanligt användningsfall för den här funktionen.

Definition för ett nytt beräknat mått för&quot;Approximate Customers&quot;:

![Ungefärlig regionspecifik ny dimensionsdefinition som visar Kund-ID (eVar1)](../assets/approx-count-distinct.png)

Så här kan måttet&quot;Approximate Customers&quot; användas vid rapportering:

![Frihandstabell med unika besökare och ungefärliga kunder ](../assets/approx-customers.png)

### Jämföra räkningsfunktioner

Approximate Count Distinct() är en förbättring av funktionerna Count() och RowCount() eftersom måttet som skapas kan användas i alla dimensionella rapporter för att återge ett ungefärligt antal objekt för en separat dimension. Exempel: antalet kund-ID:n som används i en rapport av typ av mobil enhet.

Den här funktionen är marginellt mindre exakt än Count() och RowCount() eftersom den använder HLL-metoden, medan Count() och RowCount() är exakta tal.

## Båge cosinus (rad)

Returnerar arcus cosinus, eller inverterad cosinus, för ett mätresultat. Arcus cosinus är den vinkel vars cosinus är tal. Den returnerade vinkeln anges i radianer i intervallet 0 (noll) till pi. Om du vill konvertera resultatet från radianer till grader multiplicerar du det med 180/PI( ).

```
ACOS(metric)
```

| Argument |  |
|---|---|
| *metrisk* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Båge sinus (rad)

Returnerar arcus sinus, eller inverterad sinus, för ett tal. Arcussinus är vinkeln vars sinus är tal. Den returnerade vinkeln anges i radianer i intervallet -pi/2 till pi/2. Om du vill uttrycka arcussinus i grader multiplicerar du resultatet med 180/PI( ).

```
ASIN(metric)
```

| Argument |  |
|---|---|
| *metrisk* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Bågtangent (rad)

Returnerar talets arcus tangens, eller inverterade tangent. Arcus tangent är vinkeln vars tangent är tal. Den returnerade vinkeln anges i radianer i intervallet -pi/2 till pi/2. Om du vill uttrycka arcus tangens i grader multiplicerar du resultatet med 180/PI( ).

```
ATAN(metric)
```

| Argument |  |
|---|---|
| *metrisk* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Exponentiell regression: Förväntat Y (rad)

Beräknar de förväntade y-värdena (metric_Y), med tanke på de kända x-värdena (metric_X), med hjälp av metoden &quot;minst fyrkanter&quot; för att beräkna raden för bästa passform baserat på .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Cdf-T

Returnerar procentandelen av värden i en elevs t-fördelning, med n frihetsgrader som har ett z-score mindre än x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returnerar procentandelen av värden i en normal fördelning som har ett z-score mindre än x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499
```

## Tak (rad)

Returnerar det minsta heltalet som inte är mindre än ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har 569,34 USD använder du formeln CEILING( *Intäkter*) för att avrunda intäkter upp till närmaste dollar, eller 570 USD.

```
CEILING(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det mätvärde som du vill runda av. |

## Förtroende

[!UICONTROL Confidence] är ett sannolikhetsmått på hur mycket det finns bevis för att en given variant är samma som kontrollvarianten. Ett högre förtroende tyder inte på att kontrollvarianten och icke-kontrollvarianten har samma prestanda.

```
fx Confidence (normalizing-container, success-metric, control, significance-threshold)
```

| Argument | Beskrivning |
| --- | --- |
| Normaliserar behållare | Grundläggande (Personer, sessioner eller Händelser) som ett test ska köras på. |
| Resultatmått | Mätvärden eller mätvärden som en användare jämför varianter med. |
| Kontroll | Den variant som alla andra varianter i experimentet jämförs med. Ange namnet på kontrollvariantens dimensionsobjekt. |
| Tröskelvärde för signifikans | Tröskelvärdet i den här funktionen är inställt på 95 % som standard. |

{style="table-layout:auto"}

## Cosine (rad)

Returnerar cosinus för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
COS(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Vinkeln i radianer som du vill ha cosinus för. |

## Kubrot

Returnerar den positiva kubroten för ett tal. Kubroten för ett tal är värdet för det talet upphöjt till upphöjt till upphöjt till 1/3.

```
CBRT(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Måttet som du vill ha kubroten för. |

## Kumulativ

Returnerar summan av x för de sista N-raderna (enligt ordningen i dimensionen, med hash-värden för strängbaserade fält).

Om N &lt;= 0 används alla föregående rader. Eftersom den ordnas efter dimensionen är den bara användbar för dimensioner som har en naturlig ordning som datum eller längd.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) |
|------+------+--------------+--------------|
| May  | $500 | $500         | $500         |
| June | $200 | $700         | $700         |
| July | $400 | $1100        | $600         |
```

## Kumulativt genomsnitt

Returnerar medelvärdet för de sista N raderna.

Om N &lt;= 0 används alla föregående rader. Eftersom den ordnas efter dimensionen är den bara användbar för dimensioner som har en naturlig ordning som datum eller längd.

>[!NOTE]
>
>Detta fungerar inte som ni kan förvänta er med taxeringsvärden som intäkter/person: i stället för att summera intäkterna för de senaste N-siffrorna och summera personer över de senaste N-siffrorna och sedan dela upp dem. Använd i stället

```
cumul(revenue)/cumul(person)
```

## Jämn

Returnerar objekt som matchar exakt för ett numeriskt värde eller strängvärde.

## Exponentiell regression_korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r*, mellan två metriska kolumner ( *metric_A* och *metric_B*) för regressionsekvationen.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Exponentiell regression: Intercept (tabell)

Returnerar spärren *b* mellan två måttkolumner ( *metric_X* och *metric_Y*) för

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Exponentiell regression: Lutning (tabell)

Returnerar lutningen *a* mellan två måttkolumner ( *metric_X* och *metric_Y*) för .

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Våning (rad)

Returnerar det största heltalet som inte är större än ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har 569,34 USD, använder du formeln FLOOR( *Intäkter*) för att avrunda intäkten nedåt till närmaste dollar, eller 569 USD.

```
FLOOR(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det mätvärde som du vill runda av. |

## Större än

Returnerar objekt vars numeriska antal är större än det angivna värdet.

## Större än eller lika med

Returnerar objekt vars numeriska värde är större än eller lika med det angivna värdet.

## Hyperbolisk cosinus (rad)

Returnerar hyperbolisk cosinus för ett tal.

```
COSH(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Vinkeln i radianer som du vill hitta hyperbolisk cosinus för. |

## Hyperbolisk sinus (rad)

Returnerar hyperbolisk sinus för ett tal.

```
SINH(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Vinkeln i radianer som du vill hitta hyperbolisk sinus för. |

## Hyperbolisk tangens (rad)

Returnerar hyperbolisk tangens för ett tal.

```
TANH(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Vinkeln i radianer som du vill hitta den hyperboliska tangenten för. |

## IF (rad)

IF-funktionen returnerar ett värde om ett villkor som du anger utvärderas till TRUE och ett annat värde om villkoret utvärderas till FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argument | Beskrivning |
|---|---|
| *logical_test* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE. |
| *[value_if_true]* | Värdet som du vill returnera om argumentet *logical_test* utvärderas till TRUE. (Det här argumentet är som standard 0 om det inte inkluderas.) |
| *[value_if_false]* | Värdet som du vill returnera om argumentet *logical_test* utvärderas till FALSE. (Det här argumentet är som standard 0 om det inte inkluderas.) |

## Mindre än

Returnerar objekt vars numeriska antal är mindre än det angivna värdet.

## Mindre än eller lika med

Returnerar objekt vars numeriska värde är mindre än eller lika med det angivna värdet.

## Lyft

Returnerar det Lyft som en viss variant hade i konverteringar över en kontrollvariant. Det är skillnaden i prestanda mellan en given variant och baslinjen, dividerat med baslinjens prestanda, uttryckt i procent.

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Beskrivning |
| --- | --- |
| Normaliserar behållare | Grundläggande (Personer, sessioner eller Händelser) som ett test ska köras på. |
| Resultatmått | Mätvärden eller mätvärden som en användare jämför varianter med. |
| Kontroll | Den variant som alla andra varianter i experimentet jämförs med. Ange namnet på kontrollvariantens dimensionsobjekt. |

{style="table-layout:auto"}

## Linjär regression_Korrelationskoefficient

Y = a X + b. Returnerar korrelationskoefficienten

## Linear regression_Intercept

Y = a X + b. Returnerar b.

## Linear regression_Predicated Y

Y = a X + b. Returnerar Y.

## Linear regression_Slope

Y = a X + b. Returnerar a.

## Loggbas 10 (rad)

Returnerar 10-logaritmen för ett tal.

```
LOG10(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det positiva realtal som du vill ha bas-10-logaritmen för. |

## Loggregression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r*, mellan två metriska kolumner (*metric_X* och *metric_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med CORREL-ekvationen.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Loggregression: Intercept (tabell)

Returnerar spärren *b* som regressionen mellan två metriska kolumner (*metric_X* och *metric_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med INTERCEPT-ekvationen.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Loggregression: Förväntat Y (rad)

Beräknar de förväntade [!DNL y] värdena (metric_Y) utifrån de kända [!DNL x] värdena (metric_X) med hjälp av metoden&quot;minst fyrkanter&quot; för att beräkna raden för bästa passning baserat på [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av ESTIMATE-ekvationen.

I regressionsanalys beräknar den här funktionen de förväntade [!DNL y] värdena (*metric_Y*), med tanke på de kända [!DNL x] värdena (*metric_X*) med hjälp av logaritmen för att beräkna raden som bäst passar för regressionsekvationen [!DNL Y = a ln(X) + b]. [!DNL a]-värdena motsvarar varje x-värde och [!DNL b] är ett konstant värde.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Loggregression: Långsam (tabell)

Returnerar lutningen *a* mellan två måttkolumner (*metric_X* och *metric_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av SLOPE-ekvationen.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_A* | Ett mätvärde som du vill ange som beroende data. |
| *metric_B* | Ett mätvärde som du vill ange som oberoende data. |

## Naturlig logg

Returnerar den naturliga logaritmen för ett tal. Naturliga logaritmer baseras på konstanten *e* (2.71828182845904). LN är inversen till EXP-funktionen.

```
LN(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Det positiva realtal som du vill ha den naturliga logaritmen för. |

## NOT

Returnerar 1 om talet är 0 eller returnerar 0 om det är ett annat tal.

```
NOT(logical)
```

| Argument | Beskrivning |
|---|---|
| *logisk* | Obligatoriskt. Ett värde eller uttryck som kan utvärderas till TRUE eller FALSE. |

Om du använder NOT måste du känna till om uttrycken (&lt;, >, =, &lt;> osv.) returnerar 0- eller 1-värden.

## Inte lika med

Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet.

## Eller (rad)

Returnerar TRUE om något argument är TRUE, eller returnerar FALSE om alla argument är FALSE.

>[!NOTE]
>
>0 (noll) betyder False och alla andra värden är True.

```
OR(logical_test1,[logical_test2],...)
```

| Argument | Beskrivning |
|---|---|
| *logical_test1* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE. |
| *logical_test2* | Valfritt. Ytterligare villkor som du vill utvärdera som TRUE eller FALSE |

## Pi

Returnerar konstanten PI, 3,14159265358979, med 15 siffror.

```
PI()
```

Funktionen [!DNL PI] har inga argument.

## Effektregression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r*, mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Strömregression: Skärpning (tabell)

Returnerar spärren *b* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Strömregression: Förväntat Y (rad)

Beräknar de förväntade [!DNL y] värdena ( [!DNL metric_Y]), med hänsyn till kända [!DNL x]-värden ( [!DNL metric_X]), med hjälp av metoden &quot;minst fyrkanter&quot; för att beräkna raden som passar bäst för [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Strömregression: Långsam (tabell)

Returnerar lutningen *a* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Kvadratisk regression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r*, mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Kvadratisk regression: Intercept (tabell)

Returnerar spärren *b* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Kvadratisk regression: Förväntat Y (rad)

Beräknar de förväntade [!DNL y] värdena (metric_Y) utifrån de kända [!DNL x] värdena (metric_X) med hjälp av metoden med minst fyrkanter för att beräkna raden för bästa passform med hjälp av [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_A* | Ett mätvärde som du vill ange som beroende data. |
| *metric_B* | Ett mätvärde som du vill ange som beroende data. |

## Kvadratisk regression: Långsam (tabell)

Returnerar lutningen *a* mellan två måttkolumner (*metric_X* och metric_Y) för [!DNL Y=(a*X+b)]***.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Ömsesidig regression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r*, mellan två måttkolumner (*metric_X)* och *metric_Y*) för [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Ömsesidig regression: Intercept (tabell)

Returnerar spärren *b* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Ömsesidig regression: Förväntat Y (rad)

Beräknar de förväntade [!DNL y] värdena (metric_Y), utifrån de kända [!DNL x] värdena (metric_X) med hjälp av metoden med minst fyrkanter för att beräkna raden för bästa passning med [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Ömsesidig regression: Lutning (tabell)

Returnerar lutningen *a* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Sinus (rad)

Returnerar sinus för angiven vinkel. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
SIN(metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Vinkeln i radianer som du vill ha sinus för. |

## T-poäng

Alias för Z-poäng, dvs. avvikelsen från medelvärdet dividerat med standardavvikelsen

## T-test

Utför ett m-tailed t-test med t-score på kol och n frihetsgrader.

Signaturen är `t_test( x, n, m )`. Under anropet anropas bara `m*cdf_t(-abs(x),n)`. (Detta liknar z-test-funktionen som kör `m*cdf_z(-abs(x))`.

Här är `m` antalet svansar och `n` antalet frihetsgrader. Dessa ska vara tal (konstanta för hela rapporten, dvs. inte ändras rad för rad).

`X` är t-test-statistik och skulle ofta vara en formel (t.ex. zscore) baserad på ett mätvärde och kommer att utvärderas på varje rad.

Returvärdet är sannolikheten att se provningsvärdet x med hänsyn till antalet frihetsgrader och antalet svansar.

**Exempel:**

1. Använd den för att hitta avvikelser:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Kombinera den med `if` om du vill ignorera mycket höga eller låga avhoppsfrekvenser och räkna besök för allt annat:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returnerar tangenten för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
TAN (metric)
```

| Argument | Beskrivning |
|---|---|
| *metrisk* | Vinkeln i radianer som du vill ha tangenten för. |

## Z-poäng (rad)

Returnerar Z-poäng, eller normal poäng, baserat på en normal fördelning. Z-värdet är antalet standardavvikelser som en observation ligger från medelvärdet. Ett Z-värde på 0 (noll) innebär att poängen är samma som medelvärdet. Ett Z-värde kan vara positivt eller negativt, vilket anger om det ligger över eller under medelvärdet och hur många standardavvikelser.

Ekvationen för Z-score är:

![](../assets/z_score.png)

där [!DNL x] är råpoängen, är [!DNL μ] medelvärdet för populationen och [!DNL σ] är standardavvikelsen för populationen.

>[!NOTE]
>
>[!DNL μ] (mu) och [!DNL σ] (sigma) beräknas automatiskt utifrån måttet.

Z-score (metrisk)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metrisk</i> </td>
   <td colname="col2"> <p> Returnerar värdet för dess första argument som inte är noll. </p> </td>
  </tr>
 </tbody>
</table>

## Z-test

Utför ett n-tailed Z-test med Z-score på A.

Returnerar sannolikheten för att den aktuella raden kan ses av en slump i kolumnen.

>[!NOTE]
>
>Anta att värdena normalt fördelas.

+++

