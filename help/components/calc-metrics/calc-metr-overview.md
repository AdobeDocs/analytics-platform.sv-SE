---
title: Översikt över beräknade mätvärden
description: Lär dig mer om filtrerade mätvärden som genereras vid rapportkörning.
feature: Calculated Metrics
exl-id: c9205c95-8b01-4177-a89c-038886f41d3d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 2%

---

# Översikt över beräknade mätvärden

Beräknade och avancerade beräknade (eller härledda) mått är anpassade mått som du kan skapa utifrån befintliga mätvärden. Våra verktyg för beräknade värden är ett mycket flexibelt sätt att bygga, hantera och strukturera mätvärden. Med dem kan ni som marknadsförare, produktchefer och analytiker ställa frågor om data utan att behöva ändra implementeringen.

Du kan

* Skapa filtrerade mätvärden som genereras vid rapportkörning, utan att behöva ändra implementeringen. Dessa kan visas historiskt eftersom de baseras på filter.
* (Endast avancerade beräknade värden) Filtrera på mätvärden. Du kan t.ex. skapa ett mått för&quot;Nya personer&quot; med antalet personer som detta är den första sessionen för.
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
| [Avancerade funktioner (regression, if/then, t-score etc)](/help/components/calc-metrics/cm-adv-functions.md) | Nej | Ja |

## verktyg

| Verktyg | Funktioner |
|--- |--- |
| Bygg beräknade mätvärden | <ul><li>Skapa beräknade och avancerade beräknade värden med avancerade allokeringsmodeller.</li><li>Lägg till textbundna filter i metriska formler.</li><li>Jämför filter i samma rapport. Exempel: jämför lokala personer med internationella.</li><li>Använd statistiska funktioner.</li><li> Tillhandahåll detaljerade måttbeskrivningar (visa vad den gör, var den ska användas, var den inte ska användas).</li><li>Kopiera definitioner till nya mätvärden.</li><li>Ange en intern metrisk förhandsgranskning.</li><li>Ange metrisk polaritet, vilket anger om det är bra eller dåligt om en viss anpassad händelse (metrisk) inträffar.</li><li>Märk måtten.</li></ul> |
| Beräknad måtthanterare | <ul><li>Dela mätvärden med andra.</li><li>Godkänn och strukturera mätvärden.</li><li>Ordna (tagga) mätvärden så att andra kan hitta dem.</li><li>Ta bort mätvärden.</li><li>Byt namn på mätvärden.</li></ul> |
| API för beräknade värden | En del av API-uppsättningen för Customer Journey Analytics. |

## Mallar för beräknade värden i Customer Journey Analytics

| Namn på beräknat mått | Beskrivning av beräknat mått |
| --- | --- |
| Sessioner per person | Genomsnittligt antal sessioner per person |
| Starthastighet för session | Den procentandel av tiden som ett dimensionsobjekt inträffade vid den första händelsen i en session. |
| Sessionens sluthastighet | Den procentandel av tiden som ett dimensionsobjekt inträffade för den senaste händelsen i en session. |
| Tilldelad tid per person | Den genomsnittliga tiden en person tillbringat på en given dimensionspost. |
| Tilldelad tid per session | Den genomsnittliga tiden en person tillbringat per session för ett givet dimensionsobjekt. |
