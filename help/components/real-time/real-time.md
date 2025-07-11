---
description: Förstå funktioner för realtidsrapportering i Customer Journey Analytics.
title: Översikt över realtidsrapportering
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '392'
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
   * Hur ser lanseringen ut jämfört med den senaste lanseringen?
   * Fungerar era erbjudanden för denna viktiga dag eller händelse?

* Relevanta, men mindre värdefulla användningsfall för realrapportering är valideringsfall.
Du vill validera, till exempel:

   * Fungerar faktiskt kampanjresan som ni nyligen lanserade?
   * Gick den nya produktsidan ut live och samlar du in kunddata från sidan?
   * Går det bra för ditt live-mediematerial?

Överväg inte realtidsrapportering för användningsfall för övervakning av åtgärder. Om du till exempel vill svara på frågan om din webbplats faktiskt fungerar?


## Definition

Realtidsaspekten av realtidsrapportering för Customer Journey Analytics definieras som data och visualiseringar som uppdateras inom cirka 5 minuter från det att underliggande data hämtas via den associerade anslutningen.

## Begränsningar

Du bör vara medveten om följande begränsning för realtidsrapportering:

* Realtidsrapportering rapporterar endast om data som är tillgängliga under en rullande period på 24 timmar. Data som korsar denna rullande 24-timmarsperiod är inte tillgängliga.
* Attribution, segmentation, calculate metrics, and more only works on the data available within the rolling period of 24 hours.
* Realtidsrapportering fungerar bäst med data på händelse- och sessionsnivå och du bör vara försiktig med att använda realtidsrapportering för data på personnivå. <!--Need to explain this a bit better --> Överväg inställningen för händelse- och sessionsnivådata när du väljer mått, (beräknade) mått. Och när du använder funktioner som nedbrytning, nästa eller föregående, med mera i realtidsuppdateringspanelen.
* Du kan inte kombinera sammanfogning med realtidsrapportering. <!-- Do we need to explain this in more detail, why? --> Som nämnts ovan handlar realtidsrapportering om händelser och sessionsdata och inte så mycket om personbaserade data.
* Det finns inga tillgängliga värden för pulsslagsinsamlade media, med undantag för mediestart och mediefärg. Så du kan fortfarande använda realtidsrapportering för att aktivera medieanvändning.
