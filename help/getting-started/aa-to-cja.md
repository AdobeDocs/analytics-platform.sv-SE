---
title: Migrera från Adobe Analytics till Customer Journey Analytics
description: Steg för att migrera från Adobe Analytics till Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 2f38b38328816a523427d73f812041904e294bc7
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 0%

---

# Förbered migrering från Adobe Analytics till Customer Journey Analytics

Innan du migrerar data från Adobe Analytics till Customer Journey Analytics bör du ta reda på dessa överväganden för att förbereda dina data och för att bli medveten om kritiska skillnader mellan de båda teknikerna.

## Förbered data

Att förbereda dina Adobe Analytics-data för en smidig övergång till Customer Journey Analytics är avgörande för dataintegriteten och för att skapa en enhetlig rapportering.

### 1. Samla in identiteter

Den kanske viktigaste faktorn när det gäller att förstå en kundresa är att veta vem kunden är i varje steg. Om du till exempel har en identifierare som finns i alla dina kanaler och motsvarande data för Customer Journey Analytics kan du sammanfoga flera källor inom CJA.
Exempel på identiteter kan vara ett kund-ID, konto-ID eller e-post-ID. Oavsett vilken identitet (och det kan finnas flera) måste du tänka på följande för varje ID:

* ID finns eller kan läggas till i alla datakällor som du vill hämta till CJA
* ID fylls i på varje datarad
* ID:t innehåller inte PII. Hash-koda allt som kan vara känsligt.
* ID använder samma format för alla källor (samma längd, samma hash-metod osv.)

I datauppsättningar som Adobe Analytics kanske ingen identitet finns på varje datarad, men det gör en sekundär identitet. I det här fallet kan flerkanalsanalys (som tidigare kallades&quot;fältbaserad namngivning&quot;) användas för att överbrygga klyftan mellan rader när en kund bara identifieras med sitt ECID och när en identitet samlas in (till exempel när en kund autentiseras). [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=en)

### 2. Justera variablerna

Den enklaste migreringen av Adobe Analytics-data till Customer Journey Analytics är att importera en [global rapportsvit](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=en) till Experience Platform med [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en). Den här kopplingen mappar dina Adobe Analytics-variabler direkt till ett XDM-schema och en datauppsättning i AEP, som i sin tur enkelt kan anslutas till CJA.

En fullständig global rapportsvit kanske inte alltid är möjlig för en implementering. Om du planerar att ta in flera rapportsviter i Customer Journey Analytics måste du planera i förväg för att få variablerna att stämma överens i alla dessa rapportsviter.

eVar1 i rapportsviten 1 kan till exempel peka på [!UICONTROL Page]. I rapportserie 2 kan eVar1 peka på [!UICONTROL Internal Campaign]. När de hämtas in till CJA blandas dessa variabler in i en enda eVar1-dimension, vilket kan leda till förvirrande och felaktig rapportering.

Om du har undvikit att gå över till en global rapportserie på grund av problem med [!UICONTROL Uniques Exceeded] eller [!UICONTROL Low Traffic], vet att CJA inte har [kardinalitetsbegränsningar för en dimension](/help/components/dimensions/high-cardinality.md). Det gör att alla unika värden kan visas och räknas.

### 3. (Re)Konfigurera era marknadsföringskanaler

De traditionella inställningarna för Adobe Analytics Marketing Channel fungerar inte på samma sätt i CJA. Det finns två orsaker:

* Bearbetningsnivån för de Adobe Analytics-data som hämtas in till Adobe Experience Platform.

* Customer Journey Analytics är rapporttidskaraktär

Adobe har publicerat [uppdaterade metodtips för implementering av marknadsföringskanaler](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). Dessa uppdaterade rekommendationer hjälper dig att få ut det mesta av de funktioner som redan finns i Adobe Analytics med Attribution IQ. De kommer också att hjälpa dig att lyckas när du går över till Customer Journey Analytics.

### 4. Bestäm dig för att använda Analytics Source Connector jämfört med Experience Platform SDK:er

Som [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) datainsamlingen utvecklas, du kommer troligen att migrera till [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en) eller [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=en) med Adobe Experience Platform Edge Network. En vanlig implementering av SDK:er skickar data till Adobe Analytics, men det finns en ny möjlighet att skicka data direkt till Adobe Experience Platform. Den kan sedan importeras till Customer Journey Analytics, samtidigt som data skickas till Adobe Analytics bevaras.

Med den här metoden utökas möjligheterna för datainsamling avsevärt: Det finns inte längre någon begränsning av antalet fält eller behovet av att mappa dataelement till props, eVars och händelser som i Analytics. Du kan använda ett obegränsat antal schemaelement av olika typer och representera dem på flera sätt med CJA [Datavyer](/help/data-views/data-views.md). Snabbheten för datatillgänglighet ökar när data skickas direkt till Adobe Experience Platform, när tiden för databehandling via Adobe Analytics tas bort.

**Fördelar med att använda Experience Platform SDK**

* Flexibelt schema för att definiera de fält du behöver
* Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)
* Inga teckenbegränsningar (100 tecken för props)
* Snabbare datatillgänglighet i Adobe Experience Platform

**Nackdelar med att använda Experience Platform SDK**

Följande Adobe Analytics-funktioner eller -komponenter stöds inte:

* Marknadsföringskanaler
* Punktfiltrering
* Geo, domän, enhetssökningar
* Analyser för mål (A4T)

## Förbered dig för kritiska skillnader

### Arbeta bekvämt med rapporttidsbearbetning

Rapporteringen i Adobe Analytics bygger på en stor mängd förbearbetning av data för att generera resultat, som den persistence du ser i [!UICONTROL eVars]. Customer Journey Analytics kör däremot dessa beräkningar vid rapportkörning.

[!UICONTROL Report time processing] öppnar möjligheten att tillämpa inställningar som är retroaktiva och skapa flera versioner av variabel beständighet utan att behöva ändra hur underliggande data samlas in.

Denna förskjutning resulterar i vissa skillnader i hur data rapporteras, särskilt för variabler som kan ha ett långt utgångsfönster. Du kan börja med att utvärdera hur rapporttidsbearbetning kan påverka din rapportering med en [virtuell rapportsvit](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### Identifiera kritiska segment och beräknade värden

Adobe Analytics segment (kallas [!UICONTROL filters] i CJA) och beräknade värden är inte kompatibla med Customer Journey Analytics. I många fall kan dessa komponenter återskapas i CJA med hjälp av nya scheman och tillgängliga data.

För att övergången ska bli så smidig som möjligt för användarna när de växlar mellan systemen ska du planera i förväg med

1. Identifiera de viktigaste komponenterna.

1. dokumentera definitioner, och

1. Identifiera vilka fält som krävs i data för att replikera dem i CJA som [Filter](/help/components/filters/filters-overview.md) och [Beräknade mått](/help/components/calc-metrics/calc-metr-overview.md).

Här är några videor som vägleder dig:

* [Flytta Adobe Analytics-segment till Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [Flytta dina beräknade värden från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)

### Andra överväganden

* Tack vare CJA-datavyer har ni större flexibilitet när det gäller att definiera mått och mått inom Customer Journey Analytics. Du kan till exempel använda värdet för en dimension för att bli definitionen av ett mätvärde. [Läs mer](/help/data-views/data-views-usecases.md)

* Om du har definierat en anpassad kalender i Adobe Analytics har du liknande kalenderfunktioner i CJA. Du måste se till att din kalender är korrekt definierad.

* I Customer Journey Analytics kan du definiera en anpassad tidsgräns för besök/session samt definiera ett mätvärde som startar en ny session. Du kan skapa datavyer med olika sessionsdefinitioner för att få insikter över vad som var möjligt i Adobe Analytics. Den här funktionen kan vara särskilt användbar för mobildatauppsättningar.

## Nästa steg

När du har flyttat till CJA kan du jämföra dina ursprungliga Adobe Analytics-data med Adobe Analytics-data som nu finns i Customer Journey Analytics. [Läs mer](/help/troubleshooting/compare.md)