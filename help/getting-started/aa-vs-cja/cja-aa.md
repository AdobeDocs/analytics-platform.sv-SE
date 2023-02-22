---
title: Funktioner i Customer Journey Analytics
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c87d7428a2ddca35297225314e97171fe8b129fb
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 3%

---

# Funktioner i Customer Journey Analytics

I följande tabell visas vilka funktioner i Adobe Analytics som stöds, stöds delvis eller inte alls i Customer Journey Analytics (CJA). De här listorna ändras över tid när funktioner läggs till i CJA.

## Funktioner/komponenter som stöds fullt ut

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

{style=&quot;table-layout:auto&quot;}

## Stöds på ett nytt sätt

| Funktion | Anteckningar |
| --- | --- |
| Audience Publishing (segmentpublicering) | Stöds om licensen har erhållits med Adobe Customer Data Platform eller Journey Optimizer-produkter. [Audience Publishing](/help/components/audiences/audiences-overview.md) skickar målgrupper till kundprofil i realtid i Experience Platform. |
| Klassificeringar | Kallas nu&quot;Sök efter datauppsättningar&quot;. Klassifikationer som används i Analytics kan importeras till Experience Platform och CJA med hjälp av källkopplingen för analysklassificeringar. Uppslagsdatauppsättningar kan också överföras direkt till AEP och göras tillgängliga i CJA. |
| Classification Rule Builder | Stöds med [delsträngar](/help/data-views/component-settings/substring.md) i CJA. Använder strängändringar vid rapporttidpunkten i stället för att söka efter datauppsättningar. |
| Skräddarsydd professionalisering | Stöd för alla anpassade sessioneringsfunktioner, förutom mobilbakgrundstötar. |
| Varaktighet för marknadsföringsvariabel | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Kundattribut | De kallas nu&quot;profildatauppsättningar&quot; och importeras inte automatiskt från Experience Cloud, utan måste överföras till AEP innan de blir tillgängliga i CJA. |
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

{style=&quot;table-layout:auto&quot;}

## Delvis stöd

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

{style=&quot;table-layout:auto&quot;}

## Stöds inte just nu, men är planerad

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
| Datafeeds | Stöd planeras via AEP-destinationer. |
| Datakällor för transaktions-ID | Support planeras. |
| Migrera projekt/filter/beräknade värden från AA till CJA | Support planeras. |
| Datakällor på sammanfattningsnivå | Support planeras. |

{style=&quot;table-layout:auto&quot;}

## Stöd ännu inte planerat

| Funktion | Anteckningar |
| --- | --- |
| Activity Map | Support är ännu inte planerat. |
| Advertising Cloud | Support är ännu inte planerat. |

{style=&quot;table-layout:auto&quot;}

## Stöds aldrig

* Personmätvärden med Coop för olika enheter
* Rapporter och analyser på kontrollpaneler
* Bokmärken för rapporter och analyser
* Rapporter och analysmål
* Mobiltjänster
