---
title: Customer Journey Analytics Guardrails
description: Läs om Guardrails för Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: 2380d1c176f2d0d6672714ee068ec198734bcdaf
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 5%

---

# Customer Journey Analytics Guardrails

Det här dokumentet innehåller begränsningar för olika komponenter i Customer Journey Analytics. Information om säkerhetsutkast, omfångsparametrar och berättiganden finns i [Produktbeskrivning för Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) eller [Produktbeskrivning för Adobe Analytics Add-on: Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Begränsningstyper

Det finns två typer av standardgränser i det här dokumentet:

| Typ av skyddsräcke | Beskrivning |
|----------|---------|
| **PrestandagarDRAils (mjuk gräns)** | Prestandaskydd är användningsgränser som relaterar till omfattningen av dina användningsfall. När du överskrider prestanda för säkerhetsritningar kan du uppleva prestandaförsämring och fördröjning. Adobe ansvarar inte för sådana prestandaförsämringar. Kunder som genomgående överträffar en prestandaregardit kan välja att licensiera ytterligare kapacitet för att undvika prestandaförsämring. |
| **Systemstyrda skyddsräcken (fast gräns)** | Systemstyrda säkerhetsutkast används av användargränssnittet eller API:t för Customer Journey Analytics. Detta är begränsningar som du inte kan överskrida eftersom gränssnittet och API hindrar dig från att göra det eller returnerar ett fel. |

{style="table-layout:auto"}

Vissa funktioner och deras associerade värde för gränsen beror på vilket Customer Journey Analytics-paket du är berättigad till.

>[!NOTE]
>
>Värdena som beskrivs i det här dokumentet kan ändras baserat på fortsatta förbättringar av produkten. Kontrollera regelbundet om det finns uppdateringar. Om du vill veta mer om anpassade begränsningar kontaktar du kundtjänstrepresentanten.

## Ad hoc-SQL-frågor

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Timeout för försök igen | 90 | Systemstyrd Guardrail | Maximalt antal sekunder innan rapportmotorn svarar att det tar för lång tid att returnera resultaten (eventuellt på grund av andra samtidiga begäranden). Det går att begära igen. |
| Timeout för försök inte igen | 600 | Systemstyrd Guardrail | Maximalt antal sekunder innan tidsgränsen för Ad Hoc SQL-frågor uppnås. I annat fall anges det maximala antalet sekunder innan rapportmotorer rapporterar tillbaka att det har tagit för lång tid att returnera resultaten, och det bör inte göras ett nytt försök. Begäran returnerar troligen aldrig resultat på grund av fel i bakgrundsprocessen. |
| Mätvärden | 150 | Systemstyrd Guardrail | Maximalt antal mått i en begäran. |
| Interaktiva frågans utdatarader | 50 000 | Systemstyrd Guardrail | Standardantal returnerade rader om inget annat anges. |

{style="table-layout:auto"}

## Analysis Workspace-projekt

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Synliga rader per tabell | 400 | Systemstyrd Guardrail | Maximalt antal synliga rader i friformstabeller i ett Analysis Workspace-projekt. |
| Exporterbara rader per tabell | 50 000 | Systemstyrd Guardrail | Maximalt antal rader som kan exporteras per dimension. |
| Paneler per projekt | 15 | Systemstyrd Guardrail | Maximalt antal [paneler](../analysis-workspace/home.md#panels) per projekt. |
| Visualiseringar per panel | 25 | Systemstyrd Guardrail | Maximalt antal [visualiseringar](../analysis-workspace/home.md#visualizations) per panel. |
| Härledda fält per frihandstabell | 5 | Systemstyrd Guardrail | Maximalt antal olika härledda fält i en friformstabell. |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## Målgrupper

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Målgruppsfilter | 20 | Systemstyrd Guardrail | Maximalt antal [filter](../components/filters/filters-overview.md) per publik. |
| Antal målgruppsidentiteter | 20 miljoner | Systemstyrd Guardrail | Maximalt antal identiteter per publik. |
| Målgruppsuppdateringsfrekvens | 4 | Systemstyrd Guardrail | Maximal frekvens i timmar [publik](../components/audiences/audiences-overview.md) kan uppdateras. |
| Uppslagsfönster för uppdatering av målgrupp | 90 | Systemstyrd Guardrail | Maximalt antal dagar för uppdateringsfönster. |
| Uppdaterar förfallodatum för målgrupp | 13 | Systemstyrd Guardrail | Det maximala antalet månader som publiken inte längre kan uppdatera från det datum då den skapades. Kunderna kan förlänga denna period i ytterligare 13 månader. |
| Antal uppdaterade målgrupper | 75, 100 | Systemstyrd Guardrail | Maximalt antal uppdaterade målgrupper, värdet varierar beroende på paketet (se produktbeskrivning). |

{style="table-layout:auto"}

Se även Experience Platform [Real-time Customer Data Platform Guardrails](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html).


## Förfallodatum för automatiserad datamängd

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|:---:|
| Arbetsorder | 20 | Systemstyrd Guardrail | Maximalt antal arbetsorder för utgående datauppsättning per månad. |

{style="table-layout:auto"}



## Anslutningar, datavyer, projekt

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Projekt | 50 000 | Systemstyrd Guardrail | Maximalt antal projekt för en organisation. |
| Datavyer | 2 000 | Systemstyrd Guardrail | Maximalt antal [datavyer](../data-views/data-views.md) för en organisation. |
| Datavyer | 50 | Systemstyrd Guardrail | Maximalt antal datavyer för en anslutning |
| Datauppsättningar | 100 | Systemstyrd Guardrail | Maximalt antal [datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html) per anslutning. |
| Anslutningar | 1000 | Systemstyrd Guardrail | Maximalt antal [anslutningar](../connections/overview.md) för en organisation. |
| Anslutningstitel | 500 | Systemstyrd Guardrail | Högsta antal tecken för en anslutningsrubrik. |
| Mätvärden | 5 000 | Systemstyrd Guardrail | Maximalt antal mätvärden i en datavy. |
| Mått | 5 000 | Systemstyrd Guardrail | Maximalt antal dimensioner i en datavy. |
| Anteckningsrubrik | 100 | Systemstyrd Guardrail | Maximalt antal tecken för en anteckningstitel. |
| Anteckningsbeskrivning | 250 | Systemstyrd Guardrail | Maximalt antal tecken för en anteckningsbeskrivning. |
| Schemafält | 10 | Systemstyrd Guardrail | Maximalt antal schemafält (exklusive standardfält) när regler definieras för en [härlett fält](../data-views/derived-fields/derived-fields.md). |
| Uppslags-/profilfält | 3 | Systemstyrd Guardrail | Maximalt antal söknings- eller profilschemafält inom maximalt antal schemafält (exklusive standardfält) när regler definieras för ett härlett fält. |
| Härledda fält | 100 | Systemstyrd Guardrail | Maximalt antal härledda fält per anslutning. |

{style="table-layout:auto"}


## Gränser för dataöverföring

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Fält | 10 000 | Systemstyrd Guardrail | Maximalt antal egenskaper eller fält per rad i en datauppsättning. |
| Unika strängar | 10 miljoner | Systemstyrd Guardrail | Maximalt antal unika nycklar per sökdatamängd. |
| Rader | 1 miljon | Systemstyrd Guardrail | Maximalt antal rader per unikt person-ID inom en anslutning. |
| Radstorlek | 2 | Performance Guardrail/Systemstyrd Guardrail | Genomsnittlig storlek i kilobyte per rad med data som importerats till Customer Journey Analytics (mjuk gräns). En statisk gräns för radstorlek bestäms av Guardrails för datainmatning i Experience Platform. |

{style="table-layout:auto"}

Se även Experience Platform [Guardsedningar för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).


## Datallandningszon

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Data Landing Zone per sandbox | 1 | Systemstyrd Guardrail | Maximalt antal datalandningszoner per sandlåda. |
| Datalagring | 7 | Systemstyrd Guardrail | Maximalt antal dagar data lagras i datalandningszonen innan de tas bort. |

{style="table-layout:auto"}


## Fältbaserad stygn

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Namngivna datauppsättningar | 10 | Systemstyrd Guardrail | Maximalt antal sydda datauppsättningar per kund varierar värdet beroende på vilket Customer Journey Analytics-paket som används (se produktbeskrivning). |
| Backfill-data | 60 | Systemstyrd Guardrail | Maximalt antal dagar med data för bakåtfyllnad. |

{style="table-layout:auto"}


## Filter och beräknade värden

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Behållare per filter | 50 | Systemstyrd Guardrail | Maximalt antal behållare per filter. |
| Mått per beräknat mått | 25 | Systemstyrd Guardrail | Maximalt antal mätvärden per beräknat mätvärde. |
| Mätvärden och Dimensioner per filter | 25 | Systemstyrd Guardrail | Maximalt antal unika mått per filter. |
| Kapslade behållare per filter | 10 | Systemstyrd Guardrail | Maximalt antal kapslade behållare per filter. |
| Regler per filter | 100 | Systemstyrd Guardrail | Maximalt antal regler per filter. |
| Strängjämförelser per Dimension och filter | 100 | Systemstyrd Guardrail | Högsta antal strängjämförelser per dimension och filter. |
| Beräknade mätvärden | 6 000 | Systemstyrd Guardrail | Maximalt antal beräknade värden för en organisation. |
| Filter | 50 000 | Systemstyrd Guardrail | Maximalt antal filter som du kan definiera för en organisation. |
| API-anrop | 120 | Systemstyrd Guardrail | API-begäranden per minut (12 begäranden var sjätte sekund). |

{style="table-layout:auto"}


## Mobilapplikation

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Plattor | 16 | Systemstyrd Guardrail | Maximalt antal plattor per styrkort. |
| Filter | 10 | Systemstyrd Guardrail | Maximalt antal filter per styrkort. |
| Mått | 10 | Systemstyrd Guardrail | Maximalt antal dimensioner per styrkort. |

{style="table-layout:auto"}

## Report Builder

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Arbetsbokens filstorlek | 5 | Systemstyrd Guardrail | Största filstorlek i MB för en schemalagd arbetsbok. |
| Datablock | 1000 | Systemstyrd Guardrail | Maximalt antal [datablock](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html) per arbetsbok. |
| Mätvärden | 20 | Systemstyrd Guardrail | Maximalt antal mätvärden per datablock. |
| Datumintervall | 13 | Systemstyrd Guardrail | Maximalt antal månader som ett datumintervall kan omfatta per datablock. |
| Rader | 50 000 | Systemstyrd Guardrail | Maximalt antal rader per datablock. |

{style="table-layout:auto"}


## Fullständig tabellexport

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Rader per rapport | 3 miljoner - 300 miljoner | Systemstyrd Guardrail | Maximalt antal rapporteringsrader per rapport. Värdet varierar beroende på vilket Customer Journey Analytics-paket som används (se produktbeskrivning). |
| Uppdelningar per tabell | 5 | Systemstyrd Guardrail | Maximalt antal uppdelningar per tabell. |
| Mätvärden per tabell | 5 | Systemstyrd Guardrail | Maximalt antal mätvärden per tabell. |
| Schemaläggningsfrekvens | 1 | Systemstyrd Guardrail | Exporten kan schemaläggas en gång (1) om dagen eller längre (t.ex. en gång varannan dag eller en gång i veckan). |

{style="table-layout:auto"}

## Latenser

>[!NOTE]
>
>Bearbetningstiderna nedan är Guardrails, inte avtalade servicenivåavtal (SLA). Latensen varierar beroende på kundens konfiguration, datavolymer och konsumentprogram. Reella bearbetningstider är ofta snabbare. Se ert Customer Journey Analytics-avtal för era specifika avtalsvillkor och SLA. Se Experience Platform [Guardsedningar för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/Guardrails.html) för mer information.

| Dataflöde | Förväntad fördröjning |
|---|---|
| Adobe Analytics till Adobe Analytics Source Connector (A4T aktiverat) | &lt; 30 minuter |
| Adobe Analytics Source Connector to Real-time Customer Profile (A4T inte aktiverat) | &lt; 2 minuter |
| Adobe Analytics Source Connector to Real-time Customer Profile (A4T enabled) | &lt; 30 minuter |
| Inmatning av data i datasjön från Edge Network eller inmatning av strömning | &lt; 60 minuter |
| Datainmatning i datasjön från Adobe Analytics Source Connector | &lt; 2,25 timmar |
| Dataintag i Customer Journey Analytics från datasjön | &lt; 90 minuter |
| Stitching (valfri funktion; se [Översikt över titlar](../stitching/overview.md) för mer information) | &lt; 3,25 timmar |
| Adobe Analytics Source Connector Backfill på mindre än 10 miljarder händelser (max 13 månaders historiska data) | &lt; 4 veckor |
| Audience Publishing till kundprofil i realtid, inklusive automatisk generering av direktuppspelningssegmentet, så att segmentet kan vara klart att ta emot data. | cirka 60 minuter |
| Uppdatera frekvens för målgrupper | Engångsuppdatering: fördröjning på mindre än 5 minuter.<br/>Uppdatera var fjärde timme, varje dag, varje vecka, varje månad (fördröjningen går hand i hand med uppdateringsfrekvensen). |

{style="table-layout:auto"}
