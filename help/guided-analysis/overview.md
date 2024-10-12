---
title: Översikt över guidad analys
description: En metod för att analysera data i Customer Journey Analytics som gör att produktteam snabbt kan få högkvalitativa insikter.
keywords: produktanalys
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 61db4e228e81c921e756fdd284c1be0f730e4adb
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 0%

---

# Översikt över guidad analys

Med hjälp av guidad analys kan användare, från marknadsföring till produkter och analytiker, själva leverera högkvalitativa data och insikter om kundresan via guidade arbetsflöden som bygger på data från olika kanaler i Customer Journey Analytics. I likhet med Analysis Workspace- och Mobile-styrkort använder guidad analys data från en [datavy](../data-views/data-views.md) som refererar till data i Adobe Experience Platform via en [anslutning](../connections/overview.md). Många rapporter som skapas i guidad analys kan smidigt överföras till Analysis Workspace för ytterligare forskning.

Följande guidade analyser är tillgängliga:

| Analys | Beskrivning |
| --- | --- |
| [Aktiv tillväxt](types/active.md) | Identifiera vem som är ny, bevarad, återvändande eller vilande. |
| [Konverteringstrender](types/conversion-trends.md) | Spåra förändringar i konverteringsgrader över tid. |
| [Engagemang](types/engagement.md) | Förstå bredden och djupet av engagemanget. |
| [Inverkan vid första användningen](types/first-use.md) | Mät effekten av förstagångsanvändning på nyckelindikatorer. |
| [Frekvens](types/frequency.md) | Mät engagemang efter användningsfrekvens. |
| [Tratt](types/friction.md) | Jämför konverteringsgrader mellan steg. |
| [Nettotillväxt](types/net-growth.md) | Kommer du att få eller förlora användare? |
| [Versionseffekt](types/release.md) | Jämför prestanda i lika stora perioder före och efter lanseringen. |
| [Kvarhållning](types/retention-rates.md) | Mät användarnas återkommande returvanor. |
| [Tidslinje](types/timeline.md) | Utforska mönster i sessionsaktivitet. |
| [Trends](types/usage.md) | Mät användarengagemanget över tid. |

{style="table-layout:auto"}

## Åtkomst

Du kommer åt Guidad analys från Customer Journey Analytics hemsida.

1. Välj **[!UICONTROL Guided analysis]** på hemsidan, som tar dig direkt till [vyn Användningstrender](types/usage.md).

   ![Landningssidoruta](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Välj **[!UICONTROL Create new]** om du vill visa de olika visningsalternativen och välja en annan startpunkt för analysen.

   ![Skapa en ny modal](assets/create-new-modal.png){style="border:1px solid gray"}

Du kan även komma åt Guidad analys inifrån ett Analysis Workspace-projekt.

1. Välj **[!UICONTROL Blank project]** på startsidan om du vill skapa ett tomt Workspace-projekt.

   ![Skapa tomt projekt](assets/blank-project.png){style="border:1px solid gray"}

1. Välj ![Guidad analys](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Guided Analysis]** i den vänstra listen.

   ![Workspace left rail](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Dra en ny analys till Workspace Canvas och välj sedan **[!UICONTROL Create]** för att generera önskad analys (till exempel: **[!UICONTROL Create Trends]**). Du kan också dra en befintlig analys till Workspace Canvas från avsnittet **[!UICONTROL Saved]**.

   ![Skapa panel](assets/create-guided-analysis-panel.gif)

## Gränssnitt

Gränssnittet för guidad analys följer ett fråge- och svarsformat. Formulera frågan i frågefältet och få sedan ett svar med en skriftlig insikt, diagram och tabell. Du kan sedan ställa nästa fråga med vytyper och visualiseringsinställningar.

I den guidade analysen används följande gränssnittselement:

| Förhandsgranska gränssnitt | Gränssnittselement | Beskrivning |
| --- | --- | --- |
| ![Frågefält](assets/query-rail.png){style="border:1px solid gray"} | Frågerår | Konfigurera din&quot;fråga&quot; genom att välja de komponenter (händelser, egenskaper och segment) som en analys består av. Följande alternativ är tillgängliga för alla vytyper, med ytterligare inställningar tillgängliga per vy. <ul><li>**Analysväljare**: En listruta där du kan växla till en ny analystyp. Dina frågeval ligger inom de tillåtna gränserna för den nya analystypen.</li><li>**Händelser**: De händelser som du vill mäta. Varje vytyp tillämpar olika gränser för antalet händelser som du kan konfigurera.</li><li>**Filter**: Använd ikonen ![Filter](assets/filter.png) i avsnittet Händelser eller segment om du vill begränsa efter specifika dimensioner. När en dimension har valts är båda standardfiltervillkoren (till exempel [!UICONTROL Equals], [!UICONTROL Contains] eller [!UICONTROL Ends with]) och de 1 000 översta dimensionsvärdena tillgängliga.</li><li>**Räknas som**: Den räkningsmetod som du vill använda för de markerade händelserna.</li><li>**Segment**: Segmenten som du vill mäta. Varje vytyp tillämpar olika gränser för antalet segment som du kan konfigurera.</li></ul> |
| ![Diagram](assets/chart.png){style="border:1px solid gray"} | Diagram | En visualisering av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Vilken visualisering du ser beror på vyn och inställningarna ovanför diagrammet. Diagrammet innehåller även: <ul><li>**Verktygstips**: Håll pekaren över en diagramdatapunkt för att visa ett verktygstips med mer information.</li><li>**Förklaring**: Håll pekaren över teckenförklaringsserien för att visa definitioner där de är tillgängliga, fokusera på serien och dölja tillfälligt andra serier. Dölj en serie i teckenförklaringen genom att klicka på den.</li><li>**Anteckningar**: Tillämpliga [anteckningar](../components/annotations/overview.md) visas mellan visualiseringen och teckenförklaringen. Den visas som en ![anteckningsikon](assets/annotation.png) i anteckningens konfigurerade färg. Visa typer som visar data över tid genom att placera ikonen ![Anteckning](assets/annotation.png) under det konfigurerade datumet eller datumintervallet. Visa typer som inte visar data över tid genom att visa ikonen ![Anteckning](assets/annotation.png) i diagrammets nedre högra hörn.</li><li>**Välj åtgärder**: Visa tillgängliga nästa åtgärder genom att markera en datapunkt. Du kan välja mellan **Spara segment**.</li></ul> |
| ![Tabell](assets/table.png){style="border:1px solid gray"} | Tabell | En tabellrepresentation av de data som returneras baserat på dina indata från frågespelaren och inställningarna. Kolumnerna i tabellen beror på vilken vytyp som finns ovanför diagrammet. Tabellen innehåller även följande: <ul><li>**Välj åtgärder**: Dölj eller visa en diagramserie genom att växla ikonen ![Visa dölj](assets/hide-in-chart.png) på varje rad. Ytterligare åtgärder är tillgängliga genom att välja menyn **[!UICONTROL More]**. Du kan välja mellan **Spara segment**.</li></ul> |
| ![Visualiseringsinställningar](assets/visualization-settings.png){style="border:1px solid gray"} | Visualiseringsinställningar | Alternativ ovanför diagrammet som gör att du kan ställa nästa fråga och anpassa hur diagrammet och tabellen returnerar data. Följande alternativ är tillgängliga för alla vytyper, med ytterligare inställningar tillgängliga per vy. <ul><li>**Diagraminställningar**: Finjustera hur diagrammet och tabellen visas. Vilka alternativ som är tillgängliga beror på vilken vy du har valt.</li><li>**Datumintervall**: En kalenderväljare som gör att du kan bestämma datumintervallet för analysen. Du kan också välja ett intervall för trendvyer, till exempel dagliga, veckovisa eller månadsvisa.</li><li>**Insikter**: Sammanhangsberoende insikter beroende på vilken analys du visar. Dessa insikter ger observationer för den aktuella analysen. Om det finns flera tillgängliga insikter kan du visa dem med pilarna till höger. Du kan växla synlighet för den här rutan genom att använda glödlampsikonen i det övre högra hörnet.</li></ul> |
| ![Meny](assets/menu.png){style="border:1px solid gray"} | Meny | Kommandon i det övre högra hörnet av guidad analys som ger övergripande åtgärder för din analys.<ul><li>**Datavyväljare**: Ändra datavyn som analysen använder. När du ändrar datavyn ändras även de tillgängliga komponenterna i frågerinjen.</li><li>**Kopiera länk**: Kopierar en länk till analysen till Urklipp. Du uppmanas att spara innan du delar.</li><li>**Dela**: Öppnar den modala delningen, med ytterligare alternativ för delning till enskilda användare eller grupper. Du kan dela en analys med andra användare eller skapa en länk som du kan dela med vem som helst.</li><li>**Spara**: Sparar analysen. Om du sparar en ny analys visas ett modalt fönster som begär ett namn och en beskrivning.</li><li>**Spara som**: Sparar analysen separat från den aktuella analysen och skapar en kopia. Ett modalt fönster visas där ett nytt namn och en beskrivning efterfrågas.</li><li>**Exportera till Workspace**: Återskapar den aktuella guidade analysfrågan i Analysis Workspace. Workspace-projektet skapas på en ny flik, vilket förhindrar avbrott när du arbetar i en guidad analys. Det är en kopia av analysen och är inte synkroniserat med den ursprungliga guidade analysen när den väl har öppnats. Använd det här kommandot när du vill skicka vidare till analytikerteamet, eller fördjupa dig i data än vad som tillåts med guidad analys.</li><li>**Kopiera till Urklipp**: Kopierar diagramgrafiken till Urklipp och klistras in i andra program. Frågefältet och tabellen tas inte med i bilden.</li><li>**Hämta PNG**: Hämtar diagramgrafiken som en `.png`. Frågefältet och tabellen tas inte med i bilden.</li><li>**Hämta CSV**: Hämtar tabelldata som en `.csv`. Frågefältet och -diagrammet inkluderas inte i filen.</li></ul> |

{style="table-layout:auto"}

## Provisionering

Guidade analyser ingår i Customer Journey Analytics-paket på följande sätt:

| Paket | Tillgängliga analyser |
| --- | --- |
| [!UICONTROL Customer Journey Analytics add-ons] | Aktiv tillväxt, konverteringstrender, frekvens, tratt, nettotillväxt, lagring, trender |
| [!UICONTROL Customer Journey Analytics Foundation] | Trender |
| [!UICONTROL Customer Journey Analytics Select] | Foundation views + Active growth, Conversion trends, Frequency, Funnel, Net growth, Retention |
| [!UICONTROL Customer Journey Analytics Prime] | Välja vyer + engagemang, Första användningen, Versionseffekt, Tidslinje |
| [!UICONTROL Customer Journey Analytics Ultimate] | Prime views |

{style="table-layout:auto"}

Administratörer av produktprofiler kan lägga till eller ta bort åtkomst till guidad analys i Adobe Admin Console.

1. Logga in på [Adobe Admin Console](https://adminconsole.adobe.com).
1. Välj **[!UICONTROL Customer Journey Analytics]** i listan över produkter.
1. Välj önskad produktprofil för de behörigheter som du vill redigera.
1. Välj fliken **[!UICONTROL Permissions]** och klicka sedan på **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) bredvid **[!UICONTROL Guided Analysis Access]** i listan med [!UICONTROL Available Permission Items], som lägger till den i listan med [!UICONTROL Included Permission Items].
1. Välj **[!UICONTROL Save]**.

Mer information finns i [Åtkomst på användarnivå](/help/technotes/access-control.md#user-level-access).

>[!TIP]
>
>Vissa administratörer föredrar att aktivera guidad analys och inaktivera Analysis Workspace för nya användare i Customer Journey Analytics. När dessa användare har kommit överens med produkten och era organisationsdata kan ni aktivera åtkomst till Analysis Workspace.
