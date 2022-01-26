---
title: Customer Journey Analytics feature support
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
source-git-commit: 279778d30241e338bff97bd2b0514f3a47614bb9
workflow-type: tm+mt
source-wordcount: '1301'
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
| Sammanfogning mellan olika enheter och kanaler | Fullt stöd; Se [Flerkanalsanalys](/help/connections/cca/overview.md). |
| CSV-nedladdning | Fullt stöd |
| Anpassade kalendrar | Fullt stöd |
| Datumjämförelser | Fullt stöd |
| Datumintervall | Alla funktioner för datumintervall stöds. |
| Besparingstid för dagsljus | Fullt stöd |
| Mått | Fullt stöd; CJA utnyttjar XDM och har stöd för obegränsade dimensioner. CJA is not tied to the custom eVars or props of traditional Adobe Analytics. |
| Färdiga Analysis Workspace-dimensioner (t.ex. webbläsartyp, referenstyp, operativsystem etc.) | CJA tillhandahåller dessa dimensioner internt så länge som bas-XDM-fälten (till exempel användaragent eller enhets-ID) fylls i. For customers using the Analytics Data Connector (ADC), some of these dimensions are available, but not all. Se våra [dokumentation om vilka analysvariabler som stöds via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Borttagning av GDPR | Fullt stöd; Observera att GDPR nu hanteras i samordning med [!UICONTROL Adobe Experience Platform]. CJA inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |
| Lista variabler/listutkast | Fullt stöd; CJA utnyttjar XDM och stöder obegränsat antal strängarrayer som kan användas på liknande sätt som listVars. |
| Varaktighet för marknadsföringsvariabel | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=en#binding-dimension) (januari 2022) |
| Marknadsförande eVars | Full Support via [binding dimensions and binding metrics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=en#binding-dimension) (January 2022) |
| Mätvärden | Full Support; CJA leverages the Experience Data Model (XDM) and supports unlimited metrics and is not tied to the custom success events of traditional Analytics. Note that some standard metrics have been renamed from traditional Analytics: Visitors = People, Visits = Sessions, Hits = Events. |
| Metrisk deduplicering | Full Support |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. |
| PDF Export | Fullt stöd |
| Projekturval | Full Support |
| Projektlänkning | Fullt stöd |
| Report Builder (Excel-plugin) | Fullt stöd |
| Bearbetning av rapporttid | Full Support; CJA relies exclusively on Report Time Processing. |
| API-åtkomst för rapportering | Fullt stöd; Tillgängligt via [CJA API](https://www.adobe.io/cja-apis/docs/). |
| Schemalagda rapporter/projekt | Fullt stöd |
| Segment | Fullt stöd; Nu kallat &quot;Filter&quot; - lägg märke till att befintliga segment i traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Användarbehörigheter/dataåtkomstkontroller | Fullt stöd; CJA skiljer mellan [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=en) produktadministratörer och användare. Endast produktadministratörer kan <ul><li>Skapa/uppdatera/ta bort anslutningar eller datavyer</li><li>Uppdatera/ta bort projekt, filter eller beräkningstal som skapats av andra användare, och</li><li>Dela ett Workspace-projekt med alla användare.</li></ul> |
| Virtual Report Suites | Fullt stöd; Har anropats [Datavyer](/help/data-views/create-dataview.md). |
| VRS-komponenturval | Fullt stöd; Nu en del av datavyer. |

## Stöds med caveats

| Funktion | Anteckningar |
| --- | --- |
| A4T | Stöd ges via fälten i [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en). |
| Klassificeringar | Kallas nu&quot;Sök efter datauppsättningar&quot;. Klassifikationer som används i Analytics kan importeras till Experience Platform och CJA med Data Connector för Analytics-klassificeringar. Uppslagsdatauppsättningar kan också överföras direkt till AEP och göras tillgängliga i CJA. |
| Skräddarsydd professionalisering | Stöd för alla anpassade sessioneringsfunktioner förutom mobilbakgrundstötar. |
| Kundattribut | De kallas nu&quot;profildatauppsättningar&quot; och importeras inte automatiskt från Experience Cloud, utan måste överföras till AEP innan de blir tillgängliga i CJA. |
| Enhet, webbläsare, teknikdimensioner | These dimensions are automatically included when an AEP dataset includes specific XDM schema fields and conforms to the XDM Experience Event class. |
| Poster, avslutningar och använd tid för mått och mätvärden | Stöds (Poster och avslutningar kallas nu för Sessionsstart och Sessionsslut) och beräknas på ett något annorlunda sätt. |
| Inställningar för beständighet av eVar | Varor ingår inte längre i CJA. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Dimensions set within Data Views are limited to a 90 day max persistence and do not support unlimited persistence. |
| GeoSegmenteringsdimensioner | All GeoSegmentation/geography collected into Adobe Analytics flows into CJA through the Analytics Data Connector. Implementeringar som inte använder Analytics Data Connector, t.ex. de som använder AEP Web SDK för digital datainsamling, kommer inte att ha det totala antalet geografiska sökningar som utförs automatiskt (land och stat stöds, stad och postnummer stöds inte). |
| Marknadsföringskanaler | Marknadsföringskanalernas data flödar till CJA via Analytics Data Connector. Reglerna för marknadsföringskanaler måste fortfarande konfigureras i traditionella Adobe Analytics. Vissa regler stöds inte. Mer information finns på [Dokumentation för CJA Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases). |
| Produktvariabel | I Experience Platform kan användare använda en array med objekttypsfält i ett dataset-schema för att tillgodose detta användningsfall. Inom CJA kan kunderna använda valfritt antal produktvariabler och begränsas inte till en enda variabel som i Adobe Analytics. |
| Projektdelning | Project sharing is only supported between users of CJA - there is not project sharing between CJA and the traditional Analysis Workspace. |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |

## Delvis stöd

| Funktion | Anteckningar |
| --- | --- |
| Punktfiltrering | För Analytics Source Connector-baserade datauppsättningar tillämpas robotfiltrering. Allmän startfiltreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller CJA. |
| Medieanalys | Mediedata är tillgängliga som en del av Analytics Data Connector. |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. The Segment Comparison, Analytics for Target (A4T), and Media Concurrent Viewers panels are not supported. |
| Bearbetningsregler | For Analytics Data Connector-based datasets, processing rules are still applied. [Prestandafunktioner för data i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) kan också användas som ersättning för bearbetningsregler för data som går direkt till plattformen. |

## Not currently supported, but planned

| Funktion | Anteckningar |
| --- | --- |
| Larm | Support planeras. |
| Bidragsanalys | Support planeras. |
| data warehouse-rapportering (100 % radexport) | Support planeras från Analysis Workspace gränssnitt. Adobe Experience Platform [[!UICONTROL Query Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en) har också ett gränssnitt för de här användningsfallen i CJA. |
| ID Stitching via Device Graph | Support planeras. |
| Real-Time Reporting | Support is planned. |
| Segment IQ | Support planeras. |
| Segmentpublicering (skickar segment från Workspace till Experience Cloud) | Support planeras. Kallas &quot;Audience Publishing&quot; i CJA. |
| Ny eller upprepad sessionsrapportering | Support planeras med några kavaetter. |
| Lyft- och tillförlitlighetsrapportering | Support planeras. |
| Classification Rule Builder | Fungerar något annorlunda i CJA med hjälp av direktredigerade strängar vid rapporttillfället i stället för att söka efter datauppsättningar. |
| Bearbetningsregler, VISTA-regler, Bearbetningsregler för marknadsföringskanaler | Stöd planeras, men kommer att fungera vid frågesändning i stället för under datainsamlingen för mer flexibla och retroaktiva och icke-förstörande dataändringar. |
| Projektmallar | Support planeras. |

## Stöd ännu inte planerat

| Funktion | Anteckningar |
| --- | --- |
| Activity Map | Support är ännu inte planerat. |
| Advertising Cloud | Support är ännu inte planerat. |
| Klassificeringsregelverktyget | Support är ännu inte planerat. |
| Datafeeds | Support är ännu inte planerat. |
| Sammanfattningsdatakällor | Support är ännu inte planerat. |
| Datakällor för transaktions-ID | Support är ännu inte planerat. |
| Valutakonvertering | Support är ännu inte planerat. |
| Realtidsrapporter | Support is not yet planned. |

## Stöds aldrig

* People metric using Cross-Device Coop
* Reports &amp; Analytics Dashboards
* Bokmärken för rapporter och analyser
* Reports &amp; Analytics Targets
* Rapporter och analyskalenderhändelser
* Mobile Services
