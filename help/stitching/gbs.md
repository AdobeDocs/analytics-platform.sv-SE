---
title: Diagrambaserad stygn
description: Förklaring av diagrambaserade stygn
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 9118a3c20158b1a0373fab1b41595aa7b07075f6
workflow-type: tm+mt
source-wordcount: '1385'
ht-degree: 0%

---

# Diagrambaserad stygn


I diagrambaserade sammanfogningar anger du en händelsedatamängd samt det beständiga ID:t (cookie) och namnområdet för det tillfälliga ID:t (person-ID) för den datauppsättningen. Diagrambaserad sammanfogning skapar en ny kolumn för det sammanfogade ID:t i den nya sammanfogade datauppsättningen. Sedan används det beständiga ID:t för att fråga efter identitetsdiagrammet från identitetstjänsten i Experience Platform, med det namnområde som anges, för att uppdatera det sammanfogade ID:t.

![Diagrambaserad utjämning](/help/stitching/assets/gbs.png)

## Hur grafbaserad stygn fungerar

Med hjälp av häftning blir det minst två omgångar data i en given datauppsättning.

- **Liveutjämning**: försöker sammanfoga varje träff (händelse) när den kommer in, med det beständiga ID:t för att leta upp det tillfälliga ID:t för det valda namnområdet genom att fråga efter identitetsdiagrammet. Om det tillfälliga ID:t är tillgängligt från sökningen sammanfogas detta tillfälliga ID omedelbart.

- **Spela upp sammanfogning**: *spelar upp* data baserat på uppdaterade identiteter från identitetsdiagrammet. På den här scenen sammanfogas träffar från tidigare okända enheter (beständiga ID:n) när identitetsdiagrammet har matchat identiteten för ett namnutrymme. Uppspelningen bestäms av två parametrar: **frequency** och **lookback window**. Adobe erbjuder följande kombinationer av dessa parametrar:
   - **Daglig sökning efter en daglig frekvens**: Data spelas upp varje dag med ett 24-timmars uppslagsfönster. Det här alternativet har en fördel som innebär att repriser är mycket oftare, men oautentiserade besökare måste autentisera samma dag som de besöker webbplatsen.
   - **Veckovis uppslag med en veckofrekvens**: Data spelas upp en gång i veckan med ett veckovisa uppslagsfönster (se [alternativ](#options)). Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än en vecka gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.
   - **Veckovis uppspelning på en veckofrekvens**: Data spelas upp en gång i veckan med ett varannan vecka-uppslag (se [alternativ](#options)). Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än två veckor gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.
   - **Månadsvis uppslag på en veckofrekvens**: Data spelas upp varje vecka med ett månadsuppslag (se [alternativ](#options)). Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än en månad gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.

- **Sekretess**: När sekretessrelaterade begäranden tas emot, förutom att den begärda identiteten tas bort från källdatauppsättningen, måste alla sammanfogningar av den identiteten över oautentiserade händelser ångras. Identiteten måste också tas bort från identitetsdiagrammet för att förhindra att den specifika identiteten häftas med i framtiden.

  >[!IMPORTANT]
  >
  >Frigörandeprocessen, som en del av begäran om integritet, ändras i början av 2025. Den aktuella enhetsprocessen ändrar namn på händelser med den senaste versionen av kända identiteter. Denna omfördelning av händelser till en annan identitet kan få oönskade juridiska konsekvenser. För att åtgärda dessa problem uppdaterar den nya upplösningsprocessen från och med 2025 händelser som omfattas av sekretessposten med det beständiga ID:t.
  > 

Data utanför uppslagsfönstret spelas inte upp igen. En besökare måste autentisera sig inom ett visst fönster för att få ett oautentiserat besök och ett autentiserat besök att identifieras tillsammans. När en enhet känns igen är den sydd från den punkten framåt.

Tänk på följande två identitetsdiagram för det beständiga ID:t `246` och `3579`, hur dessa identitetsdiagram uppdateras över tid och hur dessa uppdateringar påverkar stegen i diagrambaserad sammanfogning.

![Identitetsdiagram 246](assets/identity-graph-246.svg)
![Identitetsdiagram 3579 ](assets/identity-graph-3579.svg)

Du kan visa ett identitetsdiagram över tiden för en viss profil med [Identity Graph Viewer](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Se även [Identitetstjänstens länkningslogik](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) för att få en bättre förståelse för logiken som används vid länkning av identiteter.

### Steg 1: Liveutjämning

Livehäftning försöker häfta ihop varje händelse vid samlingen till känd information från identitetsdiagrammet.

+++ Information

| | Tid | Beständigt ID<br/>`ECID` | Namnområde <br/>`Email` ![Diagram](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID (after live stitch) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Du kan se hur det sammanslagna ID:t löses för varje händelse. Baserat på tidpunkten, det beständiga ID:t och sökningen av identitetsdiagrammet för det angivna namnutrymmet (samtidigt).
När sökningen matchar mer än ett sammanfogat ID (som för händelse 7) markeras det lexikografiska första ID som returneras av identitetsdiagrammet (`a.b@yahoo.co.uk` i exemplet).

+++

### Steg 2: Spela upp sammanfogning igen

Med jämna mellanrum (beroende på vilket uppslagsfönster som har valts) beräknas om sammanfogningar av historiska data baserat på den senaste versionen av identitetsdiagrammet vid tidpunkten för intervallet.

+++ Information

Med en replay-sammanslagning som inträffar 2023-05-13 16:30, med en 24-timmars uppslagsfönsterkonfiguration, sys vissa händelser i exemplet om (indikeras av ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Tid | Beständigt ID<br/>`ECID` | Namnområde <br/>`Email` ![Diagram](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID <br/> (after live stitch) | Stitched ID <br/> (after replay 24 hours) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)  | 2023-05-12 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)  | 2023-05-12 19:00 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)  | 2023-05-13 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


I och med att repriser görs vid 2023-05-13 16:30, med en 7-dagars uppslagsfönsterkonfiguration, sammanfogas alla händelser i exemplet på nytt.


| | Tid | Beständigt ID<br/>`ECID` | Namnområde <br/>`Email` ![Diagram](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID <br/> (after live stitch) | Stitched ID <br/> (after replay 7 days) |
|---|---|---|---|---|---|
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)  | 2023-05-12 11:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)  | 2023-05-12 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)  | 2023-05-12 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)  | 2023-05-12 19:00 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)  | 2023-05-13 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Steg 3: Begäran om sekretess

När du tar emot en begäran om sekretess, tas det sammanslagna ID:t bort i alla poster för den användare som omfattas av sekretessbegäran.

+++ Information

Följande tabell representerar samma data som ovan, men visar vilken effekt en sekretessbegäran (till exempel 2023-05-13 18:00) har på exempelhändelserna.

| | Tid | Beständigt ID<br/>`ECID` | Namnområde <br/>`Email` ![Diagram](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID (after privacy request) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Förutsättningar

Följande krav gäller specifikt för diagrambaserad sammanfogning:

- Händelsedatauppsättningen i Adobe Experience Platform, som du vill använda sammanfogning på, måste ha en kolumn som identifierar en besökare på varje rad, **beständigt ID**. Till exempel ett besökar-ID som genererats av ett Adobe Analytics AppMeasurement-bibliotek eller ett ECID som genererats av Experience Platform Identity Service.
- Det beständiga ID:t måste också vara [definierat som en identitet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) i schemat.
- Identitetsdiagrammet från Experience Platform Identity Service måste ha ett namnutrymme (till exempel `Email` eller `Phone`) som du vill använda vid sammanfogning för att matcha **transient ID**. Mer information finns i [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home).

>[!NOTE]
>
>Du behöver **inte** en Real-time Customer Data Platform-licens för diagrambaserad sammanfogning. **Prime**-paketet eller senare av Customer Journey Analytics innehåller de berättiganden för Experience Platform Identity Service som krävs.


## Begränsningar

Följande begränsningar gäller specifikt för diagrambaserad sammanfogning:

- Tidsstämplar beaktas inte när du frågar efter ett tillfälligt ID med det angivna namnutrymmet. Det är alltså möjligt att ett beständigt ID sammanfogas med ett tillfälligt ID från en post som har en tidigare tidsstämpel.
- I scenarier med delade enheter, där namnutrymmet i diagrammet innehåller flera identiteter, används den första lexikografiska identiteten. Om namnutrymmesbegränsningar och -prioriteringar konfigureras som en del av releasen av regler för diagramlänkning, används den senast autentiserade användarens identitet. Mer information finns i [Delade enheter](/help/use-cases/stitching/shared-devices.md).
- I identitetsdiagrammet finns det en hård gräns på tre månader för att efterfylla identiteter. Du använder bakåtfyllnadsidentiteter om du inte använder ett Experience Platform-program, som Real-time Customer Data Platform, för att fylla i identitetsdiagrammet.
- [Identitetstjänstens skyddsprofiler](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) gäller. Se till exempel följande [statiska begränsningar](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Maximalt antal identiteter i ett diagram: 50.
   - Maximalt antal länkar till en identitet för ett enskilt batchintag: 50.
   - Maximalt antal identiteter i en XDM-post för diagraminmatning: 20.
   - Minsta antal identiteter i en XDM-post för pejling: 2.
