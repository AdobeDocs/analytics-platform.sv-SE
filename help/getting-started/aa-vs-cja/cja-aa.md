---
title: Funktioner i Customer Journey Analytics
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: fb5642f8dafdc16749b355cf4b77a8366e1f8401
workflow-type: tm+mt
source-wordcount: '2047'
ht-degree: 3%

---

# Funktioner i Adobe Customer Journey Analytics

I följande tabell visas vilka funktioner i Adobe Analytics som stöds, stöds delvis eller inte alls i Customer Journey Analytics och vilka funktioner i Customer Journey Analytics som inte stöds eller är tillgängliga i Adobe Analytics. De här listorna ändras med tiden när funktioner läggs till i Customer Journey Analytics.

## Funktioner/komponenter som stöds fullt ut {#full-support}

| Adobe Analytics Feature | Anmärkningar om stöd |
| --- | --- |
| Avvikelseidentifiering | Fullt stöd |
| Attribution IQ | Fullt stöd |
| Beräknade mätvärden | Fullt stöd. Befintliga beräknade mätvärden i traditionella Analysis Workspace porteras inte till Customer Journey Analytics. |
| Kalenderhändelser | Fullt stöd. Kalenderhändelser har implementerats som [Anteckningar](/help/components/annotations/overview.md) i Workspace. |
| CSV-nedladdning | Fullt stöd |
| Anpassade kalendrar | Fullt stöd |
| Datumjämförelser | Fullt stöd |
| Datumintervall | Alla funktioner för datumintervall stöds. |
| Mått | Fullt stöd. Customer Journey Analytics använder XDM och har stöd för obegränsade dimensioner. Customer Journey Analytics är inte knutet till de egna eVars- eller proffsfunktionerna i traditionella Adobe Analytics. |
| Borttagning av GDPR | Fullt stöd; Observera att GDPR nu hanteras i samordning med [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics ärver alla dataändringar [!UICONTROL Experience Platform] till underliggande datamängder. |
| Lyft- och tillförlitlighetsrapportering | Fullt stöd via [Panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md) |
| Lista variabler/listutkast | Fullt stöd. Customer Journey Analytics använder XDM och stöder obegränsat antal strängarrayer som kan användas på liknande sätt som listVars. |
| Marknadsförande eVars | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Mätvärden | Fullt stöd; Customer Journey Analytics använder Experience Data Model (XDM) och stöder obegränsade mätvärden och är inte knutet till Adobe Analytics anpassade success-händelser. Vissa standardvärden har bytt namn från Adobe Analytics: Besökare = människor, besök = sessioner, träffar = händelser. |
| Mobile Scorecard/Dashboards | Fullt stöd |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. |
| PDF Export | Fullt stöd |
| Projekturval | Fullt stöd |
| Projektlänkning | Fullt stöd |
| Bearbetning av rapporttid | Fullt stöd; Customer Journey Analytics förlitar sig enbart på bearbetning av rapporttid. |
| API-åtkomst för rapportering | Fullt stöd; Tillgängligt via [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/). |
| Schemalagda rapporter/projekt | Fullt stöd |
| Segment | Fullt stöd. Nu kallat &quot;Filter&quot; - observera att inga befintliga segment i Analysis Workspace importeras till Customer Journey Analytics. |
| Virtual Report Suites | Fullt stöd. Har anropats [Datavyer](/help/data-views/create-dataview.md). |
| Komponenturval för Virtual Report Suite | Fullt stöd. Nu en del av datavyer. |
| Streaming Media Analytics | Mediedata är tillgängliga med Analytics Data Connector som en del av panelen Media Concurrent Viewer och panelen Medieuppspelningstid i Workspace. |

{style="table-layout:auto"}

## Stöds på ett nytt sätt {#new-support}

| Funktion | Anteckningar |
| --- | --- |
| Audience Publishing (segmentpublicering) | Stöds om licensen har erhållits med Adobe Customer Data Platform eller Journey Optimizer-produkter. [Audience Publishing](/help/components/audiences/audiences-overview.md) skickar målgrupper till kundprofil i realtid i Experience Platform. |
| Klassificeringar | Kallas nu&quot;Sök efter datauppsättningar&quot;. Klassifikationer som används i Analytics kan importeras till Experience Platform och Customer Journey Analytics med hjälp av källkopplingen för analysklassificeringar. Uppslagsdatauppsättningar kan också överföras direkt till Experience Platform och göras tillgängliga i Customer Journey Analytics. |
| Classification Rule Builder | Stöds med [delsträngar](/help/data-views/component-settings/substring.md) i Customer Journey Analytics. Använder strängändringar vid rapporttidpunkten i stället för att söka efter datauppsättningar. |
| Skräddarsydd professionalisering | Stöd för alla anpassade sessionsfunktioner utom mobila bakgrundshändelser. |
| Valutakonvertering | Stöds som en del av [formatera en måttkomponent](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=en#currency) i en datavy. |
| Varaktighet för marknadsföringsvariabel | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Kundattribut | Profildatauppsättningar importeras inte automatiskt från Experience Cloud, utan måste överföras till Experience Platform innan de kan användas i Customer Journey Analytics. |
| Datafeeds | Första generationens dataexport av datauppsättningar är tillgänglig via [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) och via [Experience Platform Destinationer](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). Dessa alternativ ger händelse-/radnivåexport av alla data som samlats in eller importerats till Experience Platform Data Lake. Postprocessdatakolumner är inte tillgängliga eftersom postkolumner beräknas vid frågetiden. Det går att exportera postkolumner genom rapportering. |
| Metrisk deduplicering | Nu konfigurerat för mätvärden i datavyer. Metrisk borttagning av dubbletter sker på person- eller sessionsnivå i stället för på data-, data- eller anslutningsnivå. |
| Poster, avslutningar och använd tid för mått och mätvärden | Stöds (Poster och avslutningar kallas nu för Sessionsstart och Sessionsslut) och beräknas på ett något annorlunda sätt. |
| Inställningar för beständighet av eVar | Varor är inte längre en del av Customer Journey Analytics. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Dimensioner som anges i datavyer är begränsade till högst 90 dagars beständighet och stöder inte obegränsad beständighet. |
| IP-förvanskning | För Customer Journey Analytics-kunder som använder Analytics Source Connector för att fylla i data från Adobe Analytics i Customer Journey Analytics: Inställningarna för IP-förfalskning som används i Adobe Analytics flödar igenom till data från Customer Journey Analytics. Du kan kontrollera de här inställningarna i Adobe Analytics efter behov.<p>För Customer Journey Analytics-kunder som använder Experience Platform Web SDK fylls data i direkt i Platform och Customer Journey Analytics. Du kan använda Data Prep för datainsamling i Platform för att konfigurera regler som döljer IP-adressen baserat på företagets krav. |
| Ny eller upprepad sessionsrapportering | Tidigare genomförd med dimensionen Besök nummer. Det finns stöd för både nya och upprepade sessioner [med ett 13-månaders uppslagsfönster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=en). |
| Produktvariabel | I Experience Platform kan användare använda en array med objekttypsfält i ett dataset-schema för att tillgodose detta användningsfall. Inom Customer Journey Analytics kan man använda valfritt antal produktvariabler och de är inte begränsade till en enda variabel som i Adobe Analytics. |
| Projektdelning | Projektdelning stöds endast mellan användare av Customer Journey Analytics - det finns ingen projektdelning mellan Customer Journey Analytics och Analysis Workspace. |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |
| Report Builder (Excel-plugin) | Stöds med en ny Office 365-plugin för Excel. |
| Användarbehörigheter/dataåtkomstkontroller | Customer Journey Analytics skiljer mellan [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) produktadministratörer, produktprofiladministratörer och användare. Endast produktadministratörer kan skapa/uppdatera/ta bort anslutningar, projekt, filter eller beräknade värden som skapats av andra användare, medan produktadministratörer och produktprofiladministratörer kan redigera datavyer. Ytterligare användarbehörigheter finns för t.ex. att skapa beräknade värden, filter eller anteckningar. |
| Bearbetningsregler, VISTA-regler, Bearbetningsregler för marknadsföringskanaler | Stöds med Adobe Experience Platform Data Prep-funktionalitet för både WebSDK-baserade datauppsättningar och data från Analytics Data Connector. |
| Marknadsföringskanaler | När du använder Analytics Source Connector flödar data för marknadsföringskanaler till Customer Journey Analytics via den kopplingen. Reglerna för marknadsföringskanaler har konfigurerats i traditionella Adobe Analytics och vissa regler stöds inte. Mer information finns på [Dokumentation för Customer Journey Analytics Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>För WebSDK-implementeringar stöds bearbetningsregler för rapporttidskanaler via [Härledda fält](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## Delvis stöd {#partial}

| Funktion | Anteckningar |
| --- | --- |
| Sammanfogning mellan olika enheter och kanaler | Stöds för datauppsättningar som innehåller identitetsinformation direkt (kallas även&quot;fältbaserad&quot; sammanfogning). Diagrambaserad sammanfogning stöds ännu inte, men är planerad. Se [Flerkanalsanalys](/help/cca/overview.md). |
| Punktfiltrering | För [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-baserade datauppsättningar, robotfiltrering tillämpas. Allmän startfiltreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller Customer Journey Analytics. |
| Enhet, webbläsare, referens, teknikdimensioner | Stöds för [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-baserade datauppsättningar. Se [dokumentation om vilka analysvariabler som stöds via ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en).<p>Om du använder Experience Platform Web SDK-datainsamling stöds för närvarande inte enheter och dimensioner baserade på enhetssökningen. Framtida stöd planeras. |
| GeoSegmenteringsdimensioner | All GeoSegmentation/geography som samlas in i Adobe Analytics flödar in i Customer Journey Analytics via [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Implementeringar som inte använder Analytics Source Connector, men som förlitar sig på Experience Platform Web SDK för digital datainsamling, kan använda [Upplev tjänsten Edge Geo Lookup](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en). |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. Segmentjämförelse och analys för målpaneler (A4T) stöds inte. |
| Bearbetningsregler | För Analytics Source Connector-baserade datauppsättningar tillämpas fortfarande bearbetningsregler. [Prestandafunktioner för data i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) kan också användas som ersättning för bearbetningsregler för data som går direkt till plattformen. |
| A4T | Delvis stöd ges via fälten i [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Stöd för A4T-vänliga namn på målaktiviteter och upplevelser planeras. |

{style="table-layout:auto"}

## Inget stöd, men planerat {#planned}

| Funktion | Anteckningar |
| --- | --- |
| Larm | Support planeras. |
| Bidragsanalys | Support planeras. |
| data warehouse Reporting | Support planeras från Analysis Workspace gränssnitt. Adobe Experience Platform [[!UICONTROL Query Service]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv>) har också ett gränssnitt för dessa användningsområden i Customer Journey Analytics. |
| ID Stitching via Device Graph | Support planeras. |
| Projektmallar | Support planeras. |
| Realtidsrapportering | Support planeras. |
| Segment IQ | Support planeras. |
| Datakällor för transaktions-ID | Support planeras. |
| Migrera projekt/filter/beräknade värden från Adobe Analytics till Customer Journey Analytics | Support planeras. |
| Datakällor på sammanfattningsnivå | Support planeras. |

{style="table-layout:auto"}

## Inget stöd, ännu inte planerat {#not-planned}

| Funktion | Anteckningar |
| --- | --- |
| Activity Map | Support är ännu inte planerat. |
| Advertising Cloud | Support är ännu inte planerat. |

{style="table-layout:auto"}

## Stöds aldrig {#never}

* Personmätvärden med Coop för olika enheter
* Rapporter och analyser på kontrollpaneler
* Bokmärken för rapporter och analyser
* Rapporter och analysmål

## Adobe Customer Journey Analytics-funktioner som inte finns i Adobe Analytics {#cja-not-aa}

I följande tabell visas funktioner som är tillgängliga i Customer Journey Analytics, men som inte stöds i Adobe Analytics.

| Funktion | Mer information |
| --- | --- |
| Inkvartering av alla typer av data | Customer Journey Analytics kombineras med Experience Platform för att kunna lagra alla typer av datarotor och datatyper. Använda [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv), kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. Adobe Analytics fokuserar främst på webb- och mobilanalysdata med vissa funktioner för att [importdata](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| Obegränsat antal Dimensioner | Customer Journey Analytics är obegränsade. värden kan vara numeriska värden, text, objekt, listor eller blandningar av alla. Dimensioner kan vara kapslade eller hierarkiska. Analyserna stöder upp till högst 75 props och 250 eVars. |
| Obegränsad kardinalitet/unika värden | Customer Journey Analytics stöder obegränsat antal unika värden eller dimensionsposter som kan rapporteras inom en dimension. Adobe Analytics är begränsat till 500 000 unika värden. De obegränsade unika värdena och dimensionerna eliminerar de rapporterings- och analysbegränsningar som för närvarande finns med storskalig Analytics-implementering. |
| Rapportera tidsomvandlingar | Med rapporttidsomvandlingar (kallas datavyer) i Customer Journey Analytics kan du tolka data från en anslutning ytterligare. Du kan ändra eller ta bort data utan att implementera om dem; Använda delsträngar för att manipulera dimensioner. skapa mätvärden från vilket värde som helst, filtrera delmängder. Och omvandlingen sker på ett icke-förstörande sätt. Adobe Analytics har begränsade funktioner genom virtuella rapportsviter och sessioner. |
| Experimentationsanalys | Customer Journey Analytics kan utvärdera lyften och förtroendet för alla experiment från datakällor som definieras som en del av en anslutning. Med den här utvärderingen kan ni förstå orsaks- och effektförhållandet mellan kundinteraktioner i alla kanaler. Analyserna begränsas till experimentell analys genom integreringen med Analytics for Target (A4T). |
| Enhetsövergripande analys | Customer Journey Analytics stöder den sömlösa kombinationen av enhetsspecifika datauppsättningar från oautentiserade och autentiserade sessioner. Customer Journey Analytics erbjuder att fylla i historiska data baklänges till kända enheter. I Analytics är den här funktionen begränsad till en enda rapportserie och användningen av ett enhetsdiagram. |
| SQL Access | Med hjälp av alternativet Data Distiller kan Customer Journey Analytics ta bort begränsningarna för data som samlats in på Adobe backend-bearbetning. Du kan ändra dina data med SQL, skapa värden och datauppsättningar som är unika för ditt företag och fortsätta utforska. Analytics stöder inte någon form av SQL-åtkomst till dess data. |
| Förbättrade säkerhets- och sekretessalternativ - beredskap för HIPAA | Customer Journey Analytics är redo för HIPAA och erbjuder ytterligare säkerhetsalternativ för regelefterlevnad. Adobe Analytics är inte HIPAA-klart. |

{style="table-layout:auto"}
