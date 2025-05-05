---
title: Jämförelse med Adobe Analytics
description: Översikt över hur Customer Journey Analytics står sig jämfört med Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Jämförelse med Adobe Analytics

I det här avsnittet av dokumentationen förklaras hur du jämför och förstår skillnaderna mellan Adobe Customer Journey Analytics och Adobe Analytics.

Den grundläggande skillnaden mellan de två lösningarna är den bredd på data som du (kan) tänker på när du skapar rapporter och analyser.

I Customer Journey Analytics kan *alla*-datakällan ingå i de data som du använder för rapportering och analys. Adobe Analytics riktar sig främst till onlinedata som samlats in från webbplatser och mobilappar. Adobe Analytics erbjuder funktioner för import av data från andra källor, men det huvudsakliga syftet med detta är att tillhandahålla mer kontext runt tidigare nämnda onlinedata.

## Datainsamling

Customer Journey Analytics förlitar sig på data som lagras i Adobe Experience Platform datamängder. Du kan samla in och importera data från dessa datauppsättningar i Experience Platform på flera olika sätt. De här alternativen beskrivs mer ingående i [Översikt över datainmatning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=sv-SE).

Adobe Analytics samlar slutligen in data i själva lösningen. Återigen har du flera alternativ för att samla in dessa data, som beskrivs mer ingående i [Adobe Analytics Implementeringshandbok](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=sv-SE).

Du kan använda dina Adobe Analytics rapportsvitsdata i Customer Journey Analytics med [Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE). Den här kopplingen importerar data som samlats in i Adobe Analytics till Experience Platform. Du kan sedan skapa en anslutning till den här datauppsättningen i Customer Journey Analytics. Mer information finns i [Använd Adobe Analytics rapportsvitsdata i Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=sv-SE).


## Databehandling

Innan du kan rapportera data måste du ofta bearbeta dessa data för att säkerställa att de kan användas på rätt sätt för rapportering. Databearbetning kan ske vid insamlingstid och vid rapporteringstid.

Customer Journey Analytics är generellt utformat för att fungera med insamlade och lagrade data i datauppsättningen Experience Platform vid rapporttillfället. Customer Journey Analytics har kraftfulla funktioner för bearbetning av rapporttid för att säkerställa att data är klara för rapportering och analys. Om du måste mappa, omforma och validera data innan de importeras i Experience Platform kan du använda funktionen [Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=sv-SE) i Experience Platform.

I Adobe Analytics sker merparten av databehandlingen direkt efter datainsamlingen.

Mer information finns i [Jämför databearbetning i Adobe Analytics och Customer Journey Analytics](data-processing-comparisons.md) och [Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=sv-SE).


## Terminologi

Customer Journey Analytics erbjuder flexibilitet i hur ni definierar mått och mätvärden, vilket möjliggörs av den flexibilitet som de underliggande XDM-baserade schemana (Experience Data Model) ger. Om Adobe Analytics t.ex. använder besökare, besök och träffar använder Customer Journey Analytics personer, sessioner och händelser som likvärdiga begrepp (du kan ändra namnet som du vill).

Mer information om skillnaderna i terminologi finns i [Jämför terminologi för analysdata som skickas via Analytics-källkopplingen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=sv-SE).


## Virtuella rapporteringsmiljöer och sandlådor

Adobe Analytics har begreppet virtuella rapportsviter, som gör det möjligt att segmentera insamlade data och styra åtkomsten till segmenterade data.

Customer Journey Analytics har ett liknande koncept, som kallas datavyer. Datavyer är behållare som gör att du kan avgöra hur data från en anslutning ska tolkas. De erbjuder den ultimata flexibiliteten att specificera och konfigurera mått och mätvärden som förberedelse för rapporter och analyser.

Experience Platform erbjuder sandlådor som kan tolkas som en behållare som innehåller data och program för en viss miljö. Funktionerna i en sandlåda är inte kopplade till en virtuell rapportserie från Adobe Analytics eller datavyn Customer Journey Analytics. Adobe Analytics självt har inget samband eller någon relation med sandlådor i Experience Platform alls. Customer Journey Analytics har stöd för Experience Platform sandlådor, men det finns några viktiga saker att tänka på.

Mer information finns i [Virtuella rapportsviter, datavyer, Adobe Experience Platform-sandlådor och Analytics-källkopplingen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=sv-SE).


## Identiteter

Customer Journey Analytics stöder de identiteter som du definierar som en del av de scheman som datauppsättningarna som innehåller dina data följer. Därför är identiteter ett grundläggande begrepp för Experience Platform, som Customer Journey Analytics använder när en [anslutning](../../connections/overview.md) skapas (genom att personernas ID definieras för varje datauppsättning) och när [sammanfogning](../../stitching/overview.md) används för flerkanalsanalys. En viktig identitet som används av Experience Platform SDK:er och API är Experience Cloud ID (ECID).

Adobe Analytics använder en mer definitiv uppsättning identitetsfält, som Adobe Analytics ID (AAID). När du använder Analytics-källkopplingen får dessa Adobe Analytics-identifieringsfält särskild behandling. Mer information finns i [AAID, ECID, AACUSTOMID och Analytics-källkopplingen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=sv-SE).


## Funktioner som stöds

En översikt över Adobe Analytics-funktioner och hur dessa funktioner stöds av Customer Journey Analytics finns på [Customer Journey Analytics-support](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=sv-SE).
