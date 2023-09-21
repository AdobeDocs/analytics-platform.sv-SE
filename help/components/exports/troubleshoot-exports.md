---
description: Hantera loggar för befintlig export
keywords: Analysis Workspace
title: Felsökning av misslyckade exporter
feature: Components
hide: true
hidefromtoc: true
source-git-commit: a2b2c6bca0557521ac7b6bcf635f467ca41731b7
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---

# Felsökning av misslyckade exporter

När du [exportera hela tabeller från Analysis Workspace till molnmål](/help/analysis-workspace/export/export-cloud.md)kan du visa status för dessa exporter från båda [Fliken Exportera](/help/components/exports/manage-exports.md) och från [Fliken Loggar](/help/components/exports/manage-export-logs.md). Misslyckade exporter visar status för [!UICONTROL **Misslyckades**].

## Vanliga fel och åtgärder

Export kan misslyckas av olika anledningar. I följande tabell beskrivs några av de vanligaste orsakerna, med åtgärder som du kan vidta för att åtgärda felen:

| Orsak till fel | Föreslagen åtgärd | Mer information |
|---------|----------|---------|
| Ogiltig plats- eller kontoinformation | Kontrollera att autentiseringsuppgifterna och annan information är korrekta för molnkontot och platsen som du exporterar till. | [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md) och [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md). |
| En dimension eller ett mått i rapporten togs bort från datavyn | Kontakta systemadministratören för att se vilka komponenter som har tagits bort från datavyn. Du kan behöva använda en annan datavy vid exporten eller ta bort komponenter från tabellen som inte längre är tillgängliga. | [Exportera Customer Journey Analytics-rapporter till molnet](/help/analysis-workspace/export/export-cloud.md) |
| En datastyrningsprincip som tillämpas av organisationen begränsar möjligheten att exportera komponenter i tabellen | Kontakta systemadministratören om du vill veta vilka komponenter som är begränsade från att exporteras. Ta bort de begränsade komponenterna innan du exporterar. | *Filtrera på datastyrningsprinciper i datavyer* avsnitt i [Etiketter och profiler](/help/data-views/data-governance.md) |

## Kontakta Adobe kundtjänst

Kontakta Adobe kundtjänst om du fortfarande får problem. Kontrollera att du har följande information tillgänglig när du kontaktar kundtjänst angående en misslyckad export:

* Exportnamn

* Export-ID

* Instans-ID

* Datavy name

* Plats

* Konto

* Företagsnamn

* Anslutning

* Datavy