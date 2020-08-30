---
title: Översikt över filter
description: Förstå vilka filter som används och hur du skapar ett enkelt filter.
translation-type: tm+mt
source-git-commit: 09dcb36b96d95276b357e0f1308a977f5db5d711
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 1%

---


# Översikt över filter

Med Customer Journey Analytics kan du bygga, hantera, dela och tillämpa kraftfulla, fokuserade målgruppsfilter på dina rapporter. Med filter kan du identifiera underuppsättningar besökare baserat på egenskaper eller interaktioner på webbplatsen. Filter är utformade som kodifierade målgruppsinsikter som du kan skapa för dina specifika behov och sedan verifiera, redigera och dela med andra gruppmedlemmar.

Filter kan baseras på attribut (webbläsartyp, enhet, antal besök, land, kön), interaktioner (kampanjer, sökmotor för nyckelord), utgångar och inlägg (besökare från Facebook, en definierad landningssida, referensdomän), anpassade variabler (formulärfält, definierade kategorier, kund-ID) och andra kriterier.

Du kan skapa och spara filter i Filter Builder eller generera filter från en Fallout-visualisering (på arbetsytan). Dessutom kan filter användas tillsammans som staplade filter.

>[!IMPORTANT]
>Filter kallas &quot;segment&quot; i Adobe Analytics. Vi döpte om segment till filter eftersom Adobe Experience Platform har en annan definition av segment.

Filtrering innehåller [Filter Builder](/help/components/filters/create-filters.md) för att konstruera filter och köra ett förtest, och [Filterhanteraren](/help/components/filters/manage-filters.md) om du vill samla in, tagga, godkänna, ställa in säkerhet och dela filter i hela organisationen.

## Sekventiella filter

Med sekventiella filter kan du identifiera besökare baserat på navigering och sidvisning över hela webbplatsen, vilket ger ett filter av definierade åtgärder och interaktioner. Sekventiella segment hjälper dig att identifiera vad en besökare gillar och vad en besökare undviker. När sekventiella filter byggs används operatorn THEN för att definiera och beställa besöksnavigering.

Här följer ett exempel:

![](assets/sequential_fil.png)

| Besök ett | Besök två | Besök tre |
|---|---|---|
| Besökaren gick till huvudlandningssidan (A), exkluderade kampanjsidan (B) och visade sedan sidan Produkt (C). | Besökaren gick återigen till huvudlandningssidan (A), exkluderade kampanjsidan (B) och gick sedan tillbaka till sidan Produkt (C) och sedan till en ny sida (D). | Besökaren gick in på och följde samma väg som vid det första och det andra besöket och uteslöt sedan sidan F för att gå direkt till en målproduktsida (G). |

## Filterbehållare

Filter baseras på en hierarki på person-, session- och händelsenivå med hjälp av en kapslad behållarmodell. Med kapslade behållare kan du definiera personattribut och åtgärder baserade på regler mellan och inom behållarna.

>[!NOTE]
>Personbehållaren var tidigare känd som Visitor-behållaren. Sessionsbehållaren anropades till behållaren Visit, och händelsemottagaren brukade vara Träff-behållaren.

Ett filter anger villkor för att filtrera en besökare baserat på dennes attribut eller interaktioner med platsen. Om du vill ange villkor i ett filter anger du regler för att filtrera besökare baserat på besökaregenskaper och/eller navigeringsegenskaper. Om du vill dela upp besöksdata ytterligare kan du filtrera baserat på specifika besök och/eller sidovyträffar för varje besökare. Filter Builder tillhandahåller en enkel arkitektur för att skapa dessa underuppsättningar och tillämpa regler som kapslade, hierarkiska personer, session eller händelsebehållare.

Behållararkitekturen som används i Filter Builder definierar Person som den yttersta behållaren, som innehåller överliggande data som är specifika för besökaren över besök och sidvyer. Med en kapslad sessionsbehållare kan du ställa in regler för att dela upp besökarens data baserat på sessioner, och med en kapslad händelsebehållare kan du dela upp besöksinformation baserat på enskilda sidvyer. Med varje behållare kan du rapportera över en besökares historik, interaktioner som är uppdelade efter sessioner eller dela upp enskilda händelser.

### Personbehållare

Personbehållaren innehåller alla besök och sidvisningar för besökare inom en viss tidsram. Ett filter på personnivå returnerar sidan som uppfyller villkoret plus alla andra sidor som besökaren visar (och begränsas endast av definierade datumintervall). Som den mest väldefinierade behållaren returnerar rapporter som genereras på personcontainernivå sidvyer över alla besök och gör att du kan generera en flerbesöksanalys. Personbehållaren är därför den mest känsliga för ändring baserat på definierade datumintervall.
Personcontainrar kan innehålla värden som baseras på besökarens allmänna historik:

* Dagar före första köp

* Ursprunglig startsida

* Ursprungliga referensdomäner

### Sessionsbehållare

Med sessionsbehållaren kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session. Sessionsbehållaren är den mest använda behållaren eftersom den fångar in beteenden för hela besökssessionen när regeln har uppfyllts och du kan definiera vilka sessioner som du vill inkludera eller utesluta i byggandet och tillämpningen av ett segment. Det kan hjälpa dig att besvara följande frågor:

* Hur många besökare såg avsnittet Nyheter och idrott på samma session?

* Vilka sidor bidrog till en lyckad konvertering till en försäljning?

Sessionsbehållare innehåller värden som baseras på förekomst per session:

* Sessionsnummer

* Startsida

* Återbesöksfrekvens

* Deltagandemått

* Linjärt allokerade mått

### Händelsebehållare

Händelsebehållaren definierar vilka sidhändelser som du vill inkludera eller exkludera från ett filter. Det är den mest smala av de tillgängliga behållarna som du kan använda för att identifiera specifika klickningar och sidvy där ett villkor är sant, så att du kan visa en enskild spårningskod eller isolera beteendet i ett visst avsnitt av webbplatsen. Du kanske också vill peka på ett specifikt värde när en åtgärd inträffar, t.ex. marknadsföringskanalen när en order placerades.

Händelsebehållare innehåller värden baserade på en siduppdelning:

* Produkter

* Visa proffs

* Listdimensioner

* Handelsdimensioner (i samband med händelser)