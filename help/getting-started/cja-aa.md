---
title: Funktioner i Customer Journey Analytics
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner.
translation-type: tm+mt
source-git-commit: b0b8d62eaa7ca539b04677c308fbb33345e110fe
workflow-type: tm+mt
source-wordcount: '875'
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
| Virtual Report Suites | Har anropats [Datavyer](/help/data-views/create-dataview.md). |
| VRS-komponenturval | Nu en del av datavyer. |
| Bearbetning av rapporttid | CJA använder sig enbart av Report Time Processing. |
| Borttagning av GDPR | Observera att GDPR nu hanteras i samordning med [!UICONTROL Experience Platform] - CJA ärver alla dataändringar [!UICONTROL Experience Platform] till underliggande datamängder. |
| Användarbehörigheter/dataåtkomstkontroller | CJA skiljer mellan Adobe Admin Console produktadministratörer och användare. Endast produktadministratörer kan 1) skapa/uppdatera/ta bort anslutningar eller datavyer, 2) uppdatera/ta bort projekt, filter eller beräkningstal som har skapats av andra användare och 3) dela ett Workspace-projekt med alla användare |

## Stöds med caveats

| Funktion | Anteckningar |
| --- | --- |
| Produktvariabel | Den produktvariabel som för närvarande är tillgänglig för rapportering av data som överensstämmer med Experience Event-schemat (särskilt med objektet productListItems). |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |
| AAM | Om kunderna använder [!UICONTROL Analytics Data Connector] datauppsättningar, kommer dessa data att ingå i ADC-data. |
| Projektdelning | Projektdelning stöds endast mellan CJA-användare - det finns ingen projektdelning mellan CJA och det traditionella Analysis Workspace. |
| Skräddarsydd professionalisering | Stöd för alla anpassade sessioneringsfunktioner förutom mobilbakgrundstötar. |
| Inställningar för beständighet av eVar | Varor ingår inte längre i CJA. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Detta innebär att all beständighet baseras på rapporteringsdatumintervallet i stället för på alla data. |
| Klassificeringar | De kallas nu&quot;Sök efter datauppsättningar&quot; och importeras inte automatiskt från traditionell Analytics. De måste överföras till AEP innan de är tillgängliga i CJA. |
| Kundattribut | De kallas nu&quot;profildatauppsättningar&quot; och importeras inte automatiskt från Experience Cloud, utan måste överföras till AEP innan de blir tillgängliga i CJA. |

## Delvis stöd

| Funktion | Anteckningar |
| --- | --- |
| Färdiga Analysis Workspace-dimensioner (t.ex. webbläsartyp, referenstyp, marknadsföringskanaler, besöksnummer osv.) | CJA har inte dessa dimensioner internt. För kunder som använder Analytics Data Connector (ADC) är vissa av dessa dimensioner tillgängliga, men inte alla. Se våra [dokumentation om vilka analysvariabler som stöds via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. Panelerna Segmentjämförelse, Analytics for Target (A4T) och Media Concurrent Viewer stöds inte. |
| Marknadsförande eVars | Merchandising eVars fungerar bara med ADC-baserade datauppsättningar om de inte följer samma XDM-schema (liknande produktlistans begränsningar ovan). |
| Punktfiltrering | För ADC-baserade datauppsättningar (Analytics Data Connector) tillämpas robotfiltrering. Allmän startfiltreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller CJA. |
| Bearbetningsregler | För ADC-baserade datauppsättningar tillämpas fortfarande bearbetningsregler. |
| Stitching av enhetsidentitet | Kunderna är begränsade till&quot;engångskarvar&quot; av data via Query Service, eller måste för närvarande tillämpa denna logik på data före [!UICONTROL Experience Platform] dataintag. |

## Stöds inte just nu, men är planerad

| Funktion | Anteckningar |
| --- | --- |
| Bidragsanalys | Support planeras. |
| Segment IQ | Support planeras. |
| Segmentpublicering (skickar segment från Workspace till Experience Cloud) | Support planeras. |
| CSV-nedladdning | Support planeras. |
| Schemalagda rapporter/projekt | Support planeras. |
| Larm | Support planeras. |
| Anpassade kalendrar | Support planeras. |
| Marknadsföringskanaler | Support planeras. |
| PDF-export | Support planeras. |
| API-åtkomst för rapportering | Support planeras - endast med API 2.0. |
| ID Stitching via Device Graph | Support planeras. |

## Stöd ännu inte planerat

| Funktion | Anteckningar |
| --- | --- |
| A4T | Support är ännu inte planerat. |
| Medieanalys | Support är ännu inte planerat. |
| Advertising Cloud | Support är ännu inte planerat. |
| Report Builder (Excel-plugin) | Support är ännu inte planerat. |
| Activity Map | Support är ännu inte planerat. |
| Classification Rule Builder | Support är ännu inte planerat. |
| Sammanfattningsdatakällor | Support är ännu inte planerat. |
| Realtidsrapportering | Support är ännu inte planerat. |

## Stöds aldrig

* Personmätvärden med Coop för olika enheter
* Rapporter och analyser på kontrollpaneler
* Bokmärken för rapporter och analyser
* Rapporter och analysmål
* Rapporter och analyskalenderhändelser
* Ad Hoc Analysis
* Rapportering från data warehouse - [!UICONTROL Experience Platform Query Service] kommer att bli det nya gränssnittet för de här användningsområdena i CJA.
* Mobiltjänster
* Datafeeds
