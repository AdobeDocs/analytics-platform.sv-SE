---
title: AAID, ECID, AACUSTOMID och Analytics-källkopplingen
description: Lär dig hur Analytics-källkopplingen hanterar Adobe Analytics identitetsfält.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
role: User
source-git-commit: 5c5f276711f39abb1b3f3b955ad99e17cb0ac09c
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 0%

---

# AAID, ECID, AACUSTOMID och Analytics-källkopplingen

Adobe Analytics data innehåller flera identitetsfält. Tre viktiga identitetsfält får särskild behandling av [Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE): AAID, ECID, AACUSTOMID.

## STÖD

Adobe Analytics ID (AAID) är den primära enhetsidentifieraren i Adobe Analytics och finns garanterat för varje händelse som skickas via Analytics-källkopplingen. AAID kallas ibland för &quot;Legacy Analytics ID&quot; eller `s_vi` cookie ID. Ett AAID skapas dock även om cookien `s_vi` inte finns. AAID representeras av kolumnerna `post_visid_high/post_visid_low` i [Adobe Analytics-dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=sv-SE#columns%2C-descriptions%2C-and-data-types).

I Analytics-källkopplingen omvandlas AID till `HEX(post_visid_high) + "-" + HEX(post_visid_low)`. AAID-fältet för en viss händelse innehåller en enda identitet som kan vara en av flera olika typer enligt beskrivningen i [Operationsordning för analys-ID:n](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=sv-SE). (Inom en hel rapportserie kan AAID innehålla en blandning av typer för olika händelser. Typen för varje händelse anges i kolumnen `post_visid_type` i Analytics-dataflöden.) Se även: [Datakolumnreferens](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=sv-SE).

## ECID

ECID (Experience Cloud-ID), som ibland kallas MCID (Marketing Cloud-ID), är ett separat enhetsidentifieringsfält som fylls i i Adobe Analytics när Analytics implementeras med [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=sv-SE). ECID representeras av kolumnen `mcvisid` i Adobe Analytics-dataflöden.

Om det finns ett ECID för en händelse kan AAID baseras på ECID, beroende på om [respitperioden](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=sv-SE) för Analytics har konfigurerats. Se även: [Analytics och Experience Cloud ID Requests](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=sv-SE).

## AACUSTOMID

AACUSTOMID är ett separat identifierarfält som fylls i i Adobe Analytics baserat på användningen av variabeln `s.VisitorID` i analysimplementeringen. AACUSTOMID representeras av kolumnen `cust_visid` i Adobe Analytics-dataflöden. Om det finns ett AACUSTOMID kommer stödet att baseras på AACUSTOMID. (AACUSTOMID överför alla andra identifierare enligt den ordning i vilken åtgärderna anges ovan.)

## Hur Analytics-källkopplingen hanterar dessa identiteter

Analyskällans koppling skickar dessa identiteter till Adobe Experience Platform i XDM-format som:

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

Dessa fält är inte markerade som identiteter. I stället kopieras samma identiteter till XDM:s **_identityMap_** som nyckelvärdepar enligt följande:

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

Objekten inom &lt;> hakparenteser representerar platser där faktiska värden skulle visas.

Inom identityMap:

* Om det finns ett ECID markeras det som händelsens primära identitet. Observera att i detta fall kan stöd baseras på ECID enligt diskussionen ovan.
I annat fall markeras AID som händelsens primära identitet.
* AACUSTOMID markeras aldrig som händelsens primära ID. Om det finns ett AACUSTOMID, baseras AAID dock på AACUSTOMID enligt beskrivningen ovan.

När identiteten eller identiteterna kopieras till `identityMap` ställs `endUserIDs._experience.mcid.namespace.code` också in på samma händelse:

* Om det finns ett AAID är `endUserIDs._experience.aaid.namespace.code` inställt på AAID.
* Om det finns ett ECID är `endUserIDs._experience.mcid.namespace.code` inställt på ECID.
* Om det finns ett AACUSTOMID är `endUserIDs._experience.aacustomid.namespace.code` inställt på &quot;AACUSTOMID&quot;.

## Customer Journey Analytics och primärt ID

För Customer Journey Analytics är definitionen av primärt ID bara viktig om du bestämmer dig för att använda det primära ID:t som personnummer. Det är dock inte obligatoriskt att göra detta. Du kan välja någon annan identitetskolumn som person-ID.
