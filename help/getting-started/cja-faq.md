---
title: Vanliga frågor om Customer Journey Analytics
description: Customer Journey Analytics - Frågor och svar.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: 172d80a832356b59df875336c15865c9bacdd837
workflow-type: tm+mt
source-wordcount: '2342'
ht-degree: 0%

---

# Frågor och svar

Adobe Customer Journey Analytics är nästa generation av analysprodukter. I den här artikeln finns svar på vanliga frågor om Customer Journey Analytics. Mer information finns på [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## 1. Förutsättningar {#prerequisites}

+++**Behöver jag [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]?**

Nej, [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] krävs inte för [!UICONTROL Customer Journey Analytics]. Faktum är att de ännu inte stöds.

+++


+++**Behöver jag [!UICONTROL Experience Cloud ID] (ECID) för [!UICONTROL Customer Journey Analytics]?**

Nej, [!UICONTROL Customer Journey Analytics] stöder alla ID:n i en datauppsättning, oavsett om [!UICONTROL ECID] eller något annat ID du väljer.

+++


+++**Vad händer om jag behöver ETL (Extract, Transform, Load) före [!UICONTROL Customer Journey Analytics]?**

Customer Journey Analytics omfattar [Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html) funktioner som hjälper dig att omvandla dina data innan de läggs in i Adobe Experience Platform datasjön. Om du behöver ETL efter att data redan har importerats, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html#queries) innehåller några begränsade alternativ, men det kan tillkomma extra avgifter.

+++


## 2. Stämpla data {#stitching}

+++**Kan [!UICONTROL Customer Journey Analytics] &quot;sammanfoga&quot; på olika enheter eller i olika datauppsättningar?**

Ja. [!UICONTROL Customer Journey Analytics] har [Stitlar](../stitching/overview.md) funktionalitet som fungerar för både autentiserade och oautentiserade händelser i en datauppsättning. Med den här sammanfogningen kan du matcha olika poster till ett sammanfogat ID för enhetsövergripande analys på personnivå.
När ett gemensamt namnområdes-ID (Person-ID) används för datauppsättningar i en [Anslutning](/help/connections/overview.md)kan du köra analyser på en sömlös kombination av flera datauppsättningar, sammanfogade på personnivå.

+++


+++**Stöds sammanslagning från anonymt beteende till autentiserat beteende?**

Ja. [Stitlar](../stitching/overview.md) läser användardata från både autentiserade och oautentiserade sessioner för att generera ett sammanfogat ID.

+++


+++**Hur fungerar &#39;replay&#39; när man syr ihop?**

Stitching &quot;replaying&quot; data based on unique identifier it has learn. Replay syftar till att sammanfoga till en början oautentiserade händelser från enheter som har identifierats under tiden. [Läs mer](../stitching/explained.md)

+++


+++**Hur fungerar sammanfogning av historiska data (bakgrundsfyllning)?**

När Adobe aktiveras första gången fylls data i bakåt så långt tillbaka som till början av föregående månad (upp till 60 dagar). För att denna efterfyllning ska kunna utföras måste det tillfälliga ID:t finnas i de icke sammanfogade data som är långt tillbaka i tiden. [Läs mer](../stitching/explained.md)

+++


+++**Vilket beteende förväntas för datauppsättningsposter som inte är sammanfogade?**

**Exempel på scenario**: Du ansluter två datauppsättningar i en Customer Journey Analytics-anslutning genom att använda `CRMid` som person-ID. Ett är en webbhändelsedatamängd med `CRMid` i alla poster. Den andra datauppsättningen är en CRM-profildatauppsättning. 40 % av CRM-datauppsättningen har `CRMid` finns i datauppsättningen för webbhändelser. De andra 60 % finns inte i webbhändelsedatamängden. Visas de här posterna i rapporter i Analysis Workspace?<p> **Svar**: Profilrader som inte har några kopplade händelser lagras i Customer Journey Analytics. Du kan dock inte visa dem i Analysis Workspace förrän en händelse som är kopplad till detta ID visas.

+++

## 3. Hämta data till [!UICONTROL Customer Journey Analytics] {#ingest}

+++**Kan jag kombinera data från olika [!UICONTROL Adobe Experience Platform] sandlådor i en [!UICONTROL Customer Journey Analytics] anslutning?**

Nej, du kan inte komma åt data över sandlådor. Du kan bara kombinera datauppsättningar som finns i samma sandlåda. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets)

+++


+++**Hur ansluter jag onlinedata till offlinedata i [!UICONTROL Customer Journey Analytics]?**

Så länge person-ID:t matchar mellan datauppsättningar, [!UICONTROL Customer Journey Analytics] kan koppla filter, attribuering, flöde, utfall och så vidare mellan datauppsättningar.

+++


+++**Hur överför jag offlinedata till [!UICONTROL Customer Journey Analytics]?**

Din rätt till Customer Journey Analytics gör att du kan importera data till Experience Platform. Sedan kan du skapa anslutningar till dessa data- och datavyer i [!UICONTROL Customer Journey Analytics], för rapporter i Analysis Workspace. Experience Platform datagrupp kan hjälpa dig att ge rekommendationer eller konsulttjänster vid behov.

+++


+++**Hur får jag [!UICONTROL Adobe Analytics] data till [!UICONTROL Customer Journey Analytics]?**

[!UICONTROL Adobe Analytics] data kan anslutas till Experience Platform via [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Mest [!UICONTROL Adobe Analytics] fält hämtas till XDM-format, men andra fält är inte tillgängliga ännu.

+++


+++**Hur lång tid tar det att sätta ihop datauppsättningselement till en datavy?**

Några timmar att komma igång och några dagar att fylla i de senaste 13 månadernas data.

+++


+++**Är det nödvändigt att hämta in PII-data för att upprätta kopplingar mellan data?**

Nej, du kan använda valfritt ID, inklusive en hash av ett kund-ID som inte är PII.

+++


+++**Vilka är gränserna för inmatning av tidigare eller framtida datum/tidsstämplar i datauppsättningar för händelsen Customer Journey Analytics?**

<ul><li>Gällande tidigare datum/tidsstämplar: Händelsedata upp till tio år gamla.</li><li>Angående framtida datum/tidsstämplar: Händelsedata (prediktiva) upp till en månad i framtiden.</li></ul>

+++


## 4. Svarstidsfrågor {#latency}

>[!NOTE]
>Det finns ingen fast datastorlek i Customer Journey Analytics och därför kan Adobe inte binda sig till en standardintag. Adobe arbetar aktivt för att minska dessa latenser genom nya uppdateringar och optimering av intaget.

<ul><li>Live-data eller händelser: bearbetas och hämtas inom 90 minuter när data finns tillgängliga i Adobe Experience Platform. (Batchstorlek &gt; 50 miljoner rader: längre än 90 minuter.)</li><li>Små backfillar: inom sju dagar<li>Stora backfillar: inom 30 dagar</li></ul>

Adobe har nyligen ändrat hur data behandlas i Customer Journey Analytics:

<ul><li>Alla händelsedata med en tidsstämpel som är mindre än 24 timmar gamla direktuppspelas.</li><li>Alla händelsedata med en tidsstämpel som är mer än 24 timmar gamla (även om de finns i samma batch som nyare data) betraktas som förifyllda och kapslade med lägre prioritet.</li></ul>

## 5. Ange rullande fönster för [!UICONTROL Connection] datalagring {#data-retention}

The [**[!UICONTROL Enable rolling data window]**inställning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection) Med kan du definiera datalagring i Customer Journey Analytics som ett rullande fönster på månader (tre månader, sex månader o.s.v.). Den ställs in på [!UICONTROL connection] nivå, inte på [!UICONTROL dataset] nivå. Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för datalagring för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar.

Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader.

## 6. Konsekvenser av borttagning av datakomponenter {#deletion}

För borttagning av data bör du tänka på sex typer av komponenter: sandlåda, schema, datauppsättning, anslutning, datavy och Workspace-projekt. Här följer några möjliga scenarier när du tar bort någon av dessa komponenter:

| Om du.. | Det här händer.. |
| --- | --- |
| Ta bort en sandlåda i [!UICONTROL Adobe Experience Platform] | Om du tar bort en sandlåda stoppas dataflödet till valfri [!UICONTROL Customer Journey Analytics] anslutningar till datauppsättningar i den sandlådan. För närvarande [!UICONTROL Connections] i Customer Journey Analytics som är knuten till den borttagna sandlådan tas inte bort automatiskt. |
| Ta bort ett schema i [!UICONTROL Adobe Experience Platform], men inte den eller de datauppsättningar som är associerade med schemat | [!UICONTROL Adobe Experience Platform] tillåter inte att [!UICONTROL schemas] som har en eller flera [!UICONTROL datasets] som är kopplade till dem. En administratör med rätt behörighetsuppsättning kan dock ta bort datauppsättningarna först och sedan ta bort schemat. |
| Ta bort en datauppsättning i [!UICONTROL Adobe Experience Platform] Data Lake | Om du tar bort en datauppsättning i Adobe Experience Platform datasjön avbryts dataflödet från datauppsättningen till alla Customer Journey Analytics-anslutningar som innehåller den datauppsättningen. Alla data från den datauppsättningen tas automatiskt bort från de associerade Customer Journey Analytics-anslutningarna. |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | Kontakta kontoteamet på Adobe för att sätta igång processen för att ta bort en datauppsättning i en sparad anslutning. |
| Ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform]) | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform] datauppsättning, tas samma batch bort från alla Customer Journey Analytics-anslutningar som innehåller den specifika gruppen. Customer Journey Analytics meddelas om batchborttagningar i [!UICONTROL Adobe Experience Platform]. |
| Ta bort en grupp **medan den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen visas inga data eller delar av data från den gruppen i [!UICONTROL Customer Journey Analytics]. Intag har återställts. Om det till exempel finns fem batchar i datauppsättningen och tre av dem redan har importerats när datauppsättningen togs bort, visas data från dessa tre batchar i [!UICONTROL Customer Journey Analytics]. |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande anger att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla Workspace-projekt som är beroende av datavyer i den borttagna anslutningen slutar att fungera.</li></ul> |
| Ta bort en datavy i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande indikerar att alla arbetsyteprojekt som är beroende av den här borttagna datavyn kommer att sluta fungera. |

## 7. Att tänka på vid sammanslagning av rapportsviter i Customer Journey Analytics {#merge-reportsuite}

Om du tänker importera Adobe Analytics-data via [Adobe Analytics källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)bör du ta hänsyn till dessa förändringar när du sammanfogar två eller flera rapportsviter från Adobe Analytics.

| Problem | Villkor |
| --- | --- |
| Variabler | Variabler som [!UICONTROL eVars] kan inte matcha flera rapportsviter. EVar1 i rapportsviten 1 kan till exempel peka på **[!UICONTROL Page]**. I rapportsviten 2 kan eVar1 peka på **[!UICONTROL Internal Campaign]**, vilket leder till blandad och felaktig rapportering. |
| [!UICONTROL Sessions] och [!UICONTROL People] antal | De dedupliceras över flera rapportsviter. Därför kanske antalet inte matchar. |
| Metrisk deduplicering | Tar bort förekomster av ett mått (till exempel [!UICONTROL Orders]) om flera rader har samma transaktions-ID (till exempel [!UICONTROL Purchase ID]). Detta förhindrar att nyckeltal räknas för mycket. Resultatet blir att mätvärden som [!UICONTROL Orders] kan inte sammanfatta i alla rapportsviter. |
| Valuta | Valutakonvertering stöds ännu inte i Customer Journey Analytics. Om rapportsviterna du försöker sammanfoga använder olika basvalutor kan det uppstå problem. |
| [!UICONTROL Persistence] | [Persistence](../data-views/component-settings/persistence.md) omfattar flera rapportsviter, vilket påverkar [!UICONTROL filters], [!UICONTROL attribution]och så vidare. Siffrorna kanske inte läggs ihop korrekt. |
| [!UICONTROL Classifications] | [!UICONTROL Classifications] dedupliceras inte automatiskt när du sammanfogar rapportsviter. När flera klassificeringsfiler kombineras till en enda [!UICONTROL lookup] datauppsättningen, kan du stöta på problem. |

## 8. [!UICONTROL Adobe Analytics] komponenter

+++**Kan jag dela/publicera [!UICONTROL audiences] från [!DNL Customer Journey Analytics] till Experience Platform Real-Time CDP eller andra program från Experience Cloud?**

Du kan [skapa och publicera målgrupper](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/audiences/publish) identifieras i Customer Journey Analytics till kundprofil i realtid i Adobe Experience Platform för kundanpassning och personalisering.

+++

+++**Vad hände med min gamla [!UICONTROL eVar] inställning?**

[!UICONTROL eVars], [!UICONTROL props]och [!UICONTROL events] i Adobe Analytics: finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (dimensioner, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden.

+++

+++**Var finns alla inställningar för session och variabel beständighet nu?**

[!UICONTROL Customer Journey Analytics] använder alla dessa inställningar vid rapporttillfället, och dessa inställningar finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer!

+++

+++**Vad händer med era befintliga segment/beräknade värden?**

[!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett Adobe Experience Platform-schema. Detta innebär att inget av de befintliga segmenten eller beräknade mätvärdena är kompatibelt med [!UICONTROL Customer Journey Analytics].

+++

+++**Hur [!UICONTROL Customer Journey Analytics] handtag `Uniques Exceeded` begränsningar?**

[!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem!

+++

+++**Om jag är en befintlig [!DNL Data Workbench] kund, kan jag gå över till [!UICONTROL Customer Journey Analytics] just nu?**

Det beror på ditt användningssätt, så samarbeta med ditt Adobe-kontoteam. Det aktuella användningsexemplet kanske redan passar Customer Journey Analytics!

+++

## 9. Beräkna anslutningsstorlek {#estimate-size}

Se [Beräkna och hantera användningen](/help/technotes/estimate-usage.md).

## 10. Om användningsövertäckning {#overage}

Användningsgränserna övervakas regelbundet och upprätthålls av Adobe. datarader: de dagliga genomsnittliga dataraderna som är tillgängliga för analys inom Customer Journey Analytics.

Anta till exempel att ditt avtal ger dig rätt till en miljon rader med data. Anta att du laddar upp två miljoner rader med data dag 1 av Customer Journey Analytics. På dag 2 tar du bort 1 miljon rader och behåller din användning på den högsta tillåtna nivån (det vill säga en miljon rader data) under återstoden av licensvillkoren. Beroende på dina avtalsvillkor kan du ändå ådra dig en proportionell överanvändningsavgift för dag 1 eftersom du har överskridit dina licensrättigheter för&quot;datarader&quot;.

## 11. Diagnostisera avvikelser i data {#discrepancies}

Ibland kanske du märker att det totala antalet händelser som har skickats in via anslutningen skiljer sig från antalet rader i datauppsättningen i [!UICONTROL Adobe Experience Platform]. I det här exemplet har datauppsättningen &quot;B2B-komprimering&quot; 7 650 rader, men datauppsättningen innehåller 3 830 rader i [!UICONTROL Adobe Experience Platform]. Det finns flera orsaker till varför avvikelser kan inträffa, och följande åtgärder kan vidtas för att diagnostisera:

1. Dela upp den här dimensionen med **[!UICONTROL Platform Dataset ID]** och du märker två datauppsättningar med samma storlek men olika **[!UICONTROL Platform Dataset IDs]**. Varje datauppsättning har 3825 poster. Det betyder [!UICONTROL Customer Journey Analytics] ignorerade fem poster på grund av saknade person-ID:n eller saknade tidsstämplar:

   ![uppdelning](assets/data-size2.png)

1. Om du dessutom checkar in [!UICONTROL Adobe Experience Platform], det finns ingen datauppsättning med ID:t &quot;5f21c12b732044194bffc1d0&quot;, vilket innebär att någon har tagit bort den här datauppsättningen från [!UICONTROL Adobe Experience Platform] när den första anslutningen skapades. Senare lades den till Customer Journey Analytics igen, men en annan [!UICONTROL Platform Dataset ID] genererades av [!UICONTROL Adobe Experience Platform].

Läs mer om [konsekvenser av datauppsättning och borttagning av anslutning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components) in [!UICONTROL Customer Journey Analytics] och [!UICONTROL Adobe Experience Platform].


## 12. Regional datainsamling

Adobe Experience Cloud använder Regional Data Collection (RDC) så att interaktionen mellan besökarna och Adobe och andra lösningar sker så nära besökarna som möjligt. När data har samlats in regionalt på ett datainsamlingscenter (DCC, även kallat Edge-plats, en del av Platform Edge Network) vidarebefordras de via en säker anslutning till de relevanta lösningarna baserat på konfigurationen av din datastam och/eller händelsevidarebefordran.

![Dataflöde med Edge Network](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png)

I den regionala datainsamlingsprocessen används följande steg:

1. DNS löser automatiskt samlingens värdnamn till IP-adressen för datainsamlingscentret närmast besökaren.
1. Besökaren skickar data till den platsen.
1. Data vidarebefordras omedelbart via en säker anslutning till de lösningar som definieras av konfigurationen för dataström eller händelsevidarebefordran.

Att använda regional datainsamling ger flera fördelar:

* **Prestanda**: Med RDC ansluter besökarna till närmaste DCC. Denna optimering ger den snabbaste svarstiden, vilket ger mer exakt spårning och snabbare laddningstider.
* **Redundans**: Om kommunikationen mellan DCC och din DPC avbryts, sparar Adobe RDC-infrastrukturen data lokalt och vidarebefordrar den sedan till DPC när kommunikationen återställs.

Följande platser (kan ändras) ingår för närvarande i RDC:


| Typ av domänkontrollant | Datainsamlingscentral |
| --- | --- |
| Global (standard) | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Endast Amerika | Oregon, Virginia |
| Endast Europa | Irland, Paris |
| Endast Asien och Stillahavsområdet | Mumbai, Singapore, Tokyo, Sydney |

{style="table-layout:auto"}

När data når det regionala datacentret avgör datastreamkonfigurationen hur data slussas vidare.

Customer Journey Analytics kräver datauppsättningar från Adobe Experience Platform, så din konfiguration för dataström/händelsevidarebefordran kräver att Adobe Experience Platform-tjänsten dirigerar data från det regionala datacentret till datacentret där din Adobe Experience Platform-instans finns. Customer Journey Analytics och tillhörande stödtjänster och infrastruktur driftsätts i samma Adobe Experience Platform-instans.


Se [Översikt över datainsamling](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html) för mer information om datainsamlingsprocessen utanför Adobe Experience Platform Edge Network och dess regionala datacenter.
