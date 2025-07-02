---
title: Utveckling från Adobe Analytics
description: Steg för att omvandla Adobe Analytics-data till Customer Journey Analytics-data
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 4dcf9ab808475cc3cc48cab4c076b6c3cfb66f8a
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 0%

---

# Utveckling från Adobe Analytics

## Förbered dina befintliga data

Att förbereda dina Adobe Analytics-data för en smidig övergång till Customer Journey Analytics är avgörande för dataintegriteten och för att skapa en enhetlig rapportering.

### Samla in identiteter

Den kanske viktigaste faktorn när det gäller att förstå en kundresa är att veta vem kunden är i varje steg. Om du har en identifierare som finns i alla dina kanaler och motsvarande data för Customer Journey Analytics kan du sammanfoga flera källor i Customer Journey Analytics.
Exempel på identiteter kan vara ett kund-ID, konto-ID eller e-post-ID. Oavsett vilken identitet (och det kan finnas flera) måste du tänka på följande för varje ID:

* ID finns eller kan läggas till i alla datakällor som du vill hämta till Customer Journey Analytics
* ID fylls i på varje datarad
* ID:t innehåller inte PII. Hash-koda allt som kan vara känsligt.
* ID använder samma format för alla källor (samma längd, samma hash-metod osv.)

I datauppsättningar som Adobe Analytics kanske ingen identitet finns på varje datarad, men det gör en sekundär identitet. I det här fallet kan [Flerkanalsanalys (även kallat Stitching)](/help/stitching/overview.md) användas för att överbrygga gapet mellan rader när en kund bara identifieras av deras ECID och när en identitet samlas in (till exempel när en kund autentiseras).

### Justera variablerna

Det enklaste sättet att omvandla Adobe Analytics-data till Customer Journey Analytics-data är att importera en [global rapportserie](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/global-rs) till Experience Platform med [Analytics Source Connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Den här kopplingen mappar dina Adobe Analytics-variabler direkt till ett XDM-schema och en XDM-datauppsättning i Experience Platform, som i sin tur enkelt kan anslutas till Customer Journey Analytics.

En fullständig global rapportsvit kanske inte alltid är möjlig för en implementering. Om du planerar att ta in flera rapportsviter i Customer Journey Analytics har du två alternativ:

* Planera för att få variablerna att stämma överens i alla dessa rapportsviter. EVar1 i rapportsviten 1 kan till exempel peka på [!UICONTROL Page]. I rapportserie 2 kan eVar1 peka på [!UICONTROL Internal Campaign]. När variablerna hämtas in till Customer Journey Analytics blandas de in i en enda eVar1-dimension, vilket kan leda till förvirrande och felaktig rapportering.

* Använd funktionen [Dataprep](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) för att mappa variabler. Det blir enklare om alla rapportsviter använder samma vanliga variabeldesign, men det behövs inte om du använder den nya funktionen [Dataprep](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) i Experience Platform. Det gör att du kan referera till en variabel med dess mappade värde, som finns på datastream-nivån (eller egenskapsnivån).

Om du har undvikit att gå över till en global rapportserie på grund av problem med [!UICONTROL Uniques Exceeded] eller [!UICONTROL Low Traffic], bör du vara medveten om att Customer Journey Analytics inte har några [kardinalitetsbegränsningar för en dimension](/help/components/dimensions/high-cardinality.md). Det gör att alla unika värden kan visas och räknas.

Här är ett användningsexempel för [som kombinerar rapportsviter med olika scheman](/help/use-cases/aa-data/combine-report-suites.md).

### (Re)Konfigurera era marknadsföringskanaler

De traditionella inställningarna för Adobe Analytics Marketing Channel fungerar inte på samma sätt i Customer Journey Analytics. Det finns två orsaker till skillnaden:

* Bearbetningsnivån för de Adobe Analytics-data som hämtas in till Adobe Experience Platform.

* Customer Journey Analytics rapporttidskaraktär

Adobe har publicerat [uppdaterade metodtips för implementering av marknadsföringskanal](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/mchannel-best-practices). Dessa uppdaterade rekommendationer hjälper dig att få ut det mesta av de funktioner som redan finns i Adobe Analytics med avancerade attribueringsfunktioner. Rekommendationerna hjälper dig också att lyckas när du går över till Customer Journey Analytics.

I och med introduktionen av [härledda fält](../data-views/derived-fields/derived-fields.md) som en del av Customer Journey Analytics datavyer stöds även marknadsföringskanaler på ett icke-förstörande och retroaktivt sätt med [funktionsmallen för marknadsföringskanal](../data-views/derived-fields/derived-fields.md#function-templates).

## Förbered dig för kritiska skillnader när du migrerar till Customer Journey Analytics

I takt med att ni börjar använda Customer Journey Analytics bör ni undersöka dessa steg för att förbereda era data och för att bli medvetna om kritiska skillnader mellan de båda teknikerna. Den här artikeln riktar sig till en administratörspass.

### Arbeta bekvämt med rapporttidsbearbetning {#report-time}

Rapporteringen i Adobe Analytics bygger på en stor mängd dataförbearbetning för att generera resultat, som den beständighet som du ser i [!UICONTROL eVars]. Customer Journey Analytics kör däremot dessa beräkningar vid rapportkörning.

[!UICONTROL Report time processing] öppnar möjligheten att tillämpa inställningar som är retroaktiva och skapa flera versioner av variabel beständighet utan att behöva ändra hur underliggande data samlas in.

Denna förändring ger upphov till vissa skillnader i hur data rapporteras, särskilt för variabler som kan ha ett långt utgångsfönster. Du kan börja med att utvärdera hur rapporttidsbearbetning kan påverka din rapportering med en [virtuell rapportserie](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing).

### Identifiera kritiska segment och beräknade värden {#segments-calcmetrics}

Adobe Analytics segment och beräknade värden är inte kompatibla med Customer Journey Analytics. I många fall kan dessa komponenter återskapas i Customer Journey Analytics med hjälp av nya scheman och tillgängliga data.

För att övergången ska bli så smidig som möjligt för användarna när de växlar mellan systemen ska du planera i förväg med

1. Identifiera de viktigaste komponenterna.

2. dokumentera definitioner, och

3. Identifiera vilka fält som krävs i data för att replikera dem i Customer Journey Analytics som [Segment](/help/components/segments/seg-overview.md) och [Beräknade mått](/help/components/calc-metrics/calc-metr-overview.md).

Här är några videor som vägleder dig:

* [Flytta Adobe Analytics-segment till Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/moving-adobe-analytics-segments-to-customer-journey-analytics.html)

* [Flytta dina beräknade värden från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics)

### Andra överväganden

* Tack vare kraften i Customer Journey Analytics datavyer har ni större flexibilitet när det gäller att definiera mått och mått i Customer Journey Analytics. Du kan till exempel använda värdet för en dimension för att bli definitionen av ett mätvärde. [Läs mer](/help/use-cases/data-views/data-views-usecases.md)

* Om du har definierat en anpassad kalender i Adobe Analytics har du liknande [anpassade kalenderfunktioner](/help/components/date-ranges/overview.md) i Customer Journey Analytics. Du måste se till att din kalender är korrekt definierad.

* I Customer Journey Analytics kan du definiera en anpassad sessionstimeout samt definiera ett mått som startar en ny session. Du kan skapa datavyer med olika sessionsdefinitioner för att få insikter över vad som var möjligt i Adobe Analytics. Den här funktionen kan vara särskilt användbar för mobildatauppsättningar.

* Överväg att skapa en dataordlista för användarna. Du kan också utöka SDR-filen så att den innehåller Experience Platform-fältnamnet för schemaelement.

### Nästa steg

När du har flyttat till Customer Journey Analytics kan du jämföra dina ursprungliga Adobe Analytics-data med Adobe Analytics-data som nu finns i Customer Journey Analytics. [Läs mer](/help/troubleshooting/compare.md)
