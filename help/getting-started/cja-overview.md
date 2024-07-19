---
title: Customer Journey Analytics - översikt
description: Lär dig hur du kan använda Analysis Workspace med data från Experience Platform i Customer Journey Analytics.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 2%

---

# Customer Journey Analytics - översikt

Customer Journey Analytics är Adobe nästa generation av Analytics-lösning som gör att ni kan använda kraften i Analysis Workspace med data från Adobe Experience Platform. Den kan bryta ned, filtrera, ställa frågor och visualisera årens datavärde och kombineras med plattformens möjlighet att lagra alla typer av datamappningar och datatyper. Med hjälp av **Experience Data Model (XDM)** kan data representeras och organiseras på ett enhetligt sätt, vara klara för kombinering och utforskande. Med **Adobe Experience Platform Query Service** kan du använda SQL-kompatibla verktyg och ramverk för att fråga efter och ändra alla data.

Customer Journey Analytics-arkitekturen på hög nivå visas här:

![Customer Journey Analytics-arkitekturen förklaras i det här avsnittet](assets/cja-architecture.png)

Här är en videoöversikt av Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## Jämföra Customer Journey Analytics med traditionell Adobe Analytics

Customer Journey Analytics utvidgar räckvidden för Adobe Analytics genom att erbjuda lättanvända funktioner för flera kanaler och ta bort begränsningar i tidigare versioner av Adobe Analytics. Några viktiga förbättringar är:

* **Obegränsade variabler och händelser**: Begreppen eVars, props och events finns inte längre. Data fokuseras främst på dimensioner och mätvärden. Datauppsättningar kan ha ett obegränsat antal unika mått och mätvärden.
* **Obegränsade unika värden**: Adobe Experience Platform begränsas inte till några unika begränsningar.
* **Ändra historiska data**: Med Adobe Experience Platform kan data tas bort eller korrigeras.
* **Data för tvärrapporteringsprogram**: Befintliga implementeringar från flera datauppsättningar kan kombineras i plattformen.

>[!TIP]
>
>Om du har använt Adobe Analytics och vill använda dina Adobe Analytics-data i Customer Journey Analytics läser du [Importera och använda data från den traditionella Adobe Analytics](../data-ingestion/analytics.md)-snabbstartsguiden som en del av avsnittet [Datainmatning](../data-ingestion/data-ingestion.md).

Den första releasen av Customer Journey Analytics innehåller många av de funktioner som ingår i Adobe Analytics. En fullständig lista finns i [Stöd för Customer Journey Analytics-funktioner](/help/getting-started/aa-vs-cja/cja-aa.md).

## Viktiga användningsexempel

Med Customer Journey Analytics kan du:

* **Se kunden i ett kundresekontext**: Du kan visa och analysera data sekventiellt och sedan sprida dem i flera kanaler. Data från ert callcenter, era POS-system och onlineegenskaper kan kombineras till en enda rapportvy.
* **Gör insikter tillgängliga för alla**: Demokratisera dataåtkomsten och låt fler personer fatta affärsbeslut med hjälp av datainsikter. Alla i organisationen som ansvarar för någon aspekt av kundupplevelsen kan fatta riktiga beslut snabbare, baserat på mer fullständiga data.
* **Utnyttja datavetenskapen för era analytiker**: Med Customer Journey Analytics kan vanliga människor använda datavetenskap för att låsa upp djupgående insikter och analyser.
* **Visualisera och interagera med datauppsättningar med hjälp av on demand-rapportering**: Workspace kan använda alla datauppsättningar från Adobe Experience Platform som uppfyller vissa grundläggande regler.
* **Visa data som inte är webbdata**: Workspace är inte längre begränsat till en fast definition av en träff eller händelse. Anpassade scheman ger fullständig kontroll över data och definitioner.
* **Få bättre kontroll över din datahantering**: Ändra data som du har överfört, skapa datauppsättningar och importera dem till Workspace. Adobe Experience Platform tillhandahåller verktyg för att fråga, extrahera, omforma och läsa in med Experience Platform Query Service.

## Förutsättningar

Innan du kan börja använda Customer Journey Analytics måste följande krav vara uppfyllda:

* Din organisation har ett aktivt kontrakt med Adobe Analytics för Select, Prime eller Ultimate med tillägget Customer Journey Analytics. Om du är osäker på vilken typ av kontrakt du har, eller om du är osäker på om du har tillägget Customer Journey Analytics, kontaktar du ditt kontoteam på Adobe.
* Din organisation har etablerats för Adobe Experience Platform.
* Du kan också köpa Customer Journey Analytics som fristående produkt utan Adobe Analytics.

## Åtkomstkontroll

Se [Åtkomstkontroll](/help/technotes/access-control.md).

## Uppdateringar om terminologi

Flera funktioner i Customer Journey Analytics har bytt namn, jämfört med traditionella Adobe Analytics, för att passa in i branschstandarder. Några av de uppdaterade terminologin:

* Segment kallas nu för filter.
* Virtuella rapportsviter kallas nu datavyer.
* Klassificeringar kallas nu&quot;Sök efter datauppsättningar&quot;.
* Kundattribut kallas nu profildatamängder.
* Träffbehållare kallas nu Event-behållare.
* Besöksbehållare kallas nu för sessionsbehållare.
* Besöksbehållare kallas nu för personbehållare.

## Andra funktioner som bygger på Adobe Experience Platform

Customer Journey Analytics är en funktion bland många som är beroende av Adobe Experience Platform. Flera andra funktioner, som också bygger på Experience Platform, gör att du får ut så mycket som möjligt av dina data.

Med Adobe Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser. Kunddata på plattformen lagras som datauppsättningar, som består av ett schema och grupper med data. Mer information om plattformen finns i [Översikt över Adobe Experience Platform-arkitekturen](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html).

Från datainmatning till direkt SQL-åtkomst - flera komponenter från Experience Platform är centrala för Customer Journey Analytics och kompletterar dem:

* [Experience Platform-frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv): Använd standard-SQL för att hämta data från Adobe Experience Platform, t.ex. Adobe, kunddata från första part eller andra plattformsdata. Det är ett serverfritt verktyg som gör att du kan koppla till alla datauppsättningar och samla in frågeresultaten som en ny datauppsättning för användning vid rapportering eller för att lägga in dem i profiltjänsten. Du kan använda Experience Platform Query Service för att bygga dataanalysekosystem och skapa en bild av konsumenterna över deras olika interaktionskanaler. Dessa kanaler kan omfatta försäljningsställen, webb, mobiler, CRM-system osv.
* [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv):
* [Identitetstjänst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=sv)

## Videor

* Arbeta med data i Customer Journey Analytics:

  >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Arkitektur och integrering av Customer Journey Analytics:

  >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

