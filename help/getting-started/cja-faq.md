---
title: Vanliga frågor om Customer Journey Analytics
description: Customer Journey Analytics - Frågor och svar.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---

# Frågor och svar

## Förutsättningar

| Fråga | Svar |
| --- | --- |
| Behöver jag [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] för [!UICONTROL Customer Journey Analytics]? | Nej, [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] krävs inte för [!UICONTROL Customer Journey Analytics]. Faktum är att de ännu inte stöds. |
| Behöver jag [!UICONTROL Experience Cloud ID] (ECID) för [!UICONTROL Customer Journey Analytics]? | Nej, [!UICONTROL Customer Journey Analytics] stöder alla ID:n i en datauppsättning, oavsett om det är [!UICONTROL ECID] eller något annat ID du väljer. |
| Vad händer om jag behöver ETL (Extract, Transform, Load) för mina data före [!UICONTROL Customer Journey Analytics]? | Idag måste ni arbeta tillsammans med en ETL-partner (Unifi eller Informatica) om ni behöver omvandla era data innan ni lägger in dem i AEP. Om du behöver ETL efter att data redan har importerats, kan [!UICONTROL Adobe Experience Platform Query Services] erbjuda några begränsade alternativ. |

## Sätta data

| Fråga | Svar |
| --- | --- |
| Kan [!UICONTROL Customer Journey Analytics] &quot;sy ihop&quot; mellan enheter eller mellan datauppsättningar? | Ja. [!UICONTROL Customer Journey Analytics] är ett&quot;plocka fram ditt eget ID&quot;-analyssystem. Vi lanserade en lösning som stygn i november 2020. Läs mer. |
| Stöds sammanslagning från anonymt beteende till autentiserat beteende? | Nej, inte än. |

## Hämta data till [!UICONTROL Customer Journey Analytics]

| Fråga | Svar |
| --- | --- |
| Kan jag kombinera data från olika [!UICONTROL Adobe Experience Platform]-sandlådor i en [!UICONTROL Customer Journey Analytics]-anslutning? | Nej, du kan inte komma åt data över sandlådor. Du kan bara kombinera datauppsättningar som finns i samma sandlåda. [Läs mer …](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Vilken fördröjning förväntas för [!UICONTROL Customer Journey Analytics] på [!UICONTROL Adobe Experience Platform]? | <ul><li>Under normal belastning: &lt; 60 minuter <br>**Obs!** Om dataflödet är ovanligt stort genom pipeline kan det ta upp till 24 timmar.</li><li>Data för förifyllning (upp till 13 månaders data, oavsett storlek): &lt; 4 veckor</li></ul> |
| Hur ansluter jag onlinedata till offlinedata i [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] är ett&quot;hämta ditt eget ID&quot;-analyssystem. Så länge person-ID:t matchar mellan datauppsättningar kan [!UICONTROL Customer Journey Analytics] koppla filter, attribuering, flöde, utfall osv. över datauppsättningar. |
| Hur överför jag mina offlinedata till [!UICONTROL Customer Journey Analytics]? | Du måste först överföra alla data till Experience Platform innan du kan använda dem med [!UICONTROL Customer Journey Analytics]. Experience Platform datagrupp kan hjälpa dig att ge rekommendationer eller konsulttjänster vid behov. |
| Hur hämtar jag [!UICONTROL Adobe Analytics]-data till [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] data kan anslutas till Experience Platform via  [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). De flesta [!UICONTROL Adobe Analytics]-fält överförs i XDM-format, men andra fält är ännu inte tillgängliga (som [!UICONTROL Marketing Channels]-dimensioner). |
| Hur lång tid tar det att sätta ihop datauppsättningselement till en datavy? | Några timmar att komma igång och några dagar att fylla i de senaste 13 månadernas data. |
| Är det nödvändigt att hämta in PII-data för att upprätta kopplingar mellan data? | Nej, du kan använda valfritt ID, inklusive en hash av ett kund-ID som inte är PII. |

## Traditionella [!UICONTROL Adobe Analytics]-komponenter

| Fråga | Svar |
| --- | --- |
| Vad innebär detta för vår traditionella [!UICONTROL Adobe Analytics]-produkt? | [!UICONTROL Customer Journey Analytics] är vår nästa generation av analysprodukter. Att gå från våra nuvarande produkter till [!UICONTROL Customer Journey Analytics] kommer att ta år och mycket samordning. Mer information finns i [Stöd för Customer Journey Analytics-funktioner](/help/getting-started/cja-aa.md). |
| Kan jag dela filter från [!UICONTROL Customer Journey Analytics] till AEP eller andra lösningar? | Inte än. Vi letar efter nya, innovativa sätt att dela filter från [!UICONTROL Customer Journey Analytics] till AEP i framtiden som inte har en så lång fördröjning. Med andra ord kan du dela resultatet av frågetjänster till en enhetlig profil som en möjlig lösning. |
| Vad hände med min gamla eVar? | eVars, props och events i traditionell Adobe Analytics-mening finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden. |
| Var finns alla inställningar för session och variabel beständighet nu? | [!UICONTROL Customer Journey Analytics] använder alla dessa inställningar vid rapporttillfället och dessa inställningar finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer! |
| Vad händer med våra befintliga segment/beräknade värden? | [!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inget av de befintliga segmenten eller beräkningsmåtten är kompatibelt med [!UICONTROL Customer Journey Analytics]. |
| Hur hanterar [!UICONTROL Customer Journey Analytics] `Uniques Exceeded` begränsningar? | [!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem! |
| Om jag är en befintlig [!DNL Data Workbench]-kund, kan jag då gå över till [!UICONTROL Customer Journey Analytics] nu? | Det beror på. Om ni är starkt beroende av den enhetliga kundprocessen (UCP) vill ni vänta tills vi har sytt ihop. Om ni redan har höga kundautentiseringsnivåer, eller om ni vill ha alla data på ett ställe, eller vill bli av med eVars, kan Customer Journey Analytics vara en bra passning. |

## Konsekvenser av borttagning av datakomponenter

När det gäller borttagning är vi oroade för sex komponenter: sandbox-, schema-, dataset-, connection-, data view- och Workspace-projekt. Här följer några möjliga scenarier när du tar bort någon av dessa komponenter:

| Tänk om jag.. | Det här händer.. |
| --- | --- |
| Vill du ta bort en sandlåda i [!UICONTROL Adobe Experience Platform]? | Om du tar bort en sandlåda stoppas dataflödet till alla [!UICONTROL Customer Journey Analytics]-anslutningar till datauppsättningar i den sandlådan. För närvarande tas inte anslutningar i CJA som är kopplade till den sandlådan bort automatiskt. |
| Vill du ta bort ett schema i [!UICONTROL Adobe Experience Platform], men inte de data som är associerade med det här schemat? | [!UICONTROL Adobe Experience Platform] tillåter inte att scheman som har en eller flera datauppsättningar associerade tas bort. En administratör med rätt behörighetsuppsättning kan dock ta bort datauppsättningarna först och sedan ta bort schemat. |
| Vill du ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform]? | Om du tar bort en datauppsättning i AEP avbryts dataflödet från den datauppsättningen till alla anslutningar som innehåller den datauppsättningen. Data från den datauppsättningen tas inte automatiskt bort från associerade CJA-anslutningar. |
| Vill du ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics]? | För närvarande kan du inte ta bort en datauppsättning i en anslutning som har sparats. Du måste ta bort hela anslutningen och börja om från början. (Du kan dock ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform].) |
| Vill du ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform])? | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform]-datauppsättning, tas samma batch bort från alla CJA-anslutningar som innehåller den specifika gruppen.  CJA meddelas om batchborttagningar i [!UICONTROL Adobe Experience Platform]. |
| Vill du ta bort en batch **medan den hämtas** till [!UICONTROL Customer Journey Analytics]? | Om det bara finns en batch i datauppsättningen visas inga data eller delar av data från den gruppen i [!UICONTROL Customer Journey Analytics]. Intag kommer att återställas. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när datauppsättningen togs bort, visas data från dessa tre batchar i [!UICONTROL Customer Journey Analytics]. |
| Vill du ta bort en anslutning i [!UICONTROL Customer Journey Analytics]? | Ett felmeddelande visar att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla arbetsyteprojekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul> |
| Vill du ta bort en datavy i [!UICONTROL Customer Journey Analytics]? | Ett felmeddelande visar att alla arbetsyteprojekt som är beroende av den här borttagna datavyn kommer att sluta fungera. |
