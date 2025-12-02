---
title: Jämför databehandling i Adobe Analytics och Customer Journey Analytics rapporteringsfunktioner
description: Förstå skillnaderna i databehandling för de olika rapportfunktionerna
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 0%

---

# Jämför databehandling i Adobe Analytics och Customer Journey Analytics

Du behöver ofta kunna bearbeta data innan de kan användas för rapportering. Ni kan bearbeta dessa data i flera steg under resan, från datainsamling till generering av rapporten eller visualiseringen.

I Adobe Analytics sker den mesta databearbetningen direkt efter datainsamlingen. Funktioner som VISTA-regler, bearbetningsregler och bearbetningsregler för marknadsföringskanaler finns tillgängliga som stöd för denna **insamlingstid**.
Informationen lagras sedan och vid rapporttillfället kan du använda ytterligare bearbetning. Du kan till exempel dela upp dimensioner, använda segmentering eller välja en annan attribueringsmodell. Den här **rapporttidsbearbetningen** sker direkt.

I Adobe Analytics är det oftast en mindre mängd bearbetning som sker vid insamlingen.

![Adobe Analytics insamlingstid - bearbetning](../assets/aa-processing.png)

Customer Journey Analytics är däremot utformat för att kräva minimal bearbetning i realtid innan data sorteras och lagras. Den underliggande arkitekturen i Customer Journey Analytics är utformad för att fungera med lagrade data vid rapporttillfället. Customer Journey Analytics har sina kraftfulla funktioner för bearbetning av rapporttid inte bara i Analysis Workspace. Ytterligare funktioner för rapporttidsbearbetning är tillgängliga genom definitionen av [komponenter](/help/data-views/component-settings/overview.md) och [härledda fält](/help/data-views/derived-fields/derived-fields.md) i datavyer.

![Customer Journey Analytics bearbetning av rapporttid](../assets/cja-processing.png)

Att förstå skillnaderna i databehandling för de olika rapportfunktionerna kan vara till hjälp när det gäller att förstå vilka mätvärden som är tillgängliga var och varför de kan skilja sig.

Till exempel definieras *besök* som ett mått i Adobe Analytics vid databearbetningen. Och *sessioner* beräknas som ett mått i Customer Journey Analytics vid rapporttillfället. Därför kan de två mätvärdena skilja sig åt beroende på reglerna för sessionsdefinitionen i en datavy för Customer Journey Analytics.

Besök och sessioner som mätvärden är inte heller tillgängliga i datauppsättningar som skapats av Analytics-källkopplingen. Därför måste du definiera sessionen i frågelogiken för att kunna göra jämförelser.

## Terminologi {#terms}

I tabellen nedan definieras terminologi för de olika typer av bearbetningslogik som tillämpas på Adobe Analytics och Customer Journey Analytics:

| Term | Definition | Anteckningar |
| --- | --- | --- |
| Samlingstid | Logik som utförs när data samlas in och bearbetas, innan den lagras för rapportering och analys. | Denna logik är bakad i historiska data och kan vanligtvis inte ändras på ett enkelt sätt. |
| Bearbetning vid rapporttid | Logik som utförs när en rapport körs. | Denna logik kan tillämpas på framtida och historiska data vid rapportkörning på ett icke-förstörande sätt. |
| Logik på träffnivå | Logik som tillämpas rad för rad. | Exempel: Bearbetningsregler, VISTA, vissa regler för marknadsföringskanaler. |
| Logik på besöksnivå | Logik som tillämpas på besöksnivån. | Exempel: Besök och sessionsdefinition. |
| Logik på besökarnivå | Logik som tillämpas på personnivå. | Exempel: Personsammanfogning mellan enheter och kanaler. |
| Segmentlogik | Utvärdering av segmentregler för händelse/besök/person (händelse/session/person). | Exempel: Personer som köpt röda skor. |
| Beräknade mått | Utvärdering av kundskapade anpassade mätvärden. Beräknade mätvärden kan baseras på komplexa formler, inklusive segment. | Till exempel antalet personer som köpte röda skor. |
| Attributionslogik | Logik för att beräkna attribuering. | Exempel: eVar persistence. |
| Komponentinställningar | Använda anpassningar av mätvärden eller dimensioner, som attribuering, beteende, format med mera | Exempel: värdepaketering för att kombinera numeriska värden baserade på ett intervall |
| Härledda fält | Logik som tillämpas på schema- eller standardfält som en del av definitionen av komponenter i en datavy. | Exempel: skapa en ny marknadsföringskanaldimension |

{style="table-layout:auto"}

Med tiden har Adobe Analytics och nu Customer Journey Analytics förbättrat sin flexibilitet genom att tillåta att besök- och persondata-logik utförs vid rapportkörning.

## Typer av databehandling {#types}

De databehandlingssteg som utförs av Adobe Analytics och Customer Journey Analytics och tidpunkten för dessa steg varierar från funktion till funktion. Tabellen nedan innehåller en sammanfattning av de olika typerna av databehandling för varje funktion och när databehandling används.

| Funktion | Används vid bearbetningstid | Används vid rapporttid | Inte tillgängligt | Anteckningar |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics) reporting<br/>(inkluderar inte avancerade attribueringsfunktioner eller virtuella rapportsviter med rapporttidsbearbetning) | <ul><li>[Bearbetar regler](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules)</li><li>[VISTA-regler](https://experienceleague.adobe.com/en/docs/analytics/technotes/terms)</li><li>Marknadsföringskanalregler på toppnivå [&#128279;](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules)</li><li>Marknadsföringskanalregler på besöksnivå (se anmärkning)</li><li>Besök definitionen</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li><li>Beräknade mått</li></ul> | <ul><li>Enhetsövergripande analys (se anmärkning)</li></ul> | <ul><li>Enhetsövergripande analys kräver att virtuella rapportsviter används med rapporttidsbearbetning.</li><li>Marknadsföringskanalregler på besöksnivå omfattar följande: **Är första sidan av besök**, **Åsidosätt sista-beröringskanal** och **Förfallodatum för marknadsföringskanal**. (Se [dokumentation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels).)</li></ul> |
| Adobe Analytics [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | <ul><li>Bearbetar regler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besök definitionen</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li></ul> | <ul><li>Beräknade mått</li><li>Enhetsövergripande analys</li></ul> |     |
| Adobe Analytics [Datafeeds](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | <ul><li>Bearbetar regler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besöksdefinition (besöksfält)</li><li>Attributionslogik (i postkolumner)</li></ul> |   | <ul><li>Segmentlogik</li><li>Beräknade mått</li><li>Enhetsövergripande analys</li></ul> | <ul><li>ID-mappningar för vissa marknadsföringskanalrelaterade kolumner i dataflöden ingår inte i dataflöden. (Se [dokumentationen för dataflöden](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference).)</li></ul> |
| Adobe Analytics [Livesream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Bearbetar regler</li><li>VISTA-regler</li><ul> |   | <ul><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li><li>Besökslogik</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Beräknade mått</li><li>Enhetsövergripande analys</li></ul> |  |
| Adobe Analytics [Avancerade attribueringsfunktioner](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview) | <ul><li>Bearbetar regler</li><li>VISTA-regler</li><li>Besöksdefinition (se anmärkning)</li><li>Enhetsövergripande analys (se anmärkning)</li></ul> | <ul><li>Regler för marknadsföringskanaler på toppnivå (se notering)</li><li>Marknadsföringskanalregler på besöksnivå (se anmärkning) Attribution logic</li><li>Segmentlogik</li><li>Beräknade mått</li></ul> |  | <ul><li>Enhetsövergripande analys kräver att virtuella rapportsviter används med rapporttidsbearbetning.</li><li>Avancerade attribueringsfunktioner i Core Analytics använder marknadsföringskanaler som är helt härledda vid rapporttillfället (d.v.s. härledda mellanvärden).</li><li>Avancerade attribueringsfunktioner använder en besöksdefinition vid bearbetningstid, förutom när den används i en virtuell rapportserie vid bearbetning.</li></ul> |
| Adobe Analytics virtuella rapportsviter med [rapporttidsbearbetning](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) | <ul><li>Bearbetar regler</li><li>VISTA-regler</li><li>[Enhetsövergripande analys](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview)</li></ul> | <ul><li>Besök definitionen</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Beräknade mått</li><li>Andra inställningar för bearbetning av rapporttid för virtuella rapportsviter</li></ul> | <ul><li>Marknadsföringskanalregler på toppnivå</li><li>Marknadsföringskanalregler på besöksnivå</li></ul> | <ul><li>Se Rapporttidsbearbetning för virtuell rapportserie [dokumentation](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing).</li></ul> |
| [Analyskällans koppling](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics)-baserad datauppsättning i Adobe Experience Platform-datasjön | <ul><li>Bearbetar regler</li><li>VISTA-regler</li><li>Marknadsföringskanalregler på toppnivå</li><li>Fältbaserad stygn (se anmärkning)</li></ul> |   | <ul><li>[Marknadsföringskanalregler på besöksnivå](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)</li><li>Besökslogik</li><li>Attributionslogik</li><li>Segmentlogik</li></ul> | <ul><li>Använd er egen segmentlogik och beräknade värden</li><li>Fältbaserad sammanfogning skapar en separat sammanfogad datauppsättning utöver den som skapas av Analytics-källkopplingen.</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing)-rapportering | <ul><li>Implementeras som en del av Adobe Experience Platform Data Collection</li></ul> | <ul><li>Sessionsdefinition</li><li>Inställningar för [Datavy](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views)<li>Attributionslogik</li><li>Beräknade mått</li><li>Segmentlogik</li></ul> | <ul><li>Marknadsföringskanalregler på besöksnivå</li></ul> | <ul><li>Använd sammanslagna datauppsättningar för att utnyttja flerkanalsanalyser.</li></ul> |

{style="table-layout:auto"}
