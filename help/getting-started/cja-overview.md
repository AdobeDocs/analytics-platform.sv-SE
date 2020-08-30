---
title: Översikt över kundresanalysen
description: Introduktion till kundfärgsanalys
translation-type: tm+mt
source-git-commit: 6f5c3c073069ca7f428d971515342c1a636795e3
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 0%

---


# Översikt över kundresanalysen

Customer Journey Analytics är en analyskapacitet som gör att du kan använda Analysis Workspace med data från Adobe Experience Platform. Den kan dela upp, filtrera, fråga och visualisera årens datamängd och kombineras med plattformens förmåga att lagra alla typer av datamoller och datatyper. Använda **XDM (Experience Data Model)**, kan uppgifterna representeras och organiseras på ett enhetligt sätt och vara klara att kombineras och utforskas. **Experience Query Services** Med kan du använda SQL-kompatibla verktyg och ramar för att fråga och manipulera alla data.

## Jämföra CJA med traditionell Adobe Analytics

Customer Journey Analytics utökar analytikernas omfattning genom att erbjuda lättanvända kanalfunktioner och ta bort begränsningar i tidigare versioner av Adobe Analytics. Några anmärkningsvärda förbättringar är:

* **Obegränsade variabler och händelser**: Begreppen eVars, props och händelser finns inte längre. Data är främst inriktade på dimensioner och mått. Datauppsättningar kan ha en obegränsad mängd unika dimensioner och mått.
* **Obegränsade unika värden**: Adobe Experience Platform är inte begränsat till några unika begränsningar, t.ex. de unika 500k-värdena i traditionella rapportuppsättningar.
* **Ändra historiska data**: Med hjälp av Adobe Experience Platform kan data tas bort eller korrigeras.
* **Data för korsrapportssvitt**: Befintliga implementeringar från flera datauppsättningar kan kombineras i Platform.

I den första versionen av kundresanalysen ingår många av funktionerna i Analysis Workspace. En fullständig lista finns i [Support för kundens Journey Analytics-funktion](cja-aa.md).

## Jämföra CJA med korsenhetsanalys

[Enhetskoppling](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) integreras med Adobe Experience Platform Identity Service, antingen med Co-op Graph eller Private Graph, för att identifiera hur digitala enheter mappas till människor. Den är tillgänglig för Adobe Analytics Ultimate-kunder.

CJA integreras med Adobe Experience Platform-datauppsättningar och möjliggör analys över flera kanaler i Analysis Workspace. Även om CJA ännu inte integrerar med Coop- eller Private-identitetsdiagram kan du &quot;sammanfoga ditt eget ID&quot; för att sammanfoga datauppsättningar, och dessa datauppsättningar kan gå längre än digitala data till att inkludera både online- och offline-kontaktpunkter. Förutsättningarna för CJA beskrivs närmare nedan.

## Viktiga användningsfall

Med Customer Journey Analytics kan du:

* **Visa kunden i ett resekontext**: Du kan visa och analysera data sekventiellt och sprida flera kanaler. Data från ditt samtalscenter, POS-system och onlineegenskaper kan kombineras i en enda rapportvy.
* **Gör insikter tillgängliga för alla**: Demokratisera tillgången till data och låta fler människor fatta affärsbeslut med databaserade insikter. Alla i organisationen som har ansvar för någon aspekt av kundens erfarenhet kan fatta verkliga beslut snabbare, baserat på mer fullständiga data.
* **Utnyttja dataveteknikens kraft för dina analytiker**: Med Customer Journey Analytics kan vanliga människor använda datavetenskap för att låsa upp djupa insikter och analyser.
* **Visualisera och interagera med datauppsättningarna med hjälp av ad hoc-rapportering**: Arbetsytan kan använda alla datamängder från Adobe Experience Platform som överensstämmer med vissa grundläggande regler.
* **Visa icke-webbdata**: Arbetsytan är inte längre begränsad till en strikt definition av &quot;träff&quot; eller &quot;händelse&quot;. Anpassade scheman ger fullständig kontroll över data och definitioner.
* **Få större kontroll över datamanipuleringen**: Ändra data som du har överfört, skapa nya datauppsättningar och importera dem till arbetsytan. I Adobe Experience Platform finns verktyg för att söka, extrahera, omforma och läsa in via Experience Cloud Query Service.

## Förutsättningar

Innan du kan börja använda Customer Journey Analytics måste följande villkor vara uppfyllda:

* Din organisation har ett aktivt kontrakt med Adobe Analytics för Select, Prime eller Ultimate med tillägget Customer Journey Analytics. Om du inte är säker på vilken typ av kontrakt du har eller om du inte är säker på om du har CJA-tillägget kontaktar du organisationens kontoansvarig.
* Din organisation har etablerats för Adobe Experience Platform.

## Användaråtkomstbehörigheter

Om du vill skapa anslutningar, lägga till datauppsättningar osv. behöver du följande behörigheter i [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Om du vill hantera datauppsättningar i Experience Platform måste du ingå i en produktprofil för plattformar som ger dig behörigheten Hantera datauppsättningar. Mer information finns i [Åtkomstkontroll i Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Om du vill skapa en anslutning till en plattformsdatauppsättning måste du ingå i en produktprofil för plattformar som ger dig följande behörigheter:
   * Visa scheman
   * Visa datauppsättningar
   * Hantera identitetsnamn
   * Visa sandlådor
* Om du vill få åtkomst till kundens Journey Analytics eller skapa en anslutning måste du också läggas till i kundens Journey Analytics-produktprofil i [Admin Console](https://adminconsole.adobe.com/enterprise/).

### Terminologiuppdateringar

Flera funktioner i CJA har bytt namn för att anpassa sig till branschstandarder. Några uppdaterade namn är:

* Segment kallas nu &quot;Filter&quot;.
* Virtuella rapportpaket kallas nu &quot;Vyer&quot;.
* Klassificeringar kallas nu &quot;Uppslagsuppdatamängder&quot;.
* Kundattribut kallas nu Profildatauppsättningar.
* Träcontainrar kallas nu för &quot;Händelsebehållare&quot;.
* Besökscontainrar kallas nu &quot;Sessionsbehållare&quot;.
* Besökscontainrar kallas nu &quot;Person&quot;-containrar.

## Andra funktioner som bygger på Adobe Experience Platform

Customer Journey Analytics är en av många funktioner som är beroende av Adobe Experience Platform. Flera andra funktioner, som också är byggda på Platform, gör att du kan få ut mesta möjliga av dina data.

Med Adobe Experience Platform kan du centralisera och standardisera kunddata och -innehåll från alla system och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personliga erfarenheter. Kunddata på plattformen lagras som datamängder, som består av ett schema och datamatchar. Mer information om plattformen finns i [Översikt över Adobe Experience Platform Architecture](https://www.adobe.io/apis/experienceplatform/home/overview.html).

Från datainmatning till direkt SQL-åtkomst är flera komponenter i Experience Platform centrala för kundresanalyser och fungerar tillsammans:

* [Frågetjänst](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): Använd standard-SQL för att hämta data från Adobe Experience Platform, t.ex. Adobe-lösningsdata, data från första part eller andra plattformsdata. Det är ett serverlöst verktyg som gör att du kan ansluta till valfria datauppsättningar och fånga frågeresultaten som en ny datamängd som kan användas för rapportering, Data Science Workspace, eller för inmatning i Profiltjänsten. Du kan använda Query Service för att skapa dataanalysekosystem och skapa en bild av konsumenterna över de olika interaktionskanalerna. De här kanalerna kan omfatta försäljningsPoint-of-Sale-system, webb-, Mobile-, CRM-system osv.
* [Kundprofil i realtid](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Identitetstjänst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) I alternativet &quot;exploatör&quot;: Du kan använda förbyggda AI-modeller (artificiell intelligens) och maskininlärningsmodeller i Adobe Experience Platform för att påverka olika platser på kundresan. Genom att ångra dolda insikter kan du göra bättre förutsägelser över hela kundresan, föreslå rekommenderade bästa nästa steg eller automatisera betungande processer.
