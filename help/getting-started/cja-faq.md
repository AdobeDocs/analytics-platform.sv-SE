---
title: Frågor och svar om kundreseanalys
description: Customer Journey Analytics - Frågor och svar.
translation-type: tm+mt
source-git-commit: cca701c2a18d094ee4b172b032c125e710b51ff0

---


# Frågor och svar

| Fråga | Svar |
|---|---|
| **Förutsättningar** |  |
| Behöver ni Device Graph eller Device Coop för kundreseanalys? | Nej, privat enhetsdiagram eller enhetskoop krävs inte för kundreseanalys. Faktum är att de ännu inte stöds. |
| Behöver ni Experience Cloud ID (ECID) för kundreseanalys? | Nej, kundreseanalysen stöder alla ID:n i en datauppsättning, oavsett om det är ECID eller något annat ID du väljer. |
| Vad händer om ni behöver ETL era data före kundreseanalysen? | Idag måste ni arbeta tillsammans med en ETL-partner (Unifi eller Informatica) om ni behöver omvandla era data innan ni lägger in dem i AEP. Om du behöver ETL efter att data redan har importerats, kan AEP Query Services erbjuda några begränsade alternativ. |
| **Stitlar** |  |
| Kan kundreseanalys&quot;sy ihop&quot; mellan olika enheter eller mellan datauppsättningar? | Nej. Customer Journey Analytics är ett analyssystem för att ta fram ditt eget ID. Planer för en bra sammanslagning är på gång. |
| Stöds sammanslagning från anonymt beteende till autentiserat beteende? | Nej, inte än. |
| **Hämta data till kundreseanalys** |  |
| Vilken fördröjning förväntas för kundreseanalys på plattformen? | <ul><li>Under normal belastning: &lt; 60<br>**minuterObs!**Om dataflödet genom rörledningen är ovanligt stort kan det ta upp till 24 timmar.</li><li>Data för säkerhetskopiering (upp till 10 miljarder händelser): &lt; 4 veckor</li></ul> |
| Hur kopplar ni onlinedata till offlinedata i kundreseanalysen? | Customer Journey Analytics är ett analyssystem för att ta fram ditt eget ID. Så länge person-ID:t matchar mellan datauppsättningar kan kundreseanalysen koppla ihop segment, attribuering, flöde, utfall osv. över datauppsättningar. |
| Hur får jag in mina offlinedata i kundreseanalysen? | Kunderna måste först skicka alla data till AEP innan de kan använda dem med kundreseanalysen. Experience Platforms team för datainhämtning kan hjälpa er att ge rekommendationer eller konsulttjänster för kunder vid behov. |
| Hur får jag in analysdata i kundreseanalysen? | Analysdata kan anslutas till AEP via Analytics Data Connector. De flesta Analytics-fälten visas i XDM-format, men andra fält är ännu inte tillgängliga (som dimensionerna för marknadsföringskanaler). |
| Hur lång tid tar det att sätta ihop datauppsättningselement till en datavy? | Några timmar att komma igång och några dagar att fylla i de senaste 13 månadernas data. |
| Är det nödvändigt att hämta in PII-data för att upprätta kopplingar mellan data? | Nej, du kan använda valfritt ID, inklusive en hash av ett kund-ID som inte är PII. |
| **Traditionella analyskomponenter** |  |
| Vad innebär detta för vår traditionella Adobe Analytics-produkt? | Customer Journey Analytics är nästa generationens analysprodukt. Att gå från våra nuvarande produkter till kundreseanalyser kommer att ta år och mycket samordning tillsammans. Den här versionen är ett stort steg i den riktningen. |
| Kan jag dela segment från kundreseanalys till AEP eller andra lösningar? | Inte än. Vi letar efter nya, innovativa sätt att dela segment från kundreseanalys till AEP i framtiden som inte har en så lång fördröjning. Med andra ord kan du dela resultatet av frågetjänster till en enhetlig profil som en möjlig lösning. |
| Vad hände med min gamla eVar-inställning? | eVars, props och events i traditionell Adobe Analytics-mening finns inte längre i kundreseanalysen. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden. |
| Var finns alla inställningar för session och variabel beständighet nu? | Kundreseanalys tillämpar alla dessa inställningar vid rapporttillfället, och de här inställningarna finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer! |
| Vad händer med våra befintliga segment/beräknade värden? | Customer Journey Analytics använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inget av de befintliga segmenten eller beräkningarna är kompatibelt med kundreseanalysen. |
| Hur hanterar kundreseanalyser `Uniques Exceeded` begränsningar? | Customer Journey Analytics har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem! |
| Om jag är en befintlig [!DNL Data Workbench] kund, kan jag då gå över till kundreseanalys just nu? | Det beror på. Om ni är starkt beroende av den enhetliga kundprocessen (UCP) vill ni vänta tills vi har sytt ihop. Om ni redan har höga kundautentiseringsnivåer, eller om ni vill ha alla data på ett och samma ställe, eller vill bli av med eVars, kan kundreseanalysen vara en bra passning. |

