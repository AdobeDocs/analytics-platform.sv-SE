---
title: Trender
description: Hitta mönster och förändringar i användarengagemanget över tid.
source-git-commit: c47c4364cbf027c24a355bb306ee786c3e2446a9
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 0%

---

# Trender

{{release-limited-testing}}

The **Trender** [Analystyp](overview.md) ger värdefull information om hur produkten eller användarens beteende fungerar över tid. Den vågräta axeln i den här rapporten är alltid en tidshalaritet, medan den lodräta axeln mäter dina önskade händelser. Användningsexempel för den här analystypen är:

* **Utvärdera produktens prestanda**: Trender gör att du kan utvärdera den övergripande prestandan för din produkt under en viss period. Genom att analysera mätvärden som användarinteraktion, konverteringsgrad eller intäkter kan ni identifiera om produktens prestanda förbättras, stagnerar eller försämras.
* **Antagande av nya funktioner**: Trender gör att du kan förstå hur användare antar nya funktioner eller uppdateringar som du släpper. Du kan avgöra vilka funktioner som är populära och vilka som behöver förbättras. Med den här informationen kan ni fatta datadrivna beslut om vilka funktioner ni ska prioritera utvecklingsarbetet kring.
* **Användarbeteende**: Trender ger insikt i användarbeteendet över tid. Genom att undersöka specifika åtgärder som användare utför kan du identifiera mönster där användare kan släppa av. Du kan kombinera insikter från den här analystypen med en [Tratt](funnel.md) för ännu mer insikter om beteenden.
* **A/B-testning och -experimenterande**: Om du kör A/B-tester i produkten kan du använda Trends för att mäta vilka tester som är mest framgångsrika över tid.

[Skärmbild av trender]

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Händelser**: Anger händelser som du vill mäta i rapporten. Varje händelse som markeras här representeras som en färgad linje eller en uppsättning staplar, beroende på diagramtyp. En rad som representerar händelsen trended läggs till i tabellen. Upp till fem händelser stöds.
* **Folk**: Anger de segment som du vill mäta i rapporten. Varje segment som är markerat här dubblerar antalet rader i diagrammet och raderna i tabellen. Varje uppsättning med händelser representeras för varje segment. Stöd för upp till fem segment.

## Vytyper

Trender erbjuder följande vytyper. Du kan ändra vytyp med hjälp av listrutan högst upp till vänster i diagrammet.

* **Användning:** Mät användarengagemanget över tid.

## Diagraminställningar

Trender har följande diagraminställningar. Du kan justera diagraminställningarna på menyn mellan vytypen och kalenderväljaren.

* **Mått**: Anger måttet som du vill mäta. Alternativen är Händelser, Sessioner, Användare, Händelser per session och Händelser per användare.
* **Diagramtyp**: Anger vilken typ av visualisering du vill använda. Du kan välja mellan Linje, Stapel, Staplad liggande och Staplad yta.

## Använd tidsjämförelse

Trender ger möjlighet att jämföra den aktuella tidsperioden med en tidigare tidsperiod. Om du väljer ett alternativ på den här menyn får varje rad en prickad linje med liknande färg. Den här prickade linjen representerar samma mätvärde i det valda föregående datumintervallet. Om du anger det här alternativet dubbleras antalet rader i diagrammet och raderna i tabellen.

Tillgängliga tidsjämförelsealternativ omfattar föregående period, 13 veckor före, 52 veckor före och ett anpassat datumintervall. Om du väljer Anpassat datumintervall visas ytterligare alternativ så att du kan välja antal och detaljrikedom. Om du väljer Ingen tas datumjämförelsen bort.

## Datumintervall

Anger önskat datumintervall. Den här inställningen har två viktiga komponenter:

* **Intervall**: Datumgranulariteten som du vill visa data i. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en rapport som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en rapport som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **Datum**: Start- och slutdatumet för projektet. Det finns förinställningar för datumintervall tillgängliga, eller så kan du använda kalenderväljaren för att ange exakt önskat datum.
