---
title: CUSTOMER JOURNEY ANALYTICS FAQ
description: Customer Journey Analytics - Frågor och svar.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '2387'
ht-degree: 0%

---

# Frågor och svar

Adobe Customer Journey Analytics är nästa generation av analysprodukter. I den här artikeln finns svar på vanliga frågor om Customer Journey Analytics. Mer information finns i [Funktionsstöd för Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## 1. Förutsättningar {#prerequisites}

+++**Behöver jag [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] för [!UICONTROL Customer Journey Analytics]?**

Nej, [!UICONTROL Private Device Graph] eller [!UICONTROL Device Coop] krävs inte för [!UICONTROL Customer Journey Analytics]. Faktum är att de ännu inte stöds.

+++


+++**Behöver jag [!UICONTROL Experience Cloud ID] (ECID) för [!UICONTROL Customer Journey Analytics]?**

Nej, [!UICONTROL Customer Journey Analytics] stöder alla ID:n i en datauppsättning, oavsett om det är [!UICONTROL ECID] eller något annat ID du väljer.

+++


+++**Vad händer om jag behöver ETL (Extract, Transform, Load) för mina data före [!UICONTROL Customer Journey Analytics]?**

Customer Journey Analytics innehåller funktioner för [dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html) som hjälper dig att omvandla dina data innan du skickar dem till Adobe Experience Platform dataruta. Om du behöver ETL efter att data redan har importerats, kan [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html#queries) erbjuda några begränsade alternativ, men det kan tillkomma extra avgifter.

+++


## 2. Stämpla data {#stitching}

+++**Kan [!UICONTROL Customer Journey Analytics] &quot;sy ihop&quot; mellan enheter eller mellan datauppsättningar?**

Ja. [!UICONTROL Customer Journey Analytics] har funktionen [Stitching](../stitching/overview.md) som fungerar för autentiserade och oautentiserade händelser i en datauppsättning. Med den här sammanfogningen kan du matcha olika poster till ett sammanfogat ID för enhetsövergripande analys på personnivå.
När ett gemensamt namnområdes-ID (Person ID) används för datauppsättningar i en [Connection](/help/connections/overview.md) kan du dessutom köra analyser på en sömlös kombination av flera datauppsättningar, sammanfogade på personnivå.

+++


+++**Stöds sammanslagning från anonymt beteende till autentiserat beteende?**

Ja. [Stitching](../stitching/overview.md) tittar på användardata från både autentiserade och oautentiserade sessioner för att generera ett sammanfogat ID.

+++


+++**Hur fungerar &#39;replay&#39; när du syr ihop?**

Stitching &quot;replaying&quot; data based on unique identifier it has learn. Replay syftar till att sammanfoga till en början oautentiserade händelser från enheter som har identifierats under tiden. [Läs mer](../stitching/overview.md)

+++


+++**Hur fungerar sammanfogning av historiska data (bakgrundsfyllning)?**

När Adobe aktiveras första gången fylls data i igen så långt du valt (upp till högst 25 månader, beroende på vilket Customer Journey Analytics-paket du har rätt till). För att denna efterfyllning ska kunna utföras måste det tillfälliga ID:t finnas i de icke sammanfogade data som är långt tillbaka i tiden. [Läs mer](../stitching/overview.md)

+++


+++**Vad är det förväntade beteendet för datauppsättningsposter som inte är sammanfogade?**

**Exempelscenario**: Du ansluter två datauppsättningar i en Customer Journey Analytics-anslutning genom att använda `CRMid` som person-ID. Ett är en webbhändelsedatamängd med `CRMid` i alla poster. Den andra datauppsättningen är en CRM-profildatauppsättning. 40 % av CRM-datauppsättningen har `CRMid` i webbhändelsedatauppsättningen. De andra 60 % finns inte i webbhändelsedatamängden. Visas de här posterna i rapporter i Analysis Workspace?<p> **Svar**: Profilrader som inte har några kopplade händelser lagras i Customer Journey Analytics. Du kan dock inte visa dem i Analysis Workspace förrän en händelse som är kopplad till detta ID visas.

+++

## 3. Hämta data till [!UICONTROL Customer Journey Analytics] {#ingest}

+++**Kan jag kombinera data från olika [!UICONTROL Adobe Experience Platform] sandlådor i en [!UICONTROL Customer Journey Analytics]-anslutning?**

Nej, du kan inte komma åt data över sandlådor. Du kan bara kombinera datauppsättningar som finns i samma sandlåda. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets)

+++


+++**Hur ansluter jag onlinedata till offlinedata i [!UICONTROL Customer Journey Analytics]?**

Så länge person-ID:t matchar mellan datauppsättningar kan [!UICONTROL Customer Journey Analytics] ansluta segment, attribuering, flöde, utfall och så vidare mellan datauppsättningar.

+++


+++**Hur överför jag mina offlinedata till [!UICONTROL Customer Journey Analytics]?**

Med din rätt till Customer Journey Analytics kan du importera data till Experience Platform. Du kan sedan skapa anslutningar till dessa data- och datavyer i [!UICONTROL Customer Journey Analytics] för rapportering i Analysis Workspace. Experience Platform datagrupp kan hjälpa dig att ge rekommendationer eller konsulttjänster vid behov.

+++


+++**Hur hämtar jag [!UICONTROL Adobe Analytics] data till [!UICONTROL Customer Journey Analytics]?**

[!UICONTROL Adobe Analytics]-data kan anslutas till Experience Platform via [Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). De flesta [!UICONTROL Adobe Analytics] fält hämtas över i XDM-format, men andra fält är inte tillgängliga än.

+++


+++**Hur lång tid tar det att sätta ihop datauppsättningselement till en datavy?**

Några timmar att komma igång och några dagar att fylla i de senaste 13 månadernas data.

+++


+++**Är det nödvändigt att hämta PII-data för att upprätta anslutningar mellan data?**

Nej, du kan använda valfritt ID, inklusive en hash av ett kund-ID som inte är PII.

+++


+++**Vilka är gränserna för inmatning av tidigare eller framtida datum/tidsstämplar i Customer Journey Analytics händelsedatamängder?**

* Gällande tidigare datum/tidsstämplar: Händelsedata upp till tio år gamla.
* Angående framtida datum/tidsstämplar: Händelsedata (prediktiva) upp till en månad i framtiden.

+++


## 4. Svarstidsfrågor {#latency}

>[!NOTE]
>
>Det finns ingen fast datastorlek i Customer Journey Analytics och därför kan Adobe inte binda sig till en standardintag. Adobe arbetar aktivt för att minska dessa latenser genom nya uppdateringar och optimering av intaget.

* Live-data eller händelser: bearbetas och hämtas inom 90 minuter när data finns tillgängliga i Adobe Experience Platform. (Batchstorlek > 50 miljoner rader: längre än 90 minuter.) Om sömnad är aktiverat kan intag ta upp till 4 timmar. Mer information finns i [skyddsutkast](https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/guardrails).
* Små backfillar: inom sju dagar
* Stora backfillar: inom 30 dagar

Adobe har nyligen förändrat hur data behandlas i Customer Journey Analytics:

* Händelsedata för&quot;aktuell&quot; dag direktuppspelas som livedata. Alla data med en händelsetid före klockan 11 :59:59:00 (23:59:59) föregående dag behandlas som en bakåtfyllnad.
* Alla händelsedata med en tidsstämpel som är mer än 24 timmar gamla (även om de finns i samma batch som nyare data) betraktas som förifyllda och kapslade med lägre prioritet.

## 5. Ange rullande fönster för [!UICONTROL Connection] datalagring {#data-retention}

Med inställningen [**[!UICONTROL Enable rolling data window]**](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection) kan du definiera Customer Journey Analytics-datalagring som ett rullande fönster på månader (tre månader, sex månader osv.). Den är inställd på en [!UICONTROL connection]-nivå, inte på en [!UICONTROL dataset]-nivå. Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för datalagring för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar.

Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader.

## 6. Konsekvenser av borttagning av datakomponenter {#deletion}

Vid borttagning av data bör du tänka på sex typer av komponenter: sandlåda, schema, datauppsättning, anslutning, datavy och Workspace-projekt. Här följer några möjliga scenarier när du tar bort någon av dessa komponenter:

| Om du.. | Det här händer.. |
| --- | --- |
| Ta bort en sandlåda i [!UICONTROL Adobe Experience Platform] | Om du tar bort en sandlåda stoppas dataflödet till alla [!UICONTROL Customer Journey Analytics]-anslutningar till datauppsättningar i den sandlådan. Anslutningar, datavyer, mått och dimensioner relaterade till den här borttagna sandlådan tas också bort. | |
| Ta bort ett schema i [!UICONTROL Adobe Experience Platform], men inte de datauppsättningar som är associerade med det här schemat | [!UICONTROL Adobe Experience Platform] tillåter inte att [!UICONTROL schemas] som har en eller flera [!UICONTROL datasets] associerade tas bort. En administratör med rätt behörighetsuppsättning kan dock ta bort datauppsättningarna först och sedan ta bort schemat. |
| Ta bort en datamängd i datasjön [!UICONTROL Adobe Experience Platform] | Om du tar bort en datauppsättning i Adobe Experience Platform datasjön avbryts dataflödet från datauppsättningen till alla Customer Journey Analytics Connections som innehåller den datauppsättningen. Alla data från den datauppsättningen tas automatiskt bort från de associerade Customer Journey Analytics-anslutningarna. |
| Ta bort en datauppsättning i [!UICONTROL Customer Journey Analytics] | Kontakta Adobe-kontoteamet för att sätta igång processen för att ta bort en datauppsättning i en sparad anslutning. |
| Ta bort en batch från en datauppsättning (i [!UICONTROL Adobe Experience Platform]) | Om en batch tas bort från en [!UICONTROL Adobe Experience Platform]-datauppsättning tas samma batch bort från alla Customer Journey Analytics-anslutningar som innehåller den specifika gruppen. Customer Journey Analytics meddelas om batchborttagningar i [!UICONTROL Adobe Experience Platform]. |
| Ta bort en batch **medan den importeras** till [!UICONTROL Customer Journey Analytics] | Om det bara finns en batch i datauppsättningen visas inga data eller delar av data från den gruppen i [!UICONTROL Customer Journey Analytics]. Intag har återställts. Om det till exempel finns fem grupper i datauppsättningen och tre av dem redan har importerats när datauppsättningen togs bort, visas data från dessa tre grupper i [!UICONTROL Customer Journey Analytics]. |
| Ta bort en anslutning i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande anger att:<ul><li>Datavyer som skapats för den borttagna anslutningen fungerar inte längre.</li><li> Alla Workspace-projekt som är beroende av datavyer i den borttagna anslutningen slutar fungera.</li></ul> |
| Ta bort en datavy i [!UICONTROL Customer Journey Analytics] | Ett felmeddelande indikerar att alla Workspace-projekt som är beroende av den här borttagna datavyn kommer att sluta fungera. |

## 7. Att tänka på när du sammanfogar rapportsviter i Customer Journey Analytics {#merge-reportsuite}

Om du tänker importera Adobe Analytics-data via [Adobe Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) bör du tänka på dessa förändringar när du sammanfogar två eller flera rapportsviter från Adobe Analytics.

| Problem | Villkor |
| --- | --- |
| Variabler | Variabler som [!UICONTROL eVars] kanske inte passar in i alla rapportsviter. EVar1 i rapportsviten 1 kan till exempel peka på **[!UICONTROL Page]**. I rapportserie 2 kan eVar1 peka på **[!UICONTROL Internal Campaign]**, vilket leder till blandad och felaktig rapportering. |
| [!UICONTROL Sessions] och [!UICONTROL People] antal | De dedupliceras över flera rapportsviter. Därför kanske antalet inte matchar. |
| Metrisk deduplicering | Tar bort instanser av ett mått (till exempel [!UICONTROL Orders]) om flera rader har samma transaktions-ID (till exempel [!UICONTROL Purchase ID]). Detta förhindrar att nyckeltal räknas för mycket. Därför kanske inte mätvärden som [!UICONTROL Orders] kan sammanfattas i alla rapportsviter. |
| Valuta | Valutakonvertering stöds ännu inte i Customer Journey Analytics. Om rapportsviterna du försöker sammanfoga använder olika basvalutor kan det uppstå problem. |
| [!UICONTROL Persistence] | [Persistence](../data-views/component-settings/persistence.md) sträcker sig över flera rapportsviter, vilket påverkar [!UICONTROL segments], [!UICONTROL attribution] och så vidare. Siffrorna kanske inte läggs ihop korrekt. |
| [!UICONTROL Classifications] | [!UICONTROL Classifications] dedupliceras inte automatiskt när rapportsviter sammanfogas. När du kombinerar flera klassificeringsfiler till en enda [!UICONTROL lookup]-datauppsättning kan du stöta på problem. |

## 8. [!UICONTROL Adobe Analytics] komponenter

+++**Kan jag dela/publicera [!UICONTROL audiences] från [!DNL Customer Journey Analytics] till Experience Platform Real-Time CDP eller andra Experience Cloud-program?**

Du kan [skapa och publicera målgrupper](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/audiences/publish) som identifieras i Customer Journey Analytics till kundprofilen i realtid i Adobe Experience Platform för kundanpassning och personalisering.

+++

+++**Vad hände med min gamla [!UICONTROL eVar]-inställning?**

[!UICONTROL eVars], [!UICONTROL props] och [!UICONTROL events] i Adobe Analytics-bemärkelse finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (dimensioner, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden.

+++

+++**Var finns alla inställningar för session och variabel beständighet nu?**

[!UICONTROL Customer Journey Analytics] tillämpar alla dessa inställningar vid rapporttillfället, och de här inställningarna finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer!

+++

+++**Vad händer med dina befintliga segment/beräknade värden?**

[!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett Adobe Experience Platform-schema. Detta innebär att inget av de befintliga segmenten eller beräknade måtten är kompatibelt med [!UICONTROL Customer Journey Analytics].

+++

+++**Hur hanterar [!UICONTROL Customer Journey Analytics] `Uniques Exceeded` begränsningar?**

[!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem!

+++

+++**Om jag är en befintlig [!DNL Data Workbench]-kund, kan jag flytta till [!UICONTROL Customer Journey Analytics] just nu?**

Det beror på hur du använder programmet, så samarbeta med Adobe Account Team. Det aktuella användningsexemplet kanske redan passar Customer Journey Analytics!

+++

## 9. Beräkna anslutningsstorlek {#estimate-size}

Se [Användning av anslutningar](/help/connections/manage-connections.md#usage).

## 10. Om användningsövertäckning {#overage}

Användningsbegränsningar övervakas och tillämpas regelbundet av Adobe. datarader: de dagliga genomsnittliga dataraderna som är tillgängliga för analys inom Customer Journey Analytics.

Ditt kontrakt ger till exempel en miljon rader med data. Anta att ni laddar upp två miljoner datarader dag 1 av Customer Journey Analytics. På dag 2 tar du bort 1 miljon rader och behåller din användning på den högsta tillåtna nivån (det vill säga en miljon rader data) under återstoden av licensvillkoren. Beroende på dina avtalsvillkor kan du ändå ådra dig en proportionell överanvändningsavgift för dag 1 eftersom du har överskridit dina licensrättigheter för&quot;datarader&quot;.

## 11. Diagnostisera avvikelser i data {#discrepancies}

Ibland kanske du märker att det totala antalet händelser som har kapslats av din anslutning skiljer sig från antalet rader i datauppsättningen i [!UICONTROL Adobe Experience Platform]. I det här exemplet har datauppsättningen B2B-komprimering 7650 rader, men datauppsättningen innehåller 3830 rader i [!UICONTROL Adobe Experience Platform]. Det finns flera orsaker till varför avvikelser kan inträffa, och följande åtgärder kan vidtas för att diagnostisera:

1. Dela upp den här dimensionen med **[!UICONTROL Platform Dataset ID]** och du ser två datauppsättningar med samma storlek men olika **[!UICONTROL Platform Dataset IDs]**. Varje datauppsättning har 3825 poster. Det innebär att [!UICONTROL Customer Journey Analytics] ignorerade fem poster på grund av saknade person-ID:n eller saknade tidsstämplar:

   ![nedbrytning](assets/data-size2.png)

1. Om du checkar in [!UICONTROL Adobe Experience Platform] finns det dessutom ingen datauppsättning med ID:t 5f21c12b732044194bffc1d0, vilket innebär att någon tog bort den här datauppsättningen från [!UICONTROL Adobe Experience Platform] när den första anslutningen skapades. Senare lades den till i Customer Journey Analytics igen, men en annan [!UICONTROL Platform Dataset ID] genererades av [!UICONTROL Adobe Experience Platform].

Läs mer om [konsekvenserna av datauppsättningen och borttagning av anslutningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components) i [!UICONTROL Customer Journey Analytics] och [!UICONTROL Adobe Experience Platform].


## 12. Regional datainsamling

Adobe Experience Cloud använder Regional Data Collection (RDC) så att interaktionen mellan besökarna och Adobe och andra lösningar sker så nära besökarna som möjligt. När data har samlats in lokalt på ett datainsamlingscenter (DCC, även kallat Edge-webbplats, en del av Platform Edge Network) vidarebefordras de via en säker anslutning till relevanta lösningar baserat på konfigurationen av ditt datastam och/eller din händelsevidarebefordran.

![Dataflöde med Edge Networks](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png)

I den regionala datainsamlingsprocessen används följande steg:

1. DNS löser automatiskt samlingens värdnamn till IP-adressen för datainsamlingscentret närmast besökaren.
1. Besökaren skickar data till den platsen.
1. Data vidarebefordras omedelbart via en säker anslutning till de lösningar som definieras av konfigurationen för dataström eller händelsevidarebefordran.

Att använda regional datainsamling ger flera fördelar:

* **Prestanda**: Med RDC ansluter besökarna till närmaste DCC. Denna optimering ger den snabbaste svarstiden, vilket ger mer exakt spårning och snabbare laddningstider.
* **Redundans**: Om kommunikationen mellan DCC och DPC avbryts, sparar Adobe RDC-infrastruktur data lokalt och vidarebefordrar den sedan till DPC när kommunikationen återställs.

Följande platser (kan ändras) ingår för närvarande i RDC:


| Typ av domänkontrollant | Datainsamlingscentral |
| --- | --- |
| Global (standard) | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Endast Amerika | Oregon, Virginia |
| Endast Europa | Irland, Paris |
| Endast Asien och Stillahavsområdet | Mumbai, Singapore, Tokyo, Sydney |

{style="table-layout:auto"}

När data når det regionala datacentret avgör datastreamkonfigurationen hur data slussas vidare.

Customer Journey Analytics kräver datauppsättningar från Adobe Experience Platform, så din konfiguration för dataström/händelsevidarebefordran kräver att Adobe Experience Platform-tjänsten dirigerar data från det regionala datacentret till datacentret där din Adobe Experience Platform-instans finns. Customer Journey Analytics och dess stödtjänster och infrastruktur driftsätts i samma Adobe Experience Platform-instans.


Se [Översikt över datainsamling](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html) om du vill ha mer information om hur du samlar in data utanför Adobe Experience Platform Edge Network och dess regionala datacenter.
