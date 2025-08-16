---
description: Förstå funktioner för realtidsrapportering i Customer Journey Analytics.
title: Översikt över realtidsrapportering
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 1%

---

# Översikt över rapportering i realtid

Realtidsrapportering i Customer Journey Analytics visar och uppdaterar data och visualiseringar inom en eller flera paneler i Analysis Workspace i realtid.

{{release-limited-testing}}

{{ultimate-package}}

## Användningsexempel

I det här avsnittet finns en översikt över typiska värdefulla och mindre värdefulla användningsfall. Och även information när man inte ska överväga realtidsrapportering.

* De mest värdefulla användningsområdena för realtidsrapportering är större försäljning, kampanjer eller produktlanseringar.
Som en del av lanseringen vill du veta:

   * Hur är försäljningen jämfört med din senaste försäljning?
   * Hur är produktlanseringen jämfört med den senaste produktlanseringen?
   * Fungerar era erbjudanden för denna viktiga dag eller händelse?

* Relevanta, men mindre värdefulla användningsfall för realtidsrapportering är valideringsfall.
Du vill validera, till exempel:

   * Fungerar den kampanjresa du nyligen lanserade?
   * Samlar ni in kunddata från sidan när den nya produktsidan publicerades?
   * Går det bra för ditt live-mediematerial?

Överväg inte realtidsrapportering för användningsfall för övervakning av åtgärder. Till exempel frågan om en webbplats fungerar som den ska. Eftersom [alternativet för uppdatering i realtid](use-real-time.md) automatiskt inaktiveras efter 30 minuter och rapporten i realtid slutar uppdateras, bör du inte använda en realtidsrapport som en tillförlitlig källa för de här användningsfallen.


## Definition

Realtidsaspekten av realtidsrapportering för Customer Journey Analytics definieras som data och visualiseringar som uppdateras inom ungefär 6,5 minuter från det att underliggande data hämtas via den associerade anslutningen.

Olika komponenter i konfigurationen av datainsamlingen avgör tidsfördröjningen för realtidsrapportering.

![Realtidsrapportering](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Beskrivning | Latens |
|:---:|---|--:|
| 1 | Data som samlas in via Edge Network SDK/API:er till Edge Network. | &lt; 500 millisekunder |
| 2 | Data replikerade från Edge Network till datainsamling och valideringstjänst i Experience Platform Hub. | &lt; 5 minuter |
| 3 | Data som samlas in via direktuppspelningsanslutningar till datainsamling och valideringstjänst i Experience Platform Hub. | &lt; 15 minuter |
| 4 | Data som samlas in via Adobe Analytics och vidarebefordras av Analytics-källkopplingen till källanslutningsprocessorn i Experience Platform Hub. | &lt; 15 minuter |
| 5 | Data samlas in via andra källanslutningar till källanslutningsprocessorn i Experience Platform Hub. | &lt; 24 timmar |
| 6 | Data som bearbetas av realtidsprocessorn för en konsoliderad datauppsättning för realtidsrapportering. | &lt; 90 sekunder |

## Begränsningar

Tänk på följande begränsning för realtidsrapportering:

* Realtidsrapportering rapporterar endast om data som är tillgängliga under en rullande period på 24 timmar. Data som korsar denna rullande 24-timmarsperiod döljs för realtidsrapportering. När [realtidsuppdateringen](use-real-time.md) för en rapport har inaktiverats eller inaktiverats automatiskt, är alla relevanta data för en rapport tillgängliga en gång till.
* Attribution, segmentation, calculate metrics, and more only work on the data available within the rolling period of 24 hours.
* Realtidsrapportering fungerar bäst med data på händelse- och sessionsnivå och du bör vara försiktig med realtidsrapportering för data på personnivå. <!--Need to explain this a bit better --> Eftersom endast händelser från den rullande 24-timmarsperioden är tillgängliga för realtidsrapporter, begränsas en persons händelsehistorik även till det här fönstret. Tänk på inställningen för händelse- och sessionsnivådata när du väljer en dimension och (beräknade) mått. Och när du använder funktioner som nedbrytning, nästa eller föregående, med mera i realtidsuppdateringspanelen.
* Du kan inte kombinera sammanfogning med realtidsrapportering. <!-- Do we need to explain this in more detail, why? --> Realtidsrapportering handlar om händelse- och sessionsnivådata och är mindre relevant för personbaserade data.
* Inga pulsslagsinsamlade mediemätvärden är tillgängliga, förutom mediestart och mediefärgvärden. Så du kan fortfarande använda realtidsrapportering för att aktivera medieanvändningsfall.
* När du använder [hämtnings- eller exportalternativen](/help/analysis-workspace/export/download-send.md) för att hämta ett projekt eller exportera data från en frihandstabell bör du tänka på följande:
   * Ett hämtat CSV-projekt eller en exporterad CSV-fil innehåller realtidsdata som är tillgängliga vid nedladdningen eller exporten.
   * Ett nedladdat PDF-projekt innehåller icke-realtidsdata som liknar de data som visas när uppdatering i realtid är inaktiverad.
