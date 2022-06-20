---
title: Jämför databearbetning i Adobe Analytics- och CJA-rapporteringsfunktioner
description: Förstå skillnaderna i databehandling för de olika rapportfunktionerna
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 5%

---


# Jämför databearbetning i Adobe Analytics- och CJA-rapporteringsfunktioner

Att förstå skillnaderna i databehandling för de olika rapportfunktionerna kan vara till hjälp när det gäller att förstå vilka mätvärden som är tillgängliga var och varför de kan skilja sig.

Eftersom&quot;besök&quot; som ett mått i Adobe Analytics definieras vid databearbetningstid och&quot;sessioner&quot; som ett mått i CJA beräknas vid rapporttidpunkten, kan de två mätvärdena skilja sig åt beroende på vilka regler som används för sessionsdefinition i CJA-datavyn.

Varken besök eller sessioner som mätvärden är tillgängliga i datauppsättningar som skapas av Analytics Source Connector och därför krävs det att du definierar sessionen i din frågelogik för att kunna göra jämförelser.

## Terminologi {#terms}

I tabellen nedan definieras terminologi för de olika typer av bearbetningslogik som används för Adobe Analytics och CJA:

| Term | Definition | Anteckningar |
| --- | --- | --- |
| Bearbetningstidslogik | Logik som utförs när data bearbetas, innan den lagras för rapportering och analys. | Denna logik är bakad i historiska data och kan vanligtvis inte ändras på ett enkelt sätt. |
| Rapporttidslogik | Logik som utförs när en rapport körs. | Denna logik kan tillämpas på framtida och historiska data vid rapportkörning på ett icke-förstörande sätt. |
| Logik på träffnivå | Logik som tillämpas rad för rad. | Exempel: Bearbetningsregler, VISTA, vissa regler för marknadsföringskanaler. |
| Logik på besöksnivå | Logik som tillämpas på besöksnivån. | Exempel: Besök och sessionsdefinition. |
| Logik på besökarnivå | Logik som används på besökarnivå. | Exempel: Sammanfogning av besökare över olika enheter och kanaler. |
| Segmentlogik (filter) | Utvärdering av regler för träffs-/besökssegment (händelse/session/person) (filter). | Exempel: Folk som köpte röda skor. |
| Beräknade värden | Utvärdering av kundskapade anpassade mätvärden som kan baseras på komplexa formler, inklusive segment och filter. | Exempel: Antal personer som köpt röda skor. |
| Attributionslogik | Logik för att beräkna attribuering. | Exempel: eVar beständighet. |

{style=&quot;table-layout:auto&quot;}

Med tiden har Adobe Analytics och nu Customer Journey Analytics förbättrat sin flexibilitet genom att tillåta att besöks- och besöksnivådata utförs vid rapportkörning.

## Typer av databehandling {#types}

De databearbetningssteg som utförs för Adobe Analytics och CJA och tidpunkten för dessa steg varierar från analysfunktionen till analysfunktionen. Tabellen nedan innehåller en sammanfattning av de olika typerna av databearbetning för varje analysfunktion och när databearbetningen tillämpas.

| Analysfunktion | Används vid bearbetningstid | Används vid rapporttid | Inte tillgängligt | Anteckningar |
| --- | --- | --- | --- | --- |
| [Core AA](https://experienceleague.adobe.com/docs/analytics.html?lang=en) rapportering<br/>(inkluderar inte Attribution IQ- eller virtuella rapportsviter med bearbetning vid rapporttillfället) | <ul><li>[Behandlingsregler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=en)</li><li>[VISTA-regler](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>Träffnivå [regler för marknadsföringskanaler](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=en)</li><li>Marknadsföringskanalregler på besöksnivå (se anmärkning)</li><li>Besök definitionen</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li><li>Beräknade värden</li></ul> | <ul><li>Enhetsövergripande analys (se anmärkning)</li></ul> | <ul><li>CDA kräver att virtuella rapportsviter används med bearbetning av rapporttid.</li><li>Marknadsföringskanalregler på besöksnivå omfattar följande: **Är första sidan av besök**, **Åsidosätt sista tryckkanalen** och **Utgångsdatum för marknadsföringskanal**. (Se [dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en).)</li></ul> |
| Core AA [data warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besök definitionen</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li></ul> | <ul><li>Beräknade värden</li><li>Enhetsövergripande analys</li></ul> |  |
| Core AA [Dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besöksdefinition (besöksfält)</li><li>Attributionslogik (i postkolumner)</li></ul> |  | <ul><li>Segmentlogik</li><li>Beräknade värden</li><li>Enhetsövergripande analys</li></ul> | <ul><li>ID-mappningar för vissa marknadsföringskanalrelaterade kolumner i dataflöden ingår inte i dataflöden. (Se [dokumentation för datafeed](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en).)</li></ul> |
| Core AA [Livesream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Behandlingsregler</li><li>VISTA-regler</li><ul> |  | <ul><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besökslogik</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Beräknade värden</li><li>Enhetsövergripande analys</li></ul> |  |
| Core AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en) | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Besöksdefinition (se anmärkning)</li><li>Enhetsövergripande analys (se anmärkning)</li></ul> | <ul><li>Regler för marknadsföringskanaler på toppnivå (se notering)</li><li>Marknadsföringskanalregler på besöksnivå (se anmärkning)Attributionslogik</li><li>Segmentlogik</li><li>Beräknade värden</li></ul> |  | <ul><li>CDA kräver att virtuella rapportsviter används med bearbetning av rapporttid.</li><li>Attribution IQ i Core Analytics använder marknadsföringskanaler som är helt härledda vid rapporttidpunkten (dvs. härledda mellanvärden).</li><li>Attribution IQ använder en besöksdefinition vid bearbetningstid utom när den används i en rapporttidsbearbetning av VRS.</li></ul> |
| Core AA virtuella rapportsviter med [bearbeta rapporttid](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) (VRS RTP) | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>[Enhetsövergripande analys](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en)</li></ul> | <ul><li>Besök definitionen</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Beräknade värden</li><li>Andra VRS RTP-inställningar</li></ul> | <ul><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li></ul> | <ul><li>Se VRS RTP [dokumentation](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul> |
| [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en)-baserad datauppsättning i AEP-datasjön | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Fältbaserad stygn (se anmärkning)</li></ul> |  | <ul><li>[Marknadsföringskanalregler på besöksnivå](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>Besökslogik</li><li>Attributionslogik</li><li>Filterlogik</li></ul> | <ul><li>Måste använda din egen filterlogik och beräknade värden</li><li>Fältbaserad sammanfogning skapar en separat sammanfogad datauppsättning utöver den som skapas av Analytics Source Connector.</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en) rapportering | <ul><li>Behandlingsregler</li><li>VISTA-regler</li><li>Träffnivå [regler för marknadsföringskanaler](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>[Anslutning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en) inställningar</li><li>Fältbaserad stygn (se anmärkning)</li></ul> | <ul><li>Sessionsdefinition</li><li>[Datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) inställningar</li><li>Attributionslogik</li><li>Beräknade värden</li><li>Filterlogik</li></ul> | <ul><li>Marknadsföringskanalregler på besöksnivå</li></ul> | <ul><li>Måste använda en sammanfogad datauppsättning för att kunna utnyttja fältbaserad sammanfogning.</li></ul> |

{style=&quot;table-layout:auto&quot;}