---
title: STÖD, ECID, AACUSTOMID och Analytics Source Connector
description: Läs om hur Analytics Source Connector hanterar Adobe Analytics identitetsfält.
source-git-commit: 348f4e8596146f7ff4234535fa76a54f7be33171
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 0%

---


# STÖD, ECID, AACUSTOMID och Analytics Source Connector

Adobe Analytics data innehåller flera identitetsfält. Tre viktiga identitetsfält ges särskild behandling av [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en): STÖD, ECID, AACUSTOMID.

## AAID

Adobe Analytics ID (AAID) är den primära enhetsidentifieraren i Adobe Analytics och finns garanterat för varje händelse som skickas via Analytics Source Connector. AAID kallas ibland för &quot;Legacy Analytics ID&quot; eller `s\_vi cookie id`. Ett AID skapas dock även om `s\_vi` cookie finns inte. AAID representeras av `_post\_visid\_high/post\_visid\_low_` kolumner i [Adobe Analytics dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en#columns%2C-descriptions%2C-and-data-types).

I Analytics Source Connector omvandlas AID till `HEX(post_visid_high) + "-" + HEX(host_visid_low)`. AAID-fältet för en viss händelse innehåller en enda identitet som kan vara en av flera olika typer enligt beskrivningen i [Åtgärdsordning för analys-ID:n](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Inom en hel rapportserie kan AAID innehålla en blandning av typer för olika händelser. Typen för varje träff visas i `_[post\_]visid\_type_` i Analytics-dataflöden.) Se även: [Referens för datakolumn](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en).

## ECID

ECID (Experience Cloud-ID), som ibland kallas MCID (Marketing Cloud-ID), är ett separat fält för enhetsidentifierare som fylls i i Adobe Analytics när Analytics implementeras med [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=en). ECID representeras av `_mcvisid_` i Adobe Analytics dataflöden.

Om det finns ett ECID för en händelse kan AAID baseras på ECID beroende på om Analytics [respitperiod](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=en) är konfigurerad. Se även: [Begäranden om analyser och Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUSTOMID

AACUSTOMID är ett separat identifierarfält som fylls i i Adobe Analytics baserat på användningen av `s.VisitorID` i Analytics-implementeringen. AACUSTOMID representeras av `_cust_visid_` i Adobe Analytics dataflöden. Om det finns ett AACUSTOMID kommer stödet att baseras på AACUSTOMID. (AACUSTOMID överför alla andra identifierare enligt den ordning i vilken åtgärderna anges ovan.)

## Hur Analytics Source Connector hanterar dessa identiteter

Analyskällans koppling skickar dessa identiteter till Adobe Experience Platform i XDM-format som:

* `endUserIDs.\_experience.aaid.id`
* `endUserIDs.\_experience.mcid.id`
* `endUserIDs.\_experience.aacustomid.id`

Dessa fält är inte markerade som identiteter. I stället kopieras samma identiteter till XDM:er **_identityMap_** som nyckelvärdepar enligt följande:

* `{ “key”: “AAID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_**} ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_** } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **false** } ] }`

Inom identityMap:

* Om det finns ett ECID markeras det som händelsens primära identitet. Observera att i detta fall kan stöd baseras på ECID enligt diskussionen ovan.
I annat fall markeras AID som händelsens primära identitet.
* AACUSTOMID markeras aldrig som händelsens primära ID. Om det finns ett AACUSTOMID, baseras AAID dock på AACUSTOMID enligt beskrivningen ovan.

När det gäller CJA är definitionen av primärt ID bara viktig om slutanvändaren bestämmer sig för att använda primärt ID som person-ID. Det är dock inte obligatoriskt att göra detta. Användaren kan välja någon annan identitetskolumn som person-ID.

