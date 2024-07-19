---
title: Översikt över filter
description: Förstå vilka filter som används för och hur du skapar ett enkelt filter.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 0%

---


# Översikt över filter {#overview}

Med Customer Journey Analytics kan ni skapa, hantera, dela och tillämpa kraftfulla filter för riktade målgrupper i era rapporter. Med filter kan du identifiera delmängder av personer baserat på egenskaper eller interaktioner. Filter är utformade som kodade målgruppsinsikter som du kan bygga för dina specifika behov och sedan verifiera, redigera och dela med andra teammedlemmar.

Filter kan baseras på

- attribut (webbläsartyp, enhet, antal besök, land, kön),
- interaktioner (kampanjer, sökningar, sökmotor),
- utgångar och inmatningar (personer från Facebook, en definierad landningssida, hänvisande domän, geofence-händelse),
- anpassade variabler (formulärfält, definierade kategorier, kund-ID),
- och andra kriterier.

Du kan skapa och spara filter i Filter Builder eller generera filter från en utfallsvisualisering (i Workspace). Dessutom kan filter användas tillsammans som staplade filter.

Filtreringen innehåller [Filter Builder](/help/components/filters/filter-builder.md) för att skapa filter och köra ett förtest samt [Filter Manager](/help/components/filters/manage-filters.md) för att samla in, tagga, godkänna, ställa in säkerhet och dela filter i hela organisationen.

Det högsta antalet filter som du kan skapa per IMS-organisation är 50 000.

## Filtertyper {#types}

Mer information om tillgängliga typer av filter och hur du skapar dem finns i [Skapa filter](/help/components/filters/create-filters.md).

## Sekventiella filter {#sequential}

Med sekventiella filter kan du identifiera personer baserat på navigering (sidvisningar på hela webbplatsen, interaktioner med scener i mobilappen eller med en meny i en digitalbox). Sekventiella filter ger ett filter med definierade åtgärder och interaktioner och hjälper dig att identifiera vad en person gillar och vad en person undviker. När du skapar sekventiella filter används operatorn THEN för att definiera och ordna personnavigering.

>[!IMPORTANT]
>
>Du måste ha paketet **Select** för att kunna skapa sekventiella filter för flera kanaler. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

Här är ett exempel:

| Session ett | Session två | Session tre |
| --- | --- | --- |
| Personen gick till huvudlandningssidan A, exkluderade kampanjsidan B och visade sedan produktsidan C. | Personen gick åter till huvudlandningssidan A, exkluderade kampanjsidan B, gick tillbaka till produktsidan C och sedan till en ny sida D. | Personen angav och följde samma väg som i det första och andra besöket och uteslöt sedan sidan F för att gå direkt till produktsidan G. |

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

Ett filter anger villkor för att filtrera en person baserat på personens attribut eller interaktioner med din webbplats, mobilapp eller annan enhetstyp som du har samlat in data från. Om du vill ange villkor i ett filter anger du regler för att filtrera personer baserat på personegenskaper och/eller navigeringsegenskaper. Om du vill dela upp personuppgifter ytterligare kan du filtrera baserat på specifika besök och/eller sidvisningstips, skärmklickningar och menyval i en digitalbox för varje person. Men filtrera också på attribut som du har inhämtat från ett CRM- eller lojalitetssystem. I Filter Builder finns en enkel arkitektur som du kan använda för att skapa dessa delmängder och tillämpa regler som kapslade, hierarkiska person-, session- eller händelsebehållare.

Behållararkitekturen som används i Filter Builder definierar Person som den yttersta behållaren. Behållaren innehåller data som är specifika för personen vid besök och sidvisningar, mobilskärmar eller menyskärmar i en digitalbox. Med en kapslad sessionsbehållare kan du ange regler för att dela upp persondata baserat på sessioner, och med en kapslad händelsebehållare kan du dela upp personinformation baserat på individuella interaktioner. Med varje behållare kan du rapportera en persons historik, interaktioner som delats upp av sessioner eller dela upp enskilda upplevelsehändelser.

### Personbehållare {#person}

Personbehållaren innehåller alla besök och sidvisningar, mobilappsskärmar, digitalboxar eller konsolspel för personer inom en viss tidsperiod. I stort sett alla upplevelsehändelser som ingår i de datauppsättningar som du har definierat i din Customer Journey Analytics-anslutning. Ett filter på personnivå returnerar de sidvyer, mobilappar eller digitalboxskärmar som uppfyller villkoret. Dessutom kan samma person interagera med andra kanaler, både online och offline (och endast begränsat av definierade datumintervall). Som den mest väldefinierade behållaren returnerar rapporter som genereras på personbehållarnivå sidvisningar, mobilappskärmar med mera, för alla besök och gör att du kan generera en flerkanalsanalys. Det innebär att personbehållaren är den som kan ändras mest baserat på definierade datumintervall.
Personbehållare kan innehålla värden som baseras på en persons övergripande historik:

- Dagar före första köpet
- Ursprunglig startsida eller startskärm för mobilapp
- Ursprungliga referensdomäner

### Sessionsbehållare {#session}

Med sessionsbehållaren kan du identifiera sidinteraktioner eller mobilappsinteraktioner, kampanjer eller konverteringar för en viss session. Sessionsbehållaren är den vanligaste behållaren eftersom den fångar beteenden för hela besökssessionen när regeln har uppfyllts. Med sessionsbehållaren kan du också definiera vilka sessioner som du vill inkludera eller exkludera när du skapar och använder ett filter. Den kan hjälpa dig att svara på följande frågor:

- Hur många sessioner har varit kopplade till datakällor för både webben och Call Center?
- Vilka sidor bidrog till en lyckad konvertering till en försäljning?

Sessionsbehållare innehåller värden som baseras på förekomst per session:

- Sessionstyp
- Inmatningssida
- Returfrekvens
- Deltagandemått
- Linjärt allokerade mätvärden

Med datavyer i Customer Journey Analytics kan du bestämma hur länge en session varar men också när en ny session ska skapas. Du kan till exempel definiera en ny mobilappssession baserat på varje gång en användare startar din mobilapp. Mer information finns i [Sessionsinställningar](/help/data-views/session-settings.md).

### Händelsebehållare {#event}

Händelsebehållaren definierar vilken sida, vilket mobilprogram eller annan typ av händelser som du vill inkludera eller exkludera från ett filter. Det är det smalaste av de tillgängliga behållarna så att du kan identifiera specifika klick, sidvy och knapp i en mobilapp där ett villkor är uppfyllt. Med händelsebehållaren kan du visa en enskild spårningskod eller isolera beteenden inom ett visst område i din mobilapp. Du kanske också vill hitta ett specifikt värde när en åtgärd inträffar, till exempel marknadsföringskanalen när en beställning har gjorts.

Händelsebehållare innehåller värdebaserade, ensidiga uppdelningar för:

- Produkter
- Visa utkast
- Listdimensioner
- Marknadsföringsdimensioner (i samband med händelser)

## Inkörbar filtermall {#template}

Traditionell analys innehåller ett flertal färdiga mallar och beräknade mätvärden. Många av dem gäller inte i Customer Journey Analytics, eller måste namnändras eller återskapas. Andra är beroende av en lösning för sammanhangsberoende variabler i Customer Journey Analytics.

| Filternamn | Beskrivning |
| --- | --- |
| Alla data | Alla data är ett obligatoriskt filter som läggs till dynamiskt i rapporter när ett mätvärde läggs till på raden i en frihandstabell. |
