---
title: Jämförelse med Adobe Analytics
description: Översikt över hur Customer Journey Analytics står sig jämfört med Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: cb81422ed08420fe9a16c32ddd748c9569197b17
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 0%

---

# Jämförelse med Adobe Analytics

I det här avsnittet av dokumentationen förklaras hur du jämför och förstår skillnaderna mellan Customer Journey Analytics och Adobe Analytics.

Den grundläggande skillnaden mellan de två lösningarna är den bredd på data som du (kan) tänker på när du skapar rapporter och analyser.

I CUSTOMER JOURNEY ANALYTICS *alla* kan vara en del av de data som du använder för rapportering och analys. Adobe Analytics riktar sig främst till onlinedata som samlats in från webbplatser och mobilappar. Adobe Analytics erbjuder funktioner för import av data från andra källor, men huvudsyftet med detta är att ge mer kontext till tidigare nämnda onlinedata.

## Datainsamling

Customer Journey Analytics förlitar sig på data som lagras i datauppsättningarna för Experience Platform. Det finns flera alternativ för att samla in och importera data i dessa datauppsättningar i Experience Platform. Dessa alternativ beskrivs mer ingående i [Översikt över datainmatning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analytics samlar slutligen in data i själva lösningen. Återigen har du flera alternativ för att samla in dessa data, som beskrivs mer ingående i [Adobe Analytics Implementeringshandbok](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=en).

Du kan använda dina Adobe Analytics rapportsvitsdata i Customer Journey Analytics med [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en). Den här kopplingen använder data som samlats in i Adobe Analytics för att importera i Experience Platform och sedan använda i Customer Journey Analytics. Se [Använd Adobe Analytics rapportsvitsdata i Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en) för mer information.


## Databehandling

Innan du kan rapportera data måste du ofta behandla dessa data för att säkerställa att de kan användas på rätt sätt för det ändamålet. Denna databehandling kan ske vid insamlingstid och vid rapporteringstidpunkten.

Customer Journey Analytics är generellt utformat för att fungera med insamlade och lagrade data i datauppsättningen Experience Platform vid rapporttillfället. Customer Journey Analytics har kraftfulla funktioner för bearbetning av rapporttid för att säkerställa att data är klara för rapportering och analys. Om du måste mappa, omforma och validera data innan de importeras i Experience Platform kan du använda [Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) Experience Platform.

I Adobe Analytics sker merparten av databehandlingen direkt efter datainsamlingen.

Se [Jämför databehandling i Adobe Analytics och Customer Journey Analytics](data-processing-comparisons.md) och [Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=en) för mer information.


## Terminologi

Customer Journey Analytics erbjuder flexibilitet i hur ni definierar mått och mätvärden, vilket möjliggörs av den flexibilitet som de underliggande XDM-baserade schemana (Experience Data Model) ger. Om Adobe Analytics t.ex. använder besökare, besök och träffar använder Customer Journey Analytics personer, sessioner och händelser som likvärdiga koncept, men du kan ändra namnet som du vill.

Se [Jämför terminologi för analysdata som skickas via Analytics-källkopplingen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) för mer information om skillnaderna i terminologi.


## Virtuella rapporteringsmiljöer och sandlådor

Adobe Analytics har begreppet Virtual Report Suites, som gör att ni kan segmentera insamlade data och styra åtkomsten till segmenterade data.

Customer Journey Analytics har ett liknande koncept som kallas datavyer. Datavyer är behållare som gör att du kan avgöra hur data från en anslutning ska tolkas. Det ger den ultimata flexibiliteten att specificera och konfigurera mått och mätvärden som förberedelse för rapporter och analyser.

Experience Platform erbjuder sandlådor som kan tolkas som en behållare som innehåller data och program för en viss miljö. Funktionerna i en sandlåda är inte kopplade till en virtuell rapportserie från Adobe Analytics eller datavyn Customer Journey Analytics. Adobe Analytics självt har inget samband eller någon relation med sandlådor i Experience Platform alls. Customer Journey Analytics har stöd för Experience Platform sandlådor, men det finns några viktiga saker att tänka på.

Se [Virtuella rapportsviter, datavyer, Adobe Experience Platform-sandlådor och källkopplingen för Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=en) för mer information.


## Identiteter

Customer Journey Analytics stöder de identiteter som du definierar som en del av de scheman som datauppsättningarna som innehåller dina data följer. Därför är identiteter ett grundläggande begrepp för Experience Platform, som Customer Journey Analytics använder när de skapar en [anslutning](../../connections/overview.md) (genom att definiera person-ID för varje datauppsättning) och när [sammanfogning](../../stitching/overview.md) för flerkanalsanalys. En viktig identitet som används av Experience Platform SDK:er och API är Experience Cloud ID (ECID).

Adobe Analytics använder en mer definitiv uppsättning identitetsfält, som Adobe Analytics ID (AAID). När du använder Analytics-källkopplingen får dessa Adobe Analytics-identifieringsfält särskild behandling. Se [AAID, ECID, AACUSTOMID och Analytics-källkopplingen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) för mer information.


## Funktioner

En översikt över Adobe Analytics funktioner och hur de stöds av Customer Journey Analytics finns på [Funktioner i Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





