---
title: Översikt över filter
description: Förstå vilka filter som används för och hur du skapar ett enkelt filter.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: ff1f28015a2c52f79fae975c16bb7cb76f6179c3
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 1%

---

# Översikt över filter

Med Customer Journey Analytics kan ni skapa, hantera, dela och tillämpa kraftfulla filter för riktade målgrupper i era rapporter. Med filter kan du identifiera undergrupper av besökare baserat på egenskaper eller webbplatsinteraktioner. Filter är utformade som kodade målgruppsinsikter som du kan bygga för dina specifika behov och sedan verifiera, redigera och dela med andra teammedlemmar.

Filter kan baseras på attribut (webbläsartyp, enhet, antal besök, land, kön), interaktioner (kampanjer, nyckelordssökning, sökmotor), utgångar och poster (besökare från Facebook, en definierad landningssida, referensdomän), anpassade variabler (formulärfält, definierade kategorier, kund-ID) och andra kriterier.

Du kan skapa och spara filter i Filter Builder eller generera filter från en utfallsvisualisering (i Workspace). Dessutom kan filter användas tillsammans som staplade filter.

Filtreringen innehåller [Filter Builder](/help/components/filters/create-filters.md) för att konstruera filter och köra ett förtest samt [Filter Manager](/help/components/filters/manage-filters.md) för att samla in, tagga, godkänna, ställa in säkerhet och dela filter i hela organisationen.

## Filtertyper

Du kan skapa olika typer av filter i Workspace och Filter Builder, beroende på hur komplexa de behöver vara, om de bara ska gälla för det här projektet osv. Här följer en sammanfattning av filtertyper:

| Filtertyp | Skapad var? | Tillämpligt var? | När ska användas |
| --- | --- | --- | --- |
| Komponentlistefilter | Klicka på +, vilket tar dig till [Filter Builder](/help/components/filters/create-filters.md) | Alla arbetsyteprojekt | För mer komplexa filter, sekventiella filter |
| Snabbfilter | [Snabbfilterverktyg](/help/components/filters/quick-filters.md) | Endast projekt, men du kan spara och lägga till i segmentlistan. | Flexibilitet att lägga till/redigera en eller flera regler |
| Ad hoc-projektfilter | [Dra och släpp i segmentsläppzonen i ett projekt](/help/components/filters/ad-hoc-filters.md) | Endast projekt, men du kan spara och lägga till i filterlistan. | För enkelradsfilter |
| Filter i bortfallsanalys | [Bortfallsvisualisering ](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) i Analysis Workspace | Till individuella utfallsvisualiseringar | Skapa filter från en kontaktyta, lägg till filter som kontaktyta och jämför viktiga arbetsflöden mellan olika filter |
| Beräknat mätningsbaserat filter | [Bygg beräknade mätvärden](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html) | Till individuellt beräknat mått | Använd filter i måttdefinitionen |

## Sekventiella filter

Med sekventiella filter kan du identifiera besökare baserat på navigering och sidvisning på webbplatsen, vilket ger ett filter med definierade åtgärder och interaktioner. Med sekventiella filter kan du identifiera vad en besökare gillar och vad en besökare undviker. När sekventiella filter skapas används operatorn THEN för att definiera och ordna besökarnavigering.

Här är ett exempel:

![](assets/sequential_fil.png)

| Besök en | Besök två | Besök tre |
| --- | --- | --- |
| Besökaren gick till huvudlandningssidan (A), uteslöt kampanjsidan (B) och visade sedan produktsidan (C). | Besökaren gick åter till huvudlandningssidan (A), exkluderade kampanjsidan (B), gick tillbaka till produktsidan (C) och sedan till en ny sida (D). | Besökaren gick in på och följde samma väg som i det första och andra besöket och uteslöt sedan sidan F för att gå direkt till en målproduktsida (G). |

## Filterbehållare

Filter baseras på en hierarki på person-, sessions- och händelsenivå med hjälp av en kapslad behållarmodell. Med de kapslade behållarna kan du definiera personattribut och åtgärder baserat på regler mellan och inom behållarna.

>[!NOTE]
>Personbehållaren kallades tidigare besökarbehållare. Sessionsbehållaren kallades besöksbehållaren och händelsebehållaren var tidigare Träff-behållaren.

Ett filter anger villkor för att filtrera en besökare baserat på hans eller hennes attribut eller interaktioner med din webbplats. Om du vill ange villkor i ett filter anger du regler för att filtrera besökare baserat på besökarens egenskaper och/eller navigeringsegenskaper. Om du vill dela upp besöksdata ytterligare kan du filtrera baserat på specifika besök och/eller sidvisningsträffar för varje besökare. I Filter Builder finns en enkel arkitektur som du kan använda för att skapa dessa delmängder och tillämpa regler som kapslade, hierarkiska person-, session- eller händelsebehållare.

Behållararkitekturen som används i Filter Builder definierar Person som den yttersta behållaren och innehåller övergripande data som är specifika för besökaren vid besök och sidvyer. Med en kapslad sessionsbehållare kan du ange regler för att dela upp besökarens data baserat på sessioner, och med en kapslad händelsebehållare kan du dela upp besökarinformation baserat på enskilda sidvyer. Med varje behållare kan du rapportera över en besökares historik, interaktioner uppdelade efter sessioner eller dela upp enskilda händelser.

### Personbehållare

Personbehållaren innehåller alla besök och sidvisningar för besökare inom en viss tidsperiod. Ett filter på personnivå returnerar den sida som uppfyller villkoret plus alla andra sidor som visas av besökaren (och som bara begränsas av definierade datumintervall). Som den mest omfattande behållaren kommer rapporter som genereras på personbehållarnivå att returnera sidvisningar för alla besök och göra att du kan generera en flerbesöksanalys. Det innebär att personbehållaren är den som kan ändras mest baserat på definierade datumintervall.
Personbehållare kan innehålla värden som baseras på en besökares övergripande historik:

* Dagar före första köp
* Ursprunglig startsida
* Ursprungliga referensdomäner

### Sessionsbehållare

Med sessionsbehållaren kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session. Sessionsbehållaren är den vanligaste behållaren eftersom den fångar upp beteenden för hela besökssessionen när regeln har uppfyllts och låter dig definiera vilka sessioner som du vill inkludera eller exkludera när du skapar och använder ett filter. Den kan hjälpa dig att svara på följande frågor:

* Hur många besökare tittade på News and Sports-delen i samma session?
* Vilka sidor bidrog till en lyckad konvertering till en försäljning?

Sessionsbehållare innehåller värden som baseras på förekomst per session:

* Sessionsnummer
* Startsida
* Återbesöksfrekvens
* Deltagandemått
* Linjärt allokerade mätvärden

### Händelsebehållare

Händelsebehållaren definierar vilka sidhändelser som du vill inkludera eller exkludera från ett filter. Det är den mest smala av de tillgängliga behållarna så att du kan identifiera specifika klick och sidvy där ett villkor är sant, så att du kan visa en enskild spårningskod eller isolera beteenden inom ett visst avsnitt på platsen. Du kanske också vill hitta ett specifikt värde när en åtgärd inträffar, till exempel marknadsföringskanalen när en beställning har gjorts.

Händelsebehållare innehåller värdebaserade ensidesindelningar:

* Produkter
* Visa utkast
* Listdimensioner
* Marknadsföringsdimensioner (i samband med händelser)

## Inkörbar filtermall

Traditionell analys innehåller många färdiga mallfilter (filter) och beräknade mätvärden. Många av dem gäller inte i CJA, eller måste namnändras eller återskapas. Andra är beroende av en lösning för sammanhangsberoende variabler i CJA.

| Filternamn | Beskrivning |
| --- | --- |
| Alla data | Det här är ett obligatoriskt filter som läggs till dynamiskt i rapporter när ett mätvärde läggs till på raden i en Freeform-tabell. |
