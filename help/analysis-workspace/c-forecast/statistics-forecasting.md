---
description: Läs om hur prognosticeringar i Analysis Workspace använder en serie avancerade statistiska tekniker för att fastställa prognosvärden.
title: Statistiska tekniker
feature: Visualizations
role: User
exl-id: f042a6dd-6af5-4bdd-afc9-07546d8ded6e
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# Statistisk teknik

Prognostjänsten har för närvarande stöd för Prophet och har visat sig fungera effektivt och tillförlitligt för de flesta data. Prophet är ett vanligt populärt paket med öppen källkod som utvecklats av Meta. Data delas upp i komponenter för trender, säsongseffekter och händelser. Prophetmodellen är effektiv och kan skalas upp till många prognosprogram. Dessutom fungerar modellen rejält mot avvikelser och data som saknas.

I framtiden finns det planer på att välja modeller baserade på heuristik, till exempel Online Approximate Gaussian Process för strömmande data eller NeuralProphet när användarna anger den bästa prognosnoggrannheten och tolererar längre väntetid.

Tjänsten minskar automatiskt datavärden när det finns för många datapunkter, för att säkerställa svarstid. Målsvarstiden är angiven till ~3 sekunder. För närvarande, när antalet datapunkter överstiger 5500, nedsamplas tidsseriedata på ett adaptivt sätt, beroende på datalängden. Utdata konverteras tillbaka till den ursprungliga datafrekvensen, så den adaptiva samplingsprocessen påverkar inte användarupplevelsen.

Semestereffekterna beaktas när det finns flera års data tillgängliga. För närvarande är listan över helgdagar:

* Martin Luther King-dagen
* Presidentdagen
* Minnesdag
* Juli 4
* Thanksgiving
* Black Friday
* Cyber Monday
* Jul

Tjänsten kan också utföra en enkel avvikelseborttagning (avvikelser), till exempel genom att ta bort datapunkter som ligger utanför sex sigmaintervall. Detta är inte aktiverat som standard eftersom det antas att alla datapunkter är giltiga. Anomalier kan ha en negativ inverkan på modellens kvalitet även om Prophetmodellen är motståndskraftig mot avvikelser i allmänhet.

Tjänsten accepterar användardefinierade säsongsinställningar, t.ex. daglig och veckovis säsongsvariation. I annat fall väljs säsongsvariationen automatiskt. För olika datagranularitet använder tjänsten olika längder av historiska data för att skapa prognosmodeller. För dagliga data hämtas till exempel mer än ett års data (om sådana finns). För timdata hämtas åtta veckors data (om sådana finns). Att hämta data kan vara tidsödande och kan ibland orsaka längre väntetid.

Historikdata som krävs för olika tidsterminaler:

| Kornighet | Historiska data krävs |
|---|--:|
| Minut | 3 dagar |
| Timme | 2 veckor |
| Dag | 8 veckor |
| Vecka | 2 år |
| Månad | 2 år |
| Kvartal | 8 kvartal |
| År | 8 år |


Prognosresultatet för varje angiven tid har ett förutsägelseintervall (som definieras av den nedre och övre gränsen) som förväntas innehålla det framtida observerade värdet 95 % av tiden, vilket ofta kallas konfidensintervall. Det finns ingen gräns för hur långt tjänsten kan förutspå i framtiden. Osäkerheten i prognoserna ökar dock med datum längre in i framtiden, vilket avspeglas i ett större prognosintervall över tiden.

Tjänsten gör inga antaganden om användardata. Tjänsten antar till exempel inte att data är icke-negativa. Detta innebär att prognoserna och/eller deras gränser kan vara negativa om data uppvisar en stark nedåtgående trend, även om alla observerade datapunkter är icke-negativa.


## Referenser

1. Taylor, Sean J. och Benjamin Letham: *Prognoser i skala.* Amerikansk statistiker 72.1 (2018): 37-45.
1. Triebe, Oskar, et al.: *Neuralprofet: Förklara prognoser i stor skala.* arXiv preprint arXiv:2111.15397(2021).
1. Zhang och Arbor: *Avvikelseidentifiering för tidsserie.* US-patentprogram nr 18/057883.
