---
title: Målrapportering i Adobe Customer Journey Analytics
description: Integrera Adobe Target med Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: b189776de8cadae3a93c717b6814f2130ab1be43
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Målrapportering i Adobe Customer Journey Analytics

Med Target Reporting i Customer Journey Analytics kan ni mäta och rapportera om Adobe Target-aktiviteter direkt i Customer Journey Analytics. Den här funktionen är jämförbar med vad som utförs i Adobe Analytics (AA) via Analytics for Target (A4T), men med anslutningen till Adobe Experience Platform (AEP).

Genom att lägga till datauppsättningen för sökning efter målklassificering (som är tillgänglig som standard i Experience Platform) i en Customer Journey Analytics Connection, kan användare nu exponeras korrekt för rapportverktyg för mål, attribuering av målorder och andra funktioner. Med endast vissa mindre förberedelser och justeringar i datavyn i Customer Journey Analytics kan dessa aktiviteter göras omedelbart tillgängliga för alla användare som vill skicka Target-data direkt till CJA.

## Fördelar

* Marknadsförarna kan när som helst dynamiskt tillämpa Customer Journey Analytics-framgångsmått på Target-aktivitetsrapporter. Du behöver inte ange allt innan du kör aktiviteten.
* Marknadsförarna kan utnyttja Customer Journey Analytics funktioner, som Experimentation Panel, för att analysera webbplatspersonaliseringen ytterligare.
* Marknadsförarna kan ha en enda rapportkälla för Adobe Journey Optimizer och Target. Båda personaliseringsprodukterna kan kopplas till Customer Journey Analytics för att ge en mer helhetsbild av din webbpersonalisering.

## Anteckningar och överväganden

När data för målklassificeringshändelsen har lagts till i en CJA-anslutning finns det några mindre justeringar att göra i CJA-datavyn när dessa komponenter har lagts till som dimensioner, bland annat:

* Att ange beständighet som liknar hur den spåras i Target (kontrollera med en Target-konsult eller kunden för att se till att inställningarna är korrekta).

* Om du anger beständighet till ALL, vilket gör att flera Target-aktiviteter kan spåras samtidigt och inte skrivas över av framtida eller tidigare aktiviteter.

## Mer detaljerad information

Se [Målrapportering i Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja) i Target-dokumentationen om du vill ha mer information.

Se [Panelen Experimentation](../analysis-workspace/c-panels/experimentation.md) om du vill ha mer information om hur analytiker kan jämföra olika användarupplevelser, marknadsförings- eller meddelandevarianter för att avgöra vilket som är bäst för att uppnå ett visst resultat. Ni kan utvärdera lyften och förtroendet för alla A/B-experiment från vilken experimentplattform som helst - online, offline, från Adobe-lösningar som Target eller Journey Optimizer, och till och med från BYO (hämta in dina egna) data.
