---
title: Vanliga frågor om Customer Journey Analytics
description: Customer Journey Analytics - Frågor och svar.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '1218'
ht-degree: 1%

---

# Frågor och svar

[!UICONTROL Customer Journey Analytics] (CJA) är nästa generation av analysprodukter. Här följer svar på vanliga frågor om CJA. Mer information finns i [Stöd för Customer Journey Analytics-funktioner](/help/getting-started/cja-aa.md).

## 1. Förutsättningar

| Fråga | Svar |
| --- | --- |
| Behöver jag [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] för [!UICONTROL Customer Journey Analytics]? | Nej, [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] krävs inte för [!UICONTROL Customer Journey Analytics]. Faktum är att de ännu inte stöds. |
| Behöver jag [!UICONTROL Experience Cloud ID] (ECID) för [!UICONTROL Customer Journey Analytics]? | Nej, [!UICONTROL Customer Journey Analytics] stöder alla ID:n i en datauppsättning, oavsett om det är [!UICONTROL ECID] eller något annat ID du väljer. |
| Vad händer om jag behöver ETL (Extract, Transform, Load) för mina data före [!UICONTROL Customer Journey Analytics]? | Customer Journey Analytics innehåller [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html)-funktioner som kan hjälpa dig att omvandla dina data innan de läggs in i Adobe Experience Platform Data Lake. Om du behöver ETL efter att data redan har importerats, kan [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=en#queries) erbjuda några begränsade alternativ, men det kan tillkomma extra avgifter. |

{style=&quot;table-layout:auto&quot;}

## 2. Stitching data (Cross-Channel Analytics)

| Fråga | Svar |
| --- | --- |
| Kan [!UICONTROL Customer Journey Analytics] &quot;sy ihop&quot; mellan enheter eller mellan datauppsättningar? | Ja. [!UICONTROL Customer Journey Analytics] har en sammanfogningslösning som kallas  [Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html)  (CCA). Det gör att du kan ändra datamängdens personnummer, vilket möjliggör en sömlös kombination av flera datauppsättningar. |
| Stöds sammanslagning från anonymt beteende till autentiserat beteende? | Ja. [Flerkanalsanalys ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) undersöker användardata från både autentiserade och oautentiserade sessioner för att generera ett sammanslaget ID. |
| Hur fungerar&quot;replay&quot; i CCA? | CCA&quot;repriser&quot; data baserat på unika identifierare som den har lärt sig. Replay gör att nya enheter i anslutningen sammanfogas. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=en#step-1%3A-live-stitching) |
| Hur fungerar sammanfogning av historiska data (backfill) i CCA? | När Adobe aktiveras första gången fylls data i bakåt så långt tillbaka som till början av föregående månad (upp till 60 dagar). För att denna efterfyllning ska kunna utföras måste det tillfälliga ID:t finnas i de icke sammanfogade data som är långt tillbaka i tiden. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=en#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3. Hämta data till [!UICONTROL Customer Journey Analytics]

| Fråga | Svar |
| --- | --- |
| Kan jag kombinera data från olika [!UICONTROL Adobe Experience Platform]-sandlådor i en [!UICONTROL Customer Journey Analytics]-anslutning? | Nej, du kan inte komma åt data över sandlådor. Du kan bara kombinera datauppsättningar som finns i samma sandlåda. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Vilken fördröjning förväntas för [!UICONTROL Customer Journey Analytics] på [!UICONTROL Adobe Experience Platform]? | <ul><li>Under normal belastning: &lt; 60 minuter <br>**Obs!** Om dataflödet är ovanligt stort genom pipeline kan det ta upp till 24 timmar.</li><li>Data för förifyllning (upp till 13 månaders data, oavsett storlek): &lt; 4 veckor</li></ul> |
| Hur ansluter jag onlinedata till offlinedata i [!UICONTROL Customer Journey Analytics]? | Så länge person-ID:t matchar mellan datauppsättningar kan [!UICONTROL Customer Journey Analytics] koppla filter, attribuering, flöde, utfall osv. över datauppsättningar. |
| Hur överför jag mina offlinedata till [!UICONTROL Customer Journey Analytics]? | Din rätt till Customer Journey Analytics gör att du kan importera data till Experience Platform. Du kan sedan skapa anslutningar till dessa data- och datavyer i [!UICONTROL Customer Journey Analytics] för rapportering i Analysis Workspace. Experience Platform datagrupp kan hjälpa dig att ge rekommendationer eller konsulttjänster vid behov. |
| Hur hämtar jag [!UICONTROL Adobe Analytics]-data till [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] data kan anslutas till Experience Platform via  [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). De flesta [!UICONTROL Adobe Analytics]-fält överförs i XDM-format, men andra fält är inte tillgängliga än. |
| Hur lång tid tar det att sätta ihop datauppsättningselement till en datavy? | Några timmar att komma igång och några dagar att fylla i de senaste 13 månadernas data. |
| Är det nödvändigt att hämta in PII-data för att upprätta kopplingar mellan data? | Nej, du kan använda valfritt ID, inklusive en hash av ett kund-ID som inte är PII. |

{style=&quot;table-layout:auto&quot;}

## 4. Traditionella [!UICONTROL Adobe Analytics]-komponenter

| Fråga | Svar |
| --- | --- |
| Kan jag dela/publicera filter (segment) från Customer Journey Analytics till Experience Platform enhetliga profil eller andra program från Experience Cloud? | Inte ännu, men vi arbetar aktivt för att leverera den här funktionen. |
| Vad hände med min gamla eVar? | eVars, props och events i traditionell Adobe Analytics-mening finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden. |
| Var finns alla inställningar för session och variabel beständighet nu? | [!UICONTROL Customer Journey Analytics] använder alla dessa inställningar vid rapporttillfället och dessa inställningar finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer! |
| Vad händer med våra befintliga segment/beräknade värden? | [!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inget av de befintliga segmenten eller beräkningsmåtten är kompatibelt med [!UICONTROL Customer Journey Analytics]. |
| Hur hanterar [!UICONTROL Customer Journey Analytics] `Uniques Exceeded` begränsningar? | [!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem! |
| Om jag är en befintlig [!DNL Data Workbench]-kund, kan jag då gå över till [!UICONTROL Customer Journey Analytics] nu? | Det beror på ditt användningssätt - samarbeta med ditt Adobe-kontoteam. Dina nuvarande användningsexempel kanske redan passar Customer Journey Analytics! |

{style=&quot;table-layout:auto&quot;}

## 5. Konsekvenser av borttagning av datakomponenter

När det gäller borttagning av data är vi oroade för sex typer av komponenter: sandlåda, schema, datauppsättning, anslutning, datavy och Workspace-projekt. Här följer några möjliga scenarier när du tar bort någon av dessa komponenter:

| Om du.. | Det här händer.. |
| --- | --- |
| Ta bort en sandlåda i [!UICONTROL Adobe Experience Platform] | Om du tar bort en sandlåda stoppas dataflödet till alla [!UICONTROL Customer Journey Analytics]-anslutningar till datauppsättningar i den sandlådan. För närvarande tas inte anslutningar i CJA som är kopplade till den borttagna sandlådan bort automatiskt. |
| Ta bort ett schema i [!UICONTROL Adobe Experience Platform], men inte den eller de datauppsättningar som är associerade med det här schemat | [!UICONTROL Adobe Experience Platform] tillåter inte att scheman som har en eller flera datauppsättningar associerade tas bort. En administratör med rätt behörighetsuppsättning kan dock ta bort datauppsättningarna först och sedan ta bort schemat. |
| Ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform]-datasjön | Om du tar bort en datauppsättning i AEP-datasjön avbryts dataflödet från den datauppsättningen till alla CJA-anslutningar som innehåller den datauppsättningen. Data från den datauppsättningen tas inte automatiskt bort från associerade CJA-anslutningar. |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | För närvarande kan du inte ta bort en datauppsättning i en anslutning som har sparats. Du måste ta bort hela anslutningen och börja om från början. (Kunder som har köpt CJA SKU:n kan dock ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform]-användargränssnittet.) |
| Ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform]) | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform]-datauppsättning, tas samma batch bort från alla CJA-anslutningar som innehåller den specifika gruppen.  CJA meddelas om batchborttagningar i [!UICONTROL Adobe Experience Platform]. |
| Ta bort en batch **medan den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen visas inga data eller delar av data från den gruppen i [!UICONTROL Customer Journey Analytics]. Intag kommer att återställas. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när datauppsättningen togs bort, visas data från dessa tre batchar i [!UICONTROL Customer Journey Analytics]. |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande visar att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla arbetsyteprojekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul> |
| Ta bort en datavy i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande visar att alla arbetsyteprojekt som är beroende av den här borttagna datavyn kommer att sluta fungera. |
