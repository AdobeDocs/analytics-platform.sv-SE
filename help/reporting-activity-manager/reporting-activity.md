---
title: Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 57124124254f5ca9eb2a9f63a7478cd288c19b0e
workflow-type: tm+mt
source-wordcount: '1704'
ht-degree: 1%

---

# Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren

{{release-limited-testing}}

The [!UICONTROL Reporting Activity Manager] gör det möjligt för administratörer att snabbt diagnostisera och åtgärda problem med rapporttapaciteten under perioder med hög rapporteringsnivå.

Mer information om Reporting Activity Manager, inklusive viktiga fördelar och behörighetskrav, finns i [Översikt över Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md).

## Visa rapporteringsaktivitet för alla anslutningar {#view-all-report-suites}

1. I Customer Journey Analytics, gå till **[!UICONTROL Tools]** > **[!UICONTROL Reporting Activity Manager]**.

   En lista över dina aktiverade basanslutningar visas.

   ![rapportkö](assets/reporting-activity1.png)

1. (Valfritt) Du kan söka efter eller filtrera listan över anslutningar:

   * Använd sökfältet för att söka efter en viss anslutning. Börja skriva anslutningsnamnet eller ID:t och listan över anslutningar som uppdateras medan du skriver.

   * Välj [!UICONTROL **Filter**] icon ![Filterikon](assets/filter-icon.png) om du vill expandera listan med filteralternativ. Du kan filtrera efter [!UICONTROL **Favoriter**] eller [!UICONTROL **Status**].

     Om du vill markera en anslutning som favorit väljer du stjärnikonen till vänster om anslutningsnamnet.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Visa användningsinformation om varje anslutning. Du kan välja en kolumnrubrik för att sortera tabellen efter den kolumnen.

   Följande kolumner är tillgängliga:

   | Gränssnittselement | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Connection]** | Anslutningen vars rapporteringsaktivitet du övervakar. |
   | **[!UICONTROL Data Views]** | Visar alla datavyer som matas in i anslutningen. Datavyer gör det enklare att rapportera förfrågningar på grund av ytterligare nivåer av filtrering och segmentering. Alla begäranden som kommer från datavyn kombineras med anslutningen.<p>Om du till exempel har 10 förfrågningar från 5 datavyer är det 50 förfrågningar vid anslutningen. På så sätt kan du snabbt nå ut till din kapacitet. |
   | **[!UICONTROL Capacity utilization]** | Procentandel av anslutningens rapporteringskapacitet som används i realtid. <p>**Anteckning** En användningskapacitet som är 100 % innebär inte nödvändigtvis att du omedelbart bör avbryta rapporteringsbegäranden. 100 % användningskapacitet kan vara hälsosam om den genomsnittliga väntetiden är rimlig. Å andra sidan kan 100 % av användningskapaciteten tyda på ett problem om antalet begäranden som står i kö också ökar.</p> |
   | **[!UICONTROL Queued requests]** | Antalet begäranden som väntar på att behandlas. <!-- ??? --> |
   | **[!UICONTROL Queue wait time]** | Genomsnittlig väntetid innan begäranden börjar bearbetas. <!-- ???? --> |
   | **[!UICONTROL Status]** | Möjliga statusvärden är: <ul><li>[!UICONTROL **Aktiv**] (blått): Rapporter har körts på anslutningen och den övervakas för aktivitet.</li><li>[!UICONTROL **Inaktiv**] (grå): Inga rapporter har körts på anslutningen. Den här statusen visas endast när anslutningar skapas för första gången.</li></ul> |

   {style="table-layout:auto"}

## Visa rapporteringsaktivitet för en enda anslutning

1. I Customer Journey Analytics väljer du [!UICONTROL **verktyg**] > [!UICONTROL **Rapporteringsaktivitetshanteraren**].

1. Markera den länkade titeln för anslutningen som du vill visa information om.

   Rapporteringsaktivitetsdata visas för anslutningen som du har valt.

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. Använd tillgängliga diagram och tabeller för att förstå rapporteringsaktiviteten i anslutningen.

   * [Visa diagram](#view-graphs)

   * [Visa register](#view-table)

### Visa diagram

Följande diagram är tillgängliga så att du bättre kan förstå vad som händer i anslutningen.

Om diagrammen inte visas markerar du [!UICONTROL **Visa diagram**] -knappen.

#### Användningsdiagram {#utilization}

I användningsdiagrammet visas rapporteringsanvändning för den valda anslutningen under de senaste två timmarna.

Håll pekaren över diagrammet om du vill visa tidpunkter där procentandelen av användningskapaciteten var högst för den minuten.

* **X-axel**: Rapporteringsanvändningskapaciteten under de senaste två timmarna.
* **Y-axel**: Procentandel av rapportanvändningskapaciteten, per minut.

  ![utnyttjandediagram](assets/utilization-graph.png)

#### Diagram över distinkta användare

Diagrammet Distinkta användare visar rapporteringsaktiviteten för den valda anslutningen under de senaste två timmarna.

Håll pekaren över diagrammet om du vill visa tidpunkter där det högsta antalet användare var under den minuten.

* **X-axel**: Rapporteringsaktiviteten under den senaste 2-timmars tidsramen.
* **Y-axel**: Antalet användare som har gjort rapportförfrågningar, per minut.

  ![Diagram över distinkta användare](assets/distinct-users-graph.png)

#### Begärandiagram

I diagrammet Begäranden visas antalet bearbetade och slutförda begäranden för den valda anslutningen under de senaste två timmarna.

Håll pekaren över diagrammet om du vill visa tidpunkter där det högsta antalet förfrågningar för den minuten var högst.

* **X-axel**: Antalet bearbetade och slutförda begäranden under den senaste 2-timmars tidsramen.
* **Y-axel**: Antalet bearbetade begäranden (i lila) och slutförda begäranden (i grönt), per minut.

  ![Diagram över distinkta användare](assets/requests-graph.png)

#### Köar diagram

I ködiagrammet visas den genomsnittliga väntetiden (i sekunder) i kön för att rapportera begäranden för den valda anslutningen under de senaste två timmarna.

Håll pekaren över diagrammet om du vill visa tidpunkter där den maximala genomsnittliga väntetiden var högst för den minuten.

* **X-axel**: Genomsnittlig väntetid i kön för att rapportera begäranden under den senaste 2-timmarsperioden.
* **Y-axel**: Genomsnittlig väntetid (i sekunder).

  ![Diagram över distinkta användare](assets/queueing-graph.png)

### Visa register {#view-table}

Du kan välja att visa data genom att välja någon av följande flikar högst upp i datatabellen: [!UICONTROL **Begäran**], [!UICONTROL **Användare**], [!UICONTROL **Projekt**], eller [!UICONTROL **Program**].

>[!TIP]
>
>Du kan välja [!UICONTROL **Göm diagram**] om du bara vill visa tabellen.

![tabellflikar](assets/indiv-report-ste-table-tabs.png)

#### Visa data på begäran

När du väljer [!UICONTROL **Begäran**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **ID för begäran**] | Kan användas i felsökningssyfte. |
| [!UICONTROL **Körning av tid**] | Hur länge begäran har körts. |
| [!UICONTROL **Starttid**] | När begäran började bearbetas (baserat på administratörens lokala tid). |
| [!UICONTROL **Väntetid**] | Hur länge begäran har väntat innan den bearbetas. Detta värde är vanligtvis&quot;0&quot; när det finns tillräckligt med kapacitet. |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Intelligenta aviseringar</li></ul> |
| [!UICONTROL **Användare**] | Användaren som initierade begäran. <p>**Obs!** Om värdet för den här kolumnen är [!UICONTROL **Okänd**] innebär det att användaren är på ett inloggningsföretag där du inte har administratörsbehörighet.</p> |
| [!UICONTROL **Projekt**] | Sparade projektnamn för arbetsytan, API-rapport-ID:n osv. (Metadata kan variera mellan olika program.) |
| [!UICONTROL **Status**] | Statusindikatorer: <ul><li>**Körs**: Begäran bearbetas för närvarande.</li><li>**Väntande**: Begäran väntar på att bearbetas.</li></ul> |
| [!UICONTROL **Komplex**] | Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran. <p>Möjliga värden är:</p> <ul><li>[!UICONTROL **Låg**]</li><li>[!UICONTROL **Medel**]</li><li>[!UICONTROL **Hög**]</li></ul>Värdet påverkas av värdena i följande kolumner:<ul><li>[!UICONTROL **Månadsgränser**]</li><li>[!UICONTROL **Kolumner**]</li><li>[!UICONTROL **Segment**]</li></ul> |
| [!UICONTROL **Månadsgränser**] | Antalet månader som ingår i en begäran. Fler månadsgränser gör begäran ännu mer komplex. |
| [!UICONTROL **Kolumner**] | Antalet mått och uppdelningar i begäran. Fler kolumner ökar komplexiteten i begäran. |
| [!UICONTROL **Segment**] | Antalet segment som används i begäran. Fler segment ökar komplexiteten i begäran. |

{style="table-layout:auto"}

#### Visa data per användare

När du väljer [!UICONTROL **Användare**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Användare**] | Användaren som initierade begäran. Om värdet för den här kolumnen är [!UICONTROL **Okänd**] innebär det att användaren är på ett inloggningsföretag där du inte har administratörsbehörighet. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som initierats av användaren. |
| [!UICONTROL **Antal projekt**] | Antalet projekt som är associerade med användaren. <!-- ??? --> |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Intelligenta aviseringar</li></ul> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten för begäranden som initierats av användaren. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p><ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Fler månadsgränser gör begäran ännu mer komplex. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Fler kolumner ökar komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Fler segment ökar komplexiteten i begäran. |

{style="table-layout:auto"}

#### Visa data efter projekt

När du väljer [!UICONTROL **Projekt**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Projekt**] | Det projekt där frågorna initierades. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som är associerade med projektet. |
| [!UICONTROL **Antal användare**] | Antalet användare som är associerade med projektet. <!-- ??? --> |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Intelligenta aviseringar</li></ul> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten hos begäranden som ingår i projektet. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p><ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Fler månadsgränser gör begäran ännu mer komplex. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Fler kolumner ökar komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Fler segment ökar komplexiteten i begäran. |

{style="table-layout:auto"}

#### Visa data efter program

När du väljer [!UICONTROL **Program**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Program**] | Det program där frågorna initierades. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som är associerade med programmet. |
| [!UICONTROL **Antal användare**] | Antalet användare som är associerade med programmet. <!--???--> |
| [!UICONTROL **Antal projekt**] | Antalet projekt som är associerade med programmet. <!--???--> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten för begäranden som är associerade med programmet. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:<ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Fler månadsgränser gör begäran ännu mer komplex. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Fler kolumner ökar komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Fler segment ökar komplexiteten i begäran. |

{style="table-layout:auto"}

<!--

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](/help/admin/admin/assets/filter.png)

### Summary Numbers {#summary}

![filter](/help/admin/admin/assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL **Users**] | The number of users that are currently sending reporting requests to this connection. |
| [!UICONTROL **Projects**] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL **Queries**] | The number of queries currently running. |
| [!UICONTROL **Average Wait Time**] | The average wait time for all running queries.  |
| [!UICONTROL **Usage Capacity**] | The current usage capacity for this connection. |

{style="table-layout:auto"}

-->