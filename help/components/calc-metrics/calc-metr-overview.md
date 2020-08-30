---
title: Översikt över beräknade mått
description: 'Läs mer om '
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 5%

---


# Översikt över beräknade mått

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Beräknade och avancerade beräknade (eller härledda) mått är anpassade mått som du kan skapa från befintliga mått. Våra verktyg för beräkning av mått erbjuder ett mycket flexibelt sätt att bygga, hantera och bota mått. De gör det möjligt för dig som marknadsförare, produktansvariga och analytiker att ställa frågor om data utan att behöva ändra dina [!DNL Analytics] genomförande.

Ni kan

* Skapa filtrerade mått som härleds vid rapportkörning. [utan att behöva ändra genomförandet](https://youtu.be/CuQTm9RaUpY). Dessa kan ses historiskt eftersom de baseras på filter.
* Dela mått över rapportuppsättningar. Detta innebär att alla nyskapade mått gäller för alla rapportpaket i samma inloggningsföretag.
* (Endast avancerade beräknade mått) Filter på mått. Du kan t.ex. skapa ett mått för &quot;Nya besökare&quot;, med ett antal personer som detta är den första sessionen för.
* (Endast avancerade beräknade mått) Inkludera statistiska funktioner som hjälper dig att bättre beskriva dina data. Du kan till exempel räkna antalet objekt i en rapport eller lägga till antalet standardavvikelser för varje objekt.

## Beräknade mått kontra avancerade beräknade mått

Här följer en jämförelse mellan funktionerna för Beräknade mått och Avancerade beräknade mått:

| Builder-alternativ | Beräknade mätvärden | Avancerade beräknade (härledda) mått |
|---|---|---|
| Formattyper (decimal, tid, procent, valuta) | Ja | Ja |
| Förändring av attribut (standard, linjär, deltagande osv.) | Ja | Ja |
| Metriska typer (standard, summa | Ja | Ja |
| Grundläggande operatorer (lägg till, subtrahera, multiplicera, dela) | Ja | Ja |
| Använd filter | Nej | Ja |
| [Grundläggande funktioner (antal, abvärde, medelvärde osv.)](/help/components/calc-metrics/cm-functions.md) | Nej | Ja |
| [Avancerade funktioner (regression, om/då, t-score osv.)](/help/components/calc-metrics/cm-adv-functions.md) | Nej | Ja |

## Verktyg

| Verktyg | Kapacitet |
|--- |--- |
| Beräknad metrisk Builder | <ul><li>Skapa beräknade och avancerade beräknade mått med hjälp av avancerade allokeringsmodeller.</li><li>Lägg till filter i metriska formler.</li><li>Jämför filter i samma rapport. Jämför till exempel lokala besökare jämfört med internationella besökare.</li><li>Använd statistiska funktioner.</li><li> Lämna detaljerade metriska beskrivningar (visa vad det gör, var det ska användas, var det inte ska användas).</li><li>Kopiera definitioner till nya mått.</li><li>Ange en textbunden metrisk förhandsvisning.</li><li>Ange metrisk polaritet, som anger om det är bra eller dåligt om en viss anpassad händelse (metrisk händelse) ökar.</li><li>Taggmått.</li></ul> |
| Hanterare för beräknade mätvärden | <ul><li>Dela mått med andra.</li><li>Godkänn och kurera mått.</li><li>Ordna (tagga) måtten så att personer kan hitta dem.</li><li>Ta bort mått.</li><li>Byt namn på mått.</li></ul> |
| API för beräknade mått | Del av API-uppsättningen Adobe Analytics 2.0. |

