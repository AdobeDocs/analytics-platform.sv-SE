---
title: Funktioner i Customer Journey Analytics
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 116000f3dd0212896ca96d7e45e4d4cfc5cdd357
workflow-type: tm+mt
source-wordcount: '1995'
ht-degree: 3%

---

# Funktioner i Customer Journey Analytics

I följande tabell visas vilka funktioner i Adobe Analytics (AA) som stöds, stöds delvis eller inte alls i Customer Journey Analytics (CJA) och vilka funktioner i CJA som inte stöds eller är tillgängliga i AA. De här listorna ändras över tid när funktioner läggs till i CJA.

## Funktioner/komponenter som stöds fullt ut {#full-support}

| Adobe Analytics Feature | Anmärkningar om stöd |
| --- | --- |
| Avvikelseidentifiering | Fullt stöd |
| Attribution IQ | Fullt stöd |
| Beräknade mätvärden | Fullt stöd; Observera att befintliga beräknade värden i den traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Kalenderhändelser | Fullt stöd. Kalenderhändelser har implementerats som [Anteckningar](/help/components/annotations/overview.md) i Workspace. |
| CSV-nedladdning | Fullt stöd |
| Anpassade kalendrar | Fullt stöd |
| Datumjämförelser | Fullt stöd |
| Datumintervall | Alla funktioner för datumintervall stöds. |
| Mått | Fullt stöd; CJA utnyttjar XDM och har stöd för obegränsade dimensioner. CJA är inte knutet till de anpassade eVars- eller propparna hos traditionella Adobe Analytics. |
| Borttagning av GDPR | Fullt stöd; Observera att GDPR nu hanteras i samordning med [!UICONTROL Adobe Experience Platform]. CJA ärver alla dataändringar [!UICONTROL Experience Platform] till underliggande datamängder. |
| Lyft- och tillförlitlighetsrapportering | Fullt stöd via [Panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md) |
| Lista variabler/listutkast | Fullt stöd; CJA utnyttjar XDM och stöder obegränsat antal strängarrayer som kan användas på liknande sätt som listVars. |
| Marknadsförande eVars | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Mätvärden | Fullt stöd; CJA utnyttjar Experience Data Model (XDM) och stöder obegränsade mätvärden och är inte knutet till anpassade framgångshändelser i traditionell Analytics. Observera att vissa standardvärden har bytt namn från traditionell analys: Besökare = människor, besök = sessioner, träffar = händelser. |
| Mobile Scorecard/Dashboards | Fullt stöd |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. |
| PDF Export | Fullt stöd |
| Projekturval | Fullt stöd |
| Projektlänkning | Fullt stöd |
| Bearbetning av rapporttid | Fullt stöd; CJA använder sig enbart av Report Time Processing. |
| API-åtkomst för rapportering | Fullt stöd; Tillgängligt via [CJA API](https://www.adobe.io/cja-apis/docs/). |
| Schemalagda rapporter/projekt | Fullt stöd |
| Segment | Fullt stöd; Nu kallat &quot;Filter&quot; - lägg märke till att befintliga segment i traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Virtual Report Suites | Fullt stöd; Har anropats [Datavyer](/help/data-views/create-dataview.md). |
| VRS-komponenturval | Fullt stöd; Nu en del av datavyer. |
| Streaming Media Analytics | Mediedata är tillgängliga med Analytics Data Connector som en del av panelen Media Concurrent Viewer och panelen Medieuppspelningstid i Workspace. |

{style="table-layout:auto"}

## Stöds på ett nytt sätt {#new-support}

| Funktion | Anteckningar |
| --- | --- |
| Audience Publishing (segmentpublicering) | Stöds om licensen har erhållits med Adobe Customer Data Platform eller Journey Optimizer-produkter. [Audience Publishing](/help/components/audiences/audiences-overview.md) skickar målgrupper till kundprofil i realtid i Experience Platform. |
| Klassificeringar | Kallas nu&quot;Sök efter datauppsättningar&quot;. Klassifikationer som används i Analytics kan importeras till Experience Platform och CJA med hjälp av källkopplingen för analysklassificeringar. Uppslagsdatauppsättningar kan också överföras direkt till AEP och göras tillgängliga i CJA. |
| Classification Rule Builder | Stöds med [delsträngar](/help/data-views/component-settings/substring.md) i CJA. Använder strängändringar vid rapporttidpunkten i stället för att söka efter datauppsättningar. |
| Skräddarsydd professionalisering | Stöd för alla anpassade sessioneringsfunktioner, förutom mobilbakgrundstötar. |
| Varaktighet för marknadsföringsvariabel | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Kundattribut | De kallas nu&quot;profildatauppsättningar&quot; och importeras inte automatiskt från Experience Cloud, utan måste överföras till AEP innan de blir tillgängliga i CJA. |
| Datafeeds | Första generationens dataexport är tillgänglig via [API för AEP-dataåtkomst](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) och via [AEP-destinationer](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). Dessa alternativ ger export på träffnivå/radnivå av alla data som samlas in eller hämtas till AEP Data Lake. Postprocessdatakolumner är inte tillgängliga eftersom postkolumner beräknas vid frågetiden. Det går att exportera postkolumner genom rapportering. |
| Metrisk deduplicering | Nu konfigurerat för mätvärden i datavyer. Metrisk borttagning av dubbletter sker på person- eller sessionsnivå i stället för på data-, data- eller anslutningsnivå. |
| Poster, avslutningar och använd tid för mått och mätvärden | Stöds (Poster och avslutningar kallas nu för Sessionsstart och Sessionsslut) och beräknas på ett något annorlunda sätt. |
| Inställningar för beständighet av eVar | Varor ingår inte längre i CJA. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Dimensioner som anges i datavyer är begränsade till högst 90 dagars beständighet och stöder inte obegränsad beständighet. |
| IP-förvanskning | För CJA-kunder som använder Analytics Source Connector för att fylla i data från Adobe Analytics till CJA: De inställningar för IP-förfalskning som används i Adobe Analytics flödar igenom till dina CJA-data. Du kan kontrollera de här inställningarna i Adobe Analytics efter behov.<p>För CJA-kunder som använder Adobe Experience Platform Web SDK för att fylla i data direkt i Platform och CJA: Du kan använda Data Prep för datainsamling i Platform för att konfigurera regler som döljer IP-adressen baserat på företagets krav. |
| Ny eller upprepad sessionsrapportering | Tidigare genomförd med dimensionen Besök nummer. Det finns stöd för både nya och upprepade sessioner [med ett 13-månaders uppslagsfönster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat). |
| Produktvariabel | I Experience Platform kan användare använda en array med objekttypsfält i ett dataset-schema för att tillgodose detta användningsfall. Inom CJA kan kunderna använda valfritt antal produktvariabler och begränsas inte till en enda variabel som i Adobe Analytics. |
| Projektdelning | Projektdelning stöds endast mellan CJA-användare - det finns ingen projektdelning mellan CJA och det traditionella Analysis Workspace. |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |
| Report Builder (Excel-plugin) | Stöds med en ny Office 365-plugin för Excel. |
| Användarbehörigheter/dataåtkomstkontroller | CJA skiljer mellan [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) produktadministratörer, produktprofiladministratörer och användare. Endast produktadministratörer kan skapa/uppdatera/ta bort anslutningar, projekt, filter eller beräknade värden som skapats av andra användare, medan produktadministratörer och produktprofiladministratörer kan redigera datavyer. Ytterligare användarbehörigheter finns för t.ex. att skapa beräknade värden, filter eller anteckningar. |
| Bearbetningsregler, VISTA-regler, Bearbetningsregler för marknadsföringskanaler | Stöds med Adobe Experience Platform Data Prep-funktioner för både WebSDK-baserade datauppsättningar och data från Analytics Data Connector. |

{style="table-layout:auto"}

## Delvis stöd {#partial}

| Funktion | Anteckningar |
| --- | --- |
| Marknadsföringskanaler | Marknadsföringskanalernas data flödar till CJA via Analytics Source Connector. Reglerna för marknadsföringskanal måste fortfarande konfigureras i traditionella Adobe Analytics och vissa regler stöds inte. Mer information finns på [Dokumentation för CJA Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html#cja-usecases). För WebSDK-implementeringar finns dessutom plugin-program för att definiera marknadsföringskanaler på klientsidan. Framtida stöd för regler för bearbetning av marknadsföringskanaler i rapporttid planeras. |
| Sammanfogning mellan olika enheter och kanaler | Stöds för datauppsättningar som innehåller identitetsinformation direkt (kallas även&quot;fältbaserad&quot; sammanfogning). Diagrambaserad sammanfogning stöds ännu inte, men är planerad. Se [Flerkanalsanalys](/help/cca/overview.md). |
| Punktfiltrering | För [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-baserade datauppsättningar, robotfiltrering tillämpas. Allmän startfiltreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller CJA. |
| Enhet, webbläsare, referens, teknikdimensioner | Stöds för [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-baserade datauppsättningar. Se våra [dokumentation om vilka analysvariabler som stöds via ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en).<p>Om du inte använder Adobe Source Connector för att fylla i data från Adobe Analytics till CJA, utan i stället använder du Experience Platform Web SDK-datainsamling, stöds för närvarande inte enheter och dimensioner baserade på enhetssökningen. Framtida stöd planeras. |
| GeoSegmenteringsdimensioner | All GeoSegmentation/geography som samlas in i Adobe Analytics flödar till CJA via [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Implementeringar som inte använder Analytics Source Connector, t.ex. de som använder AEP Web SDK för digital datainsamling, kommer inte att ha det fullständiga urvalet av geografiska sökningar som utförs automatiskt: Land och delstat stöds globalt, vilket inte gäller för stad och postnummer. |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. Segmentjämförelse och analys för målpaneler (A4T) stöds inte. |
| Bearbetningsregler | För Analytics Source Connector-baserade datauppsättningar tillämpas fortfarande bearbetningsregler. [Prestandafunktioner för data i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) kan också användas som ersättning för bearbetningsregler för data som går direkt till plattformen. |
| A4T | Delvis stöd ges via fälten i [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Stöd för A4T-vänliga namn på målaktiviteter och upplevelser planeras. |

{style="table-layout:auto"}

## Stöds inte just nu, men är planerad {#planned}

| Funktion | Anteckningar |
| --- | --- |
| Larm | Support planeras. |
| Bidragsanalys | Support planeras. |
| data warehouse Reporting | Support planeras från Analysis Workspace gränssnitt. Adobe Experience Platform [[!UICONTROL Query Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv) har också ett gränssnitt för de här användningsfallen i CJA. |
| ID Stitching via Device Graph | Support planeras. |
| Projektmallar | Support planeras. |
| Realtidsrapportering | Support planeras. |
| Segment IQ | Support planeras. |
| Valutakonvertering | Support planeras. |
| Datakällor för transaktions-ID | Support planeras. |
| Migrera projekt/filter/beräknade värden från AA till CJA | Support planeras. |
| Datakällor på sammanfattningsnivå | Support planeras. |

{style="table-layout:auto"}

## Stöd ännu inte planerat {#not-planned}

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

## CJA-funktioner som inte finns i Adobe Analytics {#cja-not-aa}

I följande tabell visas funktioner som är tillgängliga i Customer Journey Analytics (CJA), men som inte stöds i Adobe Analytics (AA).

| Funktion | Mer information |
| --- | --- |
| Inkvartering av alla typer av data | CJA kombineras med Experience Platform för att innehålla alla typer av datamappningar och datatyper. Använda [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv), kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. Adobe Analytics fokuserar främst på webb- och mobilanalysdata med vissa funktioner för att [importdata](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| Obegränsat antal Dimensioner | CJA-dimensionerna är obegränsade. värden kan vara numeriska värden, text, objekt, listor eller blandningar av alla. Dimensioner kan vara kapslade eller hierarkiska. Analyserna stöder upp till högst 75 props och 250 eVars. Detta tar bort de aktuella måttbegränsningarna med hjälp av dimensioner och händelser. |
| Obegränsad kardinalitet/unika värden | CJA har stöd för ett obegränsat antal unika värden eller dimensionsposter som kan rapporteras inom en enda dimension. AA är begränsat till 500 kB unika värden. Detta eliminerar de rapporterings- och analysbegränsningar som för närvarande finns med storskalig Analytics-implementering. |
| Rapportera tidsomvandlingar | Rapportera tidsomvandlingar (kallas datavyer) i CJA gör att du kan tolka data ytterligare från en anslutning. Du kan ändra eller ta bort data utan att implementera om dem; Använda delsträngar för att manipulera dimensioner. skapa mätvärden från vilket värde som helst, filtrera underhändelser. Allt detta kan göras på ett icke-förstörande sätt. Adobe Analytics har begränsade funktioner genom virtuella rapportsviter och sessioner. |
| Experimentationsanalys | CJA kan utvärdera lyften och förtroendet för alla experiment från alla datakällor som definieras som en del av en anslutning. På så sätt kan ni förstå orsaks- och effektförhållandet mellan kundinteraktioner över alla kanaler. Analyserna begränsas till experimentell analys genom integreringen med Analytics for Target (A4T). |
| Enhetsövergripande analys | CJA stöder den sömlösa kombinationen av enhetsspecifika datauppsättningar från oautentiserade och autentiserade sessioner. Du kan även fylla i historiska data baklänges till kända enheter. I Analytics är den här funktionen begränsad till en enda rapportserie och användningen av ett enhetsdiagram. |
| SQL Access | Med hjälp av alternativet Data Distiller kan CJA ta bort begränsningarna för data som samlas in på Adobe backend-bearbetningen. Du kan ändra dina data med SQL, skapa nya värden och datauppsättningar som är unika för ditt företag och fortsätta utforska. Analytics stöder inte någon form av SQL-åtkomst till dess data. |
| Förbättrade säkerhets- och sekretessalternativ - beredskap för HIPAA | CJA är redo för HIPAA och erbjuder ytterligare säkerhetsalternativ för regelefterlevnad. Adobe Analytics är inte HIPAA-klart. |

{style="table-layout:auto"}
