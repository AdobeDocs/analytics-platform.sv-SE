---
title: Funktioner i Customer Journey Analytics
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 2ebbee4ae7990bdb69f42cf25f8fcef3c20a26ee
workflow-type: tm+mt
source-wordcount: '1311'
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
| Mått | Fullt stöd; CJA utnyttjar XDM och har stöd för obegränsade dimensioner. CJA är inte knutet till de anpassade eVars- eller propparna hos traditionella Adobe Analytics. |
| Borttagning av GDPR | Fullt stöd; Observera att GDPR nu hanteras i samordning med [!UICONTROL Adobe Experience Platform]. CJA ärver alla dataändringar [!UICONTROL Experience Platform] till underliggande datamängder. |
| Lista variabler/listutkast | Fullt stöd; CJA utnyttjar XDM och stöder obegränsat antal strängarrayer som kan användas på liknande sätt som listVars. |
| Varaktighet för marknadsföringsvariabel | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=en#binding-dimension) (januari 2022) |
| Marknadsförande eVars | Fullt stöd via [bindningsdimensioner och bindningsmått](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=en#binding-dimension) (januari 2022) |
| Mätvärden | Fullt stöd; CJA utnyttjar Experience Data Model (XDM) och stöder obegränsade mätvärden och är inte knutet till anpassade framgångshändelser i traditionell Analytics. Observera att vissa standardvärden har bytt namn från traditionell analys: Besökare = människor, besök = sessioner, träffar = händelser. |
| Metrisk deduplicering | Fullt stöd |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. |
| PDF Export | Fullt stöd |
| Projekturval | Fullt stöd |
| Projektlänkning | Fullt stöd |
| Report Builder (Excel-plugin) | Fullt stöd |
| Bearbetning av rapporttid | Fullt stöd; CJA använder sig enbart av Report Time Processing. |
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
| [!UICONTROL Device], [!UICONTROL Browser], [!UICONTROL Referrer], [!UICONTROL Technology] dimensioner | Dessa dimensioner inkluderas automatiskt när en AEP-datauppsättning innehåller specifika XDM-schemafält och följer XDM Experience Event-klassen. Se våra [dokumentation om vilka analysvariabler som stöds via Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en). För CJA-kunder som inte använder källkopplingen för att fylla i data från Adobe Analytics till CJA, utan i stället använder AEP Web SDK-datainsamling, [!UICONTROL Device] och dimensioner baserade på enhetssökningen stöds för närvarande inte, men kommer inom den närmaste framtiden. |
| Poster, avslutningar och använd tid för mått och mätvärden | Stöds (Poster och avslutningar kallas nu för Sessionsstart och Sessionsslut) och beräknas på ett något annorlunda sätt. |
| Inställningar för beständighet av eVar | Varor ingår inte längre i CJA. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Dimensioner som anges i datavyer är begränsade till högst 90 dagars beständighet och stöder inte obegränsad beständighet. |
| GeoSegmenteringsdimensioner | All GeoSegmentation/geography som samlas in i Adobe Analytics flödar till CJA via [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en). Implementeringar som inte använder Analytics Source Connector, t.ex. de som använder AEP Web SDK för digital datainsamling, kommer inte att ha det fullständiga urvalet av geografiska sökningar som utförs automatiskt: Land och delstat i USA stöds inte. Det finns för närvarande begränsat eller inget stöd för delstater/regioner utanför USA. |
| Marknadsföringskanaler | Marknadsföringskanalernas data flödar till CJA via Analytics Data Connector. Reglerna för marknadsföringskanaler måste fortfarande konfigureras i traditionella Adobe Analytics. Vissa regler stöds inte. Mer information finns på [Dokumentation för CJA Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases). |
| Produktvariabel | I Experience Platform kan användare använda en array med objekttypsfält i ett dataset-schema för att tillgodose detta användningsfall. Inom CJA kan kunderna använda valfritt antal produktvariabler och begränsas inte till en enda variabel som i Adobe Analytics. |
| Projektdelning | Projektdelning stöds endast mellan CJA-användare - det finns ingen projektdelning mellan CJA och det traditionella Analysis Workspace. |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |

## Delvis stöd

| Funktion | Anteckningar |
| --- | --- |
| Punktfiltrering | För [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en)-baserade datauppsättningar, robotfiltrering tillämpas. Allmän startfiltreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller CJA. |
| Medieanalys | Mediedata är tillgängliga som en del av Analytics Source Connector. |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. Panelerna Segmentjämförelse, Analytics for Target (A4T) och Media Concurrent Viewer stöds inte. |
| Bearbetningsregler | För datauppsättningar baserade på Analytics Data Connector tillämpas fortfarande bearbetningsregler. [Prestandafunktioner för data i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) kan också användas som ersättning för bearbetningsregler för data som går direkt till plattformen. |

## Stöds inte just nu, men är planerad

| Funktion | Anteckningar |
| --- | --- |
| Larm | Support planeras. |
| Kalenderhändelser | Anteckningar kallas för Anteckningar i Workspace. |
| Classification Rule Builder | Fungerar något annorlunda i CJA, med hjälp av strängändringar vid rapporttidpunkten i stället för att söka efter datauppsättningar. |
| Bidragsanalys | Support planeras. |
| data warehouse-rapportering (100 % radexport) | Support planeras från Analysis Workspace gränssnitt. Adobe Experience Platform [[!UICONTROL Query Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en) har också ett gränssnitt för de här användningsfallen i CJA. |
| ID Stitching via Device Graph | Support planeras. |
| Lyft- och tillförlitlighetsrapportering | Support planeras. |
| Bearbetningsregler, VISTA-regler, Bearbetningsregler för marknadsföringskanaler | Stöd planeras, men kommer att fungera vid frågesändning i stället för under datainsamlingen för mer flexibla och retroaktiva och icke-förstörande dataändringar. |
| Projektmallar | Support planeras. |
| Realtidsrapportering | Support planeras. |
| Segment IQ | Support planeras. |
| Segmentpublicering (skickar segment från Workspace till Experience Cloud) | Support planeras. Kallas &quot;Audience Publishing&quot; i CJA. |
| Ny eller upprepad sessionsrapportering | Support planeras med några kavaetter. |

## Stöd ännu inte planerat

| Funktion | Anteckningar |
| --- | --- |
| Activity Map | Support är ännu inte planerat. |
| Advertising Cloud | Support är ännu inte planerat. |
| Valutakonvertering | Support är ännu inte planerat. |
| Datafeeds | Support är ännu inte planerat. |
| Sammanfattningsdatakällor | Support är ännu inte planerat. |
| Datakällor för transaktions-ID | Support är ännu inte planerat. |

## Stöds aldrig

* Personmätvärden med Coop för olika enheter
* Rapporter och analyser på kontrollpaneler
* Bokmärken för rapporter och analyser
* Rapporter och analysmål
* Mobiltjänster
