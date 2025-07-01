---
description: Förstå vilka metoder som är tillgängliga för export från Analysis Workspace.
keywords: Analysis Workspace
title: Så här exporterar du projektdata
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: c91ee21a3d4e20e3bdaeb75f2011ede6eee6cba0
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Exportera översikt

Du kan exportera (del av) Customer Journey Analytics-projekt från Analysis Workspace. Du kan behöva exportera Customer Journey Analytics-rapporter av olika anledningar, t.ex. för att använda i tredjepartsverktyg eller kombinera med externa data.

I följande avsnitt beskrivs vilka filtyper som stöds, de olika metoder som är tillgängliga för export och fördelarna med varje metod.

## Filtyper som stöds

Du kan exportera Customer Journey Analytics-rapporter som en PDF-, CSV- eller JSON-fil.

* **PDF:** Ett enkelt sätt att dela visuella data med intressenter. PDF-filer innehåller alla tabeller och visualiseringar som visas i projektet.

* **CSV:** Gör att du kan visa rådata i ett kalkylbladsprogram, till exempel Excel. CSV-filer innehåller textdata.

* **JSON:** Tillhandahåller ett öppet standardfilformat för datadelning.

## Exportmetoder

Det finns olika metoder att använda när du vill exportera från Analysis Workspace. När du väljer en exportmetod bör du tänka på vad du vill exportera och vem som behöver komma åt den.

| Exportmetod | Använd den här metoden om du vill.. |
|---------|----------|
| [Hämta till din arbetsstation](/help/analysis-workspace/export/download-send.md) | <li>Ladda ned projekt till din personliga arbetsstation.</li><li>Hämta endast ad hoc-data (inte schemalagda).</li> <li>Ladda ned högst 50 000 rader.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Skicka till andra användare](/help/analysis-workspace/export/t-schedule-report.md) | <li>E-posta exporterade Customer Journey Analytics-data till andra användare i organisationen.</li><li>Skicka ett e-postmeddelande eller ett schema.</li> <li>Ta med högst 50 000 rader i e-postmeddelandet.</li> <!--true?--> |
| [Exportera till ett molnprogram](/help/analysis-workspace/export/export-cloud.md) | <li>Exportera till en molnplats, till exempel <ul><li>Adobe Experience Platform Data Landing Zone</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Exportera data vid behov eller enligt ett schema.</li><li>Lagra större mängder Customer Journey Analytics-data.</li><li>Exportera fullständiga tabeller som innehåller tusentals eller miljontals rader.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
