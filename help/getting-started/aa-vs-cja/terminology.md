---
source-git-commit: c25e320268aeda85eb6709ca3458c60c6f24fea3
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 3%

---
# Jämföra terminologi för analysdata som skickas via Analytics Source Connector

| Relaterade villkor | Adobe Analytics | Adobe Analytics dataflöden | Källanslutning/datasjön för analyser | CJA | Anteckningar |
|---|---|---|---|---|---|
| <ul><li>Träffar</li><li>Förekomster</li><li>Poster</li><li>Händelser</li></ul> | **Förekomster** mått<br><br>Se:<ul><li>[Termer som används i Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>[Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)</li></ul> | Antal rader (poster) i dataflödesfilen | Antal rader (poster) i datauppsättningen<br><br>Se:<ul><li>[Jämför dina Adobe Analytics-data med CJA-data](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=en)</li></ul> | **Händelser** mått | <ul><li>&quot;Hit&quot; och &quot;instance&quot; är synonyma i Adobe Analytics.</li><li>Se _Anpassade händelser_ nedan.</li><li>Vissa data filtreras när de skickas via Analytics Source Connector till AEP. Se [Jämför dina Adobe Analytics-data med CJA-data](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=en) |
| <ul><li>Unika besökare</li><li>Unika enheter</li><li>Unika cookies</li></ul> | **Unika besökare** mått<br><br>Se:<ul><li>[Termer som används i Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>[Unika besökare](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=en)</li></ul> | Distinkta värden för **post\_visid\_high &amp; post\_visid\_low** sammanfogade.<br><br>Se:<ul><li>[Använd dataflöden för att beräkna gemensamma mätvärden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en)</li></ul> | Antal distinkt för **endUserID:n.\_experience.aaid.id** | **Folk** om **endUserID:n.\_experience.aaid.id** väljs som person-ID. | <ul><li>En&quot;besökare&quot; i Adobe Analytics är vanligtvis kopplad till en&quot;enhets-ID&quot; som en cookie. AAID är den primära enhetsidentifieraren i Adobe Analytics, inte ECID. Se även [STÖD, ECID, AACUSTOMID och Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/aaid-ecid-adc.html?lang=en).</li><li>&quot;Besökaren&quot; är inte ett körklart mått i CJA. Men om du väljer **endUserID:n.\_experience.aaid.id** som Person-ID är personmåttet i CJA ungefär detsamma som för unika besökare i Adobe Analytics.</li></ul> |
| <ul><li>Personer</li></ul> | **Folk** mått<br><br> Se:<ul><li>[Personer](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en)</li></ul> | Inte tillgängligt | Antal distinkt för **_\&lt;path>_.stitchedId**(endast tillgängligt i sammanfogade datauppsättningar) | **Folk** mått | <ul><li>Personmåttet i CJA är antalet som skiljer sig från person-ID:n. Beroende på vad du väljer som person-ID i CJA-anslutningen kan personmåttet betyda olika saker.</ul></li> |
| <ul><li>Besök</li><li>Sessioner</li></ul> | **Besök** mått<br><br>Se:<ul><li>[Termer som används i Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>[Besök](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en)</li><li>[Bearbetning av rapporttid](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en)</ul></li> | Distinkta värden för **post\_visid\_high, post\_visid\_low, visit\_num &amp; visit\_start\_time\_gmt** sammanfogade.<br><br>Se:<ul><li>[Använd dataflöden för att beräkna gemensamma mätvärden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en)</li></ul> | Inte tillgängligt | **Sessioner** mått | <ul><li>Med rapporttidsbearbetning i Adobe Analytics virtuella rapportsviter och CJA-datavyer kan konceptet med besök (session) konfigureras. Besöksantalet kan därför variera mellan olika miljöer beroende på vilken definition som används. Se även [Jämför databearbetning i Adobe Analytics- och CJA-rapporteringsfunktioner](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/data-processing-comparisons.html?lang=en) och [Virtuella rapportsviter, datavyer, AEP-sandlådor och Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/vrs-dataview-sandbox-adc.html?lang=en). |
| <ul><li>Anpassade händelser</li><li>Slutförda händelser</li></ul> | Anpassade händelser 1-1000 | **post\_events\_list**<br><br> Se:<ul><li>[Använd dataflöden för att beräkna gemensamma mätvärden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en) | **\_experience.analytics.<ul>event1to100.event1 **via<br>** event901to1000.event1000 **</ul> | **\_experience.analytics.<ul>event1to100.event1 **via<br>** event901to1000.event1000 **</ul> | <ul><li>En&quot;event&quot; i Adobe Analytics är en [Händelsen Slutfört](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en) (anpassad händelse) som har angetts i en Adobe Analytics-bildbegäran (serveranrop för datainsamling).</ul> |
| <ul><li>Borttagning av händelser</li><li>Metrisk deduplicering</ul></li> | Se:<ul><li>[Händelse-ID-serialisering](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en)</li></ul> | The **post_events_list** -kolumnen innehåller deduplicerade händelsemått.<br><br>Se <ul><li>[Referens för datakolumner](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en). </ul></li> | Inte tillgängligt | Se:<ul><li>[Komponentinställningar för måttborttagning av dubbletter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=en) | <ul><li>Händelse-/metrisk borttagning av dubbletter i Adobe Analytics skiljer sig något från CJA. I Adobe Analytics sker borttagning av dubbletter vid databearbetningstid. I CJA sker borttagning av dubbletter vid rapportkörning, vilket ger större flexibilitet. Ej duplicerade mätvärden kan skilja sig något mellan Adobe Analytics och CJA.</li></ul> |
| <ul><li>Instansmått</li></ul> | Se:<ul><li>[Instanser](https://experienceleague.adobe.com/docs/analytics/components/metrics/instances.html?lang=en) | Antal gånger en&quot;pre&quot;-variabel inte är null (t.ex. eVar1). | Antal gånger en &quot;mid&quot;-variabel inte är null (t.ex. **\_experience.analytics.<br>customDimensions.eVars.eVar1**). | **Instanser** mått | <ul><li>Förekomster är vanligtvis associerade med prop- och eVar-kolumner för att avgöra hur många gånger variabeln har angetts. |