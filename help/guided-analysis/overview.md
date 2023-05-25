---
title: Översikt över guidad analys
description: En metod för att analysera data i Customer Journey Analytics som gör att produktteamen enkelt kan generera rapporter och insikter.
source-git-commit: 03f6b0cef6fa4259041a82173acda852d91e06b5
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---

# Översikt över guidad analys

{{release-limited-testing}}

Guidad analys är ett rapportformat som gör att produktteamen snabbt kan ta hand om sina databehov så att de kan fatta mer databaserade produktbeslut. Funktionsövergripande team kan kommunicera i realtid för att använda och förstå dessa rapporter.

I en rapport om guidad analys, som liknar Analysis Workspace- och Mobile-styrkort, används data från en [Datavy](../data-views/data-views.md), som refererar till data i Adobe Experience Platform via en [Anslutning](../connections/overview.md). Alla rapporter som skapas i den guidade analysen kan smidigt överföras till Analysis Workspace för ytterligare forskning.

För närvarande finns det tre typer av guidade analysrapporter: [Tratt](analysis-types/funnel.md), [Trender](analysis-types/trends.md)och [Användartillväxt](analysis-types/user-growth.md). Var och en av dessa analystyper har flera vytyper som ger ytterligare insikter till var och en av dessa rapporter.

## Provisionering

Guidad analys är ett betalt tillägg till Customer Journey Analytics. Om din organisation vill börja använda den här funktionen kontaktar du kontoteamet på Adobe.

## Gränssnitt

Gränssnittet för guidad analys, oavsett analystyp, innehåller följande huvudgränssnittselement:

1. **Frågerår**: Använd den här listen till vänster för att bygga upp din analys.
1. **Diagram**: När du har valt händelser, personer eller steg visas ett diagram till höger som visar data.
1. **Tabell**: En tabell under diagrammet som visar de siffror som används i visualiseringen.
1. **Inställningar och insikter**: Flera gränssnittselement ovanför diagrammet som gör att du kan anpassa de data som returneras.

[Skärmbild av användargränssnitt]

Guidad analys innehåller följande gränssnittsdelar:

| Förhandsgranska gränssnitt | Gränssnittselement | Beskrivning |
| --- | --- | --- |
| [Skärmbild av frågespår] | Frågerår | Konfigurera önskade komponenter som utgör en rapport. Olika analystyper delar flera frågealternativ. om två analystyper delar frågealternativ, överförs de när analystyperna ändras. Se [Analystyper](analysis-types/overview.md) om du vill ha mer information om frågealternativen för varje analystyp. |
| [Skärmbild av diagram] | Diagram | En visualisering av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Vilken visualisering du ser beror på vytypen ovanför diagrammet. Vilka vytyper som är tillgängliga beror på [Analystyp](analysis-types/overview.md) ovanför sökfältet. |
| [Skärmbild av tabell] | Tabell | En tabellrepresentation av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Kolumnerna i tabellen beror på vytypen ovanför diagrammet. Vilka vytyper som är tillgängliga beror på [Analystyp](analysis-types/overview.md) ovanför sökfältet. |
| [Skärmbild av inställningar] | Inställningar | Flera alternativ ovanför diagrammet som gör att du kan anpassa hur diagrammet och tabellen returnerar data.<ul><li>**Vytyp**: En nedrullningsbar väljare som gör att du kan presentera data för en viss [Analystyp](analysis-types/overview.md) på ett annat sätt. Varje analystyp har minst två vytyper.</li><li>**Diagraminställningar**: Finjustera hur diagrammet ser ut och vilka händelser du vill att det ska användas. Vilka alternativ som är tillgängliga beror på vilken vytyp du har valt.</li><li>**Datumintervall**: En kalenderväljare som gör att du kan fastställa rapportens datumintervall. Vissa analystyper tillåter även intervaller, t.ex. varje dag, varje vecka eller varje månad.</li><li>**Insikter**: Ger sammanhangsbaserade insikter beroende på vilken rapport du visar. Du kan visa eller dölja dessa insikter med glödlampsikonen i det övre högra hörnet.</li></ul> |
| [Skärmbild av analysmenyn] | Analysmeny | Kommandon i det övre högra hörnet i den guidade analysen som ger övergripande åtgärder.<ul><li>**Datavyväljare**: Ändra datavyn som den här analysen använder. När du ändrar datavyn ändras även de tillgängliga komponenterna i frågerinjen.</li><li>**Spara**: Sparar analysen. Om du sparar en ny analys visas ett modalt fönster som begär ett namn och en beskrivning.</li><li>**Spara som**: Sparar analysen separat från den aktuella analysen och skapar en kopia. Ett modalt fönster visas där ett nytt namn och en beskrivning begärs.</li><li>**Öppna i arbetsytan**: Återskapar den aktuella guidade analysen i Analysis Workspace. Arbetsyteprojektet skapas på en ny flik, vilket förhindrar avbrott när du arbetar i den guidade analysen. Använd det här kommandot när den guidade analysen inte ger dig den flexibilitet eller specifika insikt du vill ha. Du vill till exempel ha en [Trender](analysis-types/trends.md) som använder sessioner för ett segment och personer för ett annat segment.</li><li>**Hämta PNG**: Hämtar diagramgrafiken som en `.png`. Frågefältet och tabellen tas inte med i bilden.</li><li>**Hämta SVG**: Hämtar diagramgrafiken som en `.svg`. Frågefältet och tabellen tas inte med i bilden.</li></ul> |

{style="table-layout:auto"}

## Behörigheter

Adobe planerar att i framtiden ge behörigheter som är specifika för den guidade analysen.

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
