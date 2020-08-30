---
description: Anomalys detektion i Analysis Workspace använder en rad avancerade statistiska tekniker för att avgöra om en observation bör betraktas som onormal eller inte.
title: Statistiska tekniker som används för avvikelseidentifiering
uuid: b6ef6a2e-0836-4c9a-bf7e-01910199bb92
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 2%

---


# Statistiska tekniker som används för avvikelseidentifiering

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Anomalys detektion i Analysis Workspace använder en rad avancerade statistiska tekniker för att avgöra om en observation bör betraktas som onormal eller inte.

Beroende på vilket datum granulariteten används i rapporten används tre olika statistiska metoder - särskilt för timbaserad, daglig, veckovis/månadsvis upptäckt av anomalier. Varje statistisk teknik beskrivs nedan.

## Anomalsidentifiering för daglig granularitet

För dagliga granularitetsrapporter tar algoritmen hänsyn till flera viktiga faktorer för att ge så korrekta resultat som möjligt. För det första avgör algoritmen vilken typ av modell som ska tillämpas baserat på tillgängliga data som vi väljer mellan en av två klasser - en tidsseriebaserad modell eller en outlier-detektionsmodell (kallas funktionell filtrering).

Urvalet av tidsseriemodell baseras på följande kombinationer för typ av fel, trend och säsongsbundenhet (ETS) enligt beskrivningen i [Hyndman m.fl. (2008)](https://www.springer.com/us/book/9783540719168). I algoritmen används följande kombinationer:

1. ANA (additivt fel, ingen trend, additiv säsongsbundenhet)
1. AAA (additivt fel, additiv tendens, additiv säsongsbundenhet)
1. MNM (multiplikativt fel, ingen trend, multiplikativ säsongsvariation)
1. MNA (multiplikativt fel, ingen trend, additiv säsongsbundenhet)
1. AAN (additivt fel, additiv tendens, ingen säsongsbundenhet)

Algoritmen testar lämpligheten hos var och en av dessa genom att välja den med det bästa medelvärdet för absolut procentfel (MAPE). Om MAPE för modellen med bästa tidsserie är större än 15 % tillämpas dock funktionell filtrering. Vanligtvis är data med hög repetitionsgrad (t.ex. vecka över vecka eller månad över månad) bäst lämpade för en tidsseriemodell.

Efter modellval justerar algoritmen sedan resultaten baserat på semester och årstidsbetingelser över året. För semesterdagar kontrollerar algoritmen om det finns någon av följande semesterdagar i rapporteringsdatumintervallet:

* Minnesdag
* Juli 4
* Thanksgiving
* Svarta fredagen
* Cyber Måndag
* 24-26 december
* Januari 1
* 31 december

Dessa helgdagar valdes ut på grundval av omfattande statistiska analyser över många kunddatapunkter för att identifiera de semesterdagar som var viktigast för det största antalet kunder. Även om listan inte är fullständig för alla kunder eller affärscykler fann vi att tillämpningen av dessa helgdagar avsevärt förbättrade algoritmens prestanda totalt för nästan alla kunders dataset.

När modellen har valts och helgdagar har identifierats i rapporteringsdatumintervallet, fungerar algoritmen på följande sätt:

1. Konstruera den onormala referensperioden - detta omfattar upp till 35 dagar före rapporteringsdatumintervallet och ett matchningsdatumintervall ett år tidigare (redovisning av skottdagar när så krävs och inklusive eventuella tillämpliga helgdagar som kan ha inträffat på en annan kalenderdag under föregående år).
1. Testa om semesterdagar under innevarande period (exklusive föregående år) är onormala baserat på de senaste uppgifterna.
1. Om semestern i det aktuella datumintervallet är onormal, justera det förväntade värdet och konfidensintervallet för den aktuella semestern med tanke på föregående års semester (med beaktande av två dagar före och efter). Korrigeringen för den aktuella semestern baseras på det lägsta genomsnittliga absoluta felprocentet:

   1. Additiva effekter
   1. Multiplicerande effekter
   1. YoY-differens

Observera den dramatiska förbättringen av prestandan på juldagen och nyårsdagen i följande exempel:

![](assets/anomaly_statistics.png)

## Anomalys detektion för timgranularitet

Timdata bygger på samma algoritmansmetod för tidsserier som den dagliga granularitetsalgoritmen gör. Den är dock starkt beroende av två trender: 24-timmarscykeln samt veckosluts-/veckodagscykeln. För att fånga upp dessa två säsongseffekter bygger timalgoritmen två separata modeller för en helg och en vardag med samma metod som beskrivs ovan.

Utbildningsfönstren för timtrender är beroende av ett 336-timmars uppslagsfönster.

## Anomalsidentifiering för vecko- och månadsgranularitet

Trenderna per vecka och månad uppvisar inte samma vecko- eller dagstrender som konstateras vid granularitet per dag eller per timme, vilket innebär att en sådan separat algoritm används. För varje vecka och varje månad används en metod för detektion i två steg som kallas GESD-test (Generalized Extreme Studentized Deviate). I detta test beaktas det maximala antalet förväntade anomalier i kombination med den justerade rutnätsmetoden (en icke-parametrisk metod för outlier-upptäckt) för att fastställa det maximala antalet avvikande värden. De två stegen är följande:

1. Justerad rutnätsfunktion: Den här funktionen bestämmer det maximala antalet avvikelser som anges i inmatningsdata.
1. GESD-funktion: Används på indata med utdata från steg 1.

Under semestersäsongen och Unga på väg-årsjubileet subtraheras sedan förra årets data från årets data och upprepas sedan med hjälp av tvåstegsprocessen ovan för att kontrollera att avvikelser är säsongsmässigt lämpliga. Vid var och en av dessa datum används en 15-perioders uppslag med det valda rapporteringsdatumintervallet (antingen 15 månader eller 15 veckor) och ett motsvarande datumintervall för 1 år sedan för utbildning.
