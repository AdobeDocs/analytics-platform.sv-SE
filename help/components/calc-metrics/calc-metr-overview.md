---
title: Översikt över beräknade mätvärden
description: 'Läs mer om '
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 5%

---


# Översikt över beräknade mätvärden

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Beräknade och avancerade beräknade (eller härledda) mått är anpassade mått som du kan skapa utifrån befintliga mätvärden. Våra verktyg för beräknade värden är ett mycket flexibelt sätt att bygga, hantera och strukturera mätvärden. Med dem kan ni som marknadsförare, produktchefer och analytiker ställa frågor om data utan att behöva ändra er [!DNL Analytics] implementering.

Ni kan

* Skapa filtrerade mätvärden som genereras vid rapportkörning, [utan att behöva ändra implementeringen](https://youtu.be/CuQTm9RaUpY). Dessa kan visas historiskt eftersom de baseras på filter.
* Dela mätvärden mellan olika rapportsviter. Det innebär att alla nya mätvärden gäller för alla rapportsviter i samma inloggningsföretag.
* (Endast avancerade beräknade värden) Filtrera på mätvärden. Du kan t.ex. skapa ett mått för&quot;Nya besökare&quot; med antalet personer som det här är den första sessionen för.
* (Endast avancerade beräknade värden) Inkludera statistiska funktioner som hjälper dig att beskriva dina data bättre. Du kan till exempel räkna antalet objekt i en rapport eller lägga till antalet standardavvikelser för varje objekt.

## Beräknade mått jämfört med avancerade beräknade värden

Här följer en jämförelse av funktionerna för beräknade värden och avancerade beräknade värden:

| Alternativ för verktyget Builder | Beräknade mätvärden | Avancerade beräknade (härledda) mått |
|---|---|---|
| Formattyper (decimal, time, percent, currency | Ja | Ja |
| Attributionsändringar (standard, linjär, deltagande osv.) | Ja | Ja |
| Mättyper (standard, total | Ja | Ja |
| Grundläggande operatorer (lägg till, subtrahera, multiplicera, dividera) | Ja | Ja |
| Använda filter | Nej | Ja |
| [Grundfunktioner (antal, abs-värde, medelvärde osv.)](/help/components/calc-metrics/cm-functions.md) | Nej | Ja |
| [Avancerade funktioner (regression, if/then, t-score etc.)](/help/components/calc-metrics/cm-adv-functions.md) | Nej | Ja |

## verktyg

| Verktyg | Funktioner |
|--- |--- |
| Beräknad metrisk Builder | <ul><li>Skapa beräknade och avancerade beräknade värden med avancerade allokeringsmodeller.</li><li>Lägg till textbundna filter i metriska formler.</li><li>Jämför filter i samma rapport. Exempel: jämför lokala besökare med internationella besökare.</li><li>Använd statistiska funktioner.</li><li> Ange detaljerade måttbeskrivningar (visa vad den gör, var den ska användas, var den inte ska användas).</li><li>Kopiera definitioner till nya mätvärden.</li><li>Ange en intern metrisk förhandsgranskning.</li><li>Ange metrisk polaritet, vilket anger om det är bra eller dåligt om en viss anpassad händelse (metrisk) inträffar.</li><li>Märk måtten.</li></ul> |
| Hanterare för beräknade mätvärden | <ul><li>Dela mätvärden med andra.</li><li>Godkänn och strukturera mätvärden.</li><li>Ordna (tagga) mätvärden så att andra kan hitta dem.</li><li>Ta bort mätvärden.</li><li>Byt namn på mätvärden.</li></ul> |
| API för beräknade värden | Ingår i Adobe Analytics 2.0 API. |

