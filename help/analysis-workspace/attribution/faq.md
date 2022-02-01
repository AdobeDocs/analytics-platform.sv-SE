---
title: Vanliga frågor om attribuering
description: Få svar på vanliga frågor om attribuering.
feature: Attribution
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 6%

---

# Vanliga frågor om attribuering

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Funktionsuppsättningen skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

**Vad är radobjektet &quot;Inget&quot; när du använder attribuering?**

Radobjektet Ingen är ett objekt som fångar upp alla konverteringar som har gjorts utan några beröringspunkter i uppslagsfönstret. Försök att inkludera ett längre tidsintervall i rapportfönstret.

**Varför ser jag ibland datum utanför mitt rapporteringsfönster när jag använder attribueringsmodeller?**

Dessa extra datum beror på besökarens rapportfönster. Se [Data visas utanför rapportfönstret](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) i KB:n för analyser för mer information. Adobe planerar att filtrera bort de här extra raderna i en kommande release.

**När ska jag använda ett besöks- eller besöksattribueringsbesök?**

Vilken attribueringssökning du väljer beror på ditt användningsfall. Om konverteringen tar längre tid än ett enda besök rekommenderar vi att besökaren tittar tillbaka. Att skapa en datavy med en längre besöksdefinition är också en möjlig lösning.

**Hur är props och eVars jämfört när man använder attribuering?**

Attribution beräknas om vid rapportkörning, så det finns ingen skillnad mellan ett prop eller en eVar (eller någon annan dimension) för attribueringsmodelleringens skull. Props kan finnas kvar med alla uppslagsfönster eller attribueringsmodeller, och eVar allokerings-/förfalloinställningar ignoreras.

**Vilka mått och mätvärden stöds inte?**

Attributpanelen har stöd för alla dimensioner. Mätvärden som inte stöds är:

* Unika besökare
* Besök
* Förekomster
* Sidvisningar
* A4T-mått
* Tidsmått
* Studsar
* Studsfrekvens
* Första besökssida
* Sista besökssida
* Sidor som inte hittades
* Sökningar
* Besök på en sida
* Enkelt besök

**Hur fungerar attribuering med filter?**

Attribution körs alltid före filter, och globala filter körs innan andra rapportfilter tillämpas.
