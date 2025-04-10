---
title: Översikt över filter
description: Förstå vilka filter som används för och hur du skapar ett enkelt filter.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 392ba2b9cfe090901c3dac12459f9bd8d51fdca7
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 0%

---


# Översikt över filter

Med Customer Journey Analytics kan ni skapa, hantera, dela och lägga på kraftfulla filter för riktade målgrupper i era rapporter. Med filter kan du identifiera delmängder av personer, sessioner eller händelser baserat på egenskaper eller interaktioner. Filter är utformade som kodade målgruppsinsikter som du kan bygga för dina specifika behov och sedan verifiera, redigera och dela med andra teammedlemmar.

Filter kan baseras på:

- attribut (webbläsartyp, enhet, antal besök, land, kön),
- interaktioner (kampanjer, sökningar, sökmotor),
- utgångar och inmatningar (personer från Facebook, en definierad landningssida, hänvisande domän, geofence-händelse),
- anpassade variabler (formulärfält, definierade kategorier, kund-ID),
- och andra kriterier.

Se [Skapa filter](/help/components/filters/create-filters.md) för olika alternativ för att skapa filter. Sedan skapar, ändrar och sparar du definitionen av ett filter i [filterverktyget](filter-builder.md). Du kan också skapa snabbfilter med hjälp av [snabbfilterverktyget](quick-filters.md). Du kan också generera filter från visualiseringar i Workspace, till exempel med hjälp av visualiseringen [Utfall](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) .

Du använder [filterhanteraren](manage-filters.md) för att hantera filter.

## Planfilter

I synnerhet som administratör ökar den korrekta planeringen av filter riskerna för att filtren används. Tänk på följande när du planerar filter:

- **Målgrupp**: Vem använder dina filter? Se till att du anger en bra filterbeskrivning så att läsarna förstår:
   - Vad är det här filtret användbart för?

   - När ska jag använda det här filtret?

- **Omfång**: Vilken [Filterbehållare](#filter-containers) är bäst för de data du är ute efter? Använd den minsta möjliga behållaren.

- **Komponenter**: Bestäm vilka komponenter som ska inkluderas i filterdefinitionen och mot vilka värden villkoren ska validera.

- **Process**: Överväg en godkännandeprocess för filtret. Det finns inget arbetsflöde för godkännande i Customer Journey Analytics, men du kan fortfarande ordna en process för att avgöra om du godkänner ett filter eller inte.

- **Modularitet**: Definiera filter med modularitet i åtanke. Användarna av dina filter kan enkelt [stapla filter](filter-builder.md#stack-filters) för att skapa kraftfulla nya filter.


## Filtertyper

Du kan skapa tre typer av filter:

### Snabbfilter

Med snabbfilter kan du enkelt utforska data i ett visst Workspace-projekt, utan att behöva skapa ett filter i [Filter Builder](/help/components/filters/create-filters.md). Du definierar filtret direkt i Workspace gränssnitt. Mer information finns i [Snabbfilter](quick-filters.md).

### Vanliga filter

Med hjälp av regelbundna filter kan du identifiera data (personer, sessioner, händelser) baserat på ett eller flera villkor. Om det finns fler än ett villkor använder du logiska operatorer som And och Eller för att definiera filtret ytterligare. Du kan använda behållare för att gruppera villkor och skapa mer komplexa filter. Mer information finns i [Filterverktyget](filter-builder.md).

### Sekventiella filter

>[!IMPORTANT]
>
>Du måste ha paketet **Select** för att kunna skapa sekventiella filter för flera kanaler. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

Med sekventiella filter kan du identifiera data (personer, sessioner, händelser) baserat på navigering (sidvisningar på hela webbplatsen, interaktioner med scener i mobilappen eller med en meny i en digitalbox). Med sekventiella filter kan du till exempel identifiera vad en person gillar och vad en person undviker. Använd sedan den logiska operatorn för att definiera ett sekventiellt filter. Mer information finns i [Sekventiella filter](seg-sequential-build.md).


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Filterbehållare {#containers}

Filter baseras på en hierarki på person-, session- och händelsenivå med hjälp av en kapslad behållarmodell. Med de kapslade behållarna kan du definiera villkor mellan och inuti behållarna.


<table style="table-layout: fixed; border: none;" width="100%">

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
>
>För Adobe Analytics:
> 
> - Behållaren **Person** kallas i Adobe Analytics för **besökarbehållaren**.
> - Behållaren **Session** i Adobe Analytics kallas för **Besök**.
> - **Event**-behållaren kallas i Adobe Analytics för **Hit**-behållaren.
>

Ett filter anger villkor för att filtrera personer, sessioner eller händelser baserat på villkor. Exempel: villkor för att filtrera personer baserat på personegenskaper och navigeringsegenskaper. Om du vill dela upp data ytterligare kan du filtrera efter specifika sessioner, sidvisningshändelser, skärmtapp, menyval i en digitalbox med mera. Men filtrera också på attribut som du har inhämtat från ett CRM- eller lojalitetssystem. [Filterverktyget](/help/components/filters/filter-builder.md) innehåller ett enkelt gränssnitt för att skapa dessa delmängder och tillämpa villkor i kapslade, hierarkiska person-, session- eller händelsebehållare.

Behållararkitekturen som används i [filterverktyget](/help/components/filters/filter-builder.md) definierar Person som den yttersta behållaren. Behållaren innehåller översiktsdata som är specifika för personen i olika sessioner och händelser, som sidvisningar, mobilprogramskärmar eller menyskärmar i en digitalbox. Med en kapslad sessionsbehållare kan du ange regler för att dela upp persondata baserat på sessioner. Med en kapslad händelsebehållare kan du dela upp personinformation baserat på individuella interaktioner. Med varje behållare kan du rapportera över en persons historik, interaktioner uppdelade efter sessioner eller dela upp enskilda händelser.

### Personbehållare

Personbehållaren innehåller alla sessioner och alla händelser för de personer som uppfyller villkoren som anges i behållaren. När du definierar ett filter med ett enkelt villkor som `Page Name equals Checkout` tolkas personbehållaren till:

- Alla personer som har besökt sidan med namnet `Checkout`.
- Alla sessioner för dessa personer.
- Alla händelsedata för dessa personer.

Som den mest vitt definierade behållaren returnerar rapporter som genereras på personbehållarnivå händelser och sessioner för alla personer som kvalificerar sig för filtret. Personbehållaren är den som kan ändras mest baserat på definierade datumintervall.
Personbehållare kan innehålla värden som baseras på en persons övergripande historik:

- Dagar före första köpet.
- Startsida eller startsida för mobilappar.
- Ursprungliga referensdomäner.

### Sessionsbehållare

Med sessionsbehållaren kan du identifiera sidinteraktioner eller mobilappsinteraktioner, kampanjer eller konverteringar för en viss session. Sessionsbehållaren är den vanligaste behållaren eftersom den fångar upp beteenden för hela sessionen när regeln har uppfyllts. Med sessionsbehållaren kan du också definiera vilka sessioner som du vill inkludera eller exkludera när du skapar och använder ett filter.  När du definierar ett filter med ett enkelt villkor som `Page Name equals Checkout` tolkas sessionsbehållaren som:

- Alla sessioner där en sida med namnet `Checkout` besöktes.
- Alla händelsedata för dessa sessioner.

Med sessionsbehållaren kan du besvara följande frågor:

- Hur många sessioner involverade både webbdatakällor och datakällor för callcenter?
- Vilka sidor bidrog till en lyckad konvertering till en försäljning?

Sessionsbehållare innehåller värden som baseras på händelser per session:

- Sessionstyp.
- Startsida.
- Returfrekvens.
- Deltagandestatistik.
- Linjärt allokerade mätvärden.

Med datavyer i Customer Journey Analytics kan du bestämma hur länge en session varar, men också när en ny session ska skapas. Du kan till exempel definiera en ny mobilappssession baserat på varje gång en användare startar din mobilapp. Mer information finns i [Sessionsinställningar](/help/data-views/session-settings.md).

### Händelsebehållare

Händelsebehållaren definierar vilken sida, vilket mobilprogram eller annan typ av händelser som du vill inkludera eller exkludera från ett filter. Det är det smalaste av de tillgängliga behållarna så att du kan identifiera specifika klick, sidvy och knapp i en mobilapp där ett villkor är uppfyllt. Med händelsebehållaren kan du visa en enskild spårningskod eller isolera beteenden inom ett visst område i din mobilapp. Du kanske också vill hitta ett specifikt värde när en åtgärd inträffar, till exempel marknadsföringskanalen när en beställning har gjorts. När du definierar ett filter med ett enkelt villkor som `Page Name equals Checkout` tolkas händelsebehållaren till:

- Alla sidvyhändelser där sidnamnet är lika med `Checkout`.

Händelsebehållare innehåller värdebaserade, enkelsidiga uppdelningar för:

- Produkter
- Visa utkast
- Listdimensioner
- Marknadsföringsdimensioner (i samband med händelser)


### Behållare för logikgrupp

Med Logic Group kan du gruppera villkor i en enda sekventiell filterkontrollpunkt. Som en del av sekvensen utvärderas logiken som definieras i behållaren som identifieras som [!UICONTROL Logic Group] efter en sekventiell kontrollpunkt och före efterföljande kontrollpunkter. Mer information finns i [Logikgrupp](seg-sequential-build.md#logic-group).

### Kapslade behållare

När du skapar behållare i andra behållare skapar du i själva verket ett filter i ett filter. Följande logik används för kapslade behållare:

1. Avgör vilka data som ska inkluderas med den yttersta behållaren. Alla data som inte matchar den här yttre regeln tas bort i rapporten.
2. Använd den kapslade filterdefinitionen på återstående data. Den kapslade filterdefinitionen gäller INTE för data som den första definitionen ignorerade.
3. Upprepa tills alla definitioner för kapslade behållarfilter har beräknats. Resterande data inkluderas sedan i resultatet och används för rapportering.

>[!NOTE]
>
>När du kapslar in ett filter i ett filter (du t.ex. drar ett filter från panelen Komponenter till filterdefinitionen) skapas en behållare med en kopia (inte en referens) av filterdefinitionen som dras.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Skapa filter](create-filters.md)
>[Filterverktyget](filter-builder.md)
>[Snabbfilter](quick-filters.md)
>[Sekventiella filter](seg-sequential-build.md)
>[Hantera filter](manage-filters.md)
>
