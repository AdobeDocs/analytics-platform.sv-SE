---
title: Inställningar för delsträngskomponent
description: Använd en delmängd av en sträng som dimensionsobjekt.
solution: Customer Journey Analytics
feature: Data Views
exl-id: a763027e-68f7-4f0a-8082-85db5283c8e3
source-git-commit: 0178babcd5ae87b491e849c7517eb5792fb14af1
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 1%

---

# [!UICONTROL Substring] komponentinställningar

[!UICONTROL Substring] Med komponentinställningarna kan du utföra flera strängredigeringsmetoder för att få fram önskade dimensionsobjekt i rapporter.

[!UICONTROL Substring] är bara tillgängligt för dimensioner och är retroaktivt för de data som det tillämpas på. Det är en omedelbar dataomvandling som sker innan filtrering eller andra analysåtgärder tillämpas.

![Inställningar för delsträng](../assets/substring-settings.png)

## Från vänster/höger

Ta en del av en sträng baserat på dess position till början eller slutet av en sträng. **[!UICONTROL From the Left]** och **[!UICONTROL From the Right]** metoder har två listrutor: **[!UICONTROL From]** (där utdata börjar) och **[!UICONTROL To]** (där utdata slutar).

* **[!UICONTROL String Start]**: Strängens början.
* **[!UICONTROL String End]**: Strängens slut.
* **[!UICONTROL Position]**: Ett statiskt antal tecken från vänster eller höger, beroende på metoden.
* **[!UICONTROL String]**: Matcha ett tecken eller en teckensekvens för att ange början eller slutet av en sträng. I den här listrutan visas även ytterligare alternativ:
   * **[!UICONTROL Match]**: Strängen som ska matchas. Om indata inte matchar det här fältet [Inga värdealternativ](no-value-options.md) gäller.
   * **[!UICONTROL Index]**: The **[!UICONTROL Match]** -villkor kan finnas flera gånger i en sträng. Det här heltalet avgör vilken matchning som ska användas för att starta eller avsluta utdata, beroende på metoden. Ett index på `1` representerar den första matchningen. Om indexvärdet är högre än antalet matchningar som är tillgängliga, [Inga värdealternativ](no-value-options.md) gäller.
   * **[!UICONTROL Include String]**: En kryssruta som innehåller **[!UICONTROL Match]** i utdata om det är aktiverat.
* **[!UICONTROL Length]**: Ett heltal som anger det teckenantal som ska inkluderas efter startpositionen för utdata. Endast tillgängligt under **[!UICONTROL To]** listruta.

## Avgränsare

Använd den här metoden för fält där en avgränsare används för att avgränsa flera strängvärden. Du kan antingen extrahera ett enskilt element som ska användas som utdata eller konvertera strängen till ett objektarrayschemaelement.

* **[!UICONTROL Criterion]**: Hur du vill behandla den avgränsade listan med värden.
   * **[!UICONTROL From the Left]**: Börja från början av den avgränsade listan och räkna framåt.
   * **[!UICONTROL From the Right]**: Börja i slutet av den avgränsade listan och räkna bakåt.
   * **[!UICONTROL Convert to array]**: Behandla den här dimensionen som om den är ett objektmatrisschemaelement.
* **[!UICONTROL Delimiter]**: Den avgränsare som fältet använder.
* **[!UICONTROL Index]**: Endast tillgängligt om villkoret är Från vänster/höger. Elementnumret som om det fanns i en array. Om strängindata till exempel är `"Fox,Turtle,Rabbit,Wolf"` med indexvärdet 3 är utdata `"Rabbit"`. Om indexvärdet är högre än antalet avgränsade element, [Inga värdealternativ](no-value-options.md) gäller.

## URL-analys

För användning med fält som innehåller URL-adresser. Använda exempel-URL `https://example.com/store/index.html?cid=campaign#cart`, finns följande alternativ:

* **[!UICONTROL Get protocol]**: Hämta URL:ens protokoll. Exempel, `"https://"`.
* **[!UICONTROL Get host]**: Hämta URL:ens värd. Exempel, `"example.com"`.
* **[!UICONTROL Get path]**: Hämta URL:ens sökväg. Exempel, `"store/index.html"`.
* **[!UICONTROL Get query string value]**: Hämta värdet från en enskild frågesträng. Placera den önskade frågesträngsparametern i **[!UICONTROL Query key]** fält. Om ovanstående URL används med `"cid"` frågenyckel, utdata är `"campaign"`.
* **[!UICONTROL Get hash value]**: Hämta URL:ens hash-värde. Exempel, `"cart"`.

Om indata inte är en giltig URL eller om den önskade URL-komponenten saknas, [Inga värdealternativ](no-value-options.md) gäller.

## Rensa

Trimma tomt utrymme eller specialtecken från strängen.

* **[!UICONTROL Trim whitespaces]**: En kryssruta som tar bort allt tomt utrymme i början och slutet av strängen om den är aktiverad.
* **[!UICONTROL Trim special characters]**: En kryssruta som visar en **[!UICONTROL Special characters]** indatafält om aktiverat. Alla tecken i det här fältet tas bort från utdata. Flerbytetecken stöds inte.

## Regex

Använd reguljära uttryck på en dimension för att hämta det önskade värdet.

* **[!UICONTROL Regex]**: Formeln för det reguljära uttrycket.
* **[!UICONTROL Output format]**: Ett valfritt fält där du kan lägga till text eller ordna om regex-utdata för undergrupper. Om det här fältet är tomt är strängutdata det utvärderade regex-uttrycket.
* **[!UICONTROL Case sensitive]**: En kryssruta som tvingar det reguljära uttrycket att vara skiftlägeskänsligt om det är aktiverat.

CJA använder en delmängd av Perl-regex-syntaxen. Om indata inte matchar det reguljära uttrycket och **[!UICONTROL Output format]** är tom, [Inga värdealternativ](no-value-options.md) gäller. Följande uttryck stöds:

| Uttryck | Beskrivning |
| --- | --- |
| `a` | Ett enda tecken `a`. |
| `a|b` | Ett enda tecken `a` eller `b`. |
| `[abc]` | Ett enda tecken `a`, `b`, eller `c`. |
| `[^abc]` | Ett enda tecken förutom `a`, `b`, eller `c`. |
| `[a-z]` | Ett enstaka tecken i intervallet `a`-`z`. |
| `[a-zA-Z0-9]` | Ett enstaka tecken i intervallet `a`-`z`, `A`-`Z`, eller siffror `0`-`9`. |
| `^` | Matchar början av raden. |
| `$` | Matchar radens slut. |
| `\A` | Strängstart. |
| `\z` | Strängslut. |
| `.` | Matchar alla tecken. |
| `\s` | Alla blankstegstecken. |
| `\S` | Alla tecken som inte är blanksteg. |
| `\d` | Alla siffror. |
| `\D` | Alla icke-siffror. |
| `\w` | Alla bokstäver, siffror eller understreck. |
| `\W` | Alla tecken som inte är ord. |
| `\b` | Alla ordgränser. |
| `\B` | Alla tecken som inte är en ordgräns. |
| `\<` | Ordets början. |
| `\>` | Slut på ordet. |
| `(...)` | Fånga allt inneslutet. |
| `(?:...)` | Ej markerad hämtning. Förhindrar att matchningen refereras i utdatasträngen. |
| `a?` | Noll eller något av `a`. |
| `a*` | Noll eller mer av `a`. |
| `a+` | En eller flera av `a`. |
| `a{3}` | Exakt 3 av `a`. |
| `a{3,}` | 3 eller fler av `a`. |
| `a{3,6}` | Mellan 3 och 6 av `a`. |

Utdataplatshållare stöds också. Du kan använda dessa sekvenser i **[!UICONTROL Output format]** hur många gånger och i vilken ordning som helst för att uppnå önskat strängresultat.

| Utdataplatshållarsekvens | Beskrivning |
| --- | --- |
| `$&` | Visar det som matchade hela uttrycket. |
| `$n` | Matchar det n:te underuttrycket. Till exempel: `$1` returnerar det första underuttrycket. |
| ``$` `` | Texten skapas mellan slutet av den senaste matchningen (eller början av texten om ingen tidigare matchning hittades) och början av den aktuella matchningen. |
| `$+` | Matchar det senast markerade deluttrycket i det reguljära uttrycket. |
| `$$` | Utdata för strängtecknet `"$"`. |

## Video om bindningsdimensioner

Här är en video om bindningsdimensioner:

>[!VIDEO](https://video.tv.adobe.com/v/342694/?quality=12)
