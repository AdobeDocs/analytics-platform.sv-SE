---
description: Förstå vilka metoder som är tillgängliga för export från Analysis Workspace.
keywords: Analysis Workspace
title: Så här exporterar du projektdata
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Exportera översikt

Du kan exportera Customer Journey Analytics-rapporter från Analysis Workspace. Du kan behöva exportera Customer Journey Analytics-rapporter av flera olika anledningar, t.ex. använda i tredjepartsverktyg eller kombinera med externa data.

I följande avsnitt beskrivs vilka filtyper som stöds, de olika metoder som är tillgängliga för export och fördelarna med varje metod.

## Filtyper som stöds

Du kan exportera Customer Journey Analytics-rapporter som en PDF-, CSV- eller JSON-fil.

* **PDF:** Ger ett enkelt sätt att dela visuella data med intressenter. PDF-filer innehåller alla tabeller och visualiseringar som visas i projektet.

* **CSV:** Gör att du kan visa rådata i ett kalkylbladsprogram, t.ex. Excel. CSV-filer innehåller textdata.

* **JSON:** Innehåller ett öppet standardfilformat för datadelning.

## Exportmetoder

Det finns olika metoder för export från Analysis Workspace. När du väljer en exportmetod bör du tänka på vad du vill exportera och vem som behöver få åtkomst till den.

| Exportmetod | Fördelar |
|---------|----------|
| [Hämta till din arbetsstation](/help/analysis-workspace/export/download-send.md) | Använd den här metoden om du vill: <ul><li>Ladda ned projekt till din personliga arbetsstation.</li><li>Hämtningar är endast för särskilda ändamål (kan inte schemaläggas).</li> <li>Ladda ned totalt 50 000 rader.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Skicka till andra användare](/help/analysis-workspace/export/t-schedule-report.md) | Använd den här metoden om du vill: <ul><li>E-posta exporterade Customer Journey Analytics-data till andra användare i organisationen.</li><li>Kan vara ad hoc eller enligt ett schema.</li> <li>Inkludera totalt 50 000 rader.</li> <!--true?--> |
| [Skicka till ett molnprogram](/help/analysis-workspace/export/export-cloud.md) | Använd den här metoden om du vill: <ul><li>Exportera till en delad plats, som Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 eller Snowflake.</li><li>Kan vara ad hoc eller enligt ett schema.</li><li>Lagra större mängder data från Customer Journey Analytics.</li><li>Exportera fullständiga tabeller som innehåller tusentals eller miljontals rader.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
