---
source-git-commit: f97439676c61acf1b6ba8818ef1d06542402e675
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---
# STÖD, ECID, AACUSTOMID och Analytics Source Connector

Adobe Analytics data innehåller flera identitetsfält. Tre viktiga identitetsfält ges särskild behandling av [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en):

* **STÖD** är den primära enhetsidentifieraren i Adobe Analytics och finns garanterat för varje händelse som skickas via Analytics Source Connector. AAID kallas ibland för &quot;Legacy Analytics ID&quot; eller &quot;s\_vi cookie id&quot;, även om ett AAID skapas även om s\_vi-cookien inte finns. AAID representeras av **_post\_visid\_high/post\_visid\_low_** kolumner i [Adobe Analytics dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en#columns%2C-descriptions%2C-and-data-types). I Analytics Source Connector omvandlas AID till **HEX(post_visid_high) + &quot;-&quot; + HEX(host_visid_low)**. AAID-fältet för en viss händelse innehåller en enda identitet som kan vara en av flera olika typer enligt beskrivningen i [Åtgärdsordning för analys-ID:n](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Inom en hel rapportserie kan AAID innehålla en blandning av typer för olika händelser. Typen för varje träff visas i **_[post\_]visid\_type_** i Analytics-dataflöden.) Se även: [Referens för datakolumn](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en).
* **ECID** (Experience Cloud-ID), som ibland kallas MCID (Marketing Cloud-ID), är ett separat enhetsidentifieringsfält som fylls i i Adobe Analytics när Adobe Analytics implementeras med [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=en). ECID representeras av **_mcvisid_** i Adobe Analytics dataflöden. Om det finns ett ECID för en händelse kan AAID baseras på ECID beroende på om Analytics [respitperiod](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=en) är konfigurerad. Se även: [Begäranden om analyser och Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).
* **AACUSTOMID** är ett separat identifierarfält som fylls i i Adobe Analytics baserat på användningen av variabeln s.VisitorID i analysimplementeringen. AACUSTOMID representeras av **_cust_visid_** i Adobe Analytics dataflöden. Om det finns ett AACUSTOMID kommer stödet att baseras på AACUSTOMID. (AACUSTOMID överför alla andra identifierare enligt den ordning i vilken åtgärderna anges ovan.)

Källkopplingen för analyser skickar dessa identiteter till AEP i XDM-format som:

* endUserID:n.\_experience.aaid.id
* endUserID:n.\_experience.mcid.id
* endUserID:n.\_experience.acustomid.id

Dessa fält är inte markerade som identiteter. I stället kopieras samma identiteter till XDM:er **_identityMap_** som nyckelvärdepar enligt följande:

* { &quot;key&quot;: &quot;AID&quot;, &quot;value&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;primär&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_**} ] }
* { &quot;key&quot;: &quot;ECID&quot;, &quot;value&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;primär&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_** } ] }
* { &quot;key&quot;: &quot;AACUSTOMID&quot;, &quot;value&quot;: [ { &quot;id&quot;: &quot;**_\&lt;identity>_**&quot;, &quot;primär&quot;: **false** } ] }

Inom identityMap:

* Om det finns ett ECID markeras det som händelsens primära identitet. Observera att i detta fall kan stöd baseras på ECID enligt diskussionen ovan.
I annat fall markeras AID som händelsens primära identitet.
* AACUSTOMID markeras aldrig som händelsens primära ID. Om det finns ett AACUSTOMID baseras dock AAID på AACUSTOMID enligt beskrivningen ovan.

När det gäller CJA är definitionen av primärt ID bara viktig om slutanvändaren bestämmer sig för att använda primärt ID som person-ID. Det är dock inte obligatoriskt att göra detta. Användaren kan välja någon annan identitetskolumn som person-ID.

