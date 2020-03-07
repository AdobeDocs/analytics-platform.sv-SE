---
title: Referens - avancerade funktioner
description: Du får åtkomst till dessa funktioner genom att markera Visa avancerat i listrutan Funktioner.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Referens - avancerade funktioner

Du får åtkomst till dessa funktioner genom att kontrollera **[!UICONTROL Show Advanced]** i **[!UICONTROL Functions]** listrutan.

## Tabellfunktioner kontra radfunktioner

En tabellfunktion är en funktion där utdata är desamma för alla rader i tabellen. En radfunktion är en funktion där utdata är olika för alla rader i tabellen.

## Vad betyder parametern Include-Zeros?

Den anger om nollor ska inkluderas i beräkningen. Ibland betyder noll&quot;ingenting&quot;, men ibland är det viktigt.

Om du till exempel har ett intäktsmått och sedan lägger till ett sidvymått i rapporten finns det plötsligt fler rader för dina intäkter som alla är noll. Du vill antagligen inte att detta ska påverka MEAN, MIN, QUARTILE osv. beräkningar som du har i intäktskolumnen. I det här fallet kontrollerar du parametern include-zeros.

Å andra sidan, om du har två mätvärden som du är intresserad av, kan det vara svårt att säga att en har ett högre genomsnitt eller ett lägre värde, eftersom vissa av raderna var nollor, så du skulle inte kontrollera parametern så att den inkluderar nollorna.

## OCH

Returnerar värdet för dess argument. Använd NOT för att kontrollera att ett värde inte är lika med ett visst värde.

> [!NOTE] 0 (noll) betyder False och alla andra värden är True.

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

## Exempel på användningsfall

Approximate Count Distinct (kundens ID eVar) är ett vanligt användningsfall för den här funktionen.

Definition för ett nytt beräknat mått för&quot;Approximate Customers&quot;:

![](assets/approx-count-distinct.png)

Så här kan måttet&quot;Approximate Customers&quot; användas vid rapportering:

![](assets/approx-customers.png)

## Uniques överskreds

Precis som Count() och RowCount() omfattas [UniquesOver-gränserna](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html)för Approximate Count Distinct(). Om gränsen för antal unika tecken överskrids inom en viss månad för en dimension räknas värdet som 1 dimensionspost.

## Jämföra räkningsfunktioner

Approximate Count Distinct() är en förbättring av funktionerna Count() och RowCount() eftersom måttet som skapas kan användas i alla dimensionella rapporter för att återge ett ungefärligt antal objekt för en separat dimension. Exempel: antalet kund-ID:n som används i en rapport av typ av mobil enhet.

Den här funktionen är marginellt mindre exakt än Count() och RowCount() eftersom den använder HLL-metoden, medan Count() och RowCount() är exakta tal.

## Båge cosinus (rad)

Returnerar arcus cosinus, eller inverterad cosinus, för ett mätresultat. Arcus cosinus är den vinkel vars cosinus är tal. Den returnerade vinkeln anges i radianer i intervallet 0 (noll) till pi. Om du vill konvertera resultatet från radianer till grader multiplicerar du det med 180/PI( ).

```
ACOS(metric)
```

| Argument |  |
|---|---|
| *mått* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Båge sinus (rad)

Returnerar arcus sinus, eller inverterad sinus, för ett tal. Arcussinus är vinkeln vars sinus är tal. Den returnerade vinkeln anges i radianer i intervallet -pi/2 till pi/2. Om du vill uttrycka arcussinus i grader multiplicerar du resultatet med 180/PI( ).

```
ASIN(metric) 
```

| Argument |  |
|---|---|
| *mått* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Bågtangent (rad)

Returnerar talets arcus tangens, eller inverterade tangent. Arcus tangent är vinkeln vars tangent är tal. Den returnerade vinkeln anges i radianer i intervallet -pi/2 till pi/2. Om du vill uttrycka arcus tangens i grader multiplicerar du resultatet med 180/PI( ).

```
ATAN(metric)
```

| Argument |  |
|---|---|
| *mått* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Exponentiell regression: Förutsedd Y (rad)

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

Returnerar det minsta heltalet som inte är mindre än ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har 569,34 USD använder du formeln CEILING( *intäkt*) för att avrunda intäkten upp till närmaste dollar, eller 570 USD.

```
CEILING(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mätvärde som du vill runda av. |

## Cosine (rad)

Returnerar cosinus för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
COS(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill ha cosinus för. |

## Kubrot

Returnerar den positiva kubroten för ett tal. Kubroten för ett tal är värdet för det talet upphöjt till upphöjt till upphöjt till 1/3.

```
CBRT(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Måttet som du vill ha kubroten för. |

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

> [!NOTE] Detta fungerar inte som du kan förvänta dig med tariffvärden som intäkter/besökare: i stället för att summera intäkterna under det senaste N:et och summera besökarna under det senaste N:et och sedan dela upp dem. Använd i stället

```
cumul(revenue)/cumul(visitor)
```

## Jämn

Returnerar objekt som matchar exakt för ett numeriskt värde eller strängvärde.

## Exponentiell regression_korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten *r* mellan två metriska kolumner ( *metric_A* och *metric_B*) för regressionsekvationen.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Exponentiell regression: Intercept (tabell)

Returnerar spärren, *b*, mellan två metriska kolumner ( *metric_X* och *metric_Y*) för

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Exponentiell regression: Lutning (tabell)

Returnerar lutningen, *a*, mellan två måttkolumner ( *metric_X* och *metric_Y*) för .

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Våning (rad)

Returnerar det största heltalet som inte är större än ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har 569,34 USD, använder du formeln FLOOR( *Intäkter*) för att avrunda intäkten nedåt till närmaste dollar, eller 569 dollar.

```
FLOOR(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mätvärde som du vill runda av. |

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
| *mått* | Vinkeln i radianer som du vill hitta hyperbolisk cosinus för. |

## Hyperbolisk sinus (rad)

Returnerar hyperbolisk sinus för ett tal.

```
SINH(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill hitta hyperbolisk sinus för. |

## Hyperbolisk tangens (rad)

Returnerar hyperbolisk tangens för ett tal.

```
TANH(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill hitta den hyperboliska tangenten för. |

## IF (rad)

IF-funktionen returnerar ett värde om ett villkor som du anger utvärderas till TRUE och ett annat värde om villkoret utvärderas till FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argument | Beskrivning |
|---|---|
| *logical_test* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE. |
| *[value_if_true]* | Värdet som du vill returnera om argumentet *logical_test* utvärderas till TRUE. (Detta argument är som standard 0 om det inte inkluderas.) |
| *[value_if_false]* | Värdet som du vill returnera om argumentet *logical_test* utvärderas till FALSE. (Detta argument är som standard 0 om det inte inkluderas.) |

## Mindre än

Returnerar objekt vars numeriska antal är mindre än det angivna värdet.

## Mindre än eller lika med

Returnerar objekt vars numeriska värde är mindre än eller lika med det angivna värdet.

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
| *mått* | Det positiva realtal som du vill ha bas-10-logaritmen för. |

## Loggregression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten *r* mellan två metriska kolumner (*metric_X* och *metric_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med CORREL-ekvationen.

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

## Loggregression: Förutsedd Y (rad)

Beräknar de förväntade [!DNL y] värdena (metric_Y), med de kända [!DNL x] värdena (metric_X) som använder metoden&quot;minst fyrkanter&quot; för att beräkna raden för bästa passning baserat på [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av ESTIMATE-ekvationen.

I regressionsanalys beräknar den här funktionen de förväntade [!DNL y] värdena (*metric_Y*), med hänsyn till de kända [!DNL x] värdena (*metric_X*) med hjälp av logaritmen för att beräkna raden som bäst passar för regressionsekvationen [!DNL Y = a ln(X) + b]. Värdena [!DNL a] motsvarar varje x-värde och [!DNL b] är ett konstant värde.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Loggregression: Lutning (tabell)

Returnerar lutningen, *a*, mellan två metriska kolumner (*metric_X* och *metric_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av SLOPE-ekvationen.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_A* | Ett mätvärde som du vill ange som beroende data. |
| *metrisk_B* | Ett mätvärde som du vill ange som oberoende data. |

## Naturlig logg

Returnerar den naturliga logaritmen för ett tal. Naturliga logaritmer baseras på konstanten *e* (2.71828182845904). LN är inversen till EXP-funktionen.

```
LN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det positiva realtal som du vill ha den naturliga logaritmen för. |

## NOT

Returnerar 1 om talet är 0 eller returnerar 0 om det är ett annat tal.

```
NOT(logical)
```

| Argument | Beskrivning |
|---|---|
| *logisk* | Obligatoriskt. Ett värde eller uttryck som kan utvärderas till TRUE eller FALSE. |

Om du använder NOT måste du känna till om uttrycken (&lt;, >, =, &lt;> osv.) returnera 0- eller 1-värden.

## Inte lika med

Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet.

## Eller (rad)

Returnerar TRUE om något argument är TRUE, eller returnerar FALSE om alla argument är FALSE.

> [!NOTE] 0 (noll) betyder False och alla andra värden är True.

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

Funktionen [!DNL PI]har inga argument.

## Strömregression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten *r* mellan två metriska kolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Strömregression: Intercept (tabell)

Returnerar spärren *b* mellan två metriska kolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Strömregression: Förutsedd Y (rad)

Beräknar de förväntade [!DNL y] värdena ( [!DNL metric_Y]), med hänsyn till de kända [!DNL x] värdena ( [!DNL metric_X]), med hjälp av metoden &quot;minst fyrkanter&quot; för att beräkna raden som passar bäst för [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Strömregression: Lutning (tabell)

Returnerar lutningen, *a*, mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Kvadratisk regression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten *r* mellan två metriska kolumner (*metric_X* och *metric_Y*) för [!DNL Y=(a*X+b)]***.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Kvadratisk regression: Intercept (tabell)

Returnerar spärren *b* mellan två metriska kolumner (*metric_X* och *metric_Y*) för [!DNL Y=(a*X+b)]***.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Kvadratisk regression: Förutsedd Y (rad)

Beräknar de förväntade [!DNL y] värdena (metric_Y), med hänsyn till kända [!DNL x] värden (metric_X), med hjälp av metoden med minst fyrkanter för att beräkna raden för bästa passform med hjälp av [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_A* | Ett mätvärde som du vill ange som beroende data. |
| *metrisk_B* | Ett mätvärde som du vill ange som beroende data. |

## Kvadratisk regression: Lutning (tabell)

Returnerar lutningen, *a*, mellan två måttkolumner (*metric_X* och metric_Y) för [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Ömsesidig regression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten *r* mellan två metriska kolumner (*metric_X)* och *metric_Y*) för [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Ömsesidig regression: Intercept (tabell)

Returnerar spärren *b* mellan två metriska kolumner (*metric_X* och *metric_Y*) för [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Ömsesidig regression: Förutsedd Y (rad)

Beräknar de förväntade [!DNL y] värdena (metric_Y), med de kända [!DNL x] värdena (metric_X) som använder metoden med minst fyrkanter för att beräkna raden för bästa passning med [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Ömsesidig regression: Lutning (tabell)

Returnerar lutningen, *a*, mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som beroende data. |
| *metric_Y* | Ett mätvärde som du vill ange som oberoende data. |

## Sinus (rad)

Returnerar sinus för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
SIN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill ha sinus för. |

## T-poäng

Alias för Z-poäng, dvs. avvikelsen från medelvärdet dividerat med standardavvikelsen

## T-test

Utför ett m-tailed t-test med t-score på kol och n frihetsgrader.

Underskriften är `t_test( x, n, m )`. Under det anropas bara `m*cdf_t(-abs(x),n)`. (Detta liknar z-test-funktionen som körs `m*cdf_z(-abs(x))`.

Här `m` är antalet svansar och `n` antalet frihetsgrader. Dessa ska vara tal (konstanta för hela rapporten, dvs. inte ändras rad för rad).

`X` är t-test-värdet och skulle ofta vara en formel (t.ex. zscore) som baseras på ett mätresultat och utvärderas på varje rad.

Returvärdet är sannolikheten att se provningsvärdet x med hänsyn till antalet frihetsgrader och antalet svansar.

**Exempel:**

1. Använd den för att hitta avvikelser:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Kombinera den med `if` att ignorera mycket höga eller låga studsfrekvenser och räkna med besök på allt annat:

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
| *mått* | Vinkeln i radianer som du vill ha tangenten för. |

## Z-poäng (rad)

Returnerar Z-poäng, eller normal poäng, baserat på en normal fördelning. Z-värdet är antalet standardavvikelser som en observation ligger från medelvärdet. Ett Z-värde på 0 (noll) innebär att poängen är samma som medelvärdet. Ett Z-värde kan vara positivt eller negativt, vilket anger om det ligger över eller under medelvärdet och hur många standardavvikelser.

Ekvationen för Z-score är:

![](assets/z_score.png)

där [!DNL x] är råpoängen, [!DNL μ] är medelvärdet av populationen och [!DNL σ] är standardavvikelsen för populationen.

> [!NOTE] [!DNL μ] (mu) och[!DNL σ] (sigma) beräknas automatiskt utifrån måttet.

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
   <td colname="col1"> <i>mått</i> </td> 
   <td colname="col2"> <p> Returnerar värdet för dess första argument som inte är noll. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z-test

Utför ett n-tailed Z-test med Z-score på A.

Returnerar sannolikheten för att den aktuella raden kan ses av en slump i kolumnen.

> [!NOTE] Anta att värdena normalt fördelas.

