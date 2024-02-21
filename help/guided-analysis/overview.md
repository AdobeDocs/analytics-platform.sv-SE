---
title: Översikt över guidad analys
description: En metod för att analysera data i Customer Journey Analytics som gör att produktteam snabbt kan få högkvalitativa insikter. Kallas även Product Analytics.
keywords: produktanalys
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 0%

---

# Översikt över guidad analys

Med hjälp av guidad analys kan användarna själva leverera högkvalitativa data och insikter om kundresan via guidade arbetsflöden som bygger på data från olika kanaler i Customer Journey Analytics. Funktionsövergripande team, från marknadsföring till produkt, kan kommunicera i realtid för att använda och förstå dessa rapporter.

>[!NOTE]
>
> Guidad analys är för närvarande endast tillgänglig som en del av Adobe Product Analytics, som är ett betalt tillägg till Customer Journey Analytics. Om din organisation vill börja använda den här uppsättningen funktioner kontaktar du ditt Adobe-kontoteam.

I likhet med Analysis Workspace- och Mobile-styrkort används data från en [Datavy](../data-views/data-views.md), som refererar till data i Adobe Experience Platform via en [Anslutning](../connections/overview.md). Många rapporter som skapas i guidad analys kan smidigt överföras till Analysis Workspace för ytterligare forskning.

Följande guidade analysvyer är tillgängliga:

| Analystyp | Vytyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Funnel] | [Funktion](types/friction.md) | Jämför konverteringsgrader mellan steg. |
| [!UICONTROL Funnel] | [Konverteringstrender](types/conversion-trends.md) | Spåra förändringar i konverteringsgrader över tid. |
| [!UICONTROL Impact] | [Frigör](types/release.md) | Jämför prestanda i lika stora perioder före och efter lanseringen. |
| [!UICONTROL Impact] | [Första användningen](types/first-use.md) | Mät effekten av förstagångsanvändning på nyckelindikatorer. |
| [!UICONTROL Retention] | [Bevarandegrad](types/retention-rates.md) | Mät användarnas återkommande returvanor. |
| [!UICONTROL Trends] | [Användning](types/usage.md) | Mät användarengagemanget över tid. |
| [!UICONTROL Trends] | [Frekvens](types/frequency.md) | Mät engagemang efter användningsfrekvens. |
| [!UICONTROL User growth] | [Aktiv](types/active.md) | Identifiera vem som är ny, bevarad, återvändande eller vilande. |
| [!UICONTROL User growth] | [Nettotillväxt](types/net-growth.md) | Kommer du att få eller förlora användare? |
| [!UICONTROL User stream] | [Tidslinje](types/timeline.md) | Utforska mönster i sessionsaktivitet. |

{style="table-layout:auto"}

## Åtkomst

Om din organisation är etablerad för guidad analys kan du komma åt den från Customer Journey Analytics hemsida.

1. Klicka **[!UICONTROL Guided analysis]** från hemsidan, som tar dig direkt till [Vyn Användningstrender](types/usage.md).

   ![Landing page tile](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Klicka **[!UICONTROL Create new]** om du vill se de olika visningsalternativen och välja en annan startpunkt för analysen.

   ![Skapa en ny modal](assets/create-new-modal.png){style="border:1px solid gray"}

Om din organisation ännu inte har etablerats för guidad analys kontaktar du ditt Adobe-kontoteam.

## Gränssnitt

Gränssnittet för guidad analys följer ett fråge- och svarsformat. Formulera frågan i frågefältet och få sedan ett svar med en skriftlig insikt, diagram och tabell. Du kan sedan ställa nästa fråga med vytyper och visualiseringsinställningar.

I den guidade analysen används följande gränssnittselement:

| Förhandsgranska gränssnitt | Gränssnittselement | Beskrivning |
| --- | --- | --- |
| ![Frågerår](assets/query-rail.png){style="border:1px solid gray"} | Frågerår | Konfigurera din&quot;fråga&quot; genom att välja de komponenter (händelser, egenskaper och segment) som en analys består av. Följande alternativ är tillgängliga för alla vytyper, med ytterligare inställningar tillgängliga per vy. <ul><li>**Analysväljare**: En listruta där du kan växla till en ny analystyp. Dina frågeval ligger inom de tillåtna gränserna för den nya analystypen.</li><li>**Vyväljare**: En nedrullningsbar meny där du kan växla till en ny vy (&quot;svar&quot;) för frågan som du skapade. Dina frågeval ligger inom de tillåtna gränserna för den nya vytypen.</li><li>**Händelser**: De händelser som du vill mäta. Varje vytyp tillämpar olika gränser för antalet händelser som du kan konfigurera.</li><li>**Filter**: Använd ![Filter](assets/filter.png) -ikonen i avsnittet Händelser eller Segment om du vill begränsa efter specifika egenskaper. När en egenskap är markerad är båda standardfiltervillkoren (som [!UICONTROL Equals], [!UICONTROL Contains], eller [!UICONTROL Ends with]) och de övre 1000 egenskapsvärdena är tillgängliga.</li><li>**Räknas som**: Den nedräkningsmetod som du vill använda för de markerade händelserna.</li><li>**Segment**: De segment som du vill mäta. Varje vytyp tillämpar olika gränser för antalet segment som du kan konfigurera.</li></ul> |
| ![Diagram](assets/chart.png){style="border:1px solid gray"} | Diagram | En visualisering av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Vilken visualisering du ser beror på vyn och inställningarna ovanför diagrammet. Diagrammet innehåller även: <ul><li>**Verktygstips**: Håll pekaren över en diagramdatapunkt för att visa ett verktygstips med mer information.</li><li>**Förklaring**: Håll pekaren över teckenförklaringsserien för att visa definitioner där det finns, fokusera på serien och tillfälligt dölja andra serier. Dölj en serie i teckenförklaringen genom att klicka på den.</li><li>**Anteckningar**: Tillämpligt [anteckningar](../components/annotations/overview.md) är synliga mellan visualiseringen och teckenförklaringen. Det visas som en ![Anteckningsikon](assets/annotation.png) -ikonen i anteckningens konfigurerade färg. Visa typer som visar data över tiden genom att placera ![Anteckningsikon](assets/annotation.png) -ikonen under det konfigurerade datumet eller datumintervallet. Visa typer som inte visar data över tid ![Anteckningsikon](assets/annotation.png) i diagrammets nedre högra hörn.</li><li>**Klicka på funktionsmakron**: Visa tillgängliga nästa åtgärd genom att vänsterklicka på en datapunkt. Alternativen inkluderar **Spara segment**.</li></ul> |
| ![Tabell](assets/table.png){style="border:1px solid gray"} | Tabell | En tabellrepresentation av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Kolumnerna i tabellen beror på vilken vytyp som finns ovanför diagrammet. Tabellen innehåller även följande: <ul><li>**Klicka på funktionsmakron**: Dölja eller visa en diagramserie genom att växla ![Visa ikon för Dölj](assets/hide-in-chart.png) -ikonen i varje rad. Ytterligare åtgärder är tillgängliga genom att klicka på **[!UICONTROL More]** -menyn. Alternativen inkluderar **Spara segment**.</li></ul> |
| ![Visualiseringsinställningar](assets/visualization-settings.png){style="border:1px solid gray"} | Visualiseringsinställningar | Alternativ ovanför diagrammet som gör att du kan ställa nästa fråga och anpassa hur diagrammet och tabellen returnerar data. Följande alternativ är tillgängliga för alla vytyper, med ytterligare inställningar tillgängliga per vy. <ul><li>**Diagraminställningar**: Finjustera hur diagram och tabeller visas. Vilka alternativ som är tillgängliga beror på vilken vy du har valt.</li><li>**Datumintervall**: En kalenderväljare som gör att du kan bestämma datumintervallet för analysen. Du kan också välja ett intervall för trendvyer, till exempel dagliga, veckovisa eller månadsvisa.</li><li>**Insikter**: Sammanhangsberoende insikter beroende på vilken analys du visar. Du kan använda piltangenterna för att gå till ytterligare insikter eller visa eller dölja dessa insikter med hjälp av glödlampsikonen i det övre högra hörnet.</li></ul> |
| ![Meny](assets/menu.png){style="border:1px solid gray"} | Meny | Kommandon i det övre högra hörnet av guidad analys som ger övergripande åtgärder för din analys.<ul><li>**Datavyväljare**: Ändra datavyn som analysen använder. När du ändrar datavyn ändras även de tillgängliga komponenterna i frågerinjen.</li><li>**Kopiera länk**: Kopierar en länk till analysen till Urklipp. Du uppmanas att spara innan du delar.</li><li>**Dela**: Öppnar den modala delningen, med ytterligare alternativ för delning till enskilda användare eller grupper. Du uppmanas att spara innan du delar.</li><li>**Spara**: Sparar analysen. Om du sparar en ny analys visas ett modalt fönster som begär ett namn och en beskrivning.</li><li>**Spara som**: Sparar analysen separat från den aktuella analysen och skapar en kopia. Ett modalt fönster visas där ett nytt namn och en beskrivning efterfrågas.</li><li>**Öppna i arbetsytan**: Återskapar den aktuella guidade analysen i Analysis Workspace. Arbetsyteprojektet skapas på en ny flik, vilket förhindrar avbrott när du arbetar i en guidad analys. Det är en kopia av analysen och är inte synkroniserat med den ursprungliga guidade analysen när den väl har öppnats. Använd det här kommandot när du vill skicka vidare till analytikerteamet, eller fördjupa dig i data än vad som tillåts med guidad analys.</li><li>**Kopiera till Urklipp**: Kopierar diagramgrafiken till Urklipp och klistras in i andra program. Frågefältet och tabellen tas inte med i bilden.</li><li>**Hämta PNG**: Hämtar diagramgrafiken som en `.png`. Frågefältet och tabellen tas inte med i bilden.</li><li>**Hämta CSV**: Hämtar tabelldata som `.csv`. Frågefältet och -diagrammet inkluderas inte i filen.</li></ul> |

{style="table-layout:auto"}

## Provisionering

Guidad analys ingår i Adobe Product Analytics, som är ett betalt tillägg till Customer Journey Analytics. Om din organisation vill börja använda den här uppsättningen funktioner kontaktar du ditt Adobe-kontoteam.

När organisationen har etablerats för att använda guidad analys kan produktprofiladministratörer lägga till eller ta bort åtkomst till den i Adobe Admin Console.

1. Logga in på [Adobe Admin Console](https://adminconsole.adobe.com).
1. Välj **[!UICONTROL Customer Journey Analytics]** i produktlistan.
1. Välj önskad produktprofil för de behörigheter som du vill redigera.
1. Klicka på **[!UICONTROL Permissions]** tabbtangenten och klicka sedan på **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Klicka på plusikonen bredvid **[!UICONTROL Guided Analysis Access]** i listan över [!UICONTROL Available Permission Items], vilket lägger till det i listan över [!UICONTROL Included Permission Items].
1. Klicka på **[!UICONTROL Save]**.

>[!TIP]
>
>Vissa administratörer föredrar att aktivera guidad analys och inaktivera Analysis Workspace för nya användare i Customer Journey Analytics. När dessa användare har kommit överens med produkten och era organisationsdata kan ni aktivera åtkomst till Analysis Workspace.
