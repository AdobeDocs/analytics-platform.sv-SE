---
title: Översikt över kundreseanalys
description: Introduktion till kundreseanalys
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Översikt över kundreseanalys

Customer Journey Analytics är en analysfunktion som gör att ni kan använda Analysis Workspace med data från Adobe Experience Platform. Den kan bryta ned, filtrera, ställa frågor och visualisera årens datavärde och kombineras med plattformens möjlighet att lagra alla typer av datamodeller och datatyper. Med hjälp av XDM ( **Experience Data Model)** kan data representeras och organiseras på ett enhetligt sätt, vara klara för kombinering och utforskande. **Med Experience Query Services** kan ni använda SQL-kompatibla verktyg och ramverk för att fråga efter och ändra alla era data.

## Jämföra CJA med traditionell Adobe Analytics

Customer Journey Analytics utökar räckvidden för Analytics genom att erbjuda lättanvända funktioner för flera kanaler och ta bort begränsningar i tidigare versioner av Adobe Analytics. Några viktiga förbättringar är:

* **Obegränsade variabler och händelser**: Begreppen eVars, props och events finns inte längre. Data fokuseras främst på dimensioner och mätvärden. Datauppsättningar kan ha en obegränsad mängd unika mått och mätvärden.
* **Obegränsade unika värden**: Adobe Experience Platform begränsas inte till några unika begränsningar, som 500 kB unika värden i traditionella rapportsviter.
* **Ändra historiska data**: Med Adobe Experience Platform kan data tas bort eller korrigeras.
* **Data** för flera rapporter: Befintliga implementeringar från flera datauppsättningar kan kombineras i Platform.

Den första versionen av kundreseanalysen innehåller många av de funktioner som ingår i Analysis Workspace. En fullständig lista finns i Funktioner för [kundreseanalys](cja-aa.md).

## Jämföra CJA med enhetsövergripande analys

[Enhetsövergripande analys](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) integreras med Adobe Experience Platform Identity Service, som använder Co-op Graph eller Private Graph, för att identifiera hur digitala enheter mappar till människor. Det är tillgängligt för Adobe Analytics Ultimate-kunder.

CJA kan integreras med Adobe Experience Platform-datauppsättningar och möjliggör flerkanalsanalys i Analysis Workspace. Även om CJA ännu inte är integrerat med Co-op- eller Private-identitetsdiagram kan du&quot;sammanföra ditt eget ID&quot; för att sammanfoga datauppsättningar, och dessa datauppsättningar kan gå utöver digitala data och inkludera både online- och offlinekontaktpunkter. CJA-kraven beskrivs närmare nedan.

## Viktiga användningsexempel

Med kundreseanalys kan ni:

* **Se kunden i ett kundsammanhang**: Du kan visa och analysera data sekventiellt, över flera kanaler. Data från callcenter, POS-system och onlineegenskaper kan kombineras till en enda rapportvy.
* **Gör insikter tillgängliga för alla**: Demokratisera dataåtkomsten och låt fler människor fatta affärsbeslut med hjälp av datainriktade insikter. Alla i organisationen som ansvarar för någon aspekt av kundupplevelsen kan fatta riktiga beslut snabbare, baserat på mer fullständiga data.
* **Utnyttja datavetenskapens styrka för era analytiker**: Med kundreseanalys kan vanliga människor använda datavetenskap för att få djupgående insikter och analyser.
* **Visualisera och interagera med era datauppsättningar med ad hoc-rapportering**: Arbetsytan kan använda alla datauppsättningar från Adobe Experience Platform som följer vissa grundläggande regler.
* **Visa icke-webbdata**: Arbetsytan är inte längre begränsad till en fast definition av en träff eller händelse. Anpassade scheman ger fullständig kontroll över data och definitioner.
* **Få bättre kontroll över datahanteringen**: Ändra data som du har överfört, skapa nya datauppsättningar och importera dem till arbetsytan. Adobe Experience Platform erbjuder verktyg för att fråga, extrahera, omvandla och läsa in, via Experience Cloud-frågetjänsten.

## Förutsättningar

Innan du kan börja använda kundreseanalys måste följande krav vara uppfyllda:

* Din organisation har ett aktivt kontrakt med Adobe Analytics för Select, Prime eller Ultimate med kundreseanalystillägget. Om du är osäker på vilken typ av kontrakt du har, eller om du är osäker på om du har CJA-tillägget, kontaktar du din organisations Account Manager.
* Din organisation har etablerats för Adobe Experience Platform.

## Behörigheter för användaråtkomst

Om du vill skapa anslutningar, lägga till datauppsättningar osv. behöver du följande behörigheter i [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Om du vill hantera datauppsättningar i Experience Platform måste du vara en del av en plattformsproduktprofil som ger dig behörigheten&quot;Hantera datauppsättningar&quot;. Mer information finns i [Åtkomstkontroll i Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Om du vill skapa en anslutning till en plattformsdatauppsättning måste du ingå i en plattformsproduktprofil som ger dig följande behörigheter:
   * Visa scheman
   * Visa datauppsättningar
   * Hantera identitetsnamnutrymmen
   * Visa sandlådor
* Om du vill få tillgång till kundreseanalys eller skapa en anslutning måste du också läggas till i en kundreseanalysproduktprofil i [Admin Console](https://adminconsole.adobe.com/enterprise/).

### Uppdateringar om terminologi

Flera funktioner i CJA har bytt namn så att de överensstämmer med branschstandarder. Några av de uppdaterade namnen:

* Segment kallas nu för filter.
* Virtuella rapportsviter kallas nu för vyer.
* Klassificeringar kallas nu&quot;Sök efter datauppsättningar&quot;.
* Kundattribut kallas nu profildatamängder.
* Träffbehållare kallas nu Event-behållare.
* Besöksbehållare kallas nu för sessionsbehållare.
* Besöksbehållare kallas nu för personbehållare.

## Andra funktioner som bygger på Adobe Experience Platform

Kundreseanalys är en funktion bland många som är beroende av Adobe Experience Platform. Flera andra funktioner, som också bygger på Platform, gör att ni får ut så mycket som möjligt av era data.

Med Adobe Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser. Kunddata på plattformen lagras som datauppsättningar, som består av ett schema och grupper med data. Mer information om plattformen finns i Översikt över [Adobe Experience Platform Architecture](https://www.adobe.io/apis/experienceplatform/home/overview.html).

Från datainmatning till direkt SQL-åtkomst - flera komponenter i Experience Platform är centrala för kundreseanalysen och fungerar tillsammans med den:

* [Frågetjänst](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): Använd standard-SQL för att hämta data från Adobe Experience Platform, till exempel data från Adobes lösning, kunddata från första part eller andra plattformsdata. Det är ett serverlöst verktyg som gör att du kan ansluta till valfria datauppsättningar och samla in frågeresultaten som en ny datamängd som kan användas för rapportering, datavetenskapen eller för inmatning i profiltjänsten. Du kan använda frågetjänsten för att bygga dataanalysekosystem och skapa en bild av konsumenterna över deras olika interaktionskanaler. Dessa kanaler kan omfatta försäljningsställen, webb-, mobil-, CRM-system etc.
* [Kundprofil](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)i realtid:
* [Identitetstjänst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) in &quot;developer&quot; option: kan ni använda färdiga artificiell intelligens (AI) och maskininlärningsmodeller i Adobe Experience Platform för att påverka olika delar av kundresan. Genom att lyfta fram dolda insikter kan ni göra bättre prognoser över kundresan, föreslå rekommenderade bästa nästa steg eller automatisera krångliga processer.
