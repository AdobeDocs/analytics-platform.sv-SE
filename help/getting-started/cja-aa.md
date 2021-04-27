---
title: Funktioner i Customer Journey Analytics
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
translation-type: tm+mt
source-git-commit: bf8864103dc4e52734952c0c93d49f97e35b2817
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 4%

---

# Funktioner i Customer Journey Analytics

I följande tabell visas vilka funktioner i Adobe Analytics som stöds, stöds delvis eller inte alls i Customer Journey Analytics (CJA). De här listorna ändras över tid när funktioner läggs till i CJA.

## Funktioner/komponenter som stöds fullt ut

| Adobe Analytics Feature | Anmärkningar om stöd |
| --- | --- |
| Avvikelseidentifiering | Fullt stöd |
| Attribution IQ | Fullt stöd |
| Beräknade mätvärden | Observera att alla befintliga kalkylmått i det traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Sammanfogning mellan olika enheter och kanaler | Se [Flerkanalsanalys](/help/connections/cca/overview.md). |
| Datumjämförelser | Fullt stöd |
| Datumintervall | Stöd för anpassade kalendrar planeras. |
| Mått | CJA utnyttjar XDM och har stöd för obegränsade dimensioner och är inte knuten till anpassade eVars-variabler eller props från traditionell Analytics. |
| Färdiga Analysis Workspace-dimensioner (t.ex. webbläsartyp, referenstyp, operativsystem etc.) | CJA tillhandahåller dessa dimensioner internt så länge som bas-XDM-fälten (till exempel användaragent eller enhets-ID) fylls i. För kunder som använder Analytics Data Connector (ADC) är vissa av dessa dimensioner tillgängliga, men inte alla. Läs vår [dokumentation om vilka analysvariabler som stöds via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Borttagning av GDPR | Observera att GDPR nu hanteras i samordning med [!UICONTROL Adobe Experience Platform] - CJA ärver alla dataändringar [!UICONTROL Experience Platform] som görs i underliggande datauppsättningar. |
| Lista variabler/listutkast | CJA utnyttjar XDM och stöder obegränsat antal strängarrayer som kan användas på liknande sätt som listVars. |
| Mätvärden | CJA utnyttjar Experience Data Model (XDM) och stöder obegränsade mätvärden och är inte knutet till anpassade framgångshändelser i traditionell Analytics. Observera att vissa standardvärden har bytt namn från traditionell analys: Besökare = människor, besök = sessioner, träffar = händelser. |
| PDF-export | Fullt stöd |
| Projekturval | Fullt stöd |
| Projektlänkning | Fullt stöd |
| Bearbetning av rapporttid | CJA använder sig enbart av Report Time Processing. |
| API-åtkomst för rapportering | Finns nu med [CJA API](https://www.adobe.io/cja-apis/docs/). |
| Schemalagda rapporter/projekt | Fullt stöd |
| Segment | Nu kallat &quot;Filter&quot; - lägg märke till att befintliga segment i traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Användarbehörigheter/dataåtkomstkontroller | CJA skiljer mellan Adobe Admin Console produktadministratörer och användare. Endast produktadministratörer kan 1) skapa/uppdatera/ta bort anslutningar eller datavyer, 2) uppdatera/ta bort projekt, filter eller beräkningstal som har skapats av andra användare och 3) dela ett Workspace-projekt med alla användare |
| Virtual Report Suites | Ringde nu [datavyer](/help/data-views/create-dataview.md). |
| VRS-komponenturval | Nu en del av datavyer. |

## Stöds med caveats

| Funktion | Anteckningar |
| --- | --- |
| Klassificeringar | Kallas nu&quot;Sök efter datauppsättningar&quot;. Klassifikationer som används i Analytics kan importeras till Experience Platform och CJA med Data Connector för Analytics-klassificeringar. Uppslagsdatauppsättningar kan också överföras direkt till AEP och göras tillgängliga i CJA. |
| Skräddarsydd professionalisering | Stöd för alla anpassade sessioneringsfunktioner förutom mobilbakgrundstötar. |
| Kundattribut | De kallas nu&quot;profildatauppsättningar&quot; och importeras inte automatiskt från Experience Cloud, utan måste överföras till AEP innan de blir tillgängliga i CJA. |
| Enhet, webbläsare, teknikdimensioner | Dessa dimensioner inkluderas automatiskt när en AEP-datauppsättning innehåller specifika XDM-schemafält och följer XDM Experience Event-klassen. |
| Poster, avslutningar och använd tid för mått och mätvärden | Stöds (Poster och avslutningar kallas nu för Sessionsstart och Sessionsslut) och beräknas på ett något annorlunda sätt. |
| Inställningar för beständighet av eVar | Varor ingår inte längre i CJA. Beständiga inställningar ingår nu i datavyer och är tillgängliga för alla dimensioner. Tänk på att persistence baseras på bearbetning av rapporttid, inte på bearbetning av datainsamling. Dimensioner som anges i datavyer är begränsade till högst 90 dagars beständighet och stöder inte obegränsad beständighet. |
| Marknadsföringskanaler | Marknadsföringskanalernas data flödar till CJA via Analytics Data Connector. Reglerna för marknadsföringskanaler måste fortfarande konfigureras i traditionella Adobe Analytics. Vissa regler stöds inte. Mer information finns i [dokumentationen för CJA Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases). |
| Produktvariabel | I Experience Platform kan användare använda en array med objekttypsfält i ett dataset-schema för att tillgodose detta användningsfall. Inom CJA kan kunderna använda valfritt antal produktvariabler och begränsas inte till en enda variabel som i Adobe Analytics. |
| Projektdelning | Projektdelning stöds endast mellan CJA-användare - det finns ingen projektdelning mellan CJA och det traditionella Analysis Workspace. |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |

## Delvis stöd

| Funktion | Anteckningar |
| --- | --- |
| Punktfiltrering | För ADC-baserade datauppsättningar (Analytics Data Connector) tillämpas robotfiltrering. Allmän robotfiltreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller CJA. |
| Medieanalys | Mediedata är tillgängliga som en del av Analytics Data Connector. |
| Marknadsförande eVars | Beteendet hos Merchandising eVars kan uppnås med hjälp av dimensioner i en Object-array eftersom en eVar inte är inställd på att använda persistence. För närvarande är beständighet för försäljningsdimension inte tillgängligt. |
| Paneler | Panelen Tom, panelen Attribution, panelen Frihand och Insights stöds till fullo. Panelerna Segmentjämförelse, Analytics for Target (A4T) och Media Concurrent Viewer stöds inte. |
| Bearbetningsregler | För datauppsättningar baserade på Analytics Data Connector tillämpas fortfarande bearbetningsregler. |

## Stöds inte just nu, men är planerad

| Funktion | Anteckningar |
| --- | --- |
| Larm | Support planeras. |
| Bidragsanalys | Support planeras. |
| CSV-nedladdning | Support planeras. |
| Anpassade kalendrar | Support planeras. |
| data warehouse-rapportering (100 % radexport) | Support planeras från Analysis Workspace gränssnitt. [!UICONTROL Experience Platform Query Service] har också ett gränssnitt för de här användningsfallen i CJA. |
| ID Stitching via Device Graph | Support planeras. |
| Metrisk deduplicering | Support planeras. |
| Varaktighet för marknadsföringsvariabel | Support planeras. |
| Realtidsrapportering | Support planeras. |
| Report Builder (Excel-plugin) | Support planeras. |
| Segment IQ | Support planeras. |
| Segmentpublicering (skickar segment från Workspace till Experience Cloud) | Support planeras. |

## Stöd ännu inte planerat

| Funktion | Anteckningar |
| --- | --- |
| A4T | Support är ännu inte planerat. |
| Activity Map | Support är ännu inte planerat. |
| Advertising Cloud | Support är ännu inte planerat. |
| Classification Rule Builder | Support är ännu inte planerat. |
| Datafeeds | Support är ännu inte planerat. |
| Sammanfattningsdatakällor | Support är ännu inte planerat. |

## Stöds aldrig

* Personmätvärden med Coop för olika enheter
* Rapporter och analyser på kontrollpaneler
* Bokmärken för rapporter och analyser
* Rapporter och analysmål
* Rapporter och analyskalenderhändelser
* Mobiltjänster
