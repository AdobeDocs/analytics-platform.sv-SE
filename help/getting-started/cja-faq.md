---
title: Vanliga frågor om Customer Journey Analytics
description: Customer Journey Analytics - Frågor och svar.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
source-git-commit: 3c6d1cd351df9a8db8e2fcfe66ecf713ae680c16
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 0%

---

# Frågor och svar

Adobe Customer Journey Analytics är nästa generation av analysprodukter. Här följer svar på vanliga frågor om Customer Journey Analytics. Mer information finns på [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## 1. Förutsättningar {#prerequisites}

+++**Behöver jag [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]?**

Nej, [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] krävs inte för [!UICONTROL Customer Journey Analytics]. Faktum är att de ännu inte stöds.

+++


+++**Behöver jag [!UICONTROL Experience Cloud ID] (ECID) för [!UICONTROL Customer Journey Analytics]?**

Nej, [!UICONTROL Customer Journey Analytics] stöder alla ID:n i en datauppsättning, oavsett om [!UICONTROL ECID] eller något annat ID du väljer.

+++


+++**Vad händer om jag behöver ETL (Extract, Transform, Load) före [!UICONTROL Customer Journey Analytics]?**

Customer Journey Analytics omfattar [Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html) funktioner för att omvandla data innan de läggs in i Adobe Experience Platform datasjön. Om du behöver ETL efter att data redan har importerats, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html#queries) innehåller några begränsade alternativ, men det kan tillkomma extra avgifter.

+++


## 2. Stitching data (Cross-Channel Analytics) {#stitching}

+++**Kan [!UICONTROL Customer Journey Analytics] &quot;sammanfoga&quot; på olika enheter eller i olika datauppsättningar?**

Ja. [!UICONTROL Customer Journey Analytics] har en sytlösning som kallas [Flerkanalsanalys](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) (CCA). Det gör att du kan ändra datamängdens personnummer, vilket möjliggör en sömlös kombination av flera datauppsättningar.

+++


+++**Stöds sammanslagning från anonymt beteende till autentiserat beteende?**

Ja. [Flerkanalsanalys](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) läser användardata från både autentiserade och oautentiserade sessioner för att generera ett sammanfogat ID.

+++


+++**Hur fungerar&quot;replay&quot; i CCA?**

CCA&quot;repriser&quot; data baserat på unika identifierare som den har lärt sig. Replay gör att nya enheter i anslutningen sammanfogas. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html#step-1%3A-live-stitching)

+++


+++**Hur fungerar sammanfogning av historiska data (backfill) i CCA?**

När Adobe aktiveras första gången fylls data i bakåt så långt tillbaka som till början av föregående månad (upp till 60 dagar). För att denna efterfyllning ska kunna utföras måste det tillfälliga ID:t finnas i de icke sammanfogade data som är långt tillbaka i tiden. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html#enable-cross-channel-analytics)

+++


+++**Vad är förväntat beteende för icke-sammanfogade profildatauppsättningsposter?**

**Exempel på scenario**: Du ansluter till två datauppsättningar i en Customer Journey Analytics-anslutning genom att använda `CRMid` som person-ID. Ett är en webbhändelsedatamängd med `CRMid` i alla poster. Den andra datauppsättningen är en CRM-profildatauppsättning. 40 % av CRM-datauppsättningen har `CRMid` finns i webbhändelsedatamängden. De andra 60 % finns inte i webbhändelsedatamängden. Visas de här posterna i rapporter i Analysis Workspace?<p> **Svar**: Profilrader som inte har några kopplade händelser lagras i Customer Journey Analytics. Du kan dock inte visa dem i Analysis Workspace förrän en händelse som är kopplad till detta ID visas.

+++

## 3. Hämta data till [!UICONTROL Customer Journey Analytics] {#ingest}

+++**Kan jag kombinera data från olika [!UICONTROL Adobe Experience Platform] sandlådor i en [!UICONTROL Customer Journey Analytics] anslutning?**

Nej, du kan inte komma åt data över sandlådor. Du kan bara kombinera datauppsättningar som finns i samma sandlåda. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets)

+++


+++**Hur ansluter jag onlinedata till offlinedata i [!UICONTROL Customer Journey Analytics]?**

Så länge person-ID:t matchar mellan datauppsättningar, [!UICONTROL Customer Journey Analytics] kan koppla filter, attribuering, flöde, utfall osv. över datauppsättningar.

+++


+++**Hur överför jag offlinedata till [!UICONTROL Customer Journey Analytics]?**

Din rätt till Customer Journey Analytics gör att du kan importera data till Experience Platform. Sedan kan du skapa anslutningar till dessa data- och datavyer i [!UICONTROL Customer Journey Analytics], för rapporter i Analysis Workspace. Experience Platform datagrupp kan hjälpa dig att ge rekommendationer eller konsulttjänster vid behov.

+++


+++**Hur får jag [!UICONTROL Adobe Analytics] data till [!UICONTROL Customer Journey Analytics]?**

[!UICONTROL Adobe Analytics] data kan anslutas till Experience Platform via [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Mest [!UICONTROL Adobe Analytics] fält hämtas till XDM-format, men andra fält är inte tillgängliga ännu.

+++


+++**Hur lång tid tar det att sätta ihop datauppsättningselement till en datavy?**

Några timmar att komma igång och några dagar att fylla i de senaste 13 månadernas data.

+++


+++**Är det nödvändigt att hämta in PII-data för att upprätta kopplingar mellan data?**

Nej, du kan använda valfritt ID, inklusive en hash av ett kund-ID som inte är PII.

+++


+++**Vilka är gränserna för inmatning av tidigare eller framtida datum/tidsstämplar i datauppsättningar för händelsen Customer Journey Analytics?**

<ul><li>Angående tidigare datum/tidsstämplar: Händelsedata som är upp till 10 år gamla.</li><li>Om framtida datum/tidsstämplar: Händelsedata (prediktiva) upp till en månad i framtiden.</li></ul>

+++


## 4. Svarstidsfrågor {#latency}

>[!NOTE]
>Det finns ingen fast datastorlek i Customer Journey Analytics och därför kan Adobe inte binda sig till en standardintag. Vi arbetar aktivt för att minska dessa latenser genom nya uppdateringar och optimering av intaget.

+++**Vad är förväntad fördröjning för [!UICONTROL Customer Journey Analytics] data på [!UICONTROL Adobe Experience Platform]?**

<ul><li>Live-data eller händelser: Bearbetas och importeras inom 90 minuter när data finns tillgängliga i Adobe Experience Platform. (Batchstorlek &gt; 50 miljoner rader: längre än 90 minuter.)</li><li>Små efterfyllningar - t.ex. en uppslagsdatauppsättning på 10 miljoner rader: inom 7 dagar<li>Stora backfills - till exempel 500 miljarder rader: 30 dagar</li></ul>

+++

## 5. Ange rullande fönster för [!UICONTROL Connection] datalagring {#data-retention}

The [**[!UICONTROL Enable rolling data window]**inställning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#create-connection) Med kan du definiera datalagring i Customer Journey Analytics som ett rullande fönster på månader (3 månader, 6 månader osv.). Den ställs in på [!UICONTROL connection] nivå, inte på [!UICONTROL dataset] nivå. Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för datalagring för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar.

Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader.

## 6. Konsekvenser av borttagning av datakomponenter {#deletion}

När det gäller borttagning av data är vi oroade för sex typer av komponenter: sandlåda, schema, datauppsättning, anslutning, datavy och Workspace-projekt. Här följer några möjliga scenarier när du tar bort någon av dessa komponenter:

| Om du.. | Det här händer.. |
| --- | --- |
| Ta bort en sandlåda i [!UICONTROL Adobe Experience Platform] | Om du tar bort en sandlåda stoppas dataflödet till alla [!UICONTROL Customer Journey Analytics] anslutningar till datauppsättningar i den sandlådan. För närvarande [!UICONTROL Connections] i Customer Journey Analytics som är knuten till den borttagna sandlådan tas inte bort automatiskt. |
| Ta bort ett schema i [!UICONTROL Adobe Experience Platform], men inte den eller de datauppsättningar som är associerade med det här schemat | [!UICONTROL Adobe Experience Platform] tillåter inte att [!UICONTROL schemas] som har en eller flera [!UICONTROL datasets] som är kopplade till dem. En administratör med rätt behörighetsuppsättning kan dock ta bort datauppsättningarna först och sedan ta bort schemat. |
| Ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform] Data Lake | Om du tar bort en datauppsättning i Adobe Experience Platform datasjön stoppas dataflödet från datauppsättningen till alla Customer Journey Analytics-anslutningar som innehåller den datauppsättningen. Alla data från den datauppsättningen tas automatiskt bort från associerade Customer Journey Analytics-anslutningar. |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | Kontakta kontoteamet på Adobe för att sätta igång processen för att ta bort en datauppsättning i en sparad anslutning. |
| Ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform]) | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform] datauppsättning, kommer samma batch att tas bort från alla Customer Journey Analytics-anslutningar som innehåller den specifika gruppen.  Customer Journey Analytics meddelas om batchborttagningar i [!UICONTROL Adobe Experience Platform]. |
| Ta bort en grupp **medan den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen kommer inga data eller delar av data från den gruppen att visas i [!UICONTROL Customer Journey Analytics]. Intag kommer att återställas. Om det till exempel finns 5 batchar i datauppsättningen och 3 av dem redan har importerats när datauppsättningen togs bort, kommer data från dessa tre batchar att visas i [!UICONTROL Customer Journey Analytics]. |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande visar att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla arbetsyteprojekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul> |
| Ta bort en datavy i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande visar att alla arbetsyteprojekt som är beroende av den här borttagna datavyn kommer att sluta fungera. |

## 7. Att tänka på när du sammanfogar rapportsviter i Customer Journey Analytics {#merge-reportsuite}

Om du tänker importera Adobe Analytics-data via [Adobe Analytics källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)bör du ta hänsyn till dessa förändringar när du sammanfogar två eller fler rapportsviter från Adobe Analytics.

| Problem | Villkor |
| --- | --- |
| Variabler | Variabler som [!UICONTROL eVars] kan inte matcha flera rapportsviter. eVar1 i rapportsviten 1 kan till exempel peka på **[!UICONTROL Page]**. I rapportserie 2 kan eVar1 peka på **[!UICONTROL Internal Campaign]**, vilket leder till blandad och felaktig rapportering. |
| [!UICONTROL Sessions] och [!UICONTROL People] antal | De dedupliceras över flera rapportsviter. Därför kanske antalet inte matchar. |
| Metrisk deduplicering | Tar bort förekomster av ett mått (till exempel [!UICONTROL Orders]) om flera rader har samma transaktions-ID (till exempel [!UICONTROL Purchase ID]). Detta förhindrar att nyckeltal räknas för mycket. Resultatet blir att mätvärden som [!UICONTROL Orders] kan inte sammanfatta i alla rapportsviter. |
| Valuta | Valutakonvertering stöds ännu inte i Customer Journey Analytics. Om rapportsviterna du försöker sammanfoga använder olika basvalutor kan det uppstå problem. |
| [!UICONTROL Persistence] | [Persistence](../data-views/component-settings/persistence.md) omfattar flera rapportsviter, vilket påverkar [!UICONTROL filters], [!UICONTROL attribution]och så vidare. Siffrorna kanske inte läggs ihop korrekt. |
| [!UICONTROL Classifications] | [!UICONTROL Classifications] dedupliceras inte automatiskt när du sammanfogar rapportsviter. När flera klassificeringsfiler kombineras till en enda [!UICONTROL lookup] datauppsättningen, kan du stöta på problem. |


## 8. [!UICONTROL Adobe Analytics] komponenter


+++**Kan jag dela/publicera [!UICONTROL filters] ([!UICONTROL segments]) från [!DNL Customer Journey Analytics] till Experience Platform Unified Profile eller andra program från Experience Cloud?**

Inte ännu, men vi arbetar aktivt för att leverera den här funktionen.

+++


+++**Vad hände med min gamla [!UICONTROL eVar] inställning?**

[!UICONTROL eVars], [!UICONTROL props]och [!UICONTROL events] i Adobe Analytics: finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden.

+++


+++**Var finns alla inställningar för session och variabel beständighet nu?**

[!UICONTROL Customer Journey Analytics] använder alla dessa inställningar vid rapporttillfället och dessa inställningar finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer!

+++


+++**Vad händer med våra befintliga segment/beräknade värden?**

[!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett Adobe Experience Platform-schema. Detta innebär att inget av de befintliga segmenten eller beräkningstalen är kompatibelt med [!UICONTROL Customer Journey Analytics].

+++


+++**Hur [!UICONTROL Customer Journey Analytics] handtag `Uniques Exceeded` begränsningar?**

[!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem!

+++


+++**Om jag är en befintlig [!DNL Data Workbench] kund, kan jag gå över till [!UICONTROL Customer Journey Analytics] just nu?**

Det beror på ditt användningssätt - samarbeta med ditt Adobe-kontoteam. Dina nuvarande användningsexempel kanske redan passar Customer Journey Analytics!

+++

## 9. Beräkna anslutningsstorlek {#estimate-size}

Se [Beräkna och hantera användningen](/help/admin/estimate-usage.md).

## 10. Angående användningsövertäckning {#overage}

Användningsgränserna övervakas regelbundet och upprätthålls av Adobe. datarader: de dagliga genomsnittliga datarader som finns tillgängliga för analys inom Customer Journey Analytics.

Anta till exempel att ditt avtal ger dig rätt till en miljon rader med data. Anta att du laddar upp två miljoner rader med data dag 1 av Customer Journey Analytics. På dag 2 tar du bort 1 miljon rader och behåller din användning på det högsta tillåtna antalet (dvs. en miljon rader data) under återstoden av licensvillkoren. Beroende på dina avtalsvillkor kan du ändå ådra dig en proportionell överanvändningsavgift för dag 1 eftersom du har överskridit dina licensrättigheter för&quot;datarader&quot;.

## 11. Diagnostisera dataavvikelser {#discrepancies}

I vissa fall kanske du märker att det totala antalet händelser som är inkapslade av din anslutning skiljer sig från antalet rader i datauppsättningen i [!UICONTROL Adobe Experience Platform]. I det här exemplet har datauppsättningen &quot;B2B-komprimering&quot; 7 650 rader, men datauppsättningen innehåller 3 830 rader i [!UICONTROL Adobe Experience Platform]. Det finns flera orsaker till varför avvikelser kan inträffa, och följande åtgärder kan vidtas för att diagnostisera:

1. Dela upp den här dimensionen med **[!UICONTROL Platform Dataset ID]** och du kommer att märka två datauppsättningar med samma storlek men olika **[!UICONTROL Platform Dataset IDs]**. Varje datauppsättning har 3825 poster. Det betyder [!UICONTROL Customer Journey Analytics] 5 poster ignorerades på grund av saknade person-ID:n eller saknade tidsstämplar:

   ![uppdelning](assets/data-size2.png)

2. Dessutom, om vi checkar in [!UICONTROL Adobe Experience Platform], det finns ingen datauppsättning med ID:t &quot;5f21c12b732044194bffc1d0&quot;, vilket innebär att någon har tagit bort den här datauppsättningen från [!UICONTROL Adobe Experience Platform] när den första anslutningen skapades. Senare lades det till Customer Journey Analytics igen, men med ett annat [!UICONTROL Platform Dataset ID] genererades av [!UICONTROL Adobe Experience Platform].

Läs mer om [konsekvenser av datauppsättning och borttagning av anslutning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components) in [!UICONTROL Customer Journey Analytics] och [!UICONTROL Adobe Experience Platform].
