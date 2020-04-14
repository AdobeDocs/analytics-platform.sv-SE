---
title: Funktioner för kundreseanalys
description: Funktioner i kundreseanalys jämfört med funktionerna i Adobe Analytics.
translation-type: tm+mt
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Funktioner för kundreseanalys

I följande tabeller visas vilka funktioner i Adobe Analytics som stöds, stöds delvis eller inte stöds alls i kundreseanalysen (CJA). De här listorna ändras över tid när funktioner läggs till i CJA.

## Funktioner/komponenter som stöds fullt ut

| Funktion | Anteckningar |
| --- | --- |
| Mått | CJA utnyttjar Experience Data Model (XDM) och stöder obegränsade mätvärden och är inte knutet till anpassade framgångshändelser i traditionell Analytics. Observera att vissa standardvärden har bytt namn från traditionell analys: Besökare = människor, besök = sessioner, träffar = händelser. |
| Dimensioner | CJA utnyttjar XDM och har ett obegränsat antal dimensioner och är inte knutet till anpassade framgångshändelser i traditionell Analytics. |
| Lista variabler/listutkast | CJA utnyttjar XDM och stöder obegränsat antal listvariabler |
| Datumintervall | Stöd för anpassade kalendrar planeras. |
| Beräknade mått | Observera att befintliga kalkylmått i den traditionella Analysis Workspace inte porteras till CJA. |
| Segment | Nu kallat &quot;Filter&quot; - observera att inga befintliga segment i den traditionella Analysis Workspace porteras till CJA. |
| Attributions-IQ | Fullt stöd |
| Projekturval | Fullt stöd |
| Projektlänkning | Fullt stöd |
| Datumjämförelser | Fullt stöd |
| Virtuella rapportsviter | Kallas nu [datavyer](/help/data-views/create-dataview.md). |
| VRS-komponenturval | Nu en del av datavyer. |
| Bearbetning av rapporttid | CJA använder sig enbart av Report Time Processing. |
| Borttagning av GDPR | Observera att GDPR nu hanteras i samordning med [!UICONTROL Experience Platform] - CJA ärver alla dataändringar [!UICONTROL Experience Platform] som görs i underliggande datauppsättningar. |

## Stöds med caveats

| Funktion | Anteckningar |
| --- | --- |
| Produktvariabel | Den produktvariabel som för närvarande är tillgänglig för rapportering av data som överensstämmer med Experience Event-schemat (särskilt med objektet productListItems). |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |
| AAM-målgrupper | Om kunderna använder [!UICONTROL Analytics Data Connector] datauppsättningar kommer dessa data att ingå i ADC-data. |
| Projektdelning | Projektdelning stöds bara mellan CJA-användare - det finns ingen projektdelning mellan CJA och den traditionella Analysis Workspace. |
| Skräddarsydd professionalisering | Stöd för alla anpassade sessioneringsfunktioner förutom mobilbakgrundstötar. |
| eVar persistence-inställningar | Varor ingår inte längre i CJA. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Detta innebär att all beständighet baseras på rapporteringsdatumintervallet i stället för på alla data. |
| Klassificeringar | De kallas nu&quot;Sök efter datauppsättningar&quot; och importeras inte automatiskt från traditionell Analytics. De måste överföras till AEP innan de är tillgängliga i CJA. |
| Kundattribut | De kallas nu&quot;profildatauppsättningar&quot; och importeras inte automatiskt från Experience Cloud, utan måste överföras till AEP innan de blir tillgängliga i CJA. |

## Delvis stöd

| Funktion | Anteckningar |
| --- | --- |
| Färdiga dimensioner av analysarbetsytan (t.ex. webbläsartyp, referenstyp, marknadsföringskanaler, besöksnummer osv.) | CJA har inte dessa dimensioner internt. För kunder som använder Analytics Data Connector (ADC) är vissa av dessa dimensioner tillgängliga, men inte alla. Se vår [dokumentation om vilka analysvariabler som stöds via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Paneler | Panelen Tom, panelen Attribution och panelen Frihand stöds till fullo. Segmentjämförelse stöds inte. |
| Merchandising eVars | Merchandising eVars fungerar bara med ADC-baserade datauppsättningar om de inte följer samma XDM-schema (liknande produktlistans begränsningar ovan). |
| Punktfiltrering | För ADC-baserade datauppsättningar (Analytics Data Connector) tillämpas robotfiltrering. Allmän robotfiltreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller CJA. |
| Bearbetar regler | För ADC-baserade datauppsättningar tillämpas fortfarande bearbetningsregler. |
| Stitching av enhetsidentitet | Kunderna är begränsade till&quot;engångsöppningar&quot; av data via Query Service, eller måste för närvarande tillämpa denna logik på data innan de kan matas in [!UICONTROL Experience Platform] . |

## Stöds inte just nu, men är planerad

| Funktion | Anteckningar |
| --- | --- |
| Analysidentifiering | Support planeras. |
| Bidragsanalys | Support planeras. |
| Segmentanalys | Support planeras. |
| Segmentpublicering (skicka segment från Workspace till Experience Cloud) | Support planeras. |
| Användarbehörigheter/dataåtkomstkontroller | Alla användare i CJA har samma åtkomstkontroller - det innebär att alla användare har tillgång till alla anslutningar, datavyer osv. I princip är alla användare användare på administratörsnivå i CJA. Stöd planeras för 2020. |
| CSV-nedladdning | Support planeras. |
| Schemalagda rapporter/projekt | Support planeras. |
| Varningar | Support planeras. |
| Anpassade kalendrar | Support planeras. |
| Marknadsföringskanaler | Support planeras. |
| PDF-export | Support planeras. |
| API-åtkomst för rapportering | Support planeras - endast med API 2.0. |
| ID Stitching via Device Graph | Support planeras. |

## Stöd ännu inte planerat

| Funktion | Anteckningar |
| --- | --- |
| A4T | Support är ännu inte planerat. |
| Videoanalys | Support är ännu inte planerat. |
| Advertising Cloud | Support är ännu inte planerat. |
| Report Builder (Excel-plugin) | Support är ännu inte planerat. |
| Aktivitetskarta | Support är ännu inte planerat. |
| Klassificeringsregelverktyget | Support är ännu inte planerat. |
| Sammanfattningsdatakällor | Support är ännu inte planerat. |
| Realtidsrapportering | Support är ännu inte planerat. |

## Stöds aldrig

| Funktion | Anteckningar |
| --- | --- |
| Personmätvärden med Coop för olika enheter |  |
| Rapporter och analyser på kontrollpaneler |  |
| Bokmärken för rapporter och analyser |  |
| Rapporter och analysmål |  |
| Rapporter och analyskalenderhändelser |  |
| Ad hoc-analys |  |
| Rapportering av datalager | [!UICONTROL Experience Platform Query Service] kommer att bli det nya gränssnittet för de här användningsområdena i CJA. |
| Mobiltjänster |  |
| Dataflöden |  |
