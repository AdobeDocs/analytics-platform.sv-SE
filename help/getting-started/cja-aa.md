---
title: Support för kundens Journey Analytics-funktion
description: Customer Journey Analytics-funktioner jämfört med Adobe Analytics-funktioner som har angetts.
translation-type: tm+mt
source-git-commit: 7d2abfb2cd91ee7574fce10847abb89f14b5388e
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 5%

---


# Support för kundens Journey Analytics-funktion

Följande tabelllista med funktioner i Adobe Analytics stöds, stöds delvis eller stöds inte i Customer Journey Analytics (CJA). Dessa listor kommer att ändras med tiden när funktioner läggs till i CJA.

## Funktioner/komponenter som stöds helt

| Funktion | Anmärkningar |
| --- | --- |
| Mätvärden | CJA använder XDM (Experience Data Model) och har stöd för obegränsade mått och är inte bundet till traditionella lyckohändelser i traditionell analys. Observera att vissa standardmått har bytt namn från traditionell analys: Besökare = Personer, Besök = sessioner, träffar = händelser. |
| Mått | CJA använder XDM och har stöd för obegränsade dimensioner och är inte bundet till traditionella lyckohändelser i traditionell analys. |
| Visa variabler/liståtgärder | CJA använder XDM och stöder obegränsade listvariabler |
| Datumintervall | Stöd för anpassad kalender planeras. |
| Beräknade mätvärden | Observera att befintliga kalkmått i den traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Segment | Nu kallade &quot;Filter&quot; - notera att eventuella befintliga segment i den traditionella Analysis Workspace inte kommer att porteras till CJA. |
| Avvikelseidentifiering | Fullt stöd från och med juni 2020 |
| Attribution IQ | Fullständig support |
| Projektkursion | Fullständig support |
| Projektlänkning | Fullständig support |
| Datumjämförelser | Fullständig support |
| Virtual Report Suites | Har anropats [Datavyer](/help/data-views/create-dataview.md). |
| VRS-komponentkursion | Delas nu i datavyer. |
| Rapporttid, bearbetning | CJA förlitar sig uteslutande på rapporttidsbearbetning. |
| GDPR-borttagning | Observera att GDPR nu hanteras i samordning med [!UICONTROL Experience Platform] - CJA ärver alla dataändringar [!UICONTROL Experience Platform] används för underliggande datauppsättningar. |

## Stöds med mattor

| Funktion | Anmärkningar |
| --- | --- |
| Produktvariabel | Den produktvariabel som för närvarande är tillgänglig för rapportering av data som överensstämmer med Experience-schemat (specifikt med objektet productListItems). |
| Visualiseringar | Alla visualiseringar stöds förutom för kartvisualisering. |
| AAM-målgrupper | Om kunder använder [!UICONTROL Analytics Data Connector] dessa data kommer att ingå i ADC-data. |
| Projektdelning | Projektdelning stöds endast mellan användare av CJA - det finns ingen projektdelning mellan CJA och den traditionella Analysis Workspace. |
| Anpassad sessioner | Stöd för alla anpassade sessionsfunktioner förutom mobila bakgrundshöjningar. |
| eVar-persistence-inställningar | Vars ingår inte längre i CJA. Beständighetsinställningarna ingår nu i datavyer och är tillgängliga för alla dimensioner. Kom ihåg att uthållighet baseras på bearbetning av rapporttid, inte behandling av datainsamling. Detta innebär att all uthållighet kommer att baseras på rapporteringsdatumintervallet i stället för på alla uppgifter. |
| Klassificeringar | De kallas nu &quot;Uppslagna datauppsättningar&quot; och importeras inte automatiskt från traditionell analys. De måste överföras till AEP innan de är tillgängliga i CJA. |
| Kundattribut | Profildatauppsättningar importeras inte automatiskt från Experience Cloud, utan måste överföras till AEP innan de är tillgängliga i CJA. |

## Partiellt stöd

| Funktion | Anmärkningar |
| --- | --- |
| Analysarbetsytedimensioner som inte är aktuella (t.ex. webbläsartyp, referenstyp, marknadsföringskanaler, besöksnummer osv.) | Dessa dimensioner anges inte i CJA. För kunder som använder ADC (Analytics Data Connector) är vissa av dessa dimensioner tillgängliga, men inte alla. Se vår [dokumentation om vilka analysvariabler som stöds via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Paneler | Tom panel, attributpanel, frihandspanel och Snabbinsikter stöds helt. Segmentjämförelsepanelerna och segmentanalyserna för målpanelerna (A4T) stöds inte. |
| Marknadsförande eVars | Merchandising eVars fungerar bara med ADC-baserade datauppsättningar om de inte strikt följer samma XDM-schema (liknande de begränsningar som finns ovan i produktlistan). |
| Bot Filtering | För ADC-baserade (Analytics Data Connector) datauppsättningar tillämpas båda-filtrering. Allmän Båda-filtreringslogik för andra datauppsättningar utförs inte av [!UICONTROL Experience Platform] eller CJA. |
| Bearbetningsregler | För ADC-baserade datauppsättningar tillämpas fortfarande bearbetningsregler. |
| Stitling för enhetsidentitet | Kunderna är begränsade till &quot;engångsöglor&quot; av data via Query Service, eller måste för närvarande tillämpa denna logik på data före [!UICONTROL Experience Platform] Intag av data. |

## Stöds inte just nu, men planeras

| Funktion | Anmärkningar |
| --- | --- |
| Bidragsanalys | Stödet planeras. |
| Segment IQ | Stödet planeras. |
| Segment Publishing (skicka segment från arbetsyta till Experience Cloud) | Stödet planeras. |
| Användarbehörigheter/Dataåtkomstkontroller | Alla användare i CJA har samma åtkomstkontroller - detta innebär att alla användare har tillgång till alla anslutningar, datavyer osv. I princip är alla användare användare på administratörsnivå i CJA. Stödet planeras till 2020. |
| CSV-hämtning | Stödet planeras. |
| Schemalagda rapporter/projekt | Stödet planeras. |
| Larm | Stödet planeras. |
| Anpassade kalendrar | Stödet planeras. |
| Marknadsföringskanaler | Stödet planeras. |
| PDF-export | Stödet planeras. |
| API-åtkomst för rapportering | Support planeras - kommer endast att vara tillgängligt med API 2.0. |
| ID-sökning via Device Graph | Stödet planeras. |

## Stöd ännu inte planerat

| Funktion | Anmärkningar |
| --- | --- |
| A4T | Stödet har ännu inte planerats. |
| Videoanalys | Stödet har ännu inte planerats. |
| Advertising Cloud | Stödet har ännu inte planerats. |
| Report Builder (Excel-plugin) | Stödet har ännu inte planerats. |
| Activity Map | Stödet har ännu inte planerats. |
| Classification Rule Builder | Stödet har ännu inte planerats. |
| Sammanfattande datakällor | Stödet har ännu inte planerats. |
| Realtidsrapportering | Stödet har ännu inte planerats. |

## Stöds aldrig

| Funktion | Anmärkningar |
| --- | --- |
| Personmätare med hjälp av enhetskop |  |
| Instrumentpaneler för rapporter och analyser |  |
| Bokmärken för rapporter och analyser |  |
| Rapporter och analysmål |  |
| Rapporter och analyskalenderhändelser |  |
| Ad Hoc Analysis |  |
| Rapportering av datalager | [!UICONTROL Experience Platform Query Service] kommer att bli det nya gränssnittet för dessa användningsfall i CJA. |
| Mobile Services |  |
| Datafeeds |  |
