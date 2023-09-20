---
description: Förstå de olika metoder som är tillgängliga för export från Analysis Workspace.
keywords: Analysis Workspace
title: Översikt över projektdata
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Exportera översikt

Du kan exportera Customer Journey Analytics-data från Analysis Workspace. Du kan behöva exportera Customer Journey Analytics-data av flera olika anledningar, till exempel för att lagra stora mängder historiska data eller för att analysera rådata i verktyg från tredje part.

I följande avsnitt beskrivs vilka filtyper som stöds, de olika metoder som är tillgängliga för export och fördelarna med varje metod.

## Filtyper som stöds

Du kan exportera Customer Journey Analytics-data som en PDF- eller CSV-fil.

* **PDF:** Ger ett enkelt sätt att dela visuella data med intressenter. PDF-filer innehåller alla tabeller och visualiseringar som visas i projektet.

* **CSV:** Gör att du kan visa rådata i ett kalkylbladsprogram, t.ex. Excel. CSV-filer innehåller textdata.

## Exportmetoder

Det finns olika metoder för export från Analysis Workspace. När du väljer en exportmetod bör du tänka på vad du vill exportera och vem som behöver få åtkomst till den.

| Exportmetod | Fördelar |
|---------|----------|
| [Hämta till din arbetsstation](/help/analysis-workspace/export/download-send.md) | Använd den här metoden om du vill: <ul><li>Ladda ned projekt till din personliga arbetsstation.</li><li>Hämtningar är endast för särskilda ändamål (kan inte schemaläggas).</li> <li>Ladda ned totalt 50 000 rader.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Skicka till andra användare](/help/analysis-workspace/export/t-schedule-report.md) | Använd den här metoden om du vill: <ul><li>E-posta exporterade Customer Journey Analytics-data till andra användare i organisationen.</li><li>Kan vara ad hoc eller enligt ett schema.</li> <li>Inkludera totalt 50 000 rader.</li> <!--true?--> |
| [Skicka till ett molnprogram](/help/analysis-workspace/export/export-cloud.md) | Använd den här metoden om du vill: <ul><li>Exportera till en delad plats, som Google Cloud Platform, Microsoft Azure, Amazon S3, Snowflake eller Adobe Experience Platform.</li><li>Kan vara ad hoc eller enligt ett schema.</li><li>Lagra stora mängder historiska data om Customer Journey Analytics.</br>Denna typ av data kan användas för att upptäcka långsiktiga trender för att få affärsinformation och i slutändan leda till bättre beslutsunderlag.</li><li>Exportera fullständiga tabeller som innehåller tusentals eller miljontals rader.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}

