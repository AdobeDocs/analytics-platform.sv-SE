---
title: Användningsexempel för målgruppsanalys
description: Läs om användningsexempel för målgruppsanalys.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 974d8a269be15d3ea6fbbcf96f2ab5457d9c9554
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 0%

---

# Användningsexempel för målgruppsanalys {#analyze-audiences-use-cases}

Med hjälp av målgruppsanalys kan Experience Platform rapportera medlemskapsdata i Customer Journey Analytics. Detta uppnås genom konfigurationer som hanteras via konfigurationsguiden för målgruppsanalys, som hjälper dig att avgöra vilken profildatauppsättning du gillar, tillsammans med andra parametrar och konfigurationsinformation. (Mer detaljerad översiktsinformation finns i [Översikt över målgruppsanalys](/help/connections/audience-analysis/audience-analysis-overview.md).)

Det här dokumentet innehåller exempel på användningsfall som markerar det värde som Audience Analysis tillhandahåller. Innan du granskar användningsexemplen bör du bekanta dig med rapporternas överväganden nedan. Det är viktigt att tänka på detta när du går igenom dina användningsfall, eftersom de kan påverka det slutliga resultatet av dina rapporter.

## Rapporteringshändelser

Den första versionen av Audience Analysis lägger grunden till det arbete som krävs för bearbetning och inhämtning av Experience Platform-målgrupper till Customer Journey Analytics. När du gör en analys är det viktigt att tänka på flera faktorer som kan påverka resultatet i olika Workspace-projekt:

* **Information om målgruppsmedlemskap gäller endast för föregående dag (&quot;igår&quot;)**: Information om målgruppsmedlemskap innehåller alltid den senaste profilögonblicksbildsdatauppsättningen som genererats av Unified Profile Service. Den här profildatauppsättningen är en ögonblicksbild varje dag och gäller bara för föregående dag (&quot;igår&quot;), där den automatiskt genereras om och bearbetas varje natt. Målgruppsdimensioner är tillgängliga för rapportering och uppdelningar, inte för att rekonstruera historiska målgruppstillstånd.

   * Exempel: Oavsett vilket tidsfönster som valts för rapporteringen kommer den rapportabla målgruppen i CJA alltid att respektera medlemskapsstatusen i den senaste ögonblicksbilden av den importerade profilen (&quot;igår&quot;).

      * Genom att utöka tidsfönstret för rapportering till&quot;senaste 30 dagarna&quot;, kommer till exempel fler händelser att ingå och ge intryck av att målgruppens storlek ändras. Men målgruppens profilkomposition kommer alltid att matcha ögonblicksbilden av &quot;igår&quot; oavsett vilket tidsfönster som valts.

* **Dimensioner måste ha en motsvarande händelse som ska inkluderas**: Målgruppsanalysdimensioner kan bara analyseras där motsvarande händelser finns i CJA. Om ett beteende, en kanal eller en livscykel inte representeras som en händelse i CJA-anslutningen kan den inte analyseras.

   * Exempel: En målgrupp som används för att rikta in sig på personer med en annons skulle omfatta betydligt fler personer i RTCDP än i CJA målgrupp. Detta beror på att CJA-publiken är begränsad till personer som hade en händelse i CJA under rapportperioden.

* **Identitetsupplösningen baseras enbart på ett enda namnutrymme**: Identitetsupplösningen är helt beroende av det valda identitetsnamnutrymmet som en del av målgruppsanalyskonfigurationen. Analysen kommer att begränsas till detta ID-namnutrymme, och händelser som ligger utanför det kommer inte att vara tillgängliga för rapportering av målgruppsanalyser.

   * Exempel: För en sammanfogad händelsedatamängd som kombinerar CRM och ECID, och Audience Analysis-konfigurationen använder CRM-ID:t, identifieras endast rader som innehåller ett CRM-ID som en del av den rapporterande målgruppen i CJA. Därför kan den resulterande målgruppen bli mindre än förväntat.

## Exempel på användningsområden

### Användningsfall 1

Förstå hur en viss målgrupp beter sig i en viss kanal (t.ex. på webben eller i en app) för att besvara frågor som:

* _&quot;Vad gör medlemmar i högvärdesprognoser på webbplatsen just nu (sidor, funktioner, resurser)?&quot;_

* _&quot;Vilka kampanjer och vilket innehåll är för högt för den här målgruppen jämfört med alla andra?&quot;_

#### Konfigurationsflöde

1. Konfigurera målgruppsanalys i CJA för ett enskilt ID-namnområde (t.ex. ECID eller CRM_ID) och en webbaserad datavy.

   * Detta kommer automatiskt att importera målgruppsmedlemskapsdata till den valda anslutningen via export av dagliga ögonblicksbilder av profiler

   * Vi rekommenderar att du väljer det identitetsnamnutrymme som du tror har mest täckning i din händelsedatamängd

1. Bygg dina Workspace-projekt för att

   * Dela upp målgruppsnamn per sida, produkt, kampanj, enhet osv.

   * Jämför målgrupper med icke-målgrupper (eller mot en annan målgrupp) om mätvärden som sessioner, konverteringsgrad, intäkter per person.

1. Få insikt i kanaloptimeringsstrategier (t.ex. målgruppsregler, innehåll eller erbjudandejustering).

#### Överväganden om identitetsupplösning

| Använd skiftläge | Kärnfrågan | Identitetsupplösning | High-auth/single-namespace orgs (händelser som redan finns under 1 person-ID, t.ex. login/CRM) | Fragmenterade/flernamnsorgan (händelser under ECID + CRM + andra) |
|---------|----------|---------|---------|---------|
| Dagens målgruppsbeteende - djupdykning | _&quot;Vad gör målgrupp X i kanal Y just nu?&quot; (sidor, resurser, innehåll, erbjudanden)_ | Händelser och profiler måste dela ett konsekvent ID-namnutrymme i CJA-anslutningen och Audience Analysis-konfigurationen för optimal täckning. | De flesta aktiviteter är redan kopplade till ett inloggnings-/CRM-ID, så målgrupper från AEP kan ansluta till beteendedata i CJA på ett rent sätt. <p>Ni får en tydlig bild av vad varje målgrupp gör i en viss kanal med minimala förväntade rapporteringsluckor.</p> | Även om de är sammanfogade med en sammanfogad datauppsättning begränsas rapporteringen fortfarande till det enda identitetsnamnutrymme som valts i konfigurationen. <p>Om vissa kunder finns under andra ID:n inkluderas inte deras beteende, vilket kan leda till en partiell vy under rapportering.</p> |

### Användningsfall 2

Hjälp marknadsförare och resedesigners att förstå vilka målgrupper som överlappar, så att de kan deduplicera upplevelser och undvika erbjudandekollisioner mellan kampanjer:

* _&quot;Hur mycket överlappar lojalitetsmedlemmar, Cart Abandoners och High Propensity to Churn idag?&quot;_

* _&quot;Vilka målgrupper är mest benägna att kollidera med värdefulla erbjudanden den här veckan?&quot;_

#### Konfigurationsflöde

1. Konfigurera målgruppsanalys i CJA för ett enskilt ID-namnområde som är anpassat till aktivering av RTCDP/AJO (t.ex. CRM_ID om resor är personbaserade).

   * Detta kommer automatiskt att importera målgruppsmedlemskapsdata till den valda anslutningen via export av ögonblicksbilder per dag.

   * Detta kan användas för att berika en befintlig datavy som redan driver viktiga engagemangs- och konverteringsrapporter.

1. Använd mallen för översiktlig målgruppsanalys som är färdig att användas och överlappa visualiseringar:

   * Kör publikskärningar och över-/underindexeringsvyer (t.ex. % av Cart Abandoners som också är i Loyalty Gold).

   * Segmentöverlappning efter kärndimensioner (t.ex. enhetstyp, produktintresse) för att förstå var konflikter är som störst.

1. Använd insikterna för att finjustera viktiga aspekter, som:

   * Skapa konfliktregler eller regler för marknadsföringsåtgärder i RTCDP och AJO.

   * Målgruppsförbättring (t.ex. skärpning av måldefinitioner där överlappning är för hög).

#### Överväganden om identitetsupplösning

| Använd skiftläge | Kärnfrågan | Identitetsupplösning | High-auth/single-namespace orgs (händelser som redan finns under 1 person-ID, t.ex. login/CRM) | Fragmenterade/flernamnsorgan (händelser under ECID + CRM + andra) |
|---------|----------|---------|---------|---------|
| Målgruppsöverlappning och kollisionsidentifiering | _&quot;Vilka målgrupper överlappar idag så att vi kan undvika erbjudandekollisioner?&quot;_ | Överlappning beräknas bara för målgrupper som använder samma person-ID och med aktivitet i CJA-anslutningen. | Eftersom de flesta aktiviteter redan är kopplade till ett enda inloggnings-/CRM-ID förväntas detta ge en tillförlitlig överlappningskarta över olika målgrupper. <p>Överlappningskartor ger en tillförlitlig bild av vilka målgrupper som kolliderar och var man ska tillämpa undertryckningar eller prioritetsregler.</p> | Om delar av resan lever under andra ID:n (t.ex. anonym surfning med endast ECID, call-center ID:n) visas inte dessa händelser i överlappningsanalyser. <p>Personer kan fortfarande finnas i flera namnutrymmen.</p><p>Överlappningen baseras på det identitetsnamnutrymme som ingår i konfigurationen. Om vissa profiler fortfarande delas mellan ID:n kan överlappning vara en underrapport om sanna kollisioner.</p> |

### Användningsfall 3

Förstå beteendet hos kunder som nyligen lämnat en viktig målgrupp och vad de gjorde runt den utgången för att få svar på frågor som:

* _&quot;Vem har just lämnat en nyckelpublik och vad har de gjort runt utgången?&quot;_

* _&quot;Vad hände precis innan du slutade? (fel, lågt engagemang, prisändringar).&quot;_

#### Konfigurationsflöde

1. Konfigurera målgruppsanalys i CJA för ett enskilt ID-namnområde (t.ex. CRM_ID eller inloggnings-ID) och relevanta datavyer (webb, app, CRM, etc.).

   * Detta infogar automatiskt målgruppsmedlemskapsdata i den anslutning du valt via export av ögonblicksbilder per dag.

   * Vi rekommenderar att du väljer det identitetsnamnutrymme som du tror har mest täckning i din händelsedatamängd.

1. Använd följande i mallen för målgruppsanalys/målgruppsöversikt (fast _i går_):

   * Aktuella medlemmar: som fortfarande är i publiken

   * Avslutade målgruppen: som lämnade i går

1. Bygg dina Workspace-projekt för att

   * Filtrera till profiler som slutade Audience X igår och titta sedan på:

      * Deras beteende leder till avslut (senaste sessioner, fel, pris-/erbjudandeexponering, kanalmix).

      * Deras beteende efter avslutning (bytte de produkter, nedgraderade, gick vilande).

   * Bryt ner kohorten efter region, enhet, tid och värdenivå för att hitta slagkraftiga fickor.

1. Använd insikterna för reseuppdateringar och vinn-tillbaka-målgruppskonfigurationer i RTCDP eller AJO.

#### Överväganden om identitetsupplösning

| Använd skiftläge | Kärnfrågan | Identitetsupplösning | High-auth/single-namespace orgs (händelser som redan finns under 1 person-ID, t.ex. login/CRM) | Fragmenterade/flernamnsorgan (händelser under ECID + CRM + andra) |
|---------|----------|---------|---------|---------|
| Utgångna målgrupper - bortfallsanalys | _&quot;Vem har just lämnat en nyckelpublik?&quot;_ <p>_&quot;Vad gjorde de runt att avsluta?&quot;_</p> | Målgruppsavslutning spåras med samma person-ID som används för anslutningen och målgruppskonfigurationen. | Utträden som mäts på ett stabilt inloggnings-/CRM-ID tenderar att reflektera beteendeförändringar. <p>När någon lämnar en målgrupp på detta ID betyder det vanligtvis en verklig förändring (bortfall, nedgradering, inaktivitet).</p><p>Ni kan analysera deras senaste beteenden för att finjustera resorna och vinna tillbaka erbjudanden med tillförsikt.</p> | Utträden är bara synliga där profiler och händelser delar det konfigurerade ID:t och därför krävs noggrann tolkning.<p>Använd utgångna kohorter som ett starkt tips eller en stark signal, men vi rekommenderar att du dubbelkontrollerar med andra datapunkter före kritiska beslut.</p> |

