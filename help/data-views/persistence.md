---
title: Vad är dimensionskonsistens i Customer Journey Analytics?
description: Dimensionens beständighet är en kombination av allokering och förfallodatum. Tillsammans avgör de vilka dimensionsvärden som kvarstår.
translation-type: tm+mt
source-git-commit: efe92e25229addadf57bff3f2ba73d831a3161ea
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 12%

---


# Persistence

Dimensionens beständighet är en kombination av allokering och förfallodatum. Tillsammans avgör de vilka dimensionsvärden som kvarstår. Adobe rekommenderar att du diskuterar inom organisationen hur flera värden för varje dimension hanteras (allokering) och när dimensionsvärden avbryter bestående data (förfallodatum).

* Som standard använder ett dimensionsvärde ? allokering.
* Som standard används en förfallotid på [!UICONTROL Session] för ett dimensionsvärde.

## Allokering

Allokering använder en omformning på det underliggande värdet som du använder. Följande allokeringsmodeller stöds:

* Senaste
* Original
* Alla
* Första kända
* Senast känd

### [!UICONTROL Most recent] allokering

Här följer ett före och efter-exempel på [!UICONTROL Most recent]-allokering:

| Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
| --- | --- | --- | --- | --- | --- |
| tidsstämpel (min) | 3 | 2 | 3 | 6 | 7 |
| originalvärden |  | C | B |  | A |
| Senaste allokering |  | C | B | B | A |

### [!UICONTROL Original] allokering

Här följer ett före och efter-exempel på [!UICONTROL Original]-allokering:

| Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
| --- | --- | --- | --- | --- | --- |
| tidsstämpel (min) | 3 | 2 | 3 | 6 | 7 |
| originalvärden |  | C | B |  | A |
| Ursprunglig allokering |  | C | C | C | C |

### [!UICONTROL All] allokering

Den nya dimensionsallokeringen kan användas för både matrisbaserade dimensioner och dimensioner med ett värde. Den fungerar ungefär som [!UICONTROL Participation]-attribueringsmodellen för mått. Skillnaden är att enskilda värden i fältet kan förfalla vid olika punkter. Vi har t.ex. 5 händelser i ett strängfält med allokeringen inställd på &quot;Alla&quot; och förfallotiden inställd på 5 minuter. Vi förväntar oss följande beteenden:

| Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
| --- | --- | --- | --- | --- | --- |
| tidsstämpel (min) | 3 | 2 | 3 | 6 | 7 |
| originalvärden | A | B | C |  | A |
| after-persistence | A | A,B | A, B, C | B,C | A,C |

Observera att värdet för A kvarstår tills det når 5-minutersmarkeringen, medan B och C fortsätter till Träff 4 eftersom 5 minuter ännu inte har passerat för dessa värden. Observera att den här allokeringen skapar en flervärdesdimension från ett fält med ett värde. Den här modellen bör även ha stöd för matrisbaserade dimensioner:

| Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
| --- | --- | --- | --- | --- | --- |
| tidsstämpel (min) | 1 | 2 | 3 | 6 | 7 |
| originalvärden | A,B | C | B,C |  | A |
| after-persistence | A,B | A, B, C | A, B, C | B,C | A, B, C |

### &quot;First Known&quot; och &quot;Last Known&quot;-allokeringar

Dessa två nya allokeringsmodeller tar det första eller sista observerade värdet för en dimension inom ett angivet beständigt omfång (session, person eller anpassad tidsperiod med uppslag) och tillämpar det på alla händelser inom det angivna omfånget. Exempel:

| Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
| --- | --- | --- | --- | --- | --- |
| tidsstämpel (min) | 3 | 2 | 3 | 6 | 7 |
| originalvärden |  | C | B |  | A |
| först känd | C | C | C | C | C |
| senast känd | A | A | A | A | A |

De första eller sista kända värdena kan användas endast för en session eller i en persons (rapportfönstrets) omfång eller i ett anpassat eller tidsbaserat omfång (i huvudsak ett personomfång med ett uppslagsfönster tillagt).

## Förfaller

[!UICONTROL Expiration] gör att du kan ange det beständiga fönstret för en dimension.

Det finns fyra sätt att förfalla ett dimensionsvärde:

* Session (standard): Upphör att gälla efter en viss session.
* Person: ?
* Tid: Du kan ange att dimensionsvärdet ska förfalla efter en angiven tidsperiod eller händelse.
* Mått: Du kan ange vilken som helst av de definierade måtten som förfallodatum för den här dimensionen (t.ex. ett köpmått).
* Anpassad:

### Vad är skillnaden mellan allokering och attribuering?

**Allokering**: Tänk på allokering som&quot;dataomvandling&quot; av dimensionen. Allokering sker före filtrering. Om du skapar ett filter avaktiveras den omformade dimensionen.

**Attribution**: Hur fördelar jag krediten för ett mätresultat till den dimension som det tillämpas på? Attribuering sker efter filtrering.

