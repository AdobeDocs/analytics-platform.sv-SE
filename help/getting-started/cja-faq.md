---
title: Vanliga frågor om Customer Journey Analytics
description: Customer Journey Analytics - Frågor och svar.
translation-type: tm+mt
source-git-commit: eb7d7d80ee07298f7d0fe308bdc93a3435f2c381
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 1%

---


# Frågor och svar

| Fråga | Svar |
| --- | --- |
| **Förutsättningar** |  |
| Behöver jag Device Graph eller Device Coop för [!UICONTROL Customer Journey Analytics]? | Nej, privat enhetsdiagram eller enhetskopia krävs inte för [!UICONTROL Customer Journey Analytics]. Faktum är att de ännu inte stöds. |
| Behöver jag Experience Cloud ID (ECID) för [!UICONTROL Customer Journey Analytics]? | Nej, [!UICONTROL Customer Journey Analytics] har stöd för alla ID:n i en datauppsättning, oavsett om det är ECID eller något annat ID du väljer. |
| Vad händer om jag behöver ETL (Extract, Transform, Load) för mina data före Customer Journey Analytics? | Idag måste ni arbeta tillsammans med en ETL-partner (Unifi eller Informatica) om ni behöver omvandla era data innan ni lägger in dem i AEP. Om du behöver ETL efter att data redan har importerats, kan AEP Query Services erbjuda några begränsade alternativ. |
| **Stitlar** |  |
| Kan [!UICONTROL Customer Journey Analytics] &quot;sammanfoga&quot; på olika enheter eller i olika datauppsättningar? | Nej. [!UICONTROL Customer Journey Analytics] är ett&quot;plocka fram ditt eget ID&quot;-analyssystem. Planer för en bra sammanslagning är på gång. |
| Stöds sammanslagning från anonymt beteende till autentiserat beteende? | Nej, inte än. |
| **Hämta data till[!UICONTROL Customer Journey Analytics]** |  |
| Kan jag kombinera data från olika Experience Platform-sandlådor i en CJA-anslutning? | Nej, du kan inte komma åt data över sandlådor. Du kan bara kombinera datauppsättningar som finns i samma sandlåda. [Läs mer …](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Vad är förväntad fördröjning för [!UICONTROL Customer Journey Analytics] på [!UICONTROL Experience Platform]? | <ul><li>Under normal belastning: &lt; 60 minuter <br>**Obs!** Om dataflödet genom rörledningen är ovanligt stort kan det ta upp till 24 timmar.</li><li>Data för förifyllning (upp till 13 månaders data, oavsett storlek): &lt; 4 veckor</li></ul> |
| Hur ansluter jag onlinedata till offlinedata i [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] är ett&quot;hämta ditt eget ID&quot;-analyssystem. Så länge person-ID:t matchar mellan datauppsättningar, [!UICONTROL Customer Journey Analytics] kan koppla samman segment, attribuering, flöde, utfall osv. över datauppsättningar. |
| Hur överför jag offlinedata till Customer Journey Analytics? | Du måste först skicka alla data till Experience Platform innan du kan använda dem med Customer Journey Analytics. Experience Platform datagrupp kan hjälpa dig att ge rekommendationer eller konsulttjänster vid behov. |
| Hur får jag in analysdata i Customer Journey Analytics? | Analysdata kan anslutas till Experience Platform via [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). De flesta Analytics-fälten visas i XDM-format, men andra fält är ännu inte tillgängliga (som dimensionerna för marknadsföringskanaler). |
| Hur lång tid tar det att sätta ihop datauppsättningselement till en datavy? | Några timmar att komma igång och några dagar att fylla i de senaste 13 månadernas data. |
| Är det nödvändigt att hämta in PII-data för att upprätta kopplingar mellan data? | Nej, du kan använda valfritt ID, inklusive en hash av ett kund-ID som inte är PII. |
| **Traditionella analyskomponenter** |  |
| Vad innebär detta för vår traditionella Adobe Analytics-produkt? | Customer Journey Analytics är nästa generation av analysprodukt. Att utvecklas från våra nuvarande produkter till Customer Journey Analytics kommer att ta år och mycket samordning tillsammans. Mer information finns på [Funktioner i Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| Kan jag dela segment från Customer Journey Analytics till AEP eller andra lösningar? | Inte än. Vi letar efter nya, innovativa sätt att dela segment från Customer Journey Analytics till AEP i framtiden som inte har en så lång fördröjning. Med andra ord kan du dela resultatet av frågetjänster till en enhetlig profil som en möjlig lösning. |
| Vad hände med min gamla eVar? | Varor, props och händelser i traditionell Adobe Analytics-mening finns inte längre i Customer Journey Analytics. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden. |
| Var finns alla inställningar för session och variabel beständighet nu? | Customer Journey Analytics tillämpar alla dessa inställningar vid rapporttillfället och dessa inställningar finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer! |
| Vad händer med våra befintliga segment/beräknade värden? | Customer Journey Analytics använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inget av de befintliga segmenten eller beräkningstalen är kompatibelt med Customer Journey Analytics. |
| Hur hanterar Customer Journey Analytics? `Uniques Exceeded` begränsningar? | Customer Journey Analytics har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem! |
| Om jag är en befintlig [!DNL Data Workbench] kund, kan jag flytta till Customer Journey Analytics just nu? | Det beror på. Om ni är starkt beroende av den enhetliga kundprocessen (UCP) vill ni vänta tills vi har sytt ihop. Om ni redan har höga kundautentiseringsnivåer, eller om ni vill ha alla data på ett ställe, eller vill bli av med eVars, kan Customer Journey Analytics vara en bra passning. |

