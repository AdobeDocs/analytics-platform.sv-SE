---
description: Förstå funktioner för realtidsrapportering i Customer Journey Analytics.
title: Översikt över realtidsrapportering
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: 34dfbc98acecf1ca953434a7d1f0547ff45139a8
workflow-type: tm+mt
source-wordcount: '471'
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

   * Fungerar faktiskt kampanjresan som ni nyligen lanserade?
   * Samlar ni in kunddata från sidan när den nya produktsidan publicerades?
   * Går det bra för ditt live-mediematerial?

Överväg inte realtidsrapportering för användningsfall för övervakning av åtgärder. Till exempel: Fungerar en webbplats?


## Definition

Realtidsaspekten av realtidsrapportering för Customer Journey Analytics definieras som data och visualiseringar som uppdateras inom cirka 5 minuter från det att underliggande data hämtas via den associerade anslutningen.

## Begränsningar

Du bör vara medveten om följande begränsning för realtidsrapportering:

* Realtidsrapportering rapporterar endast om data som är tillgängliga under en rullande period på 24 timmar. Data som korsar denna rullande 24-timmarsperiod är inte tillgängliga.
* Attribution, segmentation, calculate metrics, and more only work on the data available within the rolling period of 24 hours.
* Realtidsrapportering fungerar bäst med data på händelse- och sessionsnivå och du bör vara försiktig med realtidsrapportering för data på personnivå. <!--Need to explain this a bit better --> Eftersom endast händelser från den rullande 24-timmarsperioden är tillgängliga för realtidsrapporter, begränsas en persons händelsehistorik även till det här fönstret. Tänk på inställningen för händelse- och sessionsnivådata när du väljer mått, (beräknade) mått. Och när du använder funktioner som nedbrytning, nästa eller föregående, med mera i realtidsuppdateringspanelen.
* Du kan inte kombinera sammanfogning med realtidsrapportering. <!-- Do we need to explain this in more detail, why? --> Realtidsrapportering handlar om händelse- och sessionsnivådata och är mindre relevant för personbaserade data.
* Det finns inga tillgängliga värden för pulsslagsinsamlade media, med undantag för mediestart och mediefärg. Så du kan fortfarande använda realtidsrapportering för att aktivera medieanvändning.
* När du använder [hämtnings- eller exportalternativen](/help/analysis-workspace/export/download-send.md) för att hämta ett projekt eller exportera data från en frihandstabell bör du tänka på följande:
   * Ett hämtat CSV-projekt eller en exporterad CSV-fil innehåller realtidsdata som är tillgängliga vid nedladdningen eller exporten.
   * Ett nedladdat PDF-projekt innehåller icke-realtidsdata som liknar de data som visas när uppdatering i realtid är inaktiverad.
