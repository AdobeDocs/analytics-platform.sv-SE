---
title: Funktioner i Customer Journey Analytics
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 8e6f16acc475fb89c9b9ba50ccef174d3c7b10ea
workflow-type: tm+mt
source-wordcount: '2189'
ht-degree: 1%

---

# Funktioner i Customer Journey Analytics

I följande tabell visas vilka funktioner i Adobe Analytics som stöds, stöds delvis eller inte alls i Customer Journey Analytics och vilka funktioner i Customer Journey Analytics som inte stöds eller är tillgängliga i Adobe Analytics. De här listorna ändras med tiden när funktioner läggs till i Customer Journey Analytics.

## Funktioner/komponenter som stöds fullt ut {#full-support}

| Adobe Analytics Feature | Anmärkningar om stöd |
| --- | --- |
| Analysidentifiering | Fullt stöd |
| Attribution IQ | Fullt stöd |
| Punktavkänning | [Fullt stöd](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) |
| Beräknade mått | Fullt stöd. Befintliga beräknade mätvärden i traditionella Analysis Workspace porteras inte till Customer Journey Analytics. |
| Kalenderhändelser | Fullt stöd. Kalenderhändelser har implementerats som [Anteckningar](/help/components/annotations/overview.md) i Workspace. |
| CSV-nedladdning | Fullt stöd |
| Anpassade kalendrar | Fullt stöd |
| Datumjämförelser | Fullt stöd |
| Datumintervall | Alla funktioner för datumintervall stöds. |
| Mått | Fullt stöd. Customer Journey Analytics använder XDM och stöder obegränsade dimensioner. Customer Journey Analytics är inte knutet till de egna eVars- eller proffsfunktionerna i traditionella Adobe Analytics. |
| Borttagning av GDPR | Fullt stöd; notera att GDPR nu hanteras i samordning med [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics ärver alla dataändringar [!UICONTROL Experience Platform] till underliggande datamängder. |
| Lyft- och förtroenderapportering | Fullt stöd via [Panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md) |
| List variables/List props | Fullt stöd. Customer Journey Analytics använder XDM och stöder obegränsat antal strängarrayer som kan användas på liknande sätt som listVars. |
| Marknadsförande eVars | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Mätvärden | Fullt stöd; Customer Journey Analytics använder Experience Data Model (XDM) och har stöd för obegränsade mätvärden och är inte knutet till Adobe Analytics anpassade framgångshändelser. Vissa standardmått har bytt namn från Adobe Analytics: Besökare = Folk, Besök = Sessioner, Hits = Händelser. |
| Migrera projekt, filter och beräknade värden från Adobe Analytics till Customer Journey Analytics | Fullt stöd. |
| Mobil styrkort/instrumentpaneler | Fullt stöd |
| Panel | Fullt stöd för följande paneler: Tom panel, Attribution, Freeform, Quick insights och Next eller previous item. |
| Export från PDF | Fullt stöd |
| Projekturval | Fullt stöd |
| Projektlänkning | Fullt stöd |
| Bearbetning av rapporttid | Fullt stöd; Customer Journey Analytics förlitar sig enbart på bearbetning av rapporttid. |
| API-åtkomst för rapportering | Fullt stöd, tillgängligt via [CUSTOMER JOURNEY ANALYTICS API](https://developer.adobe.com/cja-apis/docs/). |
| Schemalagda rapporter/projekt | Fullt stöd |
| Segment | Fullt stöd. Nu kallat &quot;Filter&quot; - observera att inga befintliga segment i Analysis Workspace importeras till Customer Journey Analytics. |
| Virtuella rapportsviter | Fullt stöd. Har anropats [Datavyer](/help/data-views/create-dataview.md). |
| Komponentstrukturering för virtuell rapportserie | Fullt stöd. Nu en del av datavyer. |
| Enhet, webbläsare, referens, teknikdimensioner | Stöds för båda [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-baserade datauppsättningar och datauppsättningar som genererats av WebSDK. Se [dokumentation om vilka analysvariabler som stöds via ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html).Om du använder Experience Platform Web SDK-datainsamling stöds för närvarande inte enheter och dimensioner baserade på enhetssökning. Framtida stöd planeras. Information om hur du lägger till enhets- och webbläsarsökningar i Web SDK-dataströmmen finns i [den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html) |
| Streaming Media Analytics | Mediedata är tillgängliga med Analytics-källkopplingen som en del av panelen Medievisningsprogram och panelen Medieuppspelningstid för spenderad tid i Workspace. |

{style="table-layout:auto"}

## Stöds på ett nytt sätt {#new-support}

| Funktion | Anteckningar |
| --- | --- |
| Analyser för mål (A4T) | The [integrering mellan Adobe Customer Journey Analytics och Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja) innehåller kraftfulla analys- och tidsbesparande verktyg för optimeringsprogrammet. |
| Målgruppspublicering | Stöds om licensen har erhållits med Adobe Customer Data Platform eller Journey Optimizer-produkter. [Audience Publishing](/help/components/audiences/audiences-overview.md) skickar målgrupper till kundprofil i realtid i Experience Platform. |
| Klassificeringar | Kallas nu&quot;Sök efter datauppsättningar&quot;. Klassifikationer som används i Analytics kan importeras till Experience Platform och Customer Journey Analytics med hjälp av källkopplingen för analysklassificeringar. Uppslagsdatauppsättningar kan också överföras direkt till Experience Platform och göras tillgängliga i Customer Journey Analytics. |
| Skapa klassificeringsregel | Stöds med [delsträngar](/help/data-views/component-settings/substring.md) i Customer Journey Analytics. Använder strängändringar vid rapporttidpunkten i stället för att söka efter datauppsättningar. |
| Anpassad sessionslängd | Sessionslängden kan konfigureras via [Sessionsinställningar](../../data-views/create-dataview.md#session-settings) i en datavy. Se  [Sessionsinställningar](../../data-views/session-settings.md) för mer information. <br/>Hantering av mobila bakgrundshändelser stöds via Adobe Experience Platform Mobile SDK. Se [Livscykel för Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) för mer information. |
| Valutakonvertering | Stöds som en del av [formatera en måttkomponent](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html#currency) i en datavy. |
| Varaktighet för marknadsföringsvariabel | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Kundattribut | Profildatauppsättningar importeras inte automatiskt från Experience Cloud, utan måste överföras till Experience Platform innan de kan användas i Customer Journey Analytics. |
| Dataflöden | Första generationens dataexport av datauppsättningar är tillgänglig via [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html) och via [Experience Platform Destinationer](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html). Dessa alternativ ger händelse-/radnivåexport av alla data som samlats in eller importerats till Experience Platform Data Lake. Postprocessdatakolumner är inte tillgängliga eftersom postkolumner beräknas vid frågetiden. Det går att exportera postkolumner genom rapportering. |
| Data Warehouse | [Customer Journey Analytics Full Table Export](/help/analysis-workspace/export/export-cloud.md) är utvecklingen av rapporter om Data Warehouse i Adobe Analytics, med många nya, ofta efterfrågade funktioner som inte är tillgängliga i Data Warehouse idag. |
| Poster, avslutningar och använd tid för mått och mätvärden | Stöds (Poster och avslutningar kallas nu för Sessionsstart och Sessionsslut) och beräknas på ett något annorlunda sätt. |
| Beständiga inställningar för eVar | Varor är inte längre en del av Customer Journey Analytics. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Dimensioner som anges i datavyer är begränsade till högst 90 dagars beständighet och stöder inte obegränsad beständighet. |
| Geosegmenteringsdimensioner | [Fullt stöd](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html) |
| IP-förvrängning | För Customer Journey Analytics-kunder som använder Analytics-källkopplingen för att fylla i data från Adobe Analytics till Customer Journey Analytics: IP-begränsningsinställningar som används i Adobe Analytics flödar igenom till Customer Journey Analytics-data. Du kan kontrollera de här inställningarna i Adobe Analytics efter behov.<p>För Customer Journey Analytics-kunder som använder Experience Platform Web SDK fylls data i direkt i Platform och Customer Journey Analytics. Du kan använda Data Prep för datainsamling i Platform för att konfigurera regler som döljer IP-adressen baserat på ditt företags krav. |
| Marknadsföringskanaler | När du använder Analytics-källkopplingen flödar Marketing Channels-data in i Customer Journey Analytics via den kopplingen. Reglerna för marknadsföringskanaler har konfigurerats i traditionella Adobe Analytics och vissa regler stöds inte. Se [Customer Journey Analytics Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html) för mer information. <br/>För WebSDK-implementeringar stöds regler för kanalbearbetning i rapporttid via [Härledda fält](../../data-views/derived-fields/derived-fields.md). |
| Metrisk deduplicering | Nu konfigurerat för mätvärden i datavyer. Metrisk borttagning av dubbletter sker på person- eller sessionsnivå i stället för på data-, data- eller anslutningsnivå. |
| Ny eller upprepad sessionsrapportering | Tidigare genomförd med dimensionen Besök nummer. Det finns stöd för både nya och upprepade sessioner [med ett 13-månaders uppslagsfönster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html). |
| Bearbetningsregler, VISTA-regler, regler för bearbetning av marknadsföringskanaler | Stöds både med Adobe Experience Platform Data Prep-funktioner och [härledda fält](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html) för både WebSDK-baserade datauppsättningar och data från Analytics-källkopplingen. |
| Variabeln Produkter | Inom Experience Platform kan användare använda en array med objekt i ett dataset-schema för att tillgodose detta användningsfall. Inom Customer Journey Analytics kan man använda valfritt antal produktvariabler och de är inte begränsade till en enda variabel som i Adobe Analytics. |
| Projektdelning | Projektdelning stöds endast mellan användare av Customer Journey Analytics - det finns ingen projektdelning mellan Customer Journey Analytics och Analysis Workspace. |
| Report Builder | Stöds med en ny Office 365-plugin för Excel. |
| Användarbehörigheter/Dataåtkomstkontroller | Customer Journey Analytics skiljer mellan [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) produktadministratörer, produktprofiladministratörer och användare. Endast produktadministratörer kan skapa/uppdatera/ta bort anslutningar, projekt, filter eller beräknade värden som skapats av andra användare, medan produktadministratörer och produktprofiladministratörer kan redigera datavyer. Ytterligare användarbehörigheter är tillgängliga för exempelvis att skapa beräknade värden, filter eller anteckningar. |
| Visualiseringar | Alla arbetsytevisualiseringar stöds förutom för kartvisualisering. |
| Sammanfogning mellan olika enheter och kanaler | Stöds för datauppsättningar som innehåller identitetsinformation direkt (kallas även fältbaserad sammanfogning). Diagrambaserad sammanfogning stöds ännu inte, men är planerad. Se [Stitlar](../../stitching/overview.md). |

{style="table-layout:auto"}

## Delvis stöd {#partial}

| Funktion | Anteckningar |
| --- | --- |
| Panel | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. Segmentjämförelse och analys för målpaneler (A4T) stöds inte. |

{style="table-layout:auto"}

## Inget stöd, men planerat {#planned}

| Funktion | Anteckningar |
| --- | --- |
| Larm | Support planeras. |
| Bidragsanalys | Support planeras. |
| Häftning av ID med enhetsdiagram | Support planeras. |
| Projektmallar | Support planeras. |
| Realtidsrapportering | Support planeras. |
| Segmentanalys | Support planeras. |
| Datakällor för transaktions-ID | Support planeras. |
| Datakällor på sammanfattningsnivå | Support planeras. |

{style="table-layout:auto"}

## Inget stöd, ännu inte planerat {#not-planned}

| Funktion | Anteckningar |
| --- | --- |
| Activity Map | Support är ännu inte planerad. |
| Advertising Cloud | Support är ännu inte planerad. |

{style="table-layout:auto"}

## Stöds aldrig {#never}

* Personmätvärden med Coop för olika enheter

## Adobe Customer Journey Analytics-funktioner som inte finns i Adobe Analytics {#cja-not-aa}

I följande tabell visas funktioner som är tillgängliga i Customer Journey Analytics, men som inte stöds i Adobe Analytics.

| Funktion | Mer information |
| --- | --- |
| Möjlighet att kombinera datauppsättningar (t.ex. Adobe Analytics rapportsviter) | Med Customer Journey Analytics kan ni kombinera data från flera rapportsviter som om de vore ett enda rapportpaket i Adobe Analytics. |
| Inkvartering av alla typer av data | Customer Journey Analytics kombineras med Experience Platform för att kunna lagra alla typer av datarotor och datatyper. Använda [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv), kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. Adobe Analytics fokuserar främst på webb- och mobilanalysdata med vissa funktioner för att [importdata](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| Enhetsövergripande analys | Customer Journey Analytics stöder den sömlösa kombinationen av enhetsspecifika datauppsättningar från oautentiserade och autentiserade sessioner. Customer Journey Analytics erbjuder att fylla i historiska data baklänges till kända enheter. I Analytics är den här funktionen begränsad till en enda rapportserie och användningen av ett enhetsdiagram. |
| Förbättrad Dimension | Customer Journey Analytics ger större flexibilitet vid användning av dimensioner: <ul><li>**Anpassade numeriska dimensioner**: [Skapa egna numeriska mått i en datavy](/help/data-views/create-dataview.md#components).</li><li>**Sortera strängbaserade dimensioner**: [Sortera strängbaserade dimensioner i bokstavsordning i en friformstabell.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>I Adobe Analytics fanns bara en handfull inbyggda numeriska mått tillgängliga, och det gick inte att sortera efter strängbaserade dimensioner.</p> |
| Härledda fält | Härledda fält gör det möjligt att göra omformningar av data vid rapporttillfället. Data kan kombineras, korrigeras eller skapas direkt och gäller retroaktivt för alla rapporter. |
| Förbättrade säkerhets- och sekretessalternativ - beredskap för HIPAA | Customer Journey Analytics är redo för HIPAA och erbjuder ytterligare säkerhetsalternativ för regelefterlevnad. Adobe Analytics är inte HIPAA-klart. |
| Experimentationsanalys | Customer Journey Analytics kan utvärdera lyften och förtroendet för alla experiment från datakällor som definieras som en del av en anslutning. Med den här utvärderingen kan ni förstå orsaks- och effektförhållandet mellan kundinteraktioner i alla kanaler. Analyserna begränsas till experimenterande analyser via A4T. |
| Prognos | Prognos är en AI/ML-funktion som inkluderar en statistisk prognos för tidsserierelaterade data baserade på historiska data som redan finns i Customer Journey Analytics. Prognoser kan visas i frihandstabeller och i linjediagramvisualiseringar. |
| Guidad analys | Guidad analys är ett rapportformat som gör att användarna snabbt kan ta hand om sina databehov så att de snabbt kan få högkvalitativa insikter och fatta mer databaserade beslut. Guidad analys ingår i Adobe Product Analytics, ett tillägg till Customer Journey Analytics. |
| Intelligenta bildtexter | Intelligenta bildtexter använder avancerad maskininlärning och generativ AI för att ge värdefulla insikter på naturspråket för arbetsytevisualiseringar. Den första versionen innehåller automatiskt genererade insikter om [Linje](/help/analysis-workspace/visualizations/line.md) visualisering. |
| Omformningar i rapporttid | Med datavyer i Customer Journey Analytics kan du tolka data från en anslutning ytterligare. Du kan ändra eller ta bort data utan att ändra implementeringen, använda delsträngar för att ändra dimensioner, skapa mätvärden från valfritt värde eller filtrera delmängder. Alla dessa omformningar görs på ett icke-förstörande sätt. Adobe Analytics har begränsade möjligheter genom virtuella rapportsviter och anpassad sessionslängd. |
| BI-tillägg | Med BI Extension kan du ansluta CJA direkt till vanliga BI-visualiseringsverktyg som PowerBI eller Tableau, så att du kan ha dina BI-rapporter som exakt matchar det du ser i Analysis Workspace och andra CJA-rapporteringsgränssnitt. Detta är ett mycket enklare sätt att få BI-rapportering för CJA utan att behöva återskapa rapporter/mätvärden från rådata. |
| SQL-åtkomst | Med hjälp av alternativet Data Distiller kan Customer Journey Analytics ta bort begränsningarna för data som samlats in på Adobe backend-bearbetning. Du kan ändra dina data med SQL, skapa värden och datauppsättningar som är unika för ditt företag och fortsätta utforska. Analytics stöder inte någon form av SQL-åtkomst till dess data. |
| Obegränsade kunddimensioner och mätvärden | Customer Journey Analytics är obegränsade. Värden kan vara numeriska, text, objekt, listor eller blandningar av alla. Dimensioner kan vara kapslade eller hierarkiska. <p>Adobe Analytics stöder däremot upp till högst 75 props och 250 eVars.</p> |
| Obegränsade unika värden | Customer Journey Analytics stöder obegränsat antal unika värden eller dimensionsposter som kan rapporteras inom en dimension.<p>Det finns inga [kardinalitetsbegränsningar för en dimension](/help/components/dimensions/high-cardinality.md), vilket gör att unika värden kan visas och räknas.</p><p>Detta tillvägagångssätt tar bort rapporterings- och analysbegränsningar som kan förekomma med storskaliga Adobe Analytics-implementeringar, vilket resulterar i [!UICONTROL Low Traffic] etiketter.</p><p>I Customer Journey Analytics kan du se [!UICONTROL Uniques Exceeded] -etiketten, men dessa förekommer betydligt mindre ofta och kan minskas genom att ett filter eller segment tillämpas på data.</p> |

{style="table-layout:auto"}
