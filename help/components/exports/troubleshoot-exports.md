---
description: Hantera loggar för befintlig export
keywords: Analysis Workspace
title: Felsökning av misslyckade exporter
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
source-git-commit: 2c9dfdf36e47b9467077310a31dc2c6258137d35
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# Felsökning av misslyckade exporter

{{release-limited-testing}}

När du [exportera hela tabeller från Analysis Workspace till molnmål](/help/analysis-workspace/export/export-cloud.md)kan du visa status för dessa exporter från båda [Fliken Exportera](/help/components/exports/manage-exports.md) och från [Fliken Loggar](/help/components/exports/manage-export-logs.md). Misslyckade exporter visar status för [!UICONTROL **Misslyckades**].

## Vanliga fel och åtgärder

Export kan misslyckas av olika anledningar. I följande tabell beskrivs några av de vanligaste orsakerna, med åtgärder som du kan vidta för att åtgärda felen:

| Orsak till fel | Föreslagen åtgärd | Mer information |
|---------|----------|---------|
| Ogiltig plats- eller kontoinformation | Kontrollera att autentiseringsuppgifterna och annan information är korrekta för molnkontot och platsen som du exporterar till. | [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md) och [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md). |
| En dimension eller ett mått i rapporten togs bort från datavyn | Kontakta systemadministratören för att se vilka komponenter som har tagits bort från datavyn. Du kan behöva använda en annan datavy vid exporten eller ta bort komponenter från tabellen som inte längre är tillgängliga. | [Exportera Customer Journey Analytics-rapporter till molnet](/help/analysis-workspace/export/export-cloud.md) |
| Radgränsen har överskridits | Beroende på licenstyp kan du exportera högst 3 miljoner, 30 miljoner, 150 miljoner eller 300 miljoner rader. Uppdatera tabellen som du exporterar för att minska antalet totala rader. | [Exportera Customer Journey Analytics-rapporter till molnet](/help/analysis-workspace/export/export-cloud.md) |
| Schemalagd exportförfallotid | Den schemalagda exporten som du konfigurerade har upphört att gälla. Uppdatera exportens förfallodatum. | [Hantera exporter](/help/components/exports/manage-exports.md) |
| Dimensionen stöds inte | <p>Alla dimensioner som uppfyller följande villkor stöds inte i Fullständig tabellexport:</p> <ul><li>Använder en objektarray</li><li>Har beständighet aktiverat<li>Använder inte en bindningsdimension</li> | <ul><li>[Använda arrayer med objekt](/help/use-cases/object-arrays.md)</li><li>[Inställningar för Persistence-komponent](/help/data-views/component-settings/persistence.md)<li>[Använd bindningsdimensioner och mätvärden i Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| En datastyrningsprincip som tillämpas av organisationen begränsar möjligheten att exportera komponenter i tabellen | Kontakta systemadministratören om du vill veta vilka komponenter som är begränsade från att exporteras. Ta bort de begränsade komponenterna innan du exporterar. | *Filtrera på datastyrningsprinciper i datavyer* avsnitt i [Etiketter och profiler](/help/data-views/data-governance.md) |

## Kontakta Adobe kundtjänst

Kontakta Adobe kundtjänst om du fortfarande får problem. Kontrollera att du har följande information tillgänglig när du kontaktar kundtjänst angående en misslyckad export:

* Exportnamn

* Export-ID

* Instans-ID

* Datavy name

* Plats

* Konto

* Anslutning

* Företag
