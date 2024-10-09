---
title: Avancerade funktioner
description: Du får åtkomst till dessa funktioner genom att markera Visa avancerat i listrutan Funktioner.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: e355194d6699128ac817ea564940c0afdea61efc
workflow-type: tm+mt
source-wordcount: '2856'
ht-degree: 2%

---

# Avancerade funktioner

Med verktyget [Beräknade mätvärden](cm-workflow/cm-build-metrics.md) kan du använda statistiska och matematiska funktioner. I den här artikeln visas en alfabetisk lista över de avancerade funktionerna och deras definitioner.

Du får åtkomst till de här funktionerna genom att välja **[!UICONTROL Show all]** under listan ![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL Functions]** på panelen Komponenter. Bläddra ned för att se listan med **[!UICONTROL Advanced functions]**.

## Tabellfunktioner jämfört med radfunktioner

En tabellfunktion är en funktion där utdata är desamma för alla rader i tabellen. En radfunktion är en funktion där utdata är olika för alla rader i tabellen.

I tillämpliga fall och när det är relevant kommenteras en funktion med funktionstypen: [!BADGE Tabell]{type="Neutral"}[!BADGE Rad]{type="Neutral"}

## Vad betyder parametern include-zeros?

Den anger om nollor ska inkluderas i beräkningen. Ibland betyder noll *ingenting*, men ibland är det viktigt.

Om du till exempel har ett intäktsmått och sedan lägger till ett sidvymått i rapporten finns det plötsligt fler rader för dina intäkter, som alla är noll. Du vill förmodligen inte att det ytterligare måttet ska påverka några **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** och fler beräkningar som du har i intäktskolumnen. I det här fallet kontrollerar du parametern `include-zeros`.

Ett alternativt scenario är att du har två intressanta mätvärden och ett har ett högre genomsnitt eller minimum eftersom några av raderna är nollor.  I så fall kan du välja att inte kontrollera parametern så att den innehåller nollor.


## Och

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**


Förening. Inte lika med noll anses vara sant och lika med noll anses vara falskt. Utdata är antingen 0 (false) eller 1 (true).


| Argument | Beskrivning |
|---|---|
| logical_test | Kräver minst en parameter, men kan ha ett valfritt antal parametrar. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE |

## Distinkt antal

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


Returnerar det ungefärliga distinkta antalet dimensionsobjekt för den valda dimensionen.


| Argument | Beskrivning |
|---|---|
| dimension | Dimensionen som du vill beräkna det ungefärliga distinkta artikelantalet för |

### Exempel

Ett vanligt användningsexempel för den här funktionen är när du vill få ett ungefärligt antal kunder.




## Arc Cosine

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | cosinus för vinkeln du vill ha från -1 till 1 |



## Båge sinus

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Vinkelns sinus som du vill ha från -1 till 1 |



## Bågtangent

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Tangenten för vinkeln som du vill ha från -1 till 1 |



## Cdf-T

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**


Returnerar sannolikheten för att en slumpmässig variabel med studentfördelning med n frihetsgrader har ett z-score mindre än kol.


| Argument | Beskrivning |
|---|---|
| mått | Det mätvärde för vilket du vill ha den kumulativa fördelningsfunktionen för studenternas t-distribution |
| tal | Frihetsgrader för studentens funktion för kumulativ fördelning |

### Exempel

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**


Returnerar sannolikheten för att en slumpvariabel med en normal fördelning har ett z-score som är mindre än col.


| Argument | Beskrivning |
|---|---|
| mått | Det mått för vilket du vill ha den kumulativa distributionsfunktionen för Standard Normal Distribution |

### Exempel

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Tak

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Det mätvärde som du vill runda av |


## Förtroende (lägre)

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Beräkna valfri giltig konfidensgrad **lower** med WASKR-metoden enligt beskrivningen i [Tidsenhetlig central gränsteori och asymptotiska konfidenssekvenser](https://arxiv.org/pdf/2103.06476).

Förtroende är ett sannolikhetsmått på hur mycket det finns belägg för att en viss variant är densamma som kontrollvarianten. Ett högre förtroende tyder inte på att kontrollvarianten och icke-kontrollvarianten har samma prestanda.

| Argument | Beskrivning |
| --- | --- |
| normalizing-container | Basen (Personer, Sessioner eller Händelser) som ett test körs på. |
| framgångsmått | Mätvärden eller mätvärden som en användare jämför varianter med. |
| control | Den variant som alla andra varianter i experimentet jämförs med. Ange namnet på kontrollvariantens dimensionsobjekt. |
| signifikanströskel | Tröskelvärdet i den här funktionen är inställt på 95 % som standard. |

## Förtroende (övre)

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Beräkna det valfria tidsgiltiga förtroendet **upper** med WASKR-metoden enligt beskrivningen i [Tidsenhetlig central gränsteori och asymptotiska konfidenssekvenser](https://arxiv.org/pdf/2103.06476).

Förtroende är ett sannolikhetsmått på hur mycket det finns belägg för att en viss variant är densamma som kontrollvarianten. Ett högre förtroende tyder inte på att kontrollvarianten och icke-kontrollvarianten har samma prestanda.

| Argument | Beskrivning |
| --- | --- |
| normalizing-container | Basen (Personer, Sessioner eller Händelser) som ett test körs på. |
| framgångsmått | Mätvärden eller mätvärden som en användare jämför varianter med. |
| control | Den variant som alla andra varianter i experimentet jämförs med. Ange namnet på kontrollvariantens dimensionsobjekt. |
| signifikanströskel | Tröskelvärdet i den här funktionen är inställt på 95 % som standard. |


## Cosine

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(metric)]**

[!BADGE Rad]{type="Neutral"}

| Argument | Beskrivning |
|---|---|
| mått | Vinkeln i radianer som du vill ha cosinus för |


## Kubrot

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


Returnerar den positiva kubroten för ett tal. Kubroten för ett tal är värdet för det talet upphöjt till upphöjt till upphöjt till 1/3.


| Argument | Beskrivning |
|---|---|
| mått | Måttet som du vill beräkna kubroten för |



## Kumulativ

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Returnerar summan av de sista n elementen i kolumn x. Om n > 0 är summan av de sista n elementen eller x. Om n &lt; 0, summera föregående element.

| Argument | Beskrivning |
| --- | --- |
| tal | Det sista N-antalet rader som summan ska returneras för. Om N &lt;= 0 använder du alla föregående rader. |
| mått | Mätvärdet som du vill ha den ackumulerade summan för. |

### Exempel

| Datum | Intäkter | CUMULATIVE(0, Intäkter) | CUMULATIVE(2, Revenue) |
|------|------:|--------------:|--------------:|
| Maj | 500 dollar | 500 dollar | 500 dollar |
| Juni | 200 dollar | 700 dollar | 700 dollar |
| Juli | 400 dollar | 1 100 dollar | 600 dollar |


## Kumulativ (medel)

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

Returnerar medelvärdet för de sista n elementen i kolumn x. Om n > 0 är summan av de sista n elementen eller x. Om n &lt; 0, summera föregående element.

| Argument | Beskrivning |
| --- | --- |
| tal | Det sista N-antalet rader som medelvärdet ska returneras för. Om N &lt;= 0 använder du alla föregående rader. |
| mått | Det mätvärde som du vill ha för det ackumulerade genomsnittet. |

>[!NOTE]
>
>Den här funktionen fungerar inte med tariffvärden som intäkter per person. Funktionen beräknar genomsnittsnivån i stället för att summera intäkterna för de senaste N:en och summerar personer under de senaste N:en och delar sedan upp dem. <br/>Använd [**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![Dela](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative) i stället.
>


## Jämn

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**


Lika. Utdata är antingen 0 (false) eller 1 (true).


| Argument | Beskrivning |
|---|---|
| metric_X | |
| metric_Y | |

### Exempel

`Metric 1 = Metric 2`



## Exponentiell regression: Korrelationskoefficient

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mått som du vill korrelera med metric_Y |
| metric_Y | Ett mått som du vill korrelera med metric_X |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |

## Exponentiell regression: Förväntat Y

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som oberoende data. |
| metric_Y | Ett mätvärde som du vill ange som beroende data. |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Exponentiell regression: Intercept

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}

| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Exponentiell regression: Lutning

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Floor

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE Rad]{type="Neutral"}

| Argument | Beskrivning |
|---|---|
| mått | Det mätvärde som du vill runda av. |


## Större än

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**


Utdata är antingen 0 (false) eller 1 (true).


| Argument | Beskrivning |
|---|---|
| metric_X | |
| metric_Y | |

### Exempel

`Metric 1 > Metric 2`

## Större än eller lika med

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**


Större än eller lika med. Utdata är antingen 0 (false) eller 1 (true).


| Argument | Beskrivning |
|---|---|
| metric_X |  |
| metric_Y |  |

### Exempel

`Metric 1 >= Metric 2`



## Hyperbolisk cosinus

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Vinkeln i radianer som du vill hitta hyperbolisk cosinus för |



## Hyperbolisk sinus

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Vinkeln i radianer som du vill hitta hyperbolisk sinus för |



## Hyperbolisk tangens

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Vinkeln i radianer som du vill hitta hyperbolisk tangent för |


## If

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| logical_test | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE |
| value_if_true | Värdet som du vill returnera om argumentet logical_test utvärderas till TRUE. (Det här argumentet är som standard 0 om det inte inkluderas.) |
| value_if_false | Värdet som du vill returnera om argumentet logical_test utvärderas till FALSE. (Det här argumentet är som standard 0 om det inte inkluderas.) |


## Mindre än

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**


Utdata är antingen 0 (false) eller 1 (true).


| Argument | Beskrivning |
|---|---|
| metric_X | |
| metric_Y | |


### Exempel

`Metric 1 < Metric 2`

## Mindre än eller lika med

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

Mindre än eller lika med. Utdata är antingen 0 (false) eller 1 (true).


| Argument | Beskrivning |
|---|---|
| metric_X | |
| metric_Y | |

### Exempel

`Metric 1 <= Metric 2`



## Linjär regression: Korrelationskoefficient

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mått som du vill korrelera med metric_Y |
| metric_Y | Ett mått som du vill korrelera med metric_X |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Linear regression: Intercept

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Linear regression: Predicated Y

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Linjär regression: Lutning

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Loggbas 10

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Det positiva realtal som du vill ha bas-10-logaritmen för |


## Loggregression: Korrelationskoefficient

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mått som du vill korrelera med metric_Y |
| metric_Y | Ett mått som du vill korrelera med metric_X |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Loggregression: Korsning

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Loggregression: Förväntat Y

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Loggregression: Långsam

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Naturlig logg

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**


Returnerar den naturliga logaritmen för ett tal. Naturliga logaritmer baseras på konstanten e (2.71828182845904). LN är inversen till EXP-funktionen.


| Argument | Beskrivning |
|---|---|
| mått | Det positiva realtal som du vill ha den naturliga logaritmen för |



## Inte

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL NOT(logical)]**


Negation som boolesk. Utdata är antingen 0 (false) eller 1 (true).


| Argument | Beskrivning |
|---|---|
| logisk | Obligatoriskt. Ett värde eller uttryck som kan utvärderas till TRUE eller FALSE |



## Inte lika med

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


Inte lika med. Utdata är antingen 0 (false) eller 1 (true).


| Argument | Beskrivning |
|---|---|
| metric_X | |
| metric_Y | |

### Exempel

`Metric 1 != Metric 2`


## eller

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| logical_test | Kräver minst en parameter, men kan ha ett valfritt antal parametrar. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE |


>[!NOTE]
>
>0 (noll) betyder False och alla andra värden är True.


## Pi

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Returnerar Pi: 3,14159...


## Effektregression: Korrelationskoefficient

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mått som du vill korrelera med metric_Y |
| metric_Y | Ett mått som du vill korrelera med metric_X |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Strömregression: Skärpning

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Strömregression: Förväntat Y

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Strömregression: Långsam

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Kvadratisk regression: Korrelationskoefficient

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mått som du vill korrelera med metric_Y |
| metric_Y | Ett mått som du vill korrelera med metric_X |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |

## Kvadratisk regression: Intercept

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Kvadratisk regression: Förväntat Y

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |

## Kvadratisk regression: Långsam

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |



## Ömsesidig regression: Korrelationskoefficient

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mått som du vill korrelera med metric_Y |
| metric_Y | Ett mått som du vill korrelera med metric_X |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Ömsesidig regression: Skärpning

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Ömsesidig regression: Förväntat Y

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## Ömsesidig regression: Lutning

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabell]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| metric_X | Ett mätvärde som du vill ange som beroende data |
| metric_Y | Ett mätvärde som du vill ange som oberoende data |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |




## Sinus

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Vinkeln i radianer som du vill ha sinus för |




## T-poäng

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**


Avvikelsen från [MEAN](cm-functions.md#mean), dividerad med standardavvikelsen. Alias för [Z-bakgrundsmusik](#z-score).


| Argument | Beskrivning |
|---|---|
| mått | Det mätvärde som du vill ha T-poäng för |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |


## T-test

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails)]**


Utför ett m-tailed t-test med t-score på x och n frihetsgrader.


| Argument | Beskrivning |
|---|---|
| mått | Det mätvärde som du vill utföra T-testet på |
| grader | Frihetsgrader |
| svans | Längden på svansen som ska användas för T-testet |

### Information

Underskriften är T-TEST(metrisk, grader, svans). Under anropet anropas bara ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Den här funktionen liknar funktionen **[Z-TEST](#z-test)** som kör ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**.

- ***m*** är antalet svans.
- ***n*** är antalet frihetsgrader och ska vara ett konstant tal för hela rapporten, d.v.s. inte ändras rad för rad.
- ***x*** är T-teststatistik och skulle ofta vara en formel (till exempel **[Z-SCORE](#z-score)**) baserad på ett mätvärde och utvärderas på varje rad.

Returvärdet är sannolikheten att se provningsvärdet x med hänsyn till antalet frihetsgrader och antalet svansar.

**Exempel:**

1. Använd funktionen för att hitta avvikelser:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Kombinera funktionen med **[IF](#if)** om du vill ignorera mycket höga eller låga avhoppsfrekvenser och räkna sessioner med allt annat:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```




## Tangent

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**


Returnerar tangenten för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.


| Argument | Beskrivning |
|---|---|
| mått | Vinkeln i radianer som du vill ha tangenten för |



## Z-poäng

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**


[!BADGE Rad]{type="Neutral"}


| Argument | Beskrivning |
|---|---|
| mått | Det mätvärde som du vill ha Z-poängen för |
| include_zeros | Om nollvärden ska inkluderas eller inte i beräkningarna |

Ett Z-värde på 0 (noll) innebär att poängen är samma som medelvärdet. Ett Z-värde kan vara positivt eller negativt, vilket anger om det ligger över eller under medelvärdet och hur många standardavvikelser.

Ekvationen för Z-score är:

![](assets/z_score.png)

***[!DNL x]*** är råpoängen, ***[!DNL μ]*** är medelvärdet för populationen och ***[!DNL σ]*** är standardavvikelsen för populationen.

>[!NOTE]
>
>***[!DNL μ]*** (mu) och ***[!DNL σ]*** (sigma) beräknas automatiskt utifrån måttet.



## Z-test

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**


Utför ett n-tailed z-test med z-score x.


| Argument | Beskrivning |
|---|---|
| mått | Det mätvärde som du vill utföra ett Z-test på |
| svans | Längden på svansen som ska användas för Z-testet |

>[!NOTE]
>
>Anta att värdena normalt fördelas.









<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->