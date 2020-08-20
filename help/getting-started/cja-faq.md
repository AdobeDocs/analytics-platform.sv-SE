---
title: FAQ för kundfärgsanalys
description: Customer Journey Analytics - Vanliga frågor och svar.
translation-type: tm+mt
source-git-commit: 297ed03ff59cc8d719a6bf0984e82597e8d33392
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 1%

---


# Frågor och svar

| Fråga | Svar |
| --- | --- |
| **Förutsättningar** |  |
| Behöver jag Device Graph eller Device Coop för [!UICONTROL Customer Journey Analytics]? | Nej, Private Device Graph eller Device Coop krävs inte för [!UICONTROL Customer Journey Analytics]. I själva verket har de ännu inte fått något stöd. |
| Behöver jag uppleva Cloud ID (ECID) för [!UICONTROL Customer Journey Analytics]? | Nej. [!UICONTROL Customer Journey Analytics] stöder valfritt ID i en datamängd, oavsett om det är ECID eller något annat ID som du väljer. |
| Tänk om jag behöver ETL (Extract, Transform, Load) mina data före kundens färjeanalys? | Idag behöver du samarbeta med en ETL-partner (Unifi eller Informatica) om du behöver omvandla dina data innan du sätter in dem i AEP. Om du behöver ETL när data redan har intagits, ger AEP Query Services vissa begränsade alternativ. |
| **Spekande** |  |
| Kan [!UICONTROL Customer Journey Analytics] &quot;STICK&quot; mellan olika enheter eller datauppsättningar? | Nej. [!UICONTROL Customer Journey Analytics] är ett system för att &quot;hämta ditt eget ID&quot;-analys. Det finns planer på ett bra lappverk. |
| Stöds sömnad från anonymt beteende till autentiserat beteende? | Nej, inte än. |
| **Hämta data till[!UICONTROL Customer Journey Analytics]** |  |
| Kan jag kombinera data från olika Experience Platform-sandlådor i en CJA-anslutning? | Nej, du kan inte komma åt data över sandlådor. Du kan bara kombinera datauppsättningar som finns i samma sandlåda. [Läs mer …](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Vad är förväntad latens för [!UICONTROL Customer Journey Analytics] den [!UICONTROL Experience Platform]? | <ul><li>Vid normal belastning: &lt; 60 minuter <br>**Anmärkning:** Om dataflödet genom rörledningen är ovanligt stort kan det ta upp till 24 timmar.</li><li>Säkerhetskopiera data (upp till 10 miljarder händelser): &lt; 4 veckor</li></ul> |
| Hur ansluter jag online-data till offline-data i [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] är ett analytiksystem för &quot;ta med ditt eget ID&quot;-kort. Så länge person-ID:t överensstämmer mellan datauppsättningarna [!UICONTROL Customer Journey Analytics] kan ansluta segment, attribut, flöde, utfall osv. över datauppsättningar. |
| Hur tar jag med mina offlinedata till Customer Journey Analytics? | Du måste först hämta alla data till Experience Platform innan du kan använda dem med Customer Journey Analytics. Expertplattformens datateam för ombordstigning kan hjälpa dig att ge rekommendationer eller konsultera dig vid behov. |
| Hur får jag analysdata till kundens Journey Analytics? | Analysdata kan anslutas till Experience Platform via [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). De flesta analysfält överförs i XDM-format, men andra fält är ännu inte tillgängliga (t.ex. marknadsföringskanalernas dimensioner). |
| Hur lång tid tar det att samla in datauppsättningselement i en datavy? | Några timmar att komma igång, och några dagar att backa upp de senaste 13 månaderna av data. |
| Är det nödvändigt att föra in PII-uppgifter för att upprätta samband mellan uppgifterna? | Nej, du kan använda valfritt ID, inklusive ett hash-värde för ett kund-ID som inte är PII. |
| **Traditionella analyskomponenter** |  |
| Vad betyder detta för vår traditionella Adobe Analytics-produkt? | Customer Journey Analytics är vår nästa generations analysprodukt. Att gå från våra nuvarande produkter till Customer Journey Analytics kommer att ta flera år och det kommer att krävas mycket samordning tillsammans. |
| Kan jag dela segment från Customer Journey Analytics till AEP eller andra lösningar? | Inte än. Vi undersöker nya, innovativa sätt att dela segment från Customer Journey Analytics till AEP i framtiden som inte har så lång fördröjning. Med det sagt kan du dela resultatet av Query Services till Unified Profile som en möjlig lösning. |
| Vad hände med min gamla eVar-inställning? | Varor, support och händelser i traditionell Adobe Analytics-mening finns inte längre i Customer Journey Analytics. Du har obegränsade schemaelement (dimensioner, mått, listfält). Alla de tilldelningsinställningar som du tidigare tillämpade under datainsamlingsprocessen tillämpas nu vid frågestunden. |
| Var är alla inställningar för session och variabel persistence nu? | Alla dessa inställningar används vid rapporttid i kundresanalysen, och de här inställningarna finns nu i datavyer. Ändringarna av dessa inställningar är nu retroaktiva och du kan ha flera versioner med hjälp av flera datavyer! |
| Vad händer med våra befintliga segment/beräknade mått? | Customer Journey Analytics använder inte längre eVars, props eller händelser och använder istället ett AEP-schema. Detta innebär att inget av de befintliga segmenten eller kalkmåtten är kompatibelt med kundens Journey Analytics. |
| Hur hanterar kundens researrangör? `Uniques Exceeded` begränsningar? | Customer Journey Analytics har inga unika värdebegränsningar, så du behöver inte oroa dig för dem! |
| Om jag är en befintlig [!DNL Data Workbench] Kan jag gå till Customer Journey Analytics just nu? | Det beror på. Om du är mycket beroende av UCP (Unified Customer Process), vill du vänta tills vi har sytt till implementerat. Om du redan har höga autentiseringstariffer för kunder, eller om du vill ha alla dina data på ett ställe, eller vill bli av med eVars, kan kundens Journey Analytics vara en bra passning. |

