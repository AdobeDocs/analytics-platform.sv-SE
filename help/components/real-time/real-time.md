---
description: Förstå funktioner för realtidsrapportering i Customer Journey Analytics.
title: Översikt över realtidsrapportering
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: d0067d8271b7628f0d174d1fa647ba1b4558ffb4
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 0%

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


## Latenser

Hur du samlar in data avgör tidsfördröjningen i realtid vid rapportering för Customer Journey Analytics. Bilden och tabellen nedan visar ungefärliga latenser för olika scenarier för datainsamling när realtids- och standardrapportering används.

Illustrationen betonar också att realtidsrapportering använder en konsoliderad datamängd som är helt skild från den [konsoliderade (kombinerade) datamängden ](/help/connections/combined-dataset.md) som används för standardrapportering. Du använder [Uppdatera i realtid-växeln](use-real-time.md) för att växla mellan:

* Realtidsrapportering för en konsoliderad datauppsättning som innehåller upp till 24 timmars rullande data.
* Standardrapportering på den konsoliderade datauppsättningen som innehåller upp till 13 månaders rullande data (eller längre om du har licensierat tillägget för utökad datakapacitet).

![Realtidsrapportering](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Datainsamling | Latens för rapportering i realtid | Standardfördröjning för rapportering |
|:---:|---|--:|--:|
| 1 | Edge Network SDK/API:er i Edge Network | &ca; &lt; 00h:06m:30s | &ca; &lt; 01h:35m:00s |
| 2 | Strömmande anslutningar | &ca; &lt; 00h:16m:30s | &ca; &lt; 01h:45m:00s |
| 3 | Adobe Analytics källanslutning | &ca; &lt; 00h:16m:30s | &ca; &lt; 01h:45m:00s |
| 4 | Andra källkopplingar till källanslutningarna (inklusive batchdata) | &ca; &lt; 24h:01m:30s | &ca; &lt; 25h:30m:00s |

## Begränsningar

Tänk på följande begränsning för realtidsrapportering:

* Realtidsrapportering rapporterar endast om data som är tillgängliga under en rullande period på 24 timmar. Data som är mer än   24-timmarsversionen är inte tillgänglig för realtidsrapportering. När [realtidsuppdateringen](use-real-time.md) för en rapport har inaktiverats eller inaktiverats automatiskt är alla relevanta data tillgängliga en gång till från den [konsoliderade datamängden](/help/connections/combined-dataset.md) som vanligtvis används för rapportering i Customer Journey Analytics.
* Attribution, segmentation, calculate metrics, and more only work on the data available within the rolling period of 24 hours. Ett *Upprepa besökare*-segment innehåller till exempel ett fåtal personer i en realtidsrapport, eftersom rapporten endast innehåller personer som har besökt flera gånger de senaste 24 timmarna. En liknande begränsning gäller när du skapar en realtidsrapport för personer som tidigare klickat på en kampanj som inte längre är aktiv.
* Realtidsrapportering fungerar bäst med data på händelse- och sessionsnivå och du bör vara försiktig med realtidsrapportering för data på personnivå. <!--Need to explain this a bit better --> Eftersom endast händelser från den rullande 24-timmarsperioden är tillgängliga för realtidsrapporter, begränsas en persons händelsehistorik även till det här fönstret. Tänk på inställningen för händelse- och sessionsnivådata när du väljer en dimension och (beräknade) mått. Och när du använder funktioner som nedbrytning, nästa eller föregående, med mera i realtidsuppdateringspanelen.
* Du kan inte kombinera sammanfogning med realtidsrapportering. <!-- Do we need to explain this in more detail, why? --> Realtidsrapportering handlar om händelse- och sessionsnivådata och är mindre relevant för personbaserade data.
* Inga pulsslagsinsamlade mediemätvärden är tillgängliga, förutom mediestart och mediefärgvärden. Så du kan fortfarande använda realtidsrapportering för att aktivera medieanvändningsfall.
* När du använder [hämtnings- eller exportalternativen](/help/analysis-workspace/export/download-send.md) för att hämta ett projekt eller exportera data från en frihandstabell bör du tänka på följande:
   * Ett hämtat CSV-projekt eller en exporterad CSV-fil innehåller realtidsdata som är tillgängliga vid nedladdningen eller exporten.
   * Ett nedladdat PDF-projekt innehåller icke-realtidsdata som liknar de data som visas när uppdatering i realtid är inaktiverad.
