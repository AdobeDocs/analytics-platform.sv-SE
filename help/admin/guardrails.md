---
title: Customer Journey Analytics Guardrails
description: Läs om skyddsräckena för Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
source-git-commit: affe7fe57ba59a15458263afabe2715d4c5da5fe
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 5%

---


# Customer Journey Analytics Guardrails

Det här dokumentet innehåller begränsningar för olika komponenter i Customer Journey Analytics. Information om skyddsutkast, omfångsparametrar och berättiganden finns i [Produktbeskrivning för Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) eller [Produktbeskrivning för Adobe Analytics Add-on: Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Begränsningstyper

Det finns två typer av standardgränser i det här dokumentet:

| Typ av skyddsräcke | Beskrivning |
|----------|---------|
| **Skyddsskydd (mjuk gräns)** | Prestandaskydd är användarbegränsningar som relaterar till omfattningen av dina användningsfall. När du överskrider prestandaskyddet kan du uppleva prestandaförsämringar och fördröjning. Adobe ansvarar inte för sådana prestandaförsämringar. Kunder som genomgående överskrider ett prestandaresäkerhetsskydd kan välja att licensiera ytterligare kapacitet för att undvika prestandaförsämringar. |
| **Systemstyrda skyddsräcken (fast gräns)** | Systemstyrda skyddsräcken används av användargränssnittet eller API:t i Customer Journey Analytics. Detta är begränsningar som du inte kan överskrida eftersom gränssnittet och API hindrar dig från att göra det eller returnerar ett fel. |

{style="table-layout:auto"}

Vissa funktioner och deras associerade värde för gränsen beror på vilket Customer Journey Analytics-paket du har rätt till.

>[!NOTE]
>
>Värdena som beskrivs i det här dokumentet kan ändras baserat på fortsatta förbättringar av produkten. Kontrollera regelbundet om det finns uppdateringar. Om du vill veta mer om anpassade begränsningar kontaktar du kundtjänstrepresentanten.

## Ad-hoc SQL-frågor

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Försök igen med timeout | 90 | Systemstyrt skyddsräcke | Maximalt antal sekunder innan rapportmotorn svarar att det tar för lång tid att returnera resultaten (eventuellt på grund av andra samtidiga begäranden). Det går att begära igen. | |
| Försök inte igen med timeout | 600 | Systemstyrt skyddsräcke | Maximalt antal sekunder innan tidsgränsen för Ad Hoc SQL-frågor uppnås. I annat fall anges det maximala antalet sekunder innan rapportmotorer rapporterar tillbaka att det har tagit för lång tid att returnera resultaten, och det bör inte göras ett nytt försök. Begäran returnerar troligen aldrig resultat på grund av fel i bakgrundsprocessen. |
| Mätvärden | 150 | Systemstyrt skyddsräcke | Maximalt antal mått i en begäran. | | |
| Interaktiva frågans utdatarader | 50 000 | Systemstyrt skyddsräcke | Standardantal returnerade rader om inget annat anges. | |

{style="table-layout:auto"}

## Analysis Workspace-projekt

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Synliga rader per tabell | 400 | Systemstyrt skyddsräcke | Maximalt antal synliga rader i friformstabeller i ett Analysis Workspace-projekt. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Exporterbara rader per tabell | 50 000 | Systemstyrt skyddsräcke | Maximalt antal rader som kan exporteras per dimension. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Paneler per projekt | 15 | Systemstyrt skyddsräcke | Maximalt antal [paneler](../analysis-workspace/home.md#panels) per projekt. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Visualiseringar per panel | 25 | Systemstyrt skyddsräcke | Maximalt antal [visualiseringar](../analysis-workspace/home.md#visualizations) per panel. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

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
| Målgruppsfilter | 20 | Systemstyrt skyddsräcke | Maximalt antal [filter](../components/filters/filters-overview.md) per publik. |
| Antal målgruppsidentiteter | 20 miljoner | Systemstyrt skyddsräcke | Maximalt antal identiteter per publik. |
| Frekvens för målgruppsuppdatering | 4 | Systemstyrt skyddsräcke | Maximal frekvens i timmar [publik](../components/audiences/audiences-overview.md) kan uppdateras. | |
| Uppslagsfönster för uppdatering av målgrupp | 90 | Systemstyrt skyddsräcke | Maximalt antal dagar för uppdateringsfönster. |
| Uppdaterar målgruppens förfallodatum | 13 | Systemstyrt skyddsräcke | Det maximala antalet månader som publiken inte längre kan uppdatera från det datum då den skapades. Kunderna kan förlänga denna period i ytterligare 13 månader. |
| Antal uppdaterade målgrupper | 75, 100, 150 | Systemstyrt skyddsräcke | Maximalt antal uppdaterade målgrupper, värdet varierar beroende på paketet. |

{style="table-layout:auto"}

Se även Experience Platform [Real-time Customer Data Platform skyddsräcken](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=en).


## Förfallodatum för automatiserad datamängd

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|:---:|
| Arbetsorder | 20 | Systemstyrt skyddsräcke | Maximalt antal arbetsorder för utgående datauppsättning per månad. |

{style="table-layout:auto"}



## Anslutningar, datavyer, projekt

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Projekt | 2 000 | Systemstyrt skyddsräcke | Maximalt antal projekt för en organisation. |
| Datavyer | 2 000 | Systemstyrt skyddsräcke | Maximalt antal [datavyer](../data-views/data-views.md) för en organisation. |
| Datavyer | 50 | Systemstyrt skyddsräcke | Maximalt antal datavyer för en anslutning |
| Datauppsättningar | 100 | Systemstyrt skyddsräcke | Maximalt antal [datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) per anslutning. |
| Anslutningar | 1000 | Systemstyrt skyddsräcke | Maximalt antal [anslutningar](../connections/overview.md) för en organisation. |
| Anslutningstitel | 500 | Systemstyrt skyddsräcke | Högsta antal tecken för en anslutningsrubrik. |
| Mätvärden | 5 000 | Systemstyrt skyddsräcke | Maximalt antal mätvärden i en datavy. |
| Mått | 5 000 | Systemstyrt skyddsräcke | Maximalt antal dimensioner i en datavy. | |
| Anteckningsrubrik | 100 | Systemstyrt skyddsräcke | Maximalt antal tecken för en anteckningstitel. |
| Anteckningsbeskrivning | 250 | Systemstyrt skyddsräcke | Maximalt antal tecken för en anteckningsbeskrivning. | |
| Schemafält | 10 | Systemstyrt skyddsräcke | Maximalt antal schemafält (exklusive standardfält) när regler definieras för en [härlett fält](../data-views/derived-fields/derived-fields.md). |
| Sök-/profilfält | 3 | Systemstyrt skyddsräcke | Maximalt antal söknings- eller profilschemafält inom maximalt antal schemafält (exklusive standardfält) när regler definieras för ett härlett fält. |
| Härledda fält | 100 | Systemstyrt skyddsräcke | Maximalt antal härledda fält per anslutning. |

{style="table-layout:auto"}


## Gränser för dataöverföring

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Fält | 10 000 | Systemstyrt skyddsräcke | Maximalt antal egenskaper eller fält per rad i en datauppsättning. | | |
| Unika strängar | 10 miljoner | Systemstyrt skyddsräcke | Maximalt antal unika nycklar per sökdatamängd. |
| Rader | 1 miljon | Systemstyrt skyddsräcke | Maximalt antal rader per unikt person-ID inom en anslutning. |
| Radstorlek | 2 | Prestandaskydd/systemstyrd garanti | Genomsnittlig storlek i kilobyte per rad med data som importerats till Customer Journey Analytics (mjuk gräns). En statisk gräns för radstorlek bestäms av skyddsritningar för dataöverföring i Experience Platform. |

{style="table-layout:auto"}

Se även Experience Platform [Guardsedningar för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en).


## Datallandningszon

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Datallandningszon per sandlåda | 1 | Systemstyrt skyddsräcke | Maximalt antal datalandningszoner per sandlåda. |
| Datalagring | 7 | Systemstyrt skyddsräcke | Maximalt antal dagar data lagras i datalandningszonen innan de tas bort. |

{style="table-layout:auto"}


## Fältbaserad stygn

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Namngivna datauppsättningar | 10 | Systemstyrt skyddsräcke | Maximalt antal sammanslagna datauppsättningar per kund, beroende på paketet. |
| Backfill-data | 60 | Systemstyrt skyddsräcke | Maximalt antal dagar med data för bakåtfyllnad. |

{style="table-layout:auto"}


## Filter och beräknade värden

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Behållare per filter | 50 | Systemstyrt skyddsräcke | Maximalt antal behållare per filter. |
| Mätvärden per beräknat mätvärde | 25 | Systemstyrt skyddsräcke | Maximalt antal mätvärden per beräknat mätvärde. |
| Mätvärden och mått per filter | 25 | Systemstyrt skyddsräcke | Maximalt antal unika mått per filter. |
| Kapslade behållare per filter | 10 | Systemstyrt skyddsräcke | Maximalt antal kapslade behållare per filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Regler per filter | 100 | Systemstyrt skyddsräcke | Maximalt antal regler per filter. |
| Strängjämförelser per dimension och filter | 100 | Systemstyrt skyddsräcke | Högsta antal strängjämförelser per dimension och filter. |
| Beräknade mått | 6 000 | Systemstyrt skyddsräcke | Maximalt antal beräknade värden för en organisation. | |
| Filter | 50 000 | Systemstyrt skyddsräcke | Maximalt antal filter som du kan definiera för en organisation. |

{style="table-layout:auto"}


## Mobilapplikation

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Plattor | 16 | Systemstyrt skyddsräcke | Maximalt antal plattor per styrkort. |
| Filter | 10 | Systemstyrt skyddsräcke | Maximalt antal filter per styrkort. |
| Mått | 10 | Systemstyrt skyddsräcke | Maximalt antal dimensioner per styrkort. |

{style="table-layout:auto"}

## Report Builder

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Arbetsbokens filstorlek | 5 | Systemstyrt skyddsräcke | Största filstorlek i MB för en schemalagd arbetsbok. |
| Datablock | 1000 | Systemstyrt skyddsräcke | Maximalt antal [datablock](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) per arbetsbok. |
| Mätvärden | 20 | Systemstyrt skyddsräcke | Maximalt antal mätvärden per datablock. |
| Datumintervall | 13 | Systemstyrt skyddsräcke | Maximalt antal månader som ett datumintervall kan omfatta per datablock. |  |
| Rader | 50 000 | Systemstyrt skyddsräcke | Maximalt antal rader per datablock. |

{style="table-layout:auto"}


## Fullständig tabellexport

| Namn | Värde | Begränsa typ | Beskrivning |
|---|--:|---|---|
| Rader per rapport | 3 miljoner - 300 miljoner | Systemstyrt skyddsräcke | Maximalt antal rapporteringsrader per rapport. Värdet baseras på det licensierade paketet. |
| Uppdelningar per tabell | 5 | Systemstyrt skyddsräcke | Maximalt antal uppdelningar per tabell. |
| Mätvärden per tabell | 5 | Systemstyrt skyddsräcke | Maximalt antal mätvärden per tabell. |
| Schemafrekvens | 1 | Systemstyrt skyddsräcke | Exporten kan schemaläggas en gång (1) om dagen eller längre (t.ex. en gång varannan dag eller en gång i veckan). |

{style="table-layout:auto"}

## Latenser

>[!NOTE]
>
>Bearbetningstiderna nedan är garantiavtal, inte avtal om servicenivå (SLA). Latensen varierar beroende på kundens konfiguration, datavolymer och konsumentprogram. Reella bearbetningstider är ofta snabbare. Se ert Customer Journey Analytics-avtal för era specifika avtalsvillkor och SLA. Se Experience Platform [Guardsedningar för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en) för mer information.

| Dataflöde | Förväntad fördröjning |
|---|---|
| Adobe Analytics till Adobe Analytics-källanslutning (A4T-aktiverad) | &lt; 30 minuter |
| Adobe Analytics källanslutning till kundprofil i realtid (A4T är inte aktiverat) | &lt; 2 minuter |
| Adobe Analytics källanslutning till kundprofil i realtid (A4T aktiverat) | &lt; 30 minuter |
| Intag av data i datasjön från Edge Network eller direktuppspelning | &lt; 60 minuter |
| Inmatning av data i Data Lake från Adobe Analytics-källanslutning | &lt; 90 minuter |
| Intag av data i Customer Journey Analytics från datasjön | &lt; 90 minuter |
| Bakåtfyllnad av Adobe Analytics källanslutning på mindre än 10 miljarder händelser (maximalt 13 månaders historiska data) | &lt; 4 veckor |
| Målgruppspublicering till kundprofil i realtid, inklusive automatisk generering av strömningssegmentet, så att segmentet kan vara klart att ta emot data. | cirka 60 minuter |
| Uppdateringsfrekvens för målgrupper | Engångsuppdatering: fördröjning på mindre än 5 minuter.<br/>Uppdatera var fjärde timme, varje dag, varje vecka, varje månad (fördröjningen går hand i hand med uppdateringsfrekvensen). |

{style="table-layout:auto"}

