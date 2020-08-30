---
title: Referens - grundläggande funktioner
description: 'Med verktyget Calculated Metrics Builder kan du använda statistiska och matematiska funktioner för att skapa avancerade beräknade mått. '
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 2%

---


# Referens - grundläggande funktioner

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Med verktyget Calculated Metrics Builder kan du använda statistiska och matematiska funktioner för att skapa avancerade beräknade mått.

Här följer en alfabetisk lista över funktioner och definitioner.

>[!NOTE]
>
>Om [!DNL metric] är identifierat som ett argument i en funktion, men andra måttuttryck är också tillåtna. Exempelvis [!DNL MAXV(metrics)] även [!DNL MAXV(PageViews + Visits).]

## Tabellfunktioner kontra radfunktioner

En tabellfunktion är en funktion där utdata är desamma för varje rad i tabellen. En radfunktion är en funktion där utdata skiljer sig åt för varje rad i tabellen.

## Absolut värde (rad)

Returnerar det absoluta värdet för ett tal. Det absoluta värdet för ett tal är talet med ett positivt värde.

```
ABS(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mått för vilket du vill ha det absoluta värdet. |

## Kolumn max

Returnerar det största värdet i en uppsättning dimensionselement för en metrisk kolumn. MAXV utvärderar vertikalt inom en enskild kolumn (metrisk) över dimensionselement.

```
MAXV(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Ett mått som du skulle ha velat utvärdera. |

## Kolumn minst

Returnerar det minsta värdet i en uppsättning dimensionselement för en metrisk kolumn. MINV utvärderar lodrätt inom en enskild kolumn (metrisk) över dimensionselement.

```
MINV(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Ett mått som du skulle ha velat utvärdera. |

## Kolumnsumma

Lägger till alla numeriska värden för ett mått i en kolumn (över elementen i en dimension).

```
SUM(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mått för vilket du vill ha det totala värdet eller summan. |

## Antal (tabell)

Returnerar antalet eller antalet värden som inte är noll för ett mått i en kolumn (antalet unika element som rapporteras inom en dimension).

```
COUNT(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mått som du vill räkna. |

## Exponent (rad)

Returnerar *e* upphöjt till ett visst nummer. Konstanten *e* är lika med 2,71828182845904, basen av den naturliga logaritmen. EXP är inverteringen av LN, den naturliga logaritmen för ett tal.

```
EXP(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | exponenten som används på basen *e*. |

## Uppskattning

Energiansvarig

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*.. (y gånger)
</pre>

## Medelvärde (tabell)

Returnerar det aritmetiska medelvärdet eller medelvärdet för ett mått i en kolumn.

```
MEAN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Måttet som du vill ha medelvärdet för. |

## Median (tabell)

Returnerar medianvärdet för ett mått i en kolumn. Medianvärdet är talet i mitten av en uppsättning tal, d.v.s. hälften av talen har värden som är större än eller lika med medianvärdet och hälften är mindre än eller lika med medianvärdet.

```
MEDIAN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Måttet som du vill ha medianvärdet för. |

## Modulo

Återstoden av kol1 / kol2, med användning av Euclidean division.

Returnerar återstoden efter att x dividerats med y.

```
x = floor(x/y) + modulo(x,y)
```

Returvärdet har samma tecken som inmatningen (eller är noll).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Om du alltid vill få ett positivt tal använder du

```
modulo(modulo(x,y)+y,y)
```

## Percentil (tabell)

Returnerar den k:te percentilen för värden för ett mått. Med den här funktionen kan du fastställa ett tröskelvärde för godkännande. Du kan t.ex. bestämma dig för att undersöka dimensionselement som ligger över 90-percentilen.

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
   <td colname="col1"> <i>mått</i> </td> 
   <td colname="col2"> Den metriska kolumn som definierar relativ position. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> percentilvärdet i intervallet 0 till och med 100. </td> 
  </tr> 
 </tbody> 
</table>

## Kvartartikel (tabell)

Returnerar kvartilen med värden för ett mått. Kvartiler kan till exempel användas för att hitta de 25 procent av de bästa produkterna som ger mest avkastning. MINV, MEDIAN och MAXV ger samma värde som QUARTILE när quart är lika med 0 (noll), 2 respektive 4.

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
   <td colname="col1"> <i>mått</i> </td> 
   <td colname="col2"> Måttet som du vill ha kvartilvärdet för. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>kvast </p> </td> 
   <td colname="col2"> Anger vilket *värde som ska returneras. </td> 
  </tr> 
 </tbody> 
</table>

*Om *kvast* = 0, QUARTILE returnerar minimivärdet. Om *kvast* = 1, KVARTIL returnerar den första kvartilen (25 percentil). Om *kvast* = 2, KVARTIL returnerar den första kvartilen (50 percentil). Om *kvast* = 3, KVARTIL returnerar den första kvartilen (75 percentil). Om *kvast* = 4, QUARTILE returnerar maxvärdet.

## Rund

Returnerar närmaste heltal för ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har $569,34, använder du formeln Round( *Intäkter*) för att avrunda intäkter till närmaste dollar, eller 569 dollar. En produkt med 569,51 dollar kommer att vara runt till närmaste dollar, eller 570 dollar.

```
ROUND(metric)
```

| Argument | Beskrivning |
|---|---|
| *nummer* | Måttet du vill runda av. |

Rund utan sifferparameter är densamma som rund med en sifferparameter på 0, nämligen rund till närmaste heltal. Med en decimalparameter returneras så många decimaler till höger om decimalkommat. Om siffrorna är negativa returneras 0 till vänster om decimaltecknet.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Radantal

Returnerar antalet rader för en given kolumn (antalet unika element som rapporteras inom en dimension). &quot;Överskridna enheter&quot; räknas som 1.

## Radmax

Maximalt antal kolumner på varje rad.

## Radmin

Minsta antal kolumner på varje rad.

## Radsumma

Summan av kolumnerna på varje rad.

## Kvadratisk rot (rad)

Returnerar den positiva kvadratroten för ett tal. Kvadratroten för ett tal är värdet för det tal som upphöjts till effekten 1/2.

```
SQRT(metric)
```

| Argument | Beskrivning |
|---|---|
| *nummer* | Måttet som du vill ha kvadratroten för. |

## Standardavvikelse (tabell)

Returnerar standardavvikelsen, eller kvadratroten av variansen, baserat på en provpopulation data.

Ekvationen för STDEV är:

![](assets/std_dev.png)

där x är provets medelvärde (*mått* och *n* är provstorleken.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Beskrivning</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> mått</i> </b> </td> 
   <td> <p> Det mått som du vill använda för standardavvikelsen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varians (tabell)

Returnerar variansen baserat på en provpopulation med data.

Ekvationen för VARIANCE är:

![](assets/variance_eq.png)

där x är provets medelvärde, MEAN(*mått*) och *n* är provstorleken.

```
VARIANCE(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Måttet som du vill ha variansen för. |

Om du vill beräkna en varians tittar du på en hel sifferkolumn. Från den nummerlistan beräknar du först medelvärdet. När du har genomsnittet går du igenom varje post och gör följande:

1. Ta bort medelvärdet från talet.

2. Fyrkantigt resultat.

3. Lägg till det till summan.

När du har itererat över hela kolumnen har du en enda summa. Sedan delar du upp summan efter antalet objekt i kolumnen. Det talet är variansen för kolumnen. Det är ett enda nummer. Den visas dock som en numreringskolumn.

Låt oss till exempel säga att du har en kolumn med tre element:

1

2

3

Genomsnittet för den här kolumnen är 2. Kolonnens avvikelse skall vara ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. I ad hoc-analysen kommer detta att se ut så här:

1 2/3

2/3

3 2/3
