---
description: Exempel när du konfigurerar en visualisering av en arbetsyta i en resa
title: Exempel på arbetsyta på resan
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: 057c9f4a0e8fb163bfb23cea1870f949ad4ae1c0
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# Felsökning av arbetsytan på resan

{{release-limited-testing}}

Med visualiseringen av arbetsytan på resande fot kan ni analysera och få djupgående insikter om de resor som ni erbjuder era användare och kunder.

Mer information om arbetsytan på resan finns i [Översikt över arbetsytan på resan](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) och [Konfigurera en visualisering av arbetsytan på resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


## Kompatibilitet mellan behållarmått och primärmått

Du kan konfigurera researbetsytebehållaren som Person (som använder personmåttet) eller Session (som använder sessionsmåttet).

När du väljer ett primärt eller sekundärt mått måste du välja ett mått som är kompatibelt med det behållarmått som är valt. De flesta mätvärden är kompatibla med de behållarmått som är tillgängliga. Vissa kombinationer av behållarmått och primära eller sekundära mått bör dock undvikas.

Om du till exempel använder Person som behållare med Session som primärt eller sekundärt mått


| Behållare | Primära eller sekundära mätvärden | Resultat |
|---------|----------|---------|
| Folk | Session | Den här kombinationen kan ge oönskade resultat. Resultatet av kombinationen kan vara |
| A2 | B2 | C2 |
| A3 | B3 | C3 |


## Procenttal som överskrider 100 %

Följande konfigurationer kan resultera i noder som visar procenttal som överskrider 100 %:

* När fältet **[!UICONTROL Percentage value]** är inställt på **[!UICONTROL Percent of total]** och ett primärt mått har valts, vilket ger mindre data för startnoden än för efterföljande noder.

  Om du t.ex. väljer Intäkter som primär måttenhet och ingen intäkt realiseras på det primära måttet, kommer det på alla noder där intäkten realiseras att visa sig som över 100 %.


## En resa som inte är trattformad

I Resans arbetsyta kan noder som kommer senare under resan visa ett högre procentvärde eller ett högre antal än noder som kommer tidigare under resan.

Till skillnad från Fallout-visualiseringar, som alltid är trattformade (där deltagandet minskar i varje steg), kan visualiseringar av arbetsytan på resande fot ha större delaktighet i senare steg av resan.

Tänk på en resa med följande egenskaper:

* Resan innehåller 3 noder: Nod A —> Nod B —> Nod C

* Fältet **[!UICONTROL Percentage value]** har värdet **[!UICONTROL Percent of total]**

* **[!UICONTROL Person]** anges som behållare

* **[!UICONTROL Event]** anges som primärt mått

Anta att en besökare besökte nod A, nod B och sedan nod C i det här scenariot. Var och en av dessa besök räknas som en enda händelse på varje nod, eftersom de besöktes i den ordning som definieras av resan.

Vid ett senare besök på webbplatsen besöker besökaren endast nod C, vilket resulterar i en extra händelse på nod C.

I det här fallet visar noderna A och B 1 händelse och 100 %, medan nod C visar 2 händelser och 200 %.

Å andra sidan skulle noderna A, B och C visa 1 händelse och 100 % om Session var inställd som container, eftersom det efterföljande besöket på webbplatsen där besökaren besökte endast nod C inte skulle ha uppfyllt kraven för resan, eftersom nod A och nod B inte besöktes före besök på nod C.
