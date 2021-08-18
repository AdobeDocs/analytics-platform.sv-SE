---
title: Bästa praxis för attribuering
description: Vilka är de bästa sätten att fatta beslut om en attribueringsmodell?
source-git-commit: 3839639858edbd019ef467ca5fb1791f48864100
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---


# Bästa praxis för attribuering

Hur ni väljer rätt attribueringsmodell för er organisation beror på ett antal överväganden. I den här artikeln utforskas en metod och några allmänna bästa metoder.

## Steg 1: Experimentell analys

>[!NOTE]
>Denna analys måste ske innan du väljer en attribueringsmodell.

Den här fasen består till att börja med av att förstå kundbeteende och definiera konverteringsmått. Baserat på konverteringsstatistik kan verktyg som [Dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) (för rådata) eller Analysis Workspace underlätta din förståelse av

* Hur många kunder tar sig an olika marknadsföringskanaler innan de konverterar?
* Andelen/fördelningen av dessa beteenden.

Om 50 % av kunderna till exempel rör tre kanaler innan de konverterar, finns det någon interaktion mellan dessa tre kanaler?
Sedan kan ni göra analyser både internt och externt för att öka er förståelse.

### Övre trattanalys

Analyser av de vanligaste kanalerna som används för att skapa varumärkes- eller produktmedvetenhet. Målet för de flesta TV-annonser är till exempel varumärkesmedvetenhet. Du kan använda attribueringsmodellen [&quot;Tidsminskning&quot;](/help/analysis-workspace/attribution/models.md), eftersom folk kommer att glömma bort din TV-annons över tiden.

### Nedre trattanalys

I den här analysen antas att folk redan känner till ert varumärke och att ni vill att de ska konvertera. Använd e-post- eller push-meddelanden eller Facebook-annonser.

## Steg 2: Regelbaserad attribuering

Syftet med det här steget är att validera dina hypoteser.

**Exempel 1**

Låt oss säga att din hypotes är &quot;Min första-beröringskanal har större effekt på konverteringen än min sista-beröringskanal. Du använder sedan attributmodellen [&quot;Inverse J-formad&quot;](/help/analysis-workspace/attribution/models.md) för att testa hypotesen. Den här modellen ger 60 % av äran till den första beröringspunkten.

**Exempel 2**

Din hypotes kan vara: &quot;I vår bransch (t.ex. resebranschen) är attribueringsfönstret 60 eller 90 dagar, inte 30 dagar, eftersom kunderna gör mycket efterforskningar innan de köper en produkt. Du skulle sedan ändra [uppslagsfönstret](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#lookback-windows) till 90 dagar.

## Steg 3: Använd algoritmisk attribuering

Eftersom det är mycket svårt att validera ett stort antal möjliga hypoteser och kombinationer kan du använda [algoritmisk attribuering](/help/analysis-workspace/attribution/algorithmic.md) för att lämna det här arbetet åt inbyggda algoritmer. Om du redan har hittat den perfekta attribueringsmodellen som besvarar alla dina frågor och är perfekt, behöver du naturligtvis inte ta det här steget.

## Andra överväganden

* Du kan behöva använda en datavetare istället för att förlita dig på Analysis Workspace.
* Du kan förlita dig på rådata, som i dataflöden från Adobe.
* Du kan till exempel använda [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en) om du vill ta hänsyn till dina Impressions-data.

