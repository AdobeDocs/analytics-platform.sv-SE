---
title: Översikt över filter
description: Förstå vilka filter som används för och hur du skapar ett enkelt filter.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
source-git-commit: d045ecf73f7e15940510b764814fb853222e88cc
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 1%

---


# Översikt över filter {#overview}

Med Customer Journey Analytics kan ni skapa, hantera, dela och tillämpa kraftfulla filter för riktade målgrupper i era rapporter. Med filter kan du identifiera delmängder av personer baserat på egenskaper eller interaktioner. Filter är utformade som kodade målgruppsinsikter som du kan bygga för dina specifika behov och sedan verifiera, redigera och dela med andra teammedlemmar.

Filter kan baseras på

- attribut (webbläsartyp, enhet, antal besök, land, kön),
- interaktioner (kampanjer, nyckelordssökning, sökmotor),
- utträde och tävlingsbidrag (personer från Facebook,
- en definierad landningssida (hänvisande domän),
- anpassade variabler (formulärfält, definierade kategorier, kund-ID),
- och andra kriterier.

Du kan skapa och spara filter i Filter Builder eller generera filter från en utfallsvisualisering (i Workspace). Dessutom kan filter användas tillsammans som staplade filter.

Filtreringen innehåller [Filter Builder](/help/components/filters/filter-builder.md) för att skapa filter och köra ett förtest samt [Filterhanteraren](/help/components/filters/manage-filters.md) för att samla in, tagga, godkänna, ställa in säkerhet och dela filter i hela organisationen.

Det högsta antalet filter som du kan skapa per IMS-organisation är 50 000.

## Filtertyper {#types}

Mer information om tillgängliga typer av filter och hur du skapar dem finns i [Skapa filter](/help/components/filters/create-filters.md).

## Sekventiella filter {#sequential}

Med hjälp av sekventiella filter kan du identifiera personer baserat på navigering och sidvisning på webbplatsen, vilket ger ett filter med definierade åtgärder och interaktioner. Med hjälp av sekventiella filter kan du identifiera vad en person gillar och vad en person undviker. När du skapar sekventiella filter används operatorn THEN för att definiera och ordna personnavigering.

>[!IMPORTANT]
>
>Du måste ha **Välj** för att skapa sekventiella flerkanalsfilter. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har. &#x200B;

Här är ett exempel:

| Session ett | Session två | Session tre |
| --- | --- | --- |
| Personen gick till huvudlandningssidan A, exkluderade kampanjsidan B och visade sedan produktsidan C. | Personen gick åter till huvudlandningssidan A, exkluderade kampanjsidan B, och gick tillbaka till produktsidan C och sedan till en ny sida D. | Personen angav och följde samma väg som i det första och andra besöket och uteslöt sedan sidan F för att gå direkt till produktsidan G. |

## Filterbehållare {#containers}

Filter baseras på en hierarki på person-, session- och händelsenivå med hjälp av en kapslad behållarmodell. Med de kapslade behållarna kan du definiera personattribut och åtgärder baserat på regler mellan och inom behållarna.


<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Person</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Session</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Händelse</td>
</tr>
</table>

>[!NOTE]
>Personbehållaren kallades tidigare besökarbehållare. Sessionsbehållaren kallades besöksbehållaren och händelsebehållaren var tidigare Träff-behållaren.

Ett filter anger villkor för att filtrera en person baserat på personens attribut eller interaktioner med din plats. Om du vill ange villkor i ett filter anger du regler för att filtrera personer baserat på personegenskaper och/eller navigeringsegenskaper. Om du vill dela upp persondata ytterligare kan du filtrera baserat på specifika besök och/eller sidvisningsträffar för varje person. I Filter Builder finns en enkel arkitektur som du kan använda för att skapa dessa delmängder och tillämpa regler som kapslade, hierarkiska person-, session- eller händelsebehållare.

Behållararkitekturen som används i Filter Builder definierar Person som den yttersta behållaren, med överliggande data som är specifika för personen vid besök och sidvyer. Med en kapslad sessionsbehållare kan du ange regler för att dela upp persondata baserat på sessioner, och med en kapslad händelsebehållare kan du dela upp personinformation baserat på enskilda sidvyer. Med varje behållare kan du rapportera över en persons historik, interaktioner uppdelade efter sessioner eller dela upp enskilda händelser.

### Personbehållare {#person}

Personbehållaren innehåller alla besök och sidvisningar för personer inom en viss tidsperiod. Ett filter på personnivå returnerar den sida som uppfyller villkoret plus alla andra sidor som visas av personen (och som bara begränsas av definierade datumintervall). Rapporterna som genereras på personbehållarnivå är den vanligaste behållaren och returnerar sidvisningar för alla besök. Du kan generera en flerbesöksanalys. Det innebär att personbehållaren är den som kan ändras mest baserat på definierade datumintervall.
Personbehållare kan innehålla värden som baseras på en persons övergripande historik:

- Dagar före första köp
- Ursprunglig startsida
- Ursprungliga referensdomäner

### Sessionsbehållare {#session}

Med sessionsbehållaren kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session. Sessionsbehållaren är den vanligaste behållaren eftersom den fångar beteenden för hela besökssessionen när regeln har uppfyllts. Med sessionsbehållaren kan du också definiera vilka sessioner som du vill inkludera eller exkludera när du skapar och använder ett filter. Den kan hjälpa dig att svara på följande frågor:

- Hur många sessioner har varit kopplade till datakällor för både webben och Call Center?
- Vilka sidor bidrog till en lyckad konvertering till en försäljning?

Sessionsbehållare innehåller värden som baseras på förekomst per session:

- Sessionstyp
- Startsida
- Återbesöksfrekvens
- Deltagandemått
- Linjärt allokerade mätvärden

### Händelsebehållare {#event}

Händelsebehållaren definierar vilka sidhändelser som du vill inkludera eller exkludera från ett filter. Det är den mest smala av de tillgängliga behållarna så att du kan identifiera specifika klick och sidvy där ett villkor är uppfyllt. Med händelsebehållaren kan du visa en enskild spårningskod eller isolera beteenden i ett visst avsnitt på platsen. Du kanske också vill hitta ett specifikt värde när en åtgärd inträffar, till exempel marknadsföringskanalen när en beställning har gjorts.

Händelsebehållare innehåller värdebaserade ensidesindelningar:

- Produkter
- Visa utkast
- Listdimensioner
- Marknadsföringsdimensioner (i samband med händelser)

## Inkörbar filtermall {#template}

Traditionell analys innehåller en mängd färdiga mallar och beräknade mätvärden. Många av dem gäller inte i Customer Journey Analytics, eller måste namnändras eller återskapas. Andra är beroende av en lösning för sammanhangsberoende variabler i Customer Journey Analytics.

| Filternamn | Beskrivning |
| --- | --- |
| Alla data | Alla data är ett obligatoriskt filter som läggs till dynamiskt i rapporter när ett mätvärde läggs till på raden i en frihandstabell. |
