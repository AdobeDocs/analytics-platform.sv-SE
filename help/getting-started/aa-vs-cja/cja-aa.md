---
title: Funktionssupport för Customer Journey Analytics
description: Läs mer om Customer Journey Analytics funktioner jämfört med Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7f44c7497a48e8377ca26cb194f828c3c8836f98
workflow-type: tm+mt
source-wordcount: '2700'
ht-degree: 0%

---

# Funktioner i Customer Journey Analytics

I följande tabell visas vilka funktioner som är unika för Customer Journey Analytics och vilka Adobe Analytics-funktioner som stöds, stöds delvis eller inte stöds i Customer Journey Analytics. Listorna ändras med tiden när funktioner läggs till i Customer Journey Analytics.

## Funktioner som är unika för Adobe Customer Journey Analytics {#cja-not-aa}

I följande tabell visas funktioner som är tillgängliga i Customer Journey Analytics, men som inte stöds i Adobe Analytics.

| Funktion | Mer information |
| --- | --- |
| **Möjlighet att kombinera datauppsättningar (till exempel Adobe Analytics rapportsviter)** | Med Customer Journey Analytics kan du [kombinera data](/help/connections/combined-dataset.md) från flera rapportsviter som om de vore en enda rapportserie i Adobe Analytics. |
| **Anordnande för alla typer av data** | Customer Journey Analytics kombineras med Experience Platform förmåga att lagra alla typer av datarotor och datatyper. Med [Experience Data Model (XDM)](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/home) kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. Adobe Analytics fokuserar främst på webb- och mobilanalysdata med vissa funktioner för att [importera data](https://experienceleague.adobe.com/sv/docs/analytics/import/home). |
| **B2B edition** | [Customer Journey Analytics B2B edition](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition?lang=en) hjälper B2B-företag att anpassa sina marknadsförings-, sälj- och produktteam genom att tillhandahålla användbara kontoinsikter som ökar intäkterna. Med kontot som placeras i mitten av datamodellen fokuserar alla analyser på kontoresan. Genom att lägga till ett nytt lager av enheter (konton, affärsmöjligheter och inköpsgrupper) utöver personliga och tidsbaserade händelser, får ni en fullständig bild av B2B-marknadsförings- och intäktslivscykeln. |
| **BI-tillägg** | Med [BI-tillägget](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) kan du ansluta Customer Journey Analytics direkt till populära BI-visualiseringsverktyg, som Power BI eller Tableau. Genom att använda det här tillägget kan du få dina BI-rapporter att exakt matcha det du ser i Analysis Workspace och andra rapportgränssnitt i Customer Journey Analytics. Det här tillägget är ett mycket enklare sätt att få BI-rapporter för Customer Journey Analytics utan att behöva återskapa rapporter/mätvärden från rådata. |
| **Kommentarer i Workspace-projekt** | Med kommentarer kan du dela insikter och ställa frågor i ett [Analysis Workspace-projekt](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects?lang=en). Detta kan effektivisera diskussioner om data och hålla konversationer inom ramen för de data som ska diskuteras. |
| **Content Analytics** | [Content Analytics](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/content-analytics/content-analytics) hjälper marknadsförare att förstå hur innehåll påverkar nyckeltal som ett företag har definierat. Förutom beteendedata samlar Content Analytics in data om hur innehåll konsumeras och hur innehåll påverkar. |
| **Enhetsövergripande analys** | Customer Journey Analytics stöder den smidiga kombinationen av enhetsspecifika datauppsättningar från oautentiserade och autentiserade sessioner. Customer Journey Analytics erbjuder att fylla i historiska data baklänges till kända enheter. I Adobe Analytics begränsas den här funktionen till en enda rapportserie och användning av ett enhetsdiagram. |
| **Agenten för datainsikter** | [Agenten för datainsikter](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai?lang=en), som ingår i AI-assistenten i Customer Journey Analytics, är en generativ AI-konversationsagent. Den använder komponenter från datavyn och era faktiska data för att snabbt och effektivt besvara datacentrerade frågor genom att skapa relevanta visualiseringar i Analysis Workspace. |
| **Dimension-förbättringar** | Customer Journey Analytics ger större flexibilitet vid användning av dimensioner: <ul><li>**Anpassade numeriska dimensioner**: [Skapa egna numeriska baserade dimensioner i en datavy](/help/data-views/create-dataview.md#components).</li><li>**Sortera strängbaserade dimensioner**: [Sortera strängbaserade dimensioner i bokstavsordning i en friformstabell.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>I Adobe Analytics fanns bara en handfull inbyggda numeriska mått tillgängliga, och det gick inte att sortera efter strängbaserade dimensioner.</p> |
| **Härledda fält** | [Härledda fält](/help/data-views/derived-fields/derived-fields.md) tillåter rapporttidsomformningar av dina data. Data kan kombineras, korrigeras eller skapas direkt, och dessa omvandlingar gäller retroaktivt för alla rapporter. |
| **Förbättrade säkerhets- och sekretessalternativ** - beredskap för HIPAA | Customer Journey Analytics är HIPAA-klart och erbjuder [ytterligare säkerhetsalternativ](/help/privacy/cmk.md) för regelefterlevnad. Adobe Analytics är inte HIPAA-klart. |
| **Experimentationsanalys** | Customer Journey Analytics kan [utvärdera lyften och förtroendet för alla experiment](/help/analysis-workspace/c-panels/experimentation.md) från alla datakällor som definieras som en del av en anslutning. Med den här utvärderingen kan ni förstå orsaks- och effektförhållandet mellan kundinteraktioner i alla kanaler. Analyserna begränsas till experimenterande analyser via A4T. |
| **Prognos** | [Prognos](/help/analysis-workspace/c-forecast/forecasting.md) är en AI/ML-funktion som innehåller en statistisk förutsägelse för tidsserierelaterade data baserat på historiska data som redan finns i Customer Journey Analytics. Prognoser kan visas i frihandstabeller och i linjediagramvisualiseringar. |
| **Guidad analys** | [Med guidad analys](/help/guided-analysis/overview.md) kan användarna själva leverera högkvalitativa data och insikter om kundresan via guidade arbetsflöden som bygger på Customer Journey Analytics flerkanalsdata. |
| **Intelligenta bildtexter** | [Intelligenta bildtexter](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) använder avancerad maskininlärning och generativ AI för att ge värdefulla insikter på naturspråket för Workspace-visualiseringar. Intelligenta bildtexter stöds för följande visualiseringar: Line, Multi-line, Bar, Horizontal bar, Donut, Area, Flow och Fallout. |
| **Researbetsyta** | [Resans arbetsyta](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas?lang=en) är en visualisering i Analysis Workspace som gör att du kan analysera hur människor går igenom eller faller bort från en definierad resa. |
| **Produktanvändning** | [Produktanvändningen](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/tools/product-usage/usage-overview) visar hur din organisation använder Customer Journey Analytics. |
| **Omformningar vid rapporttillfället** | [Med datavyer](/help/data-views/data-views.md) i Customer Journey Analytics kan du tolka data från en anslutning. Du kan ändra eller ta bort data utan att ändra implementeringen. Använd delsträngar för att ändra dimensioner. Skapa mätvärden från valfritt värde eller filtrera underhändelser. Alla dessa omformningar görs på ett icke-förstörande sätt. Adobe Analytics har begränsade möjligheter genom virtuella rapportsviter och anpassad sessionslängd. |
| **Delade mått och mått mellan datavyer** | Med delade mått och mått kan du [använda mått- och måttinställningar för flera datavyer](/help/data-views/shared-metrics-dimensions/smd-overview.md). Ändringar som görs i en delad dimension eller mätvärde gäller för alla instanser av den dimensionen eller mätvärdet i alla tillämpliga datavyer. |
| **SQL-åtkomst** | Med hjälp av alternativet Data Distiller kan Customer Journey Analytics ta bort begränsningarna för data som samlats in på Adobe backend-bearbetning. Du kan ändra dina data med SQL, skapa värden och datauppsättningar som är unika för ditt företag och fortsätta utforska. Analytics stöder inte någon form av SQL-åtkomst till dess data. |
| **Stitching** | [Stitching](/help/stitching/overview.md) är en kraftfull funktion som höjer en händelsedatamängds lämplighet för flerkanalsanalys. Flerkanalsanalys är ett vanligt användningsfall som Customer Journey Analytics kan hantera. Med flerkanalsanalys kan ni kombinera och köra rapporter sömlöst på flera datauppsättningar från olika kanaler, baserat på en gemensam identifierare (person-ID). |
| **Mallar i Adobe Journey Optimizer** | Anpassa det nya rapporteringsgränssnittet i Adobe Journey Optimizer genom att skapa eller redigera en [mall](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/templates/create-templates?lang=en) i Customer Journey Analytics och sedan spara mallen som ska användas på rapportsidan i Journey Optimizer. |
| **Obegränsade kunddimensioner och mätvärden** | Customer Journey Analytics-måtten är obegränsade. Värden kan vara numeriska, text, objekt, listor eller blandningar av alla. Dimensioner kan vara kapslade eller hierarkiska. <br/>Adobe Analytics stöder däremot upp till högst 75 props och 250 eVars. |
| **Obegränsade unika värden** | Customer Journey Analytics har stöd för ett obegränsat antal unika värden eller dimensionsobjekt som kan rapporteras i en enda dimension.<p>Det finns inga kardinalitetsbegränsningar för [för en dimension](/help/components/dimensions/high-cardinality.md), vilket gör att unika värden kan visas och räknas.</p><p>Den här metoden tar bort rapporterings- och analysbegränsningar som kan finnas med storskaliga Adobe Analytics-implementeringar, vilket resulterar i [!UICONTROL Low Traffic]-etiketter.</p><p>I Customer Journey Analytics går det att se en [!UICONTROL Uniques Exceeded]-etikett, men de här etiketterna förekommer mycket mindre ofta och kan minskas genom att ett segment används i data.</p> |

## Funktioner/komponenter i Adobe Analytics som stöds fullt ut {#full-support}

| Adobe Analytics Feature | Kommentarer till Customer Journey Analytics support |
| --- | --- |
| **Analysidentifiering** | Fullt stöd |
| **Resursöverföring** | Fullt stöd |
| **Attribueringsfunktioner** | Fullt stöd |
| **Punktavkänning** | [Fullt stöd](https://experienceleague.adobe.com/sv/docs/experience-platform/datastreams/bot-detection) |
| **Beräknade värden** | Fullt stöd. Befintliga beräknade mätvärden i det traditionella Analysis Workspace-programmet importeras inte till Customer Journey Analytics. |
| **Kalenderhändelser** | Fullt stöd. Kalenderhändelser har implementerats som [Anteckningar](/help/components/annotations/overview.md) i Workspace. |
| **CSV-hämtning** | Fullt stöd |
| **Anpassade kalendrar** | Fullt stöd |
| **Datumjämförelser** | Fullt stöd |
| **Datumintervall** | Alla funktioner för datumintervall stöds. |
| **Dimensioner** | Fullt stöd. Customer Journey Analytics använder XDM och har stöd för obegränsade dimensioner. Customer Journey Analytics är inte knutet till de anpassade eVars- eller proffsfunktionerna i traditionella Adobe Analytics. |
| **GDPR-borttagning** | Fullt stöd. Observera att GDPR nu hanteras i samordning med [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics ärver alla dataändringar som [!UICONTROL Experience Platform] gör i underliggande datauppsättningar. |
| **Lyft-och-förtroende-rapportering** | Fullt stöd via [Experimenteringspanelen](/help/analysis-workspace/c-panels/experimentation.md) |
| **Listvariabler/Listfragment** | Fullt stöd. Customer Journey Analytics använder XDM och stöder obegränsat antal strängarrayer som kan användas på liknande sätt som listVars. |
| **Merchandising eVars** | Fullt stöd genom [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Mätvärden** | Fullt stöd: Customer Journey Analytics använder Experience Data Model (XDM) och har stöd för obegränsade mätvärden och är inte knutet till Adobe Analytics anpassade framgångshändelser. Vissa standardmått har bytt namn från Adobe Analytics: Besökare = Folk, Besök = Sessioner, Hits = Händelser. |
| **Migrerar projekt, segment och beräknade värden från Adobe Analytics till Customer Journey Analytics** | Fullt stöd. |
| **Mobil styrkort/instrumentpaneler** | Fullt stöd |
| **Paneler** | Fullt stöd för följande paneler: Tom panel, Attribution, Freeform, Quick insights och Next eller previous item. |
| **PDF-export** | Fullt stöd |
| **Projektstrukturering** | Fullt stöd |
| **Projektlänkning** | Fullt stöd |
| **Produktmallar** | Innehåller [fördefinierade mallar](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/templates/use-templates) och [företagsmallar](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/templates/create-templates#access-a-company-template). |
| **Bearbetning av rapporttid** | Fullt stöd; Customer Journey Analytics förlitar sig enbart på bearbetning av rapporttid. |
| **API-åtkomst för rapportering** | Fullt stöd; tillgängligt via [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/). |
| **Schemalagda rapporter/projekt** | Fullt stöd |
| **Segment** | Fullt stöd. Segment kallas tidigare *Filter* i Customer Journey Analytics. |
| **Direktuppspelad mediasamling** | Direktuppspelande mediedata är tillgängliga med Analytics-källkopplingen som en del av panelen Media Concurrent Viewer och panelen Media Playback Time Spent (Tid för uppspelning i Workspace). |
| **Datakällor på sammanfattningsnivå** | Fullt stöd |
| **Virtuella rapportsviter** | Fullt stöd. [Datavyer](/help/data-views/create-dataview.md) är Customer Journey Analytics motsvarighet till rapportsviter i Adobe Analytics. |
| **Komponentstrukturering för virtuell rapportserie** | Fullt stöd. Komponenturval är en del av datavyfunktionaliteten. |
| **Enhet, webbläsare, referens, teknikdimensioner** | Stöds för både [Analytics-källanslutningar](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/connectors/adobe-applications/analytics)-baserade datauppsättningar och för datauppsättningar som genererats av WebSDK. Mer information finns i [dokumentationen om vilka Analytics-variabler som stöds via ADC](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Om du använder datainsamling från Experience Platform Web SDK stöds för närvarande inte enheter och dimensioner baserade på enhetssökning. Framtida stöd planeras. Mer information om hur du lägger till enhets- och webbläsarsökningar i SDK-dataströmmen finns i [den här dokumentationen](https://experienceleague.adobe.com/sv/docs/experience-platform/datastreams/configure) |

## Stöds på ett nytt sätt {#new-support}

| Funktion | Anteckningar |
| --- | --- |
| **Advertising Cloud** | Du kan [samla in historiska data för AMO ID:n och EF ID:n för användning i Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/advertising/integrations/analytics/planning/rvars-to-evars). |
| **Larm** | Processen med att [använda aviseringar i Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) är nästan identisk med att använda aviseringar i Adobe Analytics. <p>På grund av tidsangivelserna för datainsamlingen i Customer Journey Analytics är dock inga varningar tillgängliga per timme. I Customer Journey Analytics kan varningar konfigureras för varje dag, vecka eller månad.</p> |
| **Analyser för mål (A4T)** | Integrationen [mellan Adobe Customer Journey Analytics och Target](https://experienceleague.adobe.com/sv/docs/target/using/integrate/cja/target-reporting-in-cja) ger kraftfulla analyser och tidsbesparande verktyg för optimeringsprogrammet. |
| **Målgruppspublicering** | Stöds om det finns licens för Adobe Customer Data Platform eller Journey Optimizer-produkter. [Audience Publishing](/help/components/audiences/audiences-overview.md) skickar målgrupper till kundprofilen i realtid i Experience Platform. |
| **Klassificeringar** | Uppslagsdatauppsättningar motsvarar klassificeringar i Adobe Analytics. Klassifikationer som används i Analytics kan importeras till Experience Platform och Customer Journey Analytics med Analytics Classifications Source Connector. Uppslagsdatauppsättningar kan också överföras direkt till Experience Platform och göras tillgängliga i Customer Journey Analytics. |
| **Skapare av klassificeringsregel** | Stöds med [delsträngar](/help/data-views/component-settings/substring.md) i Customer Journey Analytics. Använder strängändringar vid rapporttidpunkten i stället för att söka efter datauppsättningar. |
| **Anpassad sessionslängd** | Sessionslängd kan konfigureras med [sessionsinställningar](../../data-views/create-dataview.md#session-settings) i en datavy. Mer information finns i [Sessionsinställningar](../../data-views/session-settings.md). <br/>Hantering av mobila bakgrundshändelser stöds via Adobe Experience Platform Mobile SDK. Mer information finns i [Livscykel för Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/). |
| **Valutakonvertering** | Stöds som en del av [formateringen av en måttkomponent](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/component-settings/format) i en datavy. |
| **Kundattribut** | Profildatauppsättningar motsvarar kundattribuering. Profildatauppsättningar importeras inte automatiskt från Experience Cloud, men måste överföras till Experience Platform innan de är tillgängliga i Customer Journey Analytics. |
| **Dataflöden** | Första generationens dataexport är tillgänglig via [Experience Platform Data Access API](https://experienceleague.adobe.com/sv/docs/experience-platform/data-access/api) och via [Experience Platform Destinations](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/export-datasets). Dessa alternativ ger händelse-/radnivåexport av alla data som samlats in eller importerats till Experience Platform Data Lake. Postprocessdatakolumner är inte tillgängliga eftersom postkolumner beräknas vid frågetiden. Det går att exportera postkolumner genom rapportering. |
| **Data Warehouse-rapportering** | [Customer Journey Analytics Fullständig tabellexport](/help/analysis-workspace/export/export-cloud.md) är utvecklingen av Data Warehouse-rapporter i Adobe Analytics, med många nya, ofta efterfrågade funktioner som inte är tillgängliga i Data Warehouse idag. |
| **Poster, avslutningar och använd tid för mått och mått** | Stöds (Poster och avslutningar kallas nu för Sessionsstart och Sessionsslut) och beräknas på ett något annorlunda sätt. |
| **eVar-beständighetsinställningar** | Varorna ingår inte längre i Customer Journey Analytics. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. De dimensioner som anges i datavyer är begränsade till högst 90 dagars beständighet och stöder inte obegränsad beständighet. |
| **Geografiska segmenteringsdimensioner** | [Fullt stöd](https://experienceleague.adobe.com/sv/docs/experience-platform/datastreams/configure) |
| **Diagrambaserad utjämning** | Genom [Diagrambaserad Stitching](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/stitching/overview#graph-based-stitching) kan du utnyttja kraften i identitetsdiagrammet i [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/sv/docs/experience-platform/identity/home) för att höja datauppsättningarna till den önskade identiteten. |
| **Larm** | Processen att använda [varningar](/help/components/c-intelligent-alerts/intelligent-alerts.md) i Customer Journey Analytics är nästan identisk med att använda varningar i Adobe Analytics. Det finns dock [viktiga skillnader](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-components/alerts/alerts-feature-comparison). |
| **IP-förfalskning** | För Customer Journey Analytics-kunder som använder Analytics-källkopplingen för att fylla i data från Adobe Analytics till Customer Journey Analytics: IP-begränsningsinställningar som tillämpas i Adobe Analytics flödar igenom till dina Customer Journey Analytics-data. Du kan kontrollera de här inställningarna i Adobe Analytics efter behov.<p>För Customer Journey Analytics-kunder som använder Experience Platform Web SDK att lägga in data direkt i Platform och Customer Journey Analytics. Du kan använda Data Prep för datainsamling i Platform för att konfigurera regler som döljer IP-adressen baserat på ditt företags krav. |
| **Marknadskanaler** | När du använder Analytics-källkopplingen flödar Marketing Channels-data till Customer Journey Analytics via den kopplingen. Reglerna för marknadsföringskanaler har konfigurerats i traditionella Adobe Analytics och vissa regler stöds inte. Mer information finns i [Customer Journey Analytics Marketing Channel](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels). <br/>För WebSDK-implementeringar stöds regler för kanalbearbetning i rapporttid via [Härledda fält](../../data-views/derived-fields/derived-fields.md). |
| **Merchandising-variabelbeständighet** | Fullt stöd genom [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Måttborttagning av dubbletter** | Konfigurerad på mätvärden i datavyer. Metrisk borttagning av dubbletter sker på person- eller sessionsnivå i stället för på data-, data- eller anslutningsnivå. |
| **Ny eller upprepad sessionsrapportering** | Tidigare genomförd med dimensionen Besök nummer. Nya eller upprepade sessioner stöds [ med ett 13-månaders uppslagsfönster](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases). |
| **Bearbetningsregler, VISTA-regler, regler för bearbetning av marknadsföringskanaler** | Stöds med Adobe Experience Platform Data Prep-funktioner och [härledda fält](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/derived-fields) för både WebSDK-baserade datauppsättningar och data från Analytics-källkopplingen. |
| **Produktvariabel** | Inom Experience Platform kan användare använda en array med objekt i ett dataset-schema för att tillgodose detta användningsfall. Inom Customer Journey Analytics kan kunderna använda valfritt antal produktvariabler och är inte begränsade till en enda variabel som i Adobe Analytics. |
| **Projektdelning** | Projektdelning stöds endast mellan användare av Customer Journey Analytics - det finns ingen projektdelning mellan Customer Journey Analytics och det traditionella Analysis Workspace. |
| **Realtidsrapportering** | Realtidsrapportering i Customer Journey Analytics visar och uppdaterar data och visualiseringar inom en eller flera paneler i Analysis Workspace i realtid. |
| **Report Builder** | Stöds med en ny Office 365-plugin för Microsoft Excel. |
| **Användarbehörigheter/Dataåtkomstkontroller** | Customer Journey Analytics skiljer mellan [Adobe Admin Console](https://experienceleague.adobe.com/sv/docs/core-services/interface/administration/admin-tool-experience-cloud)-produktadministratörer, produktprofiladministratörer och användare. Endast produktadministratörer kan skapa, uppdatera och ta bort anslutningar, projekt, segment eller beräknade värden som andra användare har skapat. Produktadministratörer och produktprofiladministratörer kan redigera datavyer. Ytterligare användarbehörigheter är tillgängliga för exempelvis att skapa beräknade värden, segment eller anteckningar. |
| **Visualiseringar** | Alla Workspace-visualiseringar stöds. |
| **Sammanfogning mellan enheter och kanaler** | Stöds för händelsedatamängder som innehåller identitetsinformation. Se [Stitching](../../stitching/overview.md). |

## Delvis stöd {#partial}

| Funktion | Anteckningar |
| --- | --- |
| **Workspace-paneler** | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. Segmentjämförelse och analys för målpaneler (A4T) stöds inte. |

## Inget stöd, men planerat {#planned}

| Funktion | Anteckningar |
| --- | --- |
| **Datakällor för transaktions-ID** | Support planeras. |

## Inget stöd, ännu inte planerat {#not-planned}

| Funktion | Anteckningar |
| --- | --- |
| **Activity Map** | Support är ännu inte planerad. |
| **Bidragsanalys** | Support är ännu inte planerad. |

## Stöds aldrig {#never}

* Personmätvärden med Coop för olika enheter
* Utlösare
