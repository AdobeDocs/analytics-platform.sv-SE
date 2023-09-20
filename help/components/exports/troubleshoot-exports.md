---
description: Hantera loggar för befintlig export
keywords: Analysis Workspace
title: Felsökning av misslyckade exporter
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 24e9e4151360597b099a7985a4566b3ca7bfff00
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Felsökning av misslyckade exporter

När du [exportera hela tabeller från Analysis Workspace till molnmål](/help/analysis-workspace/export/export-cloud.md)kan du visa status för dessa exporter från båda [Fliken Exportera](/help/components/exports/manage-exports.md) och från [Fliken Loggar](/help/components/exports/manage-export-logs.md). Misslyckade exporter visar status för [!UICONTROL **Misslyckades**].

Export kan misslyckas av olika anledningar. I följande tabell beskrivs några av de vanligaste orsakerna, med åtgärder som du kan vidta för att åtgärda felen:

| Orsak till fel | Föreslagen åtgärd | Mer information |
|---------|----------|---------|
| Ogiltig plats- eller kontoinformation | Kontrollera att autentiseringsuppgifterna och annan information är korrekta för molnkontot och platsen som du exporterar till. | [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md) och [Konfigurera platser för molnexport](/help/components/exports/cloud-export-locations.md). |
| En dimension eller ett mått i rapporten togs bort från datavyn | Kontakta systemadministratören för att se vilka komponenter som har tagits bort från datavyn. Du kan behöva använda en annan datavy vid exporten eller ta bort komponenter från tabellen som inte längre är tillgängliga. | [Exportera data från Customer Journey Analytics till molnet](/help/analysis-workspace/export/export-cloud.md) |
| En datastyrningsprincip som tillämpas av organisationen begränsar möjligheten att exportera komponenter i tabellen | Kontakta systemadministratören om du vill veta vilka komponenter som är begränsade från att exporteras. Ta bort de begränsade komponenterna innan du exporterar. | *Filtrera på datastyrningsprinciper i datavyer* avsnitt i [Etiketter och profiler](/help/data-views/data-governance.md) |