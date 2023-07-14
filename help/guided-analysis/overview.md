---
title: Översikt över guidad analys
description: En metod för att analysera data i Customer Journey Analytics som gör att produktteamen snabbt kan få högkvalitativa insikter.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: 75f946e65bfc0ccee4f173b699b14caced21bbaf
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 0%

---

# Översikt över guidad analys

{{release-limited-testing}}

Guidad analys är ett rapportformat som gör att produktteamen snabbt kan ta hand om sina databehov så att de snabbt kan få högkvalitativa insikter och fatta mer databaserade produktbeslut. Funktionsövergripande team kan kommunicera i realtid för att använda och förstå dessa rapporter.

I en rapport om guidad analys, som liknar Analysis Workspace- och Mobile-styrkort, används data från en [Datavy](../data-views/data-views.md), som refererar till data i Adobe Experience Platform via en [Anslutning](../connections/overview.md). Alla rapporter som skapas i den guidade analysen kan smidigt överföras till Analysis Workspace för ytterligare forskning.

Med hjälp av guidad analys kan du analysera och visa data på flera olika sätt. Visningstyper kan visa samma data på olika sätt, vilket leder till olika insikter med samma händelser och segment. Beroende på vilken vy du väljer får du olika frågerelinjer och visualiseringsinställningar. Du kan fritt växla mellan vyer, och eventuella tillämpliga frågespårskomponenter överförs om vyn har stöd för dem.

Med guidad analys kategoriseras vytyperna i **Analystyper**. Följande analys- och vytyper är tillgängliga:

| Analystyp | Vytyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Impact] | [Frigör](types/release.md) | Jämför prestanda i lika stora perioder före och efter lanseringen. |
| [!UICONTROL Impact] | [Första användningen](types/first-use.md) | Mät effekten av förstagångsanvändning på nyckelindikatorer. |
| [!UICONTROL Funnel] | [Funktion](types/friction.md) | Jämför konverteringsgrader mellan steg. |
| [!UICONTROL Funnel] | [Konverteringstrender](types/conversion-trends.md) | Spåra förändringar i konverteringsgrader över tid. |
| [!UICONTROL User growth] | [Aktiv](types/active.md) | Identifiera vem som är ny, bevarad, återvändande eller vilande. |
| [!UICONTROL Net growth] | [Nettotillväxt](types/net-growth.md) | Kommer du att få eller förlora användare? |
| [!UICONTROL Trends] | [Användning](types/usage.md) | Mät användarengagemanget över tid. |

{style="table-layout:auto"}

## Åtkomst

Om din organisation är etablerad för guidad analys kan du komma åt den från Customer Journey Analytics hemsida.

1. Klicka **[!UICONTROL Guided analysis]** från hemsidan för att gå direkt till [Vyn Användningstrender](types/usage.md).

   ![Landing page tile](assets/landing-page-tile.png)

1. Klicka **[!UICONTROL Create new]** om du vill se de olika visningsalternativen och välja en annan startpunkt för analysen.

   ![Skapa en ny modal](assets/create-new-modal.png)

## Gränssnitt

Gränssnittet för guidad analys, oavsett analystyp, innehåller följande huvudgränssnittselement:

| Förhandsgranska gränssnitt | Gränssnittselement | Beskrivning |
| --- | --- | --- |
| ![Frågerår](assets/query-rail.png) | Frågerår | Konfigurera önskade komponenter (händelser, egenskaper och segment) som utgör en analys. Varje analystyp tillämpar olika gränser för antalet händelser och segment som du kan konfigurera. Om du byter till en ny analystyp, behålls dina frågeval inom de tillåtna gränserna för den analystypen. |
| ![Diagram](assets/chart.png) | Diagram | En visualisering av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Vilken visualisering du ser beror på vyn och inställningarna ovanför diagrammet. Vilka vyer som är tillgängliga beror på analystypen ovanför frågespelaren. Diagrammet innehåller även: <ul><li>**Verktygstips**: Håll pekaren över en diagramdatapunkt för att visa ett verktygstips med mer information.</li><li>**Förklaring**: Håll pekaren över teckenförklaringen för att visa seriedefinitioner, om sådana finns.</li><li>**Klicka på funktionsmakron**: Visa tillgängliga nästa åtgärder genom att vänsterklicka på en datapunkt. Alternativen inkluderar **Spara segment**.</li></ul> |
| ![Tabell](assets/table.png) | Tabell | En tabellrepresentation av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Kolumnerna i tabellen beror på vytypen ovanför diagrammet. Vilka vyer som är tillgängliga beror på analystypen ovanför frågespelaren. Tabellen innehåller även följande: <ul><li>**Klicka på funktionsmakron**: Visa tillgängliga åtgärder genom att klicka på **[!UICONTROL More]** -menyn. Alternativen inkluderar **Spara segment**.</li></ul> |
| ![Visualiseringsinställningar](assets/visualization-settings.png) | Visualiseringsinställningar | Flera alternativ ovanför diagrammet som gör att du kan anpassa hur diagrammet och tabellen returnerar data.<ul><li>**Vytyp**: En nedrullningsbar väljare som gör att du kan presentera data för en viss analystyp på ett annat sätt.</li><li>**Diagraminställningar**: Finjustera hur diagrammet och tabellen visas. Vilka alternativ som är tillgängliga beror på vilken vy du har valt.</li><li>**Datumintervall**: En kalenderväljare som gör att du kan bestämma datumintervallet för analysen. Du kan också välja ett intervall för trendvyer, till exempel dagliga, veckovisa eller månadsvisa.</li><li>**Insikter**: Sammanhangsberoende insikter beroende på vilken analys du visar. Du kan använda piltangenterna för att gå till ytterligare insikter eller visa eller dölja dessa insikter med hjälp av glödlampsikonen i det övre högra hörnet.</li></ul> |
| ![Meny](assets/menu.png) | Meny | Kommandon i det övre högra hörnet av den guidade analysen som ger övergripande åtgärder för din analys.<ul><li>**Datavyväljare**: Ändra datavyn som analysen använder. När du ändrar datavyn ändras även de tillgängliga komponenterna i frågerinjen.</li><li>**Spara**: Sparar analysen. Om du sparar en ny analys visas ett modalt fönster som begär ett namn och en beskrivning.</li><li>**Spara som**: Sparar analysen separat från den aktuella analysen och skapar en kopia. Ett modalt fönster visas där ett nytt namn och en beskrivning begärs.</li><li>**Öppna i arbetsytan**: Återskapar den aktuella guidade analysen i Analysis Workspace. Arbetsyteprojektet skapas på en ny flik, vilket förhindrar avbrott när du arbetar i den guidade analysen. Det är en kopia av analysen och är inte synkroniserat med den ursprungliga guidade analysen när den väl har öppnats. Använd det här kommandot när du vill skicka vidare till analytikerteamet, eller fördjupa dig i data än vad guidad analys tillåter.</li><li>**Kopiera till Urklipp**: Kopierar diagramgrafiken till Urklipp och klistras in i andra program. Frågefältet och tabellen tas inte med i bilden.</li><li>**Hämta PNG**: Hämtar diagramgrafiken som en `.png`. Frågefältet och tabellen tas inte med i bilden.</li><li>**Hämta CSV**: Hämtar tabelldata som `.csv`. Frågefältet och -diagrammet inkluderas inte i filen.</li></ul> |

{style="table-layout:auto"}

## Provisionering

Guidad analys ingår i Adobe Product Analytics, som är ett betalt tillägg till Customer Journey Analytics. Om din organisation vill börja använda den här uppsättningen funktioner kontaktar du ditt Adobe-kontoteam.

När organisationen har etablerats för att använda den guidade analysen kan produktprofiladministratörer lägga till eller ta bort åtkomst till den i Adobe Admin Console.

1. Logga in på [Adobe Admin Console](https://adminconsole.adobe.com).
1. Välj **[!UICONTROL Customer Journey Analytics]** i produktlistan.
1. Välj önskad produktprofil för de behörigheter som du vill redigera.
1. Klicka på **[!UICONTROL Permissions]** tabbtangenten och sedan klicka **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Klicka på plusikonen bredvid **[!UICONTROL Guided Analysis Access]** i listan över [!UICONTROL Available Permission Items], vilket lägger till det i listan över [!UICONTROL Included Permission Items].
1. Klicka på **[!UICONTROL Save]**.

>[!TIP]
>
>Vissa administratörer föredrar att aktivera guidad analys och inaktivera Analysis Workspace för nya användare i Customer Journey Analytics. När dessa användare har kommit överens med produkten och era organisationsdata kan ni aktivera åtkomst till Analysis Workspace.
