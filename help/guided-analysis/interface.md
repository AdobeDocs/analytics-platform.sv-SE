---
title: Guidat analysgränssnitt
description: Lär dig mer om den övergripande strukturen för gränssnittet för det guidade analysprojektet.
source-git-commit: d73dc0eb1740f28c0cd0b7b64fee86069c402b63
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Guidsanalysgränssnitt

{{release-limited-testing}}

Gränssnittet för ett guidat analysprojekt, oavsett analystyp, innehåller följande huvudgränssnittselement:

* **Frågerår**: Använd den här listen till vänster om ditt projekt för att bygga upp din analys.
* **Diagram**: När du har valt händelser, personer eller steg visas ett diagram till höger som visar data.
* **Tabell**: En tabell under diagrammet som visar de siffror som används i visualiseringen.
* **Inställningar och insikter**: Flera gränssnittselement ovanför diagrammet som gör att du kan anpassa de data som returneras.

[Skärmbild av användargränssnitt]

## Frågerår

[Skärmbild av frågespår]

Frågefältet är det område där du konfigurerar de komponenter som utgör en rapport. Olika analystyper delar flera frågealternativ. om två analystyper delar frågealternativ, överförs de när analystyperna ändras. Se [Analystyper](analysis-types/overview.md) om du vill ha mer information om frågealternativen för varje analystyp.

## Diagram

[Skärmbild av diagram]

En visualisering av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Vilken visualisering du ser beror på vytypen ovanför diagrammet. Vilka vytyper som är tillgängliga beror på [Analystyp](analysis-types/overview.md) ovanför sökfältet.

## Tabell

[Skärmbild av tabell]

En tabellrepresentation av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Kolumnerna i tabellen beror på vytypen ovanför diagrammet. Vilka vytyper som är tillgängliga beror på [Analystyp](analysis-types/overview.md) ovanför sökfältet.

## Inställningar

[Skärmbild av inställningar]

Flera alternativ ovanför diagrammet som gör att du kan anpassa hur diagrammet och tabellen returnerar data.

* **Vytyp**: En nedrullningsbar väljare som gör att du kan presentera data för en viss [Analystyp](analysis-types/overview.md) på ett annat sätt. Varje analystyp har minst två vytyper.
* **Diagraminställningar**: Finjustera hur diagrammet ser ut och vilka händelser du vill att det ska användas. Vilka alternativ som är tillgängliga beror på vilken vytyp du har valt.
* **Datumintervall**: En kalenderväljare som gör att du kan fastställa rapportens datumintervall. Vissa analystyper tillåter även intervaller, t.ex. varje dag, varje vecka eller varje månad.
* **Insikter**: Ger sammanhangsbaserade insikter beroende på vilken rapport du visar. Du kan visa eller dölja dessa insikter med glödlampsikonen i det övre högra hörnet.

## Projektmeny

[Skärmbild av projektmeny]

Kommandon i det övre högra hörnet av projektet som innehåller övergripande åtgärder.

* **Datavyväljare**: Ändra datavyn som används i det här projektet. När du ändrar datavyn ändras även de tillgängliga komponenterna i frågerinjen.
* **Spara**: Sparar projektet. Om du sparar ett nytt projekt visas ett modalt fönster som begär ett namn och en beskrivning.
* **Spara som**: Sparar projektet separat från det aktuella projektet och skapar en kopia. Ett modalt fönster visas där ett nytt namn och en beskrivning begärs.
* **Öppna i arbetsytan**: Återskapar det aktuella guidade analysprojektet i Analysis Workspace. Arbetsyteprojektet skapas på en ny flik, vilket förhindrar avbrott när du arbetar med det guidade analysprojektet. Använd det här kommandot när den guidade analysen inte ger dig den flexibilitet eller specifika insikt du vill ha. Du vill till exempel ha en [Trender](analysis-types/trends.md) som använder sessioner för ett segment och personer för ett annat segment.
* **Hämta PNG**: Hämtar diagramgrafiken som en `.png`. Frågefältet och tabellen tas inte med i bilden.
* **Hämta SVG**: Hämtar diagramgrafiken som en `.svg`. Frågefältet och tabellen tas inte med i bilden.
