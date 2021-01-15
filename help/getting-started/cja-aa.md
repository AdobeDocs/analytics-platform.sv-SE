---
title: Funktioner i Customer Journey Analytics
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner.
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '973'
ht-degree: 5%

---


# Funktioner i Customer Journey Analytics

I följande tabell visas vilka funktioner i Adobe Analytics som stöds, stöds delvis eller inte alls i Customer Journey Analytics (CJA). De här listorna ändras över tid när funktioner läggs till i CJA.

## Funktioner/komponenter som stöds fullt ut

| Funktion | Anteckningar |
| --- | --- |
| Mätvärden | CJA utnyttjar Experience Data Model (XDM) och stöder obegränsade mätvärden och är inte knutet till anpassade framgångshändelser i traditionell Analytics. Observera att vissa standardvärden har bytt namn från traditionell analys: Besökare = människor, besök = sessioner, träffar = händelser. |
| Mått | CJA utnyttjar XDM och har ett obegränsat antal dimensioner och är inte knutet till anpassade framgångshändelser i traditionell Analytics. |
| Lista variabler/listutkast | CJA utnyttjar XDM och stöder obegränsat antal listvariabler |
| Datumintervall | Stöd för anpassade kalendrar planeras. |
| Beräknade mätvärden | Observera att alla befintliga kalkylmått i det traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Segment | Nu kallat &quot;Filter&quot; - lägg märke till att befintliga segment i traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Avvikelseidentifiering | Fullt stöd |
| Attribution IQ | Fullt stöd |
| Projekturval | Fullt stöd |
| Projektlänkning | Fullt stöd |
| Datumjämförelser | Fullt stöd |
| Virtual Report Suites | Ringde nu [datavyer](/help/data-views/create-dataview.md). |
| VRS-komponenturval | Nu en del av datavyer. |
| Bearbetning av rapporttid | CJA använder sig enbart av Report Time Processing. |
| Borttagning av GDPR | Observera att GDPR nu hanteras i samordning med [!UICONTROL Adobe Experience Platform] - CJA ärver alla dataändringar [!UICONTROL Experience Platform] som görs i underliggande datauppsättningar. |
| Användarbehörigheter/dataåtkomstkontroller | CJA skiljer mellan Adobe Admin Console produktadministratörer och användare. Endast produktadministratörer kan 1) skapa/uppdatera/ta bort anslutningar eller datavyer, 2) uppdatera/ta bort projekt, filter eller beräkningstal som har skapats av andra användare och 3) dela ett Workspace-projekt med alla användare |

## Stöds med caveats

| Funktion | Anteckningar |
| --- | --- |
| Produktvariabel | Den produktvariabel som för närvarande är tillgänglig för rapportering av data som överensstämmer med Experience Event-schemat (särskilt med objektet productListItems). |
| Marknadsföringskanaler | Data för marknadsföringskanaler flödar nu in i CJA via Analytics Data Connector. Reglerna för marknadsföringskanaler måste fortfarande konfigureras i traditionella Adobe Analytics. Vissa regler stöds inte. Mer information finns i [dokumentationen för CJA Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases). |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |
| Projektdelning | Projektdelning stöds endast mellan CJA-användare - det finns ingen projektdelning mellan CJA och det traditionella Analysis Workspace. |
| Skräddarsydd professionalisering | Stöd för alla anpassade sessioneringsfunktioner förutom mobilbakgrundstötar. |
| Inställningar för beständighet av eVar | Varor ingår inte längre i CJA. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Detta innebär att all beständighet baseras på rapporteringsdatumintervallet i stället för på alla data. |
| Klassificeringar | De kallas nu&quot;Sök efter datauppsättningar&quot; och importeras inte automatiskt från traditionell Analytics. De måste överföras till AEP innan de är tillgängliga i CJA. |
| Kundattribut | De kallas nu&quot;profildatauppsättningar&quot; och importeras inte automatiskt från Experience Cloud, utan måste överföras till AEP innan de blir tillgängliga i CJA. |
| Enhet, webbläsare, teknikdimensioner | Dessa dimensioner inkluderas automatiskt när en AEP-datauppsättning innehåller specifika XDM-schemafält och följer XDM Experience Event-klassen. |
| Poster, avslutningar och tidsmått | Stöds (Poster och avslutningar kallas nu för Sessionsstart och Sessionsslut) och beräknas på ett något annorlunda sätt. |

## Delvis stöd

| Funktion | Anteckningar |
| --- | --- |
| Färdiga Analysis Workspace-dimensioner (t.ex. webbläsartyp, referenstyp, marknadsföringskanaler, besöksnummer osv.) | CJA har inte dessa dimensioner internt. För kunder som använder Analytics Data Connector (ADC) är vissa av dessa dimensioner tillgängliga, men inte alla. Läs vår [dokumentation om vilka analysvariabler som stöds via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. Panelerna Segmentjämförelse, Analytics for Target (A4T) och Media Concurrent Viewer stöds inte. |
| Marknadsförande eVars | Merchandising eVars fungerar bara med ADC-baserade datauppsättningar om de inte följer samma XDM-schema (liknande produktlistans begränsningar ovan). |
| Punktfiltrering | För ADC-baserade datauppsättningar (Analytics Data Connector) tillämpas robotfiltrering. Allmän robotfiltreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller CJA. |
| Bearbetningsregler | För ADC-baserade datauppsättningar tillämpas fortfarande bearbetningsregler. |
| Stitching av enhetsidentitet | Kunderna är begränsade till&quot;engångsöppningar&quot; av data via frågetjänsten, eller måste för närvarande tillämpa denna logik på data före [!UICONTROL Experience Platform]-dataimporten. |

## Stöds inte just nu, men är planerad

| Funktion | Anteckningar |
| --- | --- |
| Bidragsanalys | Support planeras. |
| Segment IQ | Support planeras. |
| Segmentpublicering (skickar segment från Workspace till Experience Cloud) | Support planeras. |
| CSV-nedladdning | Support planeras. |
| Metrisk deduplicering | Support planeras. |
| Anpassade kalendrar | Support planeras. |
| Metrisk deduplicering | Support planeras. |
| Varaktighet för marknadsföringsvariabel | Support planeras. |
| Schemalagda rapporter/projekt | Support planeras. |
| Larm | Support planeras. |
| Anpassade kalendrar | Support planeras. |
| PDF-export | Support planeras. |
| API-åtkomst för rapportering | Support planeras - endast med API 2.0. |
| ID Stitching via Device Graph | Support planeras. |
| Report Builder (Excel-plugin) | Support planeras. |
| Realtidsrapportering | Support planeras. |

## Stöd ännu inte planerat

| Funktion | Anteckningar |
| --- | --- |
| A4T | Support är ännu inte planerat. |
| Medieanalys | Support är ännu inte planerat. |
| Advertising Cloud | Support är ännu inte planerat. |
| Activity Map | Support är ännu inte planerat. |
| Classification Rule Builder | Support är ännu inte planerat. |
| Sammanfattningsdatakällor | Support är ännu inte planerat. |

## Stöds aldrig

* Personmätvärden med Coop för olika enheter
* Rapporter och analyser på kontrollpaneler
* Bokmärken för rapporter och analyser
* Rapporter och analysmål
* Rapporter och analyskalenderhändelser
* Ad Hoc Analysis
* data warehouse Reporting - [!UICONTROL Experience Platform Query Service] kommer att vara det nya gränssnittet för de här användningsfallen i CJA.
* Mobiltjänster
* Datafeeds
