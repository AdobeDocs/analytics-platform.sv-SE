---
title: Referens - avancerade funktioner
description: Du kommer åt dessa funktioner genom att markera Visa avancerat i listrutan Funktioner.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '2946'
ht-degree: 1%

---


# Referens - avancerade funktioner

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Få åtkomst till dessa funktioner genom att kontrollera **[!UICONTROL Show Advanced]** i **[!UICONTROL Functions]** listruta.

## Tabellfunktioner kontra radfunktioner

En tabellfunktion är en funktion där utdata är desamma för varje rad i tabellen. En radfunktion är en funktion där utdata skiljer sig åt för varje rad i tabellen.

## Vad betyder parametern Include-Zeros?

Den anger om nollor ska inkluderas i beräkningen. Ibland betyder noll &quot;ingenting&quot;, men ibland är det viktigt.

Om du t.ex. har ett intäktsmått och sedan lägger till ett mått för sidvy i rapporten finns det plötsligt fler rader för dina intäkter som alla är noll. Du vill förmodligen inte att det här ska påverka MEAN, MIN, QUARTILE etc. beräkningar som du har på intäktskolumnen. I så fall kontrollerar du parametern include-zeros.

Å andra sidan, om man har två mått som man är intresserad av, kanske det inte är rättvist att säga att man har ett högre genomsnitt eller ett minimum på grund av att vissa av raderna var nollor, så du skulle inte kontrollera att parametern inkluderar nollorna.

## OCH

Returnerar värdet för argumentet. Använd INTE för att kontrollera att ett värde inte är lika med ett visst värde.

>[!NOTE]
>
>0 (noll) betyder Falskt och alla andra värden är Sant.

```
AND(logical_test1,[logical_test2],...)
```

| Argument | Beskrivning |
|---|---|
| *logisk_test1* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till SANT eller FALSKT. |
| *logisk_test2* | Valfritt. Ytterligare villkor som du vill utvärdera som SANT eller FALSKT |

## Ungefärligt antal distinkt (dimension)

Returnerar det ungefärliga avgränsade antalet dimensionsobjekt för den valda dimensionen. Funktionen använder HyperLogLog-metoden (HLL) för att approximera distinkta antal.  Det är konfigurerat för att garantera att värdet ligger inom 5 % av det faktiska värdet 95 % av tiden.

```
Approximate Count Distinct (dimension)
```

| Argument |  |
|---|---|
| *dimension* | Dimensionen som du vill ha det ungefärliga avgränsade artikelantalet för. |

## Exempel Använd skiftläge

Ungefärlig räknardifferens (Customer ID eVar) är ett vanligt användningsfall för den här funktionen.

Definition av ett nytt beräknat mått för &quot;ungefärliga kunder&quot;:

![](assets/approx-count-distinct.png)

Så här skulle måttet &quot;Ungefär kunder&quot; kunna användas vid rapportering:

![](assets/approx-customers.png)

## Uniques har överskridits

Liksom Count() och RowCount(), är approximate Count Distinct() föremål för [Överskridna uniques-gränser](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html). Om gränsen för antal överskjutande enheter nås inom en viss månad för en dimension räknas värdet som 1 dimensionsobjekt.

## Jämföra räkningsfunktioner

Ungefärligt antal distinkt() är en förbättring jämfört med funktionerna Count() och RowCount() eftersom det metriska som skapas kan användas i alla dimensionsrapporter för att återge ett ungefärligt antal artiklar för en separat dimension. Exempelvis ett antal kund-ID som används i en rapport av typen Mobile Device Type.

Den här funktionen blir marginellt mindre exakt än Count() och RowCount() eftersom den använder HLL-metoden, medan Count() och RowCount() är exakta tal.

## Arc Cosine (rad)

Returnerar arcuscosinus, eller inverterad av cosinus, för ett mätresultat. Arcuscosinus är vinkeln vars cosinus är tal. Den returnerade vinkeln anges i radianer i intervallet 0 (noll) till pi. Om du vill konvertera resultatet från radianer till grader multiplicerar du det med 180/PI( ).

```
ACOS(metric)
```

| Argument |  |
|---|---|
| *mått* | Vinkelns cosinus från -1 till 1. |

## Arc Sine (rad)

Returnerar arcussinus, eller inverterad sinus, för ett tal. Arcussinus är vinkeln vars sinus är tal. Den returnerade vinkeln anges i radianer i intervallet -pi/2 till pi/2. Om du vill uttrycka arcussinus i grader multiplicerar du resultatet med 180/PI( ).

```
ASIN(metric) 
```

| Argument |  |
|---|---|
| *mått* | Vinkelns cosinus från -1 till 1. |

## Arc Tangent (rad)

Returnerar arctangens eller inverterad tangens för ett tal. Arcustangens är vinkeln vars tangent är tal. Den returnerade vinkeln anges i radianer i intervallet -pi/2 till pi/2. Om du vill uttrycka arctangens i grader multiplicerar du resultatet med 180/PI( ).

```
ATAN(metric)
```

| Argument |  |
|---|---|
| *mått* | Vinkelns cosinus från -1 till 1. |

## Exponentiell regression: Förväntat Y (rad)

Beräknar de förväntade y-värdena (metric_Y), givet de kända x-värdena (metric_X) med hjälp av metoden &quot;minst fyrkanter&quot; för att beräkna raden för bästa passning baserat på.

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Cdf-T

Returnerar procentandelen av värdena i en students t-distribution med n frihetsgrader som har ett z-score mindre än x.

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returnerar procentandelen värden i en normalfördelning som har ett z-score mindre än x.

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## Tak (rad)

Returnerar det minsta heltalet som inte är mindre än ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har $569,34, använder du formeln CEILING( *Intäkter*) för att runda av intäkter upp till närmaste dollar, eller $570.

```
CEILING(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Måttet som du vill runda av. |

## Kosine (rad)

Returnerar cosinus för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
COS(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill ha cosinus för. |

## Kubrot

Returnerar den positiva kubroten för ett tal. Kubroten för ett nummer är värdet för det nummer som upphöjts till effekten 1/3.

```
CBRT(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Måttet som du vill ha kubroten för. |

## Ackumulerat

Returnerar summan av x för de sista N-raderna (enligt storleksordningen, med hash-värden för strängbaserade fält).

Om N &lt;= 0 används alla tidigare rader. Eftersom den har beställts av dimensionen är den endast användbar på dimensioner som har en naturlig ordning som datum eller längd.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Ackumulerat genomsnitt

Returnerar medelvärdet för de sista N-raderna.

Om N &lt;= 0 används alla tidigare rader. Eftersom den har beställts av dimensionen är den endast användbar på dimensioner som har en naturlig ordning som datum eller längd.

>[!NOTE]
>
>Detta fungerar inte som du kan förvänta dig med kursmått som intäkter/besökare: I stället för att summera inkomsterna under det senaste N-numret och summera besökarna under det senaste N-numret och sedan dela upp dem. Använd i stället

```
cumul(revenue)/cumul(visitor)
```

## Lika

Returnerar objekt som matchar exakt för ett numeriskt värde eller strängvärde.

## Exponentiell regression_ Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r* mellan två metriska kolumner ( *metrisk_A* och *metrisk_B*) för regressionsekvationen.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill korrelera med *metrisk_Y*. |
| *metrisk_Y* | Ett mått som du vill korrelera med *metrisk_X*. |

## Exponentiell regression: Intercept (tabell)

Returnerar skärningspunkten. *b* mellan två metriska kolumner ( *metrisk_X* och *metrisk_Y*) för

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Exponentiell regression: Lutning (tabell)

Returnerar lutningen. *en* mellan två metriska kolumner ( *metrisk_X* och *metrisk_Y*) för

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Golv (rad)

Returnerar det största heltalet som inte är större än ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har $569,34 använder du formeln FLOOR( *Intäkter*) för att runda av intäkterna ner till närmaste dollar, eller 569 dollar.

```
FLOOR(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Måttet du vill runda av. |

## Större än

Returnerar objekt vars numeriska antal är större än det angivna värdet.

## Större än eller lika

Returnerar objekt vars numeriska antal är större än eller lika med det angivna värdet.

## Hyperbolisk kosine (rad)

Returnerar den hyperboliska cosinus för ett tal.

```
COSH(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill hitta den hyperboliska cosinus för. |

## Hyperbolisk sinus (rad)

Returnerar den hyperboliska sinus för ett tal.

```
SINH(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill hitta hyperboliskt sinus för. |

## Hyperbolisk tangens (rad)

Returnerar den hyperboliska tangens för ett tal.

```
TANH(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill hitta den hyperboliska tangens för. |

## IF (rad)

IF-funktionen returnerar ett värde om ett villkor som du anger utvärderas till SANT och ett annat värde om det villkoret utvärderas till FALSKT.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argument | Beskrivning |
|---|---|
| *logisk_test* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till SANT eller FALSKT. |
| *[värde_om_sant]* | Värdet som du vill returnera om värdet *logisk_test* argumentet utvärderas till SANT. (Detta argument är som standard 0 om det inte ingår.) |
| *[värde_om_falskt]* | Värdet som du vill returnera om värdet *logisk_test* argument utvärderas till FALSE. (Detta argument är som standard 0 om det inte ingår.) |

## Mindre än

Returnerar objekt vars numeriska antal är lägre än det angivna värdet.

## Mindre än eller lika

Returnerar objekt vars numeriska antal är mindre än eller lika med det angivna värdet.

## Linjär regression_ Korrelationskoefficient

Y = a X + b. Returnerar korrelationskoefficienten

## Linjärt regression_ Intercept

Y = a X + b. Returnerar b.

## Linjärt regression_ Förväntad Y

Y = a X + b. Returnerar Y.

## Linjärt regression_ Slope

Y = a X + b. Returnerar a.

## Loggbas 10 (rad)

Returnerar basen 10-logaritmen för ett tal.

```
LOG10(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det positiva verkliga talet som du vill ha logaritmen base-10 för. |

## Loggregression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av CORREL-ekvationen.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill korrelera med *metrisk_Y*. |
| *metrisk_Y* | Ett mått som du vill korrelera med *metrisk_X*. |

## Loggregression: Intercept (tabell)

Returnerar skärningspunkten *b* som regression mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Det beräknas med hjälp av INTERCEPT-ekvationen.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Loggregression: Förväntat Y (rad)

Beräknar den förutspådda [!DNL y] värden (metric_Y), givet de kända [!DNL x] värden (metric_X) med hjälp av metoden &quot;minst fyrkanter&quot; för att beräkna raden för bästa passning baserat på [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av ESTIMATE-ekvationen.

I regressionsanalys beräknar den här funktionen den förväntade [!DNL y] värden (*metrisk_Y*), med tanke på de kända [!DNL x] värden (*metrisk_X*) med hjälp av logaritmen för beräkning av den linje som bäst passar för regressionsekvationen [!DNL Y = a ln(X) + b]. De [!DNL a] värdena motsvarar varje x-värde, och [!DNL b] är ett konstant värde.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Loggregression: Lutning (tabell)

Returnerar lutningen. *en* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av SLOPE-ekvationen.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_A* | Ett mått som du vill ange som beroende data. |
| *metrisk_B* | Ett mått som du vill ange som oberoende data. |

## Naturlogg

Returnerar den naturliga logaritmen för ett tal. Naturliga logaritmer baseras på konstanten *e* (2 71828182845904) LN är den inverterade funktionen EXP.

```
LN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det positiva verkliga talet som du vill ha den naturliga logaritmen för. |

## INTE

Returnerar 1 om talet är 0 eller returnerar 0 om ett annat tal används.

```
NOT(logical)
```

| Argument | Beskrivning |
|---|---|
| *logisk* | Obligatoriskt. Ett värde eller uttryck som kan utvärderas till SANT eller FALSKT. |

Om du vill använda NOT måste du veta om uttrycken (&lt;, >, =, &lt;> osv.) returnerar 0- eller 1-värden.

## Inte lika med

Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet.

## Eller (rad)

Returnerar SANT om något argument är SANT, eller returnerar FALSKT om alla argument är FALSKT.

>[!NOTE]
>
>0 (noll) betyder Falskt och alla andra värden är Sant.

```
OR(logical_test1,[logical_test2],...)
```

| Argument | Beskrivning |
|---|---|
| *logisk_test1* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till SANT eller FALSKT. |
| *logisk_test2* | Valfritt. Ytterligare villkor som du vill utvärdera som SANT eller FALSKT |

## Pi

Returnerar konstanten PI, 3.14159265358979, med en noggrannhet på 15 siffror.

```
PI()
```

De [!DNL PI]funktionen har inga argument.

## Effektregression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill korrelera med *metrisk_Y*. |
| *metrisk_Y* | Ett mått som du vill korrelera med *metrisk_X*. |

## Effektregression: Intercept (tabell)

Returnerar skärningspunkten. *b* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Effektregression: Förväntat Y (rad)

Beräknar den förutspådda [!DNL y] värden ( [!DNL metric_Y]), med tanke på de kända [!DNL x] värden ( [!DNL metric_X]) som använder metoden &quot;minsta kvadrat&quot; för att beräkna den rad som är bäst lämpad för [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Effektregression: Lutning (tabell)

Returnerar lutningen. *en* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Kvadratisk regression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill korrelera med *metrisk_Y*. |
| *metrisk_Y* | Ett mått som du vill korrelera med *metrisk_X*. |

## Kvadratisk regression: Intercept (tabell)

Returnerar skärningspunkten. *b* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Kvadratisk regression: Förväntat Y (rad)

Beräknar den förutspådda [!DNL y] värden (metric_Y), givet de kända [!DNL x] värden (metric_X) med minst kvadratmetoden för att beräkna raden för bästa passning med [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_A* | Ett mått som du vill ange som beroende data. |
| *metrisk_B* | Ett mått som du vill ange som beroende data. |

## Kvadratisk regression: Lutning (tabell)

Returnerar lutningen. *en* mellan två metriska kolumner (*metrisk_X* och metric_Y) för [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Ömsesidig regression: Korrelationskoefficient (tabell)

Returnerar korrelationskoefficienten, *r* mellan två metriska kolumner (*metrisk_X)* och *metrisk_Y*) för [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill korrelera med *metrisk_Y*. |
| *metrisk_Y* | Ett mått som du vill korrelera med *metrisk_X*. |

## Ömsesidig regression: Intercept (tabell)

Returnerar skärningspunkten. *b* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Ömsesidig regression: Förväntat Y (rad)

Beräknar den förutspådda [!DNL y] värden (metric_Y), givet de kända [!DNL x] värden (metric_X) med minst kvadratmetoden för att beräkna raden för bästa passning med [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Ömsesidig regression: Lutning (tabell)

Returnerar lutningen. *en* mellan två metriska kolumner (*metrisk_X* och *metrisk_Y*) för [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metrisk_X* | Ett mått som du vill ange som beroende data. |
| *metrisk_Y* | Ett mått som du vill ange som oberoende data. |

## Sine (rad)

Returnerar sinus för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
SIN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill ha sinuset för. |

## T-poäng

Alias för Z-Score, dvs. avvikelsen från medelvärdet dividerat med standardavvikelsen

## T-test

Utför ett m-skräddarsytt t-test med t-score kol och n frihetsgrader.

Signaturen är `t_test( x, n, m )`. Underliggande kräver man helt enkelt `m*cdf_t(-abs(x),n)`. (Detta liknar z-testfunktionen som körs `m*cdf_z(-abs(x))`.

Här, `m` är antalet svansar, och `n` är frihetsgraden. Dessa bör vara tal (konstanta för hela rapporten, dvs. inte ändras rad för rad).

`X` är t-provningsvärdet och skulle ofta vara en formel (t.ex. zscore) som baseras på ett mått och kommer att utvärderas på varje rad.

Returvärdet är sannolikheten för att se provningsvärdet med hänsyn till graden av frihet och antalet svansar.

**Exempel:**

1. Använd den för att hitta avvikande värden:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Kombinera den med `if` att bortse från mycket höga eller låga studsnivåer och räkna besök på allt annat:

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

Beräknar Z-score eller normalvärde baserat på en normalfördelning. Z- score är antalet standardavvikelser som en observation är från medelvärdet. Ett Z-score på 0 (noll) betyder att poängen är samma som medelvärdet. Ett Z-score kan vara positivt eller negativt, vilket anger om det är över eller under medelvärdet och hur många standardavvikelser.

Ekvationen för Z-score är:

![](assets/z_score.png)

där [!DNL x] är råpoängen, [!DNL μ] är medelvärdet av befolkningen, och [!DNL σ] är standardavvikelsen för populationen.

>[!NOTE]
>
>[!DNL μ] mu) och[!DNL σ] (sigma) beräknas automatiskt från metersystemet.

Z-score(metrisk)

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
   <td colname="col2"> <p> Returnerar värdet för det första argumentet som inte är noll. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z-test

Utför ett n-side Z-test med Z- score A.

Returnerar sannolikheten för att den aktuella raden kan ses av en slump i kolumnen.

>[!NOTE]
>
>Förutsätter sig att värdena fördelas normalt.

