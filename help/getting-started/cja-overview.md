---
title: Customer Journey Analytics - översikt
description: Customer Journey Analytics introduktion
translation-type: tm+mt
source-git-commit: 7fb439c0796f94e79ae2b738b71cfa85b86f2e8f
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 0%

---


# Customer Journey Analytics - översikt

Customer Journey Analytics är en analysfunktion som gör att ni kan använda kraften i Analysis Workspace med data från Adobe Experience Platform. Den kan bryta ned, filtrera, ställa frågor och visualisera årens datavärde och kombineras med plattformens möjlighet att lagra alla typer av datamappningar och datatyper. Använda **Experience Data Model (XDM)**, kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. **Experience Query Services** gör att du kan använda SQL-kompatibla verktyg och ramverk för att fråga efter och ändra alla data.

## Jämföra CJA med traditionell Adobe Analytics

Customer Journey Analytics utökar räckvidden för Analytics genom att erbjuda lättanvända flerkanalsfunktioner och tar bort begränsningar i tidigare versioner av Adobe Analytics. Några viktiga förbättringar är:

* **Obegränsade variabler och händelser**: Begreppen eVars, props och events finns inte längre. Data fokuseras främst på dimensioner och mätvärden. Datauppsättningar kan ha en obegränsad mängd unika mått och mätvärden.
* **Obegränsade unika värden**: Adobe Experience Platform begränsas inte till några unika begränsningar, som 500 kB unika värden i traditionella rapportsviter.
* **Ändra historiska data**: Med Adobe Experience Platform kan data tas bort eller korrigeras.
* **Data för flera rapporter**: Befintliga implementeringar från flera datauppsättningar kan kombineras i Platform.

Den första releasen av Customer Journey Analytics innehåller många av de funktioner som ingår i Analysis Workspace. En fullständig lista finns på [Funktioner i Customer Journey Analytics](cja-aa.md).

## Jämföra CJA med enhetsövergripande analys

[Enhetsövergripande analys](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) integreras med Adobe Experience Platform Identity Service, med Co-op Graph eller Private Graph, för att identifiera hur digitala enheter mappar till människor. Det finns för Adobe Analytics Ultimate-kunder.

CJA kan integreras med Adobe Experience Platform datauppsättningar och möjliggör flerkanalsanalys i Analysis Workspace. Även om CJA ännu inte är integrerat med Co-op- eller Private-identitetsdiagram kan du&quot;sammanföra ditt eget ID&quot; för att sammanfoga datauppsättningar, och dessa datauppsättningar kan gå utöver digitala data och inkludera både online- och offlinekontaktpunkter. CJA-kraven beskrivs närmare nedan.

## Viktiga användningsexempel

Med Customer Journey Analytics kan du:

* **Se kunden i ett kundresandesammanhang**: Du kan visa och analysera data sekventiellt, över flera kanaler. Data från ert callcenter, era POS-system och onlineegenskaper kan kombineras till en enda rapportvy.
* **Gör insikter tillgängliga för alla**: Demokratisera dataåtkomsten och låt fler människor fatta affärsbeslut med hjälp av datainriktade insikter. Alla i organisationen som ansvarar för någon aspekt av kundupplevelsen kan fatta riktiga beslut snabbare, baserat på mer fullständiga data.
* **Utnyttja kraften i datavetenskap för era analytiker**: Customer Journey Analytics låter vanliga människor använda datavetenskap för att få djupgående insikter och analyser.
* **Visualisera och interagera med era datauppsättningar med ad hoc-rapportering**: Arbetsytan kan använda alla datauppsättningar från Adobe Experience Platform som uppfyller vissa grundläggande regler.
* **Visa data som inte är webbdata**: Arbetsytan är inte längre begränsad till en fast definition av en träff eller händelse. Anpassade scheman ger fullständig kontroll över data och definitioner.
* **Få bättre kontroll över datahanteringen**: Ändra data som du har överfört, skapa nya datauppsättningar och importera dem till arbetsytan. Adobe Experience Platform tillhandahåller verktyg för att fråga, extrahera, omforma och läsa in med Experience Cloud Query Service.

## Förutsättningar

Innan du kan börja använda Customer Journey Analytics måste följande krav vara uppfyllda:

* Din organisation har ett aktivt kontrakt med Adobe Analytics för Select, Prime eller Ultimate med tillägget Customer Journey Analytics. Om du är osäker på vilken typ av kontrakt du har, eller om du är osäker på om du har CJA-tillägget, kontaktar du din organisations Account Manager.
* Din organisation har etablerats för Adobe Experience Platform.

## Behörigheter för användaråtkomst

Om du vill skapa anslutningar, lägga till datauppsättningar osv. behöver du följande behörigheter i dialogrutan [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Om du vill hantera datauppsättningar i Experience Platform måste du vara en del av en plattformsproduktprofil som ger dig behörigheten&quot;Hantera datauppsättningar&quot;. Mer information finns i [Åtkomstkontroll i Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Om du vill skapa en anslutning till en Experience Platform-datauppsättning måste du ingå i en plattformsproduktprofil som ger dig följande behörigheter:
   * Visa scheman
   * Visa datauppsättningar
   * Hantera identitetsnamnutrymmen
   * Visa sandlådor
* Från och med 9 september 2020 måste du också läggas till som administratör för en Customer Journey Analytics-produktprofil i dialogrutan [Admin Console](https://adminconsole.adobe.com/enterprise/). Administratörer har följande behörigheter:
   * Skapa/uppdatera/ta bort anslutningar eller datavyer
   * Uppdatera/ta bort projekt, filter, beräkningstal eller segment som skapats av andra användare
   * Dela ett Workspace-projekt till alla användare
* Icke-administratörer (användare) i Customer Journey Analytics kan inte visa datavyer eller anslutningar, men kan skapa filter, projekt och beräknade värden.

### Uppdateringar om terminologi

Flera funktioner i CJA har bytt namn, jämfört med traditionella Adobe Analytics, för att passa in i branschstandarder. Några av de uppdaterade terminologin:

* Segment kallas nu för filter.
* Virtuella rapportsviter kallas nu för vyer.
* Klassificeringar kallas nu&quot;Sök efter datauppsättningar&quot;.
* Kundattribut kallas nu profildatamängder.
* Träffbehållare kallas nu Event-behållare.
* Besöksbehållare kallas nu för sessionsbehållare.
* Besöksbehållare kallas nu för personbehållare.

## Andra funktioner som bygger på Adobe Experience Platform

Customer Journey Analytics är en funktion bland många som är beroende av Adobe Experience Platform. Flera andra funktioner, som också bygger på Experience Platform, gör att du får ut så mycket som möjligt av dina data.

Med Adobe Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser. Kunddata på plattformen lagras som datauppsättningar, som består av ett schema och grupper med data. Mer information om plattformen finns på [Adobe Experience Platform Architecture Overview](https://www.adobe.io/apis/experienceplatform/home/overview.html).

Från datainmatning till direkt SQL-åtkomst - flera komponenter i Experience Platform är centrala för Customer Journey Analytics och samverkar med dem:

* [Frågetjänst](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): Använd standard-SQL för att hämta data från Adobe Experience Platform, t.ex. data från Adobe-lösningar, kunddata från första part eller andra plattformsdata. Det är ett serverlöst verktyg som gör att du kan ansluta till valfria datauppsättningar och samla in frågeresultaten som en ny datamängd som kan användas för rapportering, datavetenskapen eller för inmatning i profiltjänsten. Du kan använda frågetjänsten för att bygga dataanalysekosystem och skapa en bild av konsumenterna över deras olika interaktionskanaler. Dessa kanaler kan omfatta försäljningsställen, webb-, mobil-, CRM-system etc.
* [Kundprofil i realtid](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Identitetstjänst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Datavetenskapens arbetsyta](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) i&quot;developer&quot; option: kan ni använda färdiga artificiell intelligens (AI) och maskininlärningsmodeller i Adobe Experience Platform för att påverka olika delar av kundresan. Genom att lyfta fram dolda insikter kan ni göra bättre prognoser över kundresan, föreslå rekommenderade bästa nästa steg eller automatisera krångliga processer.
