---
title: Jämför databehandling i Adobe Analytics och Customer Journey Analytics
description: Förstå skillnaderna i databehandling för de olika rapportfunktionerna
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 4%

---

# Jämför databehandling i Adobe Analytics och Customer Journey Analytics.

Du behöver ofta kunna bearbeta data innan de kan användas för rapportering. Ni kan bearbeta dessa data i flera steg under resan, från datainsamling till generering av rapporten eller visualiseringen.

I Adobe Analytics sker den mesta databearbetningen direkt efter datainsamlingen. Funktioner som VISTA Rules, Processing Rules, Marketing Channels Processing Rules finns tillgängliga som stöd för detta **insamlingstid**.
Informationen lagras sedan och vid rapporttillfället kan du använda ytterligare bearbetning. Du kan till exempel dela upp dimensioner, använda segmentering eller välja en annan attribueringsmodell. Detta **rapporttidsbearbetning** händer i farten.

I Adobe Analytics är det oftast en mindre mängd bearbetning som sker vid insamlingen.

![Adobe Analytics bearbetning vid insamlingstid](../assets/aa-processing.png)

Customer Journey Analytics är däremot utformat för att kräva minimal bearbetning i realtid innan data kan sorteras och lagras. Den underliggande arkitekturen i Customer Journey Analytics är utformad för att fungera med lagrade data vid rapporttillfället och har en kraftfull funktion för bearbetning under rapporttid, inte bara i Workspace utan även, ännu viktigare, genom att definiera [komponenter](/help/data-views/component-settings/overview.md) och [härledda fält](/help/data-views/derived-fields/derived-fields.md) i datavyer.

![Bearbetning av rapporttiden i Customer Journey Analytics](../assets/cja-processing.png)

Att förstå skillnaderna i databehandling för de olika rapportfunktionerna kan vara till hjälp när det gäller att förstå vilka mätvärden som är tillgängliga var och varför de kan skilja sig.

Eftersom&quot;besök&quot; som ett mätvärde i Adobe Analytics definieras vid databearbetningstid och&quot;sessioner&quot; som ett mätvärde i Customer Journey Analytics beräknas vid rapporttidpunkten, kan de två mätvärdena skilja sig åt beroende på vilka regler som används för sessionsdefinitionen i datavyn i Customer Journey Analytics.

Varken besök eller sessioner som mätvärden är tillgängliga i datauppsättningar som skapas av Analytics Source Connector och därför krävs det att du definierar sessionen i din frågelogik för att kunna göra jämförelser.

## Terminologi {#terms}

I tabellen nedan definieras terminologi för de olika typer av bearbetningslogik som tillämpas på Adobe Analytics och Customer Journey Analytics:

| Term | Definition | Anteckningar |
| --- | --- | --- |
| Samlingstid | Logik som utförs när data samlas in och bearbetas, innan den lagras för rapportering och analys. | Denna logik är bakad i historiska data och kan vanligtvis inte ändras på ett enkelt sätt. |
| Bearbetning vid rapporttid | Logik som utförs när en rapport körs. | Denna logik kan tillämpas på framtida och historiska data vid rapportkörning på ett icke-förstörande sätt. |
| Logik på träffnivå | Logik som tillämpas rad för rad. | Exempel: Bearbetningsregler, VISTA, vissa regler för marknadsföringskanaler. |
| Logik på besöksnivå | Logik som tillämpas på besöksnivån. | Exempel: Besök och sessionsdefinition. |
| Logik på besökarnivå | Logik som tillämpas på personnivå. | Exempel: Personsammanfogning över flera enheter/kanaler. |
| Segmentlogik (filter) | Utvärdering av regler för event/besök/person (händelse/session/person) (filter). | Exempel: Folk som köpte röda skor. |
| Beräknade värden | Utvärdering av kundskapade anpassade mätvärden som kan baseras på komplexa formler, inklusive segment och filter. | Exempel: Antal personer som köpt röda skor. |
| Attributionslogik | Logik för att beräkna attribuering. | Exempel: eVar beständighet. |
| Komponentinställningar | Använda anpassningar av mätvärden eller dimensioner, som attribuering, beteende, format med mera | Exempel: värdepaketering för att kombinera numeriska värden baserade på ett intervall |
| Härledda fält | Logiken tillämpas på schema- eller standardfält som en del av definitionen av komponenter i en datavy. | Exempel: skapa en ny marknadsföringskanaldimension |

{style="table-layout:auto"}

Med tiden har Adobe Analytics och nu Customer Journey Analytics förbättrat sin flexibilitet genom att tillåta att besök och data på personnivå utförs vid rapportkörning.

## Typer av databehandling {#types}

De databearbetningssteg som utförs för Adobe Analytics och Customer Journey Analytics och tidpunkten för dessa steg varierar från funktion till analysfunktion. Tabellen nedan innehåller en sammanfattning av de olika typerna av databearbetning för varje analysfunktion och när databearbetningen tillämpas.

| Funktion | Används vid bearbetningstid | Används vid rapporttid | Inte tillgängligt | Anteckningar |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=en) rapportering<br/>(inkluderar inte Attribution IQ- eller virtuella rapportsviter med bearbetning vid rapporttillfället) | <ul><li>[Behandlingsregler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=en)</li><li>[VISTA-regler](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>Träffnivå [regler för marknadsföringskanaler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=en)</li><li>Marknadsföringskanalregler på besöksnivå (se anmärkning)</li><li>Besök definitionen</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li><li>Beräknade värden</li></ul> | <ul><li>Enhetsövergripande analys (se anmärkning)</li></ul> | <ul><li>CDA kräver att virtuella rapportsviter används med bearbetning av rapporttid.</li><li>Marknadsföringskanalregler på besöksnivå omfattar följande: **Är första sidan av besök**, **Åsidosätt sista tryckkanalen** och **Utgångsdatum för marknadsföringskanal**. (Se [dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en).)</li></ul> |
| Adobe Analytics [data warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besök definitionen</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li></ul> | <ul><li>Beräknade värden</li><li>Enhetsövergripande analys</li></ul> |     |
| Adobe Analytics [Dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besöksdefinition (besöksfält)</li><li>Attributionslogik (i postkolumner)</li></ul> |   | <ul><li>Segmentlogik</li><li>Beräknade värden</li><li>Enhetsövergripande analys</li></ul> | <ul><li>ID-mappningar för vissa marknadsföringskanalrelaterade kolumner i dataflöden ingår inte i dataflöden. (Se [dokumentation för datafeed](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en).)</li></ul> |
| Adobe Analytics [Livesream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Behandlingsregler</li><li>VISTA-regler</li><ul> |   | <ul><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besökslogik</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Beräknade värden</li><li>Enhetsövergripande analys</li></ul> |  |
| Adobe Analytics [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en) | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Besöksdefinition (se anmärkning)</li><li>Enhetsövergripande analys (se anmärkning)</li></ul> | <ul><li>Regler för marknadsföringskanaler på toppnivå (se notering)</li><li>Marknadsföringskanalregler på besöksnivå (se anmärkning) Attribution logic</li><li>Segmentlogik</li><li>Beräknade värden</li></ul> |  | <ul><li>CDA kräver att virtuella rapportsviter används med bearbetning av rapporttid.</li><li>Attribution IQ i Core Analytics använder marknadsföringskanaler som är helt härledda vid rapporttidpunkten (dvs. härledda mellanvärden).</li><li>Attribution IQ använder en besöksdefinition vid bearbetningstid utom när den används i en rapporttidsbearbetning av VRS.</li></ul> |
| Adobe Analytics virtuella rapportsviter med [bearbeta rapporttid](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) (VRS RTP) | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>[Enhetsövergripande analys](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en)</li></ul> | <ul><li>Besök definitionen</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Beräknade värden</li><li>Andra VRS RTP-inställningar</li></ul> | <ul><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li></ul> | <ul><li>Se VRS RTP [dokumentation](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul> |
| [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en)-baserad datauppsättning i Adobe Experience Platform datasjön | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Fältbaserad stygn (se anmärkning)</li></ul> |   | <ul><li>[Marknadsföringskanalregler på besöksnivå](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>Besökslogik</li><li>Attributionslogik</li><li>Filterlogik</li></ul> | <ul><li>Måste använda din egen filterlogik och beräknade värden</li><li>Fältbaserad sammanfogning skapar en separat sammanfogad datauppsättning utöver den som skapas av Analytics Source Connector.</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en) rapportering | <ul><li>Implementeras som en del av Adobe Experience Platform Data Collection</li></ul> | <ul><li>Sessionsdefinition</li><li>[Datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) inställningar<li>Attributionslogik</li><li>Beräknade värden</li><li>Filterlogik</li></ul> | <ul><li>Marknadsföringskanalregler på besöksnivå</li></ul> | <ul><li>Måste använda sammanslagna datauppsättningar för att kunna utnyttja flerkanalsanalyser.</li></ul> |

{style="table-layout:auto"}
