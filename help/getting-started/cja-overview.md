---
title: Customer Journey Analytics - översikt
description: Lär dig hur du kan använda Analysis Workspace med data från Experience Platform i Customer Journey Analytics.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: Basics
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '941'
ht-degree: 4%

---

# Customer Journey Analytics - översikt

Customer Journey Analytics är Adobe nästa generation av Analytics-lösning som gör att ni kan använda kraften i Analysis Workspace med data från Adobe Experience Platform. Den kan bryta ned, filtrera, ställa frågor och visualisera årens datavärde och kombineras med plattformens möjlighet att lagra alla typer av datamappningar och datatyper. Använda **Experience Data Model (XDM)**, kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. **Adobe Experience Platform Query Service** gör att du kan använda SQL-kompatibla verktyg och ramverk för att fråga efter och ändra alla data.

Customer Journey Analytics-arkitekturen på hög nivå visas här:

![Customer Journey Analytics-arkitekturen förklaras i detta avsnitt](assets/cja-architecture.png)

Här är en videoöversikt av Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## Jämföra Customer Journey Analytics med traditionell Adobe Analytics

Customer Journey Analytics utvidgar räckvidden för Adobe Analytics genom att erbjuda lättanvända funktioner för flera kanaler och ta bort begränsningar i tidigare versioner av Adobe Analytics. Några viktiga förbättringar är:

* **Obegränsade variabler och händelser**: Begreppen eVars, props och händelser finns inte längre. Data fokuseras främst på dimensioner och mätvärden. Datauppsättningar kan ha ett obegränsat antal unika mått och mätvärden.
* **Obegränsade unika värden**: Adobe Experience Platform begränsas inte till några unika begränsningar.
* **Ändra historiska data**: Med Adobe Experience Platform kan data tas bort eller korrigeras.
* **Data för flera rapporter**: Befintliga implementeringar från flera datauppsättningar kan kombineras i Platform.

>[!TIP]
>
>Om du har använt Adobe Analytics och vill använda dina Adobe Analytics-data i Customer Journey Analytics, se [Importera och använda data från traditionella Adobe Analytics](../data-ingestion/analytics.md) snabbstartsguiden som en del av [Inmatning av data](../data-ingestion/data-ingestion.md) -avsnitt.

Den första releasen av Customer Journey Analytics innehåller många av de funktioner som ingår i Adobe Analytics. En fullständig lista finns på [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## Viktiga användningsexempel

Med Customer Journey Analytics kan du:

* **Se kunden i ett kundresandesammanhang**: Du kan visa och analysera data sekventiellt, över flera kanaler. Data från ert callcenter, era POS-system och onlineegenskaper kan kombineras till en enda rapportvy.
* **Gör insikter tillgängliga för alla**: Demokratisera dataåtkomsten och låt fler människor fatta affärsbeslut med hjälp av datainriktade insikter. Alla i organisationen som ansvarar för någon aspekt av kundupplevelsen kan fatta riktiga beslut snabbare, baserat på mer fullständiga data.
* **Utnyttja kraften i datavetenskap för era analytiker**: Customer Journey Analytics låter vanliga människor använda datavetenskap för att få djupgående insikter och analyser.
* **Visualisera och interagera med datauppsättningar med hjälp av on demand-rapportering**: Arbetsytan kan använda alla datauppsättningar från Adobe Experience Platform som uppfyller vissa grundläggande regler.
* **Visa data som inte är webbdata**: Arbetsytan är inte längre begränsad till en fast definition av en träff eller händelse. Anpassade scheman ger fullständig kontroll över data och definitioner.
* **Få bättre kontroll över datahanteringen**: Ändra data som du har överfört, skapa datauppsättningar och importera dem till Workspace. Adobe Experience Platform tillhandahåller verktyg för att fråga, extrahera, omforma och läsa in med Experience Platform Query Service.

## Förutsättningar

Innan du kan börja använda Customer Journey Analytics måste följande krav vara uppfyllda:

* Din organisation har ett aktivt kontrakt med Adobe Analytics för Select, Prime eller Ultimate med tillägget Customer Journey Analytics. Om du är osäker på vilken typ av kontrakt du har, eller om du är osäker på om du har tillägget Customer Journey Analytics, kontaktar du ditt kontoteam på Adobe.
* Din organisation har etablerats för Adobe Experience Platform.
* Du kan också köpa Customer Journey Analytics som fristående produkt utan Adobe Analytics.

## Åtkomstkontroll

Se [Åtkomstkontroll](/help/admin/cja-access-control.md) ämne.

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

Med Adobe Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser. Kunddata på plattformen lagras som datauppsättningar, som består av ett schema och grupper med data. Mer information om plattformen finns på [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html).

Från datainmatning till direkt SQL-åtkomst - flera komponenter från Experience Platform är centrala för Customer Journey Analytics och kompletterar dem:

* [Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv): Använd standard-SQL för att hämta data från Adobe Experience Platform, t.ex. data från Adobe-lösningar, kunddata från första part eller andra plattformsdata. Det är ett serverfritt verktyg som gör att du kan koppla till alla datauppsättningar och samla in frågeresultaten som en ny datauppsättning för användning vid rapportering eller för att lägga in dem i profiltjänsten. Du kan använda Experience Platform Query Service för att bygga dataanalysekosystem och skapa en bild av konsumenterna över deras olika interaktionskanaler. Dessa kanaler kan omfatta försäljningsställen, webb, mobiler, CRM-system osv.
* [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv):
* [Identitetstjänst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=sv)

## Videor

* Arbeta med data i Customer Journey Analytics:

  >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Arkitektur och integrering av Customer Journey Analytics:

  >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

