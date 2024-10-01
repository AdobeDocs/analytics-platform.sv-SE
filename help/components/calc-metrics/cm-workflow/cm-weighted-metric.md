---
description: Visar exempel på beräknade värden.
title: Exempel på beräknade mätvärden
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Exempel på beräknade mätvärden

I den här artikeln finns exempel på hur du definierar mer avancerade beräknade mätvärden.

## Studsfrekvens

Du vill beräkna studsfrekvensen.

+++ Information

Definitionen av ett studs är föremål för en annan diskussion, men i det här exemplet definierar du ett studsfilter där Sessionsstart är lika med 1 och Sessionsslut är lika med 1. Du använder det här filtret för att definiera frekvensen för avvisade sessioner.


### Filter

![Startar händelser](assets/example-bounce-bouncedevents.png)

### Beräknat mått

![Studsfrekvens](assets/example-bounce-rate.png)


### Härledda fält

Du kan också definiera en [studsfrekvens med hjälp av härledda fält](/help/data-views/derived-fields/derived-fields.md#bounces).

Härledda fält är en del av en datavy som har fördelen att inte alla användare kan åsidosätta eller ändra definitionen av ett värde för studsfrekvens. Den fördelen innebar också en begränsning. Användare som inte har tillgång till en datavy kan inte använda härledda fält och måste använda filter och beräknade värden för att definiera en studsfrekvens.

Mer bakgrundsinformation om hur du beräknar studsar och studsfrekvens i Customer Journey Analytics finns i det här [blogginlägget](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446).

+++


## Villkorliga sidvyer

Du vill definiera ett beräknat mått som endast beräknar sidvyer för de sidor som har besöktes i över 100 sessioner.

+++ Information

![Villkorliga sidvyer](assets/conditional-page-views.png)

+++

## Sidvyer för de 30 största sessionerna

Du vill definiera ett beräknat mått som endast beräknar sidvyer för de 30 viktigaste sessionerna.

+++ Information

![Top 30% page views](assets/top30-page-views.png)

+++
