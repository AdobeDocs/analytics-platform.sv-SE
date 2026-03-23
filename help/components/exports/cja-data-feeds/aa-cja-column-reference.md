---
title: Mappa Adobe Analytics dataflödeskolumner till Customer Journey Analytics
description: Bestäm hur du tar en viss dataflödeskolumn från Adobe Analytics och avgör dess grovmotsvarighet i din Customer Journey Analytics-implementering.
feature: Components
hide: true
hidefromtoc: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
source-git-commit: af5b30cd71ebe46e2af584ee502ef631c829f5ea
workflow-type: tm+mt
source-wordcount: '3350'
ht-degree: 0%

---

# Mappa Adobe Analytics dataflödeskolumner till Customer Journey Analytics

Det går inte att mappa :1 till true mellan dataflödeskolumner från Adobe Analytics och Customer Journey Analytics. De två produkterna skiljer sig avsevärt åt, och implementeringen i respektive organisation kan variera avsevärt.

Denna referens hjälper datatekniker att utvärdera Adobe Analytics-kolumner för dataflöden och identifiera de närmaste Customer Journey Analytics-motsvarigheterna för sina arbetsflöden.

>[!NOTE]
>
>Den här referensen innehåller bara kolumner som anses vara aktuella av Adobe, baserat på [kolumnreferensen för analysdataflöde](https://experienceleague.adobe.com/sv/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). Om du har en Analytics-dataflödeskolumn som inte finns med i den här tabellen som du aktivt använder, bör du läsa organisationens designdokument för att ta reda på vilken som är den bästa motsvarigheten i Customer Journey Analytics.

+++**`accept_language`**

Visar alla godkända språk enligt HTTP-huvudet Accept-Language i en bildbegäran.

+++

+++**`adload`**

Inläsningar av mediaannonser

{{cja-df-post}}

+++

+++**`aemassetid`**

En variabel med flera värden som motsvarar tillgångs-ID:n (GUID) för en uppsättning Adobe Experience Manager Assets. Ökar imponeringshändelser.

{{cja-df-post}}

+++

+++**`aemassetsource`**

Identifierar resurshändelsens källa. Används i Adobe Experience Manager.

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

Tillgångs-ID för en Adobe Experience Manager-resurs. Ökningar Klicka på händelser.

{{cja-df-post}}

+++

+++**`amo_cid`**

AMO ID-dimensionen, som används i Adobe Advertising-integreringar.

{{cja-df-post}}

+++

+++**`amo_ef_id`**

Dimensionen för AMO EF ID, som används i Adobe Advertising-integreringar.

{{cja-df-post}}

+++

+++**`browser`**

Ett numeriskt ID som representerar webbläsaren.

{{cja-df-lookup}}

+++

+++**`browser_height`**

Höjddimensionen i webbläsaren.

{{cja-df-post}}

+++

+++**`browser_width`**

Bredd på webbläsaren

{{cja-df-post}}

+++

+++**`campaign`**

Dimensionen Spårningskod.

{{cja-df-post}}

+++

+++**`carrier`**

Adobe Advertising integrationsvariabel. Anger mobiloperatör.

{{cja-df-lookup}}

+++

+++**`channel`**

Dimensionen Platsavsnitt.

{{cja-df-post}}

+++

+++**`ch_hdr`**

Klienttips som samlats in via HTTP-begärandehuvudet.

+++

+++**`ch_js`**

Klienttips som samlats in via JavaScript-API:t för användaragenttips för klienttips.

+++

+++**`clickmaplink`**

Activity Map länkdimension.

{{cja-df-post}}

{{cja-df-na}}

Den här kolumnen gäller inte eftersom Customer Journey Analytics ännu inte stöder Activity Map.

+++

+++**`clickmaplinkbyregion`**

Activity Map länk per region.

{{cja-df-post}}

{{cja-df-na}}

Den här kolumnen gäller inte eftersom Customer Journey Analytics ännu inte stöder Activity Map.

+++

+++**`clickmappage`**

Activity Map siddimension.

{{cja-df-post}}

{{cja-df-na}}

Den här kolumnen gäller inte eftersom Customer Journey Analytics ännu inte stöder Activity Map.

+++

+++**`clickmapregion`**

Activity Map regiondimension.

{{cja-df-post}}

{{cja-df-na}}

Den här kolumnen gäller inte eftersom Customer Journey Analytics ännu inte stöder Activity Map.

+++

+++**`code_ver`**

API- eller klient-SDK-version som används för att kompilera och skicka bildbegäran.

+++

+++**`color`**

Färgdjup-ID baserat på värdet för kolumnen `c_color`.

{{cja-df-lookup}}

+++

+++**`connection_type`**

Numeriskt ID som representerar dimensionen för anslutningstypen.

{{cja-df-lookup}}

+++

+++**`cookies`**

Cookie-supportdimensionen.<br>Y: Aktiverad<br>N: Inaktiverad<br>U: Okänd

{{cja-df-post}}

+++

+++**`country`**

Ett numeriskt ID som representerar besökarens land. Refererar till `country.tsv`-söktabellen.

{{cja-df-lookup}}

+++

+++**`currency`**

Valutakoden som användes under transaktionen. Ange med `currencyCode`.

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

Relaterat till kolumnen `connection_type`. De vanligaste värdena är LAN/Wifi, mobiloperatör och modem.

+++

+++**`curr_factor`**

Bestämmer valutadecimalen. Används för valutakonvertering. USD använder till exempel två decimaler, så det här kolumnvärdet blir `2`.

+++

+++**`curr_rate`**

Växelkursen när transaktionen inträffade. Adobe samarbetar med XE för att fastställa dagens växelkurs.

+++

+++**`customer_perspective`**

Avgör om träffen är en mobilbakgrundträff.

{{cja-df-post}}

+++

+++**`cust_hit_time_gmt`**

Endast tidsstämpelaktiverade rapportsviter. Tidsstämpeln som skickades med träffen, baserat på UNIX®-tid.

{{cja-df-post}}

+++

+++**`cust_visid`**

Det anpassade besökar-ID:t, om `visitorID` används.

{{cja-df-post}}

+++

+++**`c_color`**

Färgpalettens bitdjup. Används som en del av beräkningen av färgdjupsdimensionen. AppMeasurement använder JavaScript-funktionen `screen.colorDepth()`.

+++

+++**`daily_visitor`**

En flagga som avgör om träffen är en ny daglig besökare.

+++

+++**`dataprivacyconsentoptin`**

Tillvalsdimensionen för hantering av samtycke. Flera värden kan finnas per träff, avgränsade med ett rör (`\|`). Giltiga värden är `DMP` och `SELL`.

{{cja-df-na}}

Den här kolumnen gäller inte eftersom Customer Journey Analytics inte ?????

+++

+++**`dataprivacyconsentoptout`**

Avanmälningsdimensionen för hantering av samtycke. Flera värden kan finnas per träff, avgränsade med ett rör (`\|`). Giltiga värden är `SSF`, `DMP` och `SELL`.

+++

+++**`date_time`**

Tidpunkten för träffen i läsbart format, baserat på rapportsvitens tidszon.

+++

+++**`domain`**

Domändimensionen. Baserat på besökarens Internetanslutningspunkt.

+++

+++**`duplicated_from`**

Används endast i rapportsviter som innehåller VISTA-regler för träffkopior. Anger vilken rapportsvit som träffen kopierades från.

+++

+++**`duplicate_events`**

Listar varje händelse som räknats som en dubblett.

+++

+++**`duplicate_purchase`**

En flagga som avgör om köphändelsen för den här träffen ignoreras eftersom den är en dubblett.

+++

+++**`ef_id`**

Det EF-ID som används i Adobe Advertising-integreringar.

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

Egna variabler 1-250. Används i eVar-dimensioner. Varje organisation använder eVars på olika sätt. Det bästa stället att få mer information om hur er organisation fyller i respektive eVars är ett dokument som är specifikt för er organisation.

{{cja-df-post}}

+++

+++**`event_list`**

Kommaavgränsad lista med numeriska ID:n som representerar händelser som utlöses vid träffen. Innehåller både e-handelshändelser och anpassade händelser 1-1000. Använder `event.tsv`-sökning.

Den här kolumnen mappar troligtvis till dussintals olika mätvärden, beroende på implementeringen. Adobe rekommenderar följande process för att mappa varje mätvärde i Customer Journey Analytics till det numeriska värde som representeras i den här kolumnen för dataflöde i Analytics:

1. Använd sökningen `event.tsv` för att mappa varje numeriskt värde till måttnamnet.
1. Använd ditt lösningsdesigndokument för att mappa varje Analytics-händelsenamn till motsvarande metriska namn i Customer Journey Analytics.
1. Markera den mappade komponenten i användargränssnittet för datavyer och notera dess komponent-ID. Om komponent-ID:t är för ogenomskinligt kan du fylla i ID-fältet för datafeed-alias och använda det i stället.
1. Upprepa för alla mätvärden som används i organisationen.

{{cja-df-post}}

Om ditt schema använder fältgruppen [[!UICONTROL Commerce Details]](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/field-groups/event/commerce-details) kan vissa mått mappas direkt till följande XDM-fält:

* **Utcheckningar**: `xdm.commerce.checkouts.value`
* **Kundvagnen lägger till**: `xdm.commerce.productListAdds.value`
* **Kundvagnen öppnas**: `xdm.commerce.productListOpens.value`
* **Ta bort kundvagn**: `xdm.commerce.productListRemovals.value`
* **Vyer för kundvagn**: `xdm.commerce.productListViews.value`
* **Produktvyer**: `xdm.commerce.productViews.value`
* **Beställningar**: `xdm.commerce.purchases.value`

Vissa mätvärden kan använda händelseserialisering, vilket är hur Adobe Analytics ger fullständig kontroll över deduplicering. Du kan använda komponentinställningen [Metrisk deduplicering](/help/data-views/component-settings/metric-deduplication.md) för att uppnå paritet för deduplicering.

* Om mätvärdena dedupliceras genom att gå till Adobe Analytics kan du ställa in dedupliceringsomfånget till session i den metrisk metodens komponentinställningar.
* Om mätvärdena dedupliceras av händelse-ID i Adobe Analytics är det troligt att XDM-objektet för mätvärdet innehåller både ett `value`- och ett `id`-fält. Om ditt schema använder fältgruppen [[!UICONTROL Commerce Details]](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/field-groups/event/commerce-details) finns dessa mått troligen i dessa XDM-fält, som du kan ställa in fältet **[!UICONTROL Deduplication ID]** i måttets komponentinställningar:

   * **Utcheckningar**: `xdm.commerce.checkouts.id`
   * **Kundvagnen lägger till**: `xdm.commerce.productListAdds.id`
   * **Kundvagnen öppnas**: `xdm.commerce.productListOpens.id`
   * **Ta bort kundvagn**: `xdm.commerce.productListRemovals.id`
   * **Vyer för kundvagn**: `xdm.commerce.productListViews.id`
   * **Produktvyer**: `xdm.commerce.productViews.id`
   * **Beställningar**: `xdm.commerce.purchases.id`

+++

+++**`exclude_hit`**

En flagga som avgör om träffen utesluts från rapportering. Kolumnen `visit_num` ökas inte för uteslutna träffar.<br>1: Används inte. En del av en skrapad funktion.<br>2: Används inte. En del av en skrapad funktion.<br>3: Används inte längre. Undantag för användaragent<br>4: Undantag baserat på IP-adress<br>5: Information om träffar saknas, t.ex. `page_url`, `pagename`, `page_event` eller `event_list`<br>6: JavaScript bearbetade inte korrekt träffen<br>7: Kontospecifikt undantag, t.ex. i VISTA-regler<br>8: Används inte. Alternativt kontospecifikt undantag.<br>9: Används inte. En del av en skrapad funktion.<br>10: Ogiltig valutakod<br>11: Träff saknar en tidsstämpel i en rapportsvit som bara innehåller tidsstämplar, eller en träff innehöll en tidsstämpel i en rapportsvit som inte är en tidsstämpel.<br>12: Används inte. En del av en skrapad funktion.<br>13: Används inte. En del av en skrapad funktion.<br>14: Målträff som inte matchar en Analytics-träff<br>15: Används inte just nu.<br>16: Advertising Cloud-träff som inte matchar en Analytics-träff

+++

+++**`first_hit_pagename`**

Startsidans originaldimension. Besökarens ursprungliga startsidnamn.

+++

+++**`first_hit_page_url`**

Besökarens allra första URL.

+++

+++**`first_hit_referrer`**

Den första refererande URL:en för besökaren.

+++

+++**`first_hit_ref_domain`**

Den ursprungliga refererande domändimensionen. Baserat på `first_hit_referrer`. Den första refererande domänen för besökaren.

+++

+++**`first_hit_ref_type`**

Ett numeriskt ID som representerar referenstypen för besökarens första referent.

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

Tidsstämpel för besökarens första träff i UNIX®-tid.

+++

+++**`geo_city`**

Namnet på den stad som träffen kom från, baserat på IP. Används i stadsdimensionen.

+++

+++**`geo_country`**

Förkortningen för det land som träffen kom från, baserat på IP. Används i dimensionen Länder.

+++

+++**`geo_dma`**

Ett numeriskt ID för det demografiska område som träffen kom från, baserat på IP. Används i den amerikanska DMA-dimensionen.

+++

+++**`geo_region`**

Namnet på den stat eller region som träffen kom från, baserat på IP. Används i dimensionen Områden.

+++

+++**`geo_zip`**

Postnumret som träffen kom från, baserat på IP. Hjälper till att fylla i postkodsdimensionen. Se även `zip`.

+++

+++**`hitid_high`**

Används med `hitid_low` för att identifiera en träff.

+++

+++**`hitid_low`**

Används med `hitid_high` för att identifiera en träff.

+++

+++**`hit_source`**

Källan som träffen kom från. Träffkällor 1 och 2 faktureras. <br>1: Standardbildbegäran utan tidsstämpel <br>2: Standardbildbegäran med tidsstämpel <br> 3: Överföring av Live-datakälla med tidsstämplar <br> <br>: Används inte <br>6: Överföring av allmän datakälla 6: Används inte längre; överföring av datakälla med fullständig bearbetning <br>7: Överföring av TransactionID-datakälla <br>8: Används inte längre; Tidigare versioner av Adobe Advertising-datakällor <br> 8&rbrace;9: Används inte längre, Adobe Social-sammanfattningsmått <br> : Audience Manager serversidans vidarebefordran används

+++

+++**`hit_time_gmt`**

Tidsstämpeln för Adobe datainsamlingsservrar tog emot träffen, baserat på UNIX®-tid.

+++

+++**`hourly_visitor`**

En flagga som avgör om träffen är en ny timbesökare.

+++

+++**`ip`**

IPv4-adressen, baserad på HTTP-huvudet i bildbegäran. Mutuellt exklusiv för `ipv6`. Om den här kolumnen innehåller en icke-konfidentiell IP-adress är `ipv6` tom.

+++

+++**`ipv6`**

Den komprimerade IPv6-adressen, om den är tillgänglig. Mutuellt exklusiv för `ip`. Om den här kolumnen innehåller en icke-konfidentiell IP-adress är `ip` tom.

+++

+++**`javascript`**

Ett söknings-ID för JavaScript-version, baserat på `j_jscript`.

{{cja-df-lookup}}

+++

+++**`java_enabled`**

Den Java-aktiverade dimensionen. <br>Y: Aktiverad <br>N: Inaktiverad <br>U: Okänd

{{cja-df-post}}

+++

+++**`j_jscript`**

Den version av JavaScript som stöds av webbläsaren.

+++

+++**`language`**

Ett numeriskt ID som representerar besökarens språk.

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

Tidsstämpel (i UNIX®-tid) för föregående träff. Används för att beräkna dimensionen Dagar sedan senaste besök.

+++

+++**`last_purchase_num`**

Kundlojalitetsdimensionen. Antalet tidigare inköp som besökaren har gjort. <br>0: Inga tidigare inköp (inte en kund) <br>1: 1 tidigare inköp (ny kund) <br>2: 2 tidigare inköp (returkund) <br>3: 3 eller fler tidigare inköp (lojal kund)

+++

+++**`last_purchase_time_gmt`**

Används i dimensionen Dagar sedan senaste köp. Tidsstämpel (i UNIX®-tid) för det senaste köpet. För förstagångsköp och besökare som inte har gjort något inköp tidigare är det här värdet `0`.

+++

+++**`latlon1`**

Placering (ned till 10 km)

+++

+++**`latlon23`**

Plats (ned till 100 m)

+++

+++**`latlon45`**

Plats (ned till 1 m)

+++

+++**`mcvisid`**

Experience Cloud Visitor-ID. 128-bitars nummer som består av två sammanfogade 64-bitars tal som fyllts med 19 siffror.

+++

+++**`mc_audiences`**

Lista med Audience Manager segment-ID:n som besökaren tillhör. Kolumnen `post_mc_audiences` ändrar avgränsaren till `--**--`.

{{cja-df-post}}

+++

+++**`mobileaction`**

Mobilåtgärd. Samlas in automatiskt när `trackAction` anropas i mobilimplementeringar. Tillåter automatisk åtgärdspunkt i appen.

{{cja-df-post}}

+++

+++**`mobileappid`**

ID för mobilapp. Lagrar programnamnet och versionen i följande format: `[AppName] [BundleVersion]`

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

Används i Apteligent-dataanslutningen. Program-ID som används i Apteligent.

+++

+++**`mobileappperformancecrashid`**

Används i Apteligent-dataanslutningen. Det krasch-ID som används i Apteligent.

+++

+++**`mobileappstoreobjectid`**

Används i dataanslutningen [!DNL Appfigures]. Objekt-ID för App Store.

+++

+++**`mobilebeaconmajor`**

Mobiltjänster är viktiga

+++

+++**`mobilebeaconminor`**

Mobiltjänster är mindre

+++

+++**`mobilebeaconproximity`**

Avstånd för mobiltjänster

+++

+++**`mobilebeaconuuid`**

Beacon UUID för mobiltjänster

+++

+++**`mobilecampaigncontent`**

Namnet eller ID för innehållet som visade länken. Fylls i av Anskaffning av mobilapp.

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

Marknadsföringsmedium, som banner eller e-post. Fylls i av Anskaffning av mobilapp.

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

Namnet på kampanjen, som också lagras i kampanjvariabeln. Fylls i av Anskaffning av mobilapp.

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

Ursprunglig hänvisare, t.ex. nyhetsbrev eller sociala medier. Fylls i av Anskaffning av mobilapp.

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

Betalnyckelord eller andra termer som du vill spåra med förvärvet. Fylls i av Anskaffning av mobilapp.

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

Nummer på den veckodag då appen startades.

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

Antal dagar sedan appen kördes för första gången.

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

Antal dagar sedan appen senast kördes.

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

Samlades in från kontextdatavariabeln `a.deeplink.id`. Används i förvärvsrapporter som en identifierare för länken för mobilförvärv.

+++

+++**`mobiledevice`**

Namn på mobil enhet. I iOS lagras den som en kommaavgränsad tvåsiffrig sträng. Det första numret representerar enhetsgenereringen och det andra representerar enhetsfamiljen.

{{cja-df-post}}

+++

+++**`mobilehourofday`**

Definierar timmen på dagen då appen startades. Använder ett numeriskt format på 24 timmar.

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

Datum för mobilinstallation. Anger datumet för första gången som en användare öppnar mobilappen.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

Ökningar med ett varje gång mobilappen startas.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

Samlades in från kontextdatavariabeln `a.message.button.id`. Används för meddelanden i appen för att identifiera knappen som stängde meddelandet.

{{cja-df-post}}

+++

+++**`mobilemessageid`**

Meddelande-ID i appen

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

Meddelande i appen online

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

Samlades in från kontextdatavariabeln `a.push.optin`. Ange som&quot;true&quot; när användaren väljer att skicka meddelanden, annars är värdet&quot;false&quot;.

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

Samlades in från kontextdatavariabeln `a.push.payloadid`. Används i push-meddelanden som nyttolast-ID.

{{cja-df-post}}

+++

+++**`mobileosversion`**

Mobiltjänstens operativsystemversion

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

Samlades in från kontextdatavariabeln `a.loc.acc`. Anger GPS-noggrannheten i meter vid insamlingen.

+++

+++**`mobileplacecategory`**

Samlades in från kontextdatavariabeln `a.loc.category`. Beskriver kategorin för en viss plats.

+++

+++**`mobileplaceid`**

Samlades in från kontextdatavariabeln `a.loc.id`. Identifierare för en viss intressepunkt.

+++

+++**`mobilepushoptin`**

Push-deltagande för mobiltjänster

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

Push-nyttolast-ID för mobiltjänster

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Startinnehåll för mobiltjänster

+++

+++**`mobilerelaunchcampaignmedium`**

Startmedium för mobiltjänster

+++

+++**`mobilerelaunchcampaignsource`**

Startkälla för Mobile Services

+++

+++**`mobilerelaunchcampaignterm`**

Startperiod för Mobile Services

+++

+++**`mobilerelaunchcampaigntrackingcode`**

Samlades in från kontextdatavariabeln `a.launch.campaign.trackingcode`. Används i anskaffning som spårningskod för lanseringskampanj.

+++

+++**`mobileresolution`**

Den mobila enhetens upplösning. `[Width] x [Height]` i pixlar.

{{cja-df-post}}

+++

+++**`mobile_id`**
Om användaren använder en mobil enhet anger du enhetens numeriska ID.

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

En flagga som avgör om besökaren är unik för den aktuella månaden.

+++

+++**`mvvar1`** - **`mvvar3`**

Lista variabelvärden. Innehåller en avgränsad lista med anpassade värden beroende på implementering. Kolumnerna `post_mvvar1` - `post_mvvar3` ersätter den ursprungliga avgränsaren med `--**--`.

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

Listvariabelvärdena som angavs för den aktuella träffen. Ersätter den ursprungliga avgränsaren med `--**--`. Kolumnerna `post` innehåller vanligtvis inga data.

{{cja-df-post}}

+++

+++**`new_visit`**

En flagga som avgör om den aktuella träffen är ett nytt besök. Anges av Adobe efter 30 minuters inaktivitet.

+++

+++**`os`**

Ett numeriskt ID som representerar besökarens operativsystem. Baserat på kolumnen `user_agent`.

{{cja-df-lookup}}

+++

+++**`pagename`**

Siddimensionen. Om variabeln `pagename` är tom används `page_url` i stället.

{{cja-df-post}}

+++

+++**`pagename_no_url`**

Liknar `pagename`, förutom att den inte faller tillbaka till `page_url`. Endast kolumnen `post` är tillgänglig.

{{cja-df-post}}

+++

+++**`page_event`**

Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, anpassad länk, slutlänk).

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

Används endast vid förfrågningar om länkspårningsbilder. URL-adressen till den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickar på.

{{cja-df-post}}

+++

+++**`page_event_var2`**

Används endast vid förfrågningar om länkspårningsbilder. Länkens anpassade namn (om det anges). Anger länken Egen, länken Hämta eller länken Avsluta beroende på värdet i `page_event`.

{{cja-df-post}}

+++

+++**`page_type`**

Det gick inte att hitta dimensionen Sidor, som vanligtvis används för 404 sidor.

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**: URL:en för träffen. Använder en datatyp för text.<br>**`post_page_url`**: Borttagen för förfrågningar om länkspårningsbild (`tl()`).

{{cja-df-post}}

+++

+++**`paid_search`**

En flagga som avgör om träffen matchar betalsökningsidentifiering.

+++

+++**`persistent_cookie`**

Används i dimensionen Stöd för beständig cookie. Anger om besökaren stöder cookies som inte tas bort efter varje träff.

{{cja-df-post}}

+++

+++**`pointofinterest`**

Intressepunktsnamn för mobiltjänster

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Avstånd för mobiltjänster till intressanta center

{{cja-df-post}}

+++

+++**`product_list`**

Sidvariabeln `products`. Hjälper till att fylla i flera dimensioner och mätvärden, inklusive kategori, produkt, enheter och intäkter.

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

Anpassade trafikvariabler 1-75. Används i mått för utkast.

{{cja-df-post}}

+++

+++**`purchaseid`**

Unik identifierare för ett köp, enligt inställningen med variabeln `purchaseID`. Används av kolumnen `duplicate_purchase`.

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

En flagga som avgör om träffen är en ny kvartalsbesökare.

+++

+++**`referrer`**

Refererardimensionen. Observera att medan `referrer` använder datatypen varchar(255) använder `post_referrer` datatypen varchar(244).

{{cja-df-post}}

+++

+++**`ref_domain`**

Refererande domändimension. Baserat på kolumnen `referrer`.

+++

+++**`ref_type`**


Ett numeriskt ID som representerar typen av hänvisning för träffen. Används i referensdimension.<br>1: Inuti din webbplats<br>2: Andra webbplatser<br>3: Sökmotorer<br>4: Hårddisk<br>5: USENET<br>6: Typed/Bookmarked (ingen referent)<br>7: Email<br>8: No JavaScript<br>9: Social Networks<br>10: Conversational AI tools

+++

+++**`resolution`**

Ett numeriskt ID som representerar bildskärmens upplösning. Används i skärmupplösningsdimensionen.

{{cja-df-lookup}}

+++

+++**`search_engine`**

Ett numeriskt ID som representerar sökmotorn som refererade besökaren till din webbplats. Används i dimensioner för sökmotor.

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

Används av dimensionen Rankning för alla söksidor. Anger vilken sida med sökresultat som din webbplats visade sig på innan användaren klickade igenom till din webbplats.

+++

+++**`secondary_hit`**

En flagga som avgör om träffen är en sekundär träff. Den här flaggan kommer vanligtvis från taggar för flera programsviter och VISTA-regler som kopierar träffar.

+++

+++**`sourceid`**

SOURCE ID

+++

+++**`stats_server`**

Inte till användning. Adobe interna server som bearbetade träffen.

+++

+++**`s_kwcid`**

Nyckelord-ID som används i Adobe Advertising-integreringar.

{{cja-df-post}}

+++

+++**`s_resolution`**

Upplösningsvärde för Raw-skärm. Samlades in med JavaScript-funktionen `screen.width x screen.height`.

+++

+++**`tnt`**

Används i Adobe Target integreringar. Representerar alla tester som är kvalificerade för tillfället. Formatet är: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`.

{{cja-df-post}}

+++

+++**`tnt_action`**

Används i Adobe Target integreringar. Representerar alla tester som träffen är kvalificerad för.

{{cja-df-post}}

+++

+++**`tnt_instances`**

Används i Adobe Target integreringar. Målförekomstvariabel.

+++

+++**`transactionid`**

En unik identifierare där olika datapunkter kan överföras senare via datakällor. Samlades in med variabeln `transactionID`.

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

En flagga som anger att bildbegäran trunkerades (en partiell träff togs emot). <br>Y: Träff trunkerades. Partiell träff togs emot <br>N: Trädet trunkerades inte, fullständig träff togs emot

+++

+++**`t_time_info`**

Lokal tid för besökaren. Formatet är: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

Inte till användning. Det numeriska ID:t för rapportsvitens ID. Använd `username` i stället.

+++

+++**`username`**

Rapportsvitens ID för träffen.

+++

+++**`user_agent`**

Användaragentsträngen som skickas i HTTP-huvudet i bildbegäran.

+++

+++**`user_hash`**

Inte till användning. Hash för rapportens Suite-ID. Använd `username` i stället.

+++

+++**`user_server`**

Används i serverdimensionen.

{{cja-df-post}}

+++

+++**`va_closer_detail`**

Senaste beröringsdetaljdimension.

+++

+++**`va_closer_id`**

Ett numeriskt ID som identifierar dimensionen för den sista beröringskanalen.

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

Den första touch-detaljdimensionen.

+++

+++**`va_finder_id`**

Ett numeriskt ID som identifierar dimensionen för den första beröringskanalen.

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

En flagga som identifierar instanser av marknadsföringskanal.

+++

+++**`va_new_engagement`**

En flagga som identifierar Marketing Channel New engagement.

+++

+++**`video`**

Dimensionen för tjänster för innehållsströmning.

{{cja-df-post}}

+++

+++**`videoad`**

Ad streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadinpod`**

Ad in pod position streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadlength`**

Ad length (variable) streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadname`**

Ad name (variabel)-dimensionen för direktuppspelande medietjänster.

{{cja-df-post}}

+++

+++**`videoadplayername`**

Ad player name streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadpod`**

Ad pod streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadvertiser`**

Dimensionen för direktuppspelande medietjänster för annonsörer.

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

Dimensionen för direktuppspelande medietjänster för album.

+++

+++**`videoaudioartist`**

The Artist streaming media services dimension.

+++

+++**`videoaudioauthor`**

Dimensionen för direktuppspelande medietjänster för författare.

+++

+++**`videoaudiolabel`**

The Label streaming media services dimension.

+++

+++**`videoaudiopublisher`**

Dimensionen för direktuppspelande medietjänster för utgivare.

+++

+++**`videoaudiostation`**

The Station streaming media services dimension.

+++

+++**`videocampaign`**

Dimensionen för tjänster för direktuppspelning av kampanj-ID.

{{cja-df-post}}

+++

+++**`videochannel`**

Dimensionen för medietjänster för direktuppspelning av innehållskanal.

{{cja-df-post}}

+++

+++**`videochapter`**

The Chapter streaming media services dimension.

{{cja-df-post}}

+++

+++**`videocontenttype`**

Dimensionen för medietyp för direktuppspelning av innehåll.

{{cja-df-post}}

+++

+++**`videodaypart`**

Dagdelen för tjänster för direktuppspelning av media.

{{cja-df-post}}

+++

+++**`videoepisode`**

The Episode streaming media services dimension.

{{cja-df-post}}

+++

+++**`videofeedtype`**

Dimensionen för tjänster för direktuppspelning av medietyp i Mediefeed.

{{cja-df-post}}

+++

+++**`videogenre`**

Genre streaming media services dimension. Denna dimension tillåter flera värden i samma träff, avgränsade med kommatecken.

{{cja-df-post}}

+++

+++**`videolength`**

Dimensionen för innehållslängd (variabel) för direktuppspelande medietjänster.

{{cja-df-post}}

+++

+++**`videomvpd`**

MVPD dimension för direktuppspelande medietjänster.

{{cja-df-post}}

+++

+++**`videoname`**

Dimensionen för innehållsnamn (variabel) för direktuppspelande medietjänster.

{{cja-df-post}}

+++

+++**`videonetwork`**

Dimensionen för tjänster för direktuppspelande media i nätverk.

{{cja-df-post}}

+++

+++**`videopath`**

Media Path streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoplayername`**

Innehållsspelarens namn för att direktuppspela medietjänster.

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

Den genomsnittliga dimensionen för direktuppspelande medietjänster för bithastighet.

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

Bithastigheten ändrar dimensionen för direktuppspelande medietjänster.

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

Dimensionen för Buffer-händelser som direktuppspelar medietjänster.

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

Total buffertvaraktighet för direktuppspelning av medietjänster.

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

Dimensionen för släppta bildrutor för direktuppspelande medietjänster.

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

Dimensionen för direktuppspelning av medietjänster är felaktig.

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

Dimensionen för det externa fel-ID:t för direktuppspelning av medietjänster. Denna dimension tillåter flera värden i samma träff.

+++

+++**`videoqoeplayersdkerrors`**

Player SDK-fel-ID:n för direktuppspelning av medietjänster. Denna dimension tillåter flera värden i samma träff.

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

Tid för att starta dimensionen för direktuppspelande medietjänster.

{{cja-df-post}}

+++

+++**`videoseason`**

Dimension för direktuppspelande medietjänster för säsongen.

{{cja-df-post}}

+++

+++**`videosegment`**

Imension av medietjänster för direktuppspelning i innehållssegment.

{{cja-df-post}}

+++

+++**`videosessionid`**

Dimensionen för mediesession-ID för direktuppspelning av medietjänster.

{{cja-df-post}}

+++

+++**`videoshow`**

Dimensionen Visa tjänster för direktuppspelande media.

{{cja-df-post}}

+++

+++**`videoshowtype`**

Dimensionen Visa tjänster för direktuppspelad media.

{{cja-df-post}}

+++

+++**`videostreamtype`**

Dimensionen för tjänster för direktuppspelning av medietyp.

+++

+++**`visid_high`**

Används med `visid_low` för att unikt identifiera en besökare.

{{cja-df-post}}

+++

+++**`visid_low`**

Används med `visid_high` för att unikt identifiera en besökare.

{{cja-df-post}}

+++

+++**`visid_new`**

En flagga som avgör om träffen innehåller ett nyligen genererat besökar-ID.

+++

+++**`visid_timestamp`**

Om ett besökar-ID nyligen genereras, anger tidsstämpeln i UNIX®-tid när besökar-ID:t genererades.

+++

+++**`visid_type`**

Ej för extern användning; används internt av Adobe för optimering av bearbetningen. Ett numeriskt ID som representerar den metod som används för att identifiera besökaren.<br>`0`: Anpassat besökar-ID eller Okänt/ej tillämpligt<br>`1`: IP- och användaragentåtergång <br>`2`: HTTP Mobile Subscriber Header <br>`3`: Legacy cookie value (`s_vi`) <br>`4`: Fallback cookie value (`s_fid`) <br>`5`: Identity Service

{{cja-df-post}}

+++

+++**`visit_keywords`**

Nyckelordsdimensionen Sök. I den här kolumnen används en icke-standard teckengräns på varchar(244) för att rymma den serverlogik som används av Adobe. Den efterbearbetade kolumnen är `**post_keywords**`, inte `**post_visit_keywords**`.

{{cja-df-post}}

+++

+++**`visit_num`**

Besöksnummerdimensionen. Börjar vid 1 och ökar stegvis varje gång ett nytt besök påbörjas per besökare.

+++

+++**`visit_page_num`**

Träffdjupsdimensionen. Ökar med 1 för varje träff som besökaren skapar. Återställer varje besök.

+++

+++**`visit_referrer`**

Den första referenten till besöket.

+++

+++**`visit_ref_domain`**

Baserat på kolumnen `visit_referrer`. Den första refererande domänen för besöket.

+++

+++**`visit_ref_type`**

Ett numeriskt ID som representerar referenstypen för besökets första referent.

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

Ett numeriskt ID som representerar besökets första sökmotor.

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

Sida av första besöket.

+++

+++**`visit_start_page_url`**

URL till besökets första träff.

+++

+++**`visit_start_time_gmt`**

Tidsstämpel (i UNIX®-tid) för första besöket.

+++

+++**`weekly_visitor`**

En flagga som avgör om träffen är en ny besökare varje vecka.

+++

+++**`yearly_visitor`**

En flagga som avgör om träffen är en ny årlig besökare.

+++

+++**`zip`**

Hjälper till att fylla i postkodsdimensionen. Se även `geo_zip`.

{{cja-df-post}}

+++
