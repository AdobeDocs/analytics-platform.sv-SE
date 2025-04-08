---
title: Uppgradera från Adobe Analytics till Customer Journey Analytics
description: Läs mer om rekommenderad uppgradering från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dfc9ba843fbddc135c0f8160fb672adb36e9146f
workflow-type: tm+mt
source-wordcount: '3268'
ht-degree: 0%

---

# Uppgradera från Adobe Analytics till Customer Journey Analytics

När du uppgraderar från Adobe Analytics till Customer Journey Analytics kan du följa de [rekommenderade uppgraderingsstegen](#recommended-upgrade-steps-for-most-organizations). Du kan också [dynamiskt generera uppgraderingssteg](#dynamically-generate-upgrade-steps-for-your-organization) för organisationens unika omständigheter.

## Rekommenderade uppgraderingssteg för de flesta organisationer {#upgrade-process}

Den rekommenderade processen att uppgradera från Adobe Analytics till Customer Journey Analytics är en ny implementering av Experience Platform Web SDK, som är den bästa datainsamlingsmetoden för Customer Journey Analytics. Tillsammans med Web SDK rekommenderar Adobe också att du använder Analytics-källkopplingen för att underlätta övergången till Customer Journey Analytics. Använd Analytics-källkopplingen för att bevara historiska Adobe Analytics-data och för att utföra datavämning sida vid sida.

När du har tillräckligt med historiska data i Experience Platform Web SDK och har gått över till Customer Journey Analytics helt kan källkopplingen för Analytics stängas av och Web SDK kan användas exklusivt.

>[!NOTE]
>
>Om uppgraderingsstegen som beskrivs i det här avsnittet inte är praktiska för din organisation kan du använda Customer Journey Analytics Upgrade Guide för att dynamiskt generera uppgraderingssteg som är anpassade efter organisationens unika omständigheter. (Om du vill få åtkomst till guiden från Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.)

### Rekommenderad uppgraderingsprocess på hög nivå {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Historiska data från Adobe Analytics"
>abstract="Lägg in data från Adobe Analytics historiska rapportsserie i Adobe Experience Platform och Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementera Experience Platform Web SDK (för pågående datainsamling)**

   En ny implementering av Experience Platform Web SDK är det bästa sättet att samla in data för Customer Journey Analytics. Det är den bästa grunden för att få ut så mycket som möjligt av Customer Journey Analytics eftersom det är den mest högpresterande, enkla och framtidssäkra metoden för att implementera Customer Journey Analytics.

   * Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för personalisering i realtid

   * Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)

   * Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)

1. **Konfigurera Adobe Analytics-källkopplingen (för överföring av historiska data)**

   För att övergången till Experience Platform Web SDK med Customer Journey Analytics ska bli så smidig som möjligt rekommenderar Adobe även att du använder Adobe Analytics källanslutning. På så sätt kan du lagra historiska data och visa data från din befintliga Adobe Analytics-implementering i Customer Journey Analytics, sida vid sida med data från din nya Experience Platform Web SDK-implementering.

   Med Analytics-källkopplingen kan ni:

   * Lägg in data från Adobe Analytics historiska rapportsserie i Adobe Experience Platform och Customer Journey Analytics.

     Du kan låta Analytics-källkopplingen vara igång så länge du behöver behålla tidigare Adobe Analytics-data.

   * Visa de data som samlats in med den ursprungliga Adobe Analytics-implementeringen (antingen AppMeasurement, Analytics Extension eller Web SDK Extension) i Customer Journey Analytics. Du kan jämföra dessa data sida vid sida med den nya Web SDK-implementeringen.

     Du kan hålla Analytics-källkontakten igång tills du känner dig bekant med skillnaderna. <!--elaborate on what those differences are? -->

   Analyskällans koppling som en fristående implementering rekommenderas inte för långtidsanvändning av Customer Journey Analytics. Detta beror på hög latens, klumpiga och komplexa scheman, beroende av Adobe Analytics nomenklatur (prop, eVar o.s.v.) och svårigheter att så småningom gå från källkopplingen till den rekommenderade Web SDK-implementeringen.

### Detaljerade rekommenderade uppgraderingssteg

I följande steg beskrivs den rekommenderade processen för uppgradering från Adobe Analytics till Customer Journey Analytics.

Varje steg innehåller en detaljerad beskrivning av processen på hög nivå. Följ länken för varje steg och slutför de tillhörande uppgifterna. Återgå sedan till den här sidan och fortsätt till nästa steg i processen.

1. [Planera din XDM-schemaarkitektur](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Skapa ett anpassat schema i Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Tänk på följande alternativ när du skapar ditt schema:

   * Om du vill integrera Customer Journey Analytics med RTCDP måste du aktivera alternativet **[!UICONTROL Profile]** i ditt schema enligt beskrivningen i [Skapa ett XDM-schema som ska användas med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). När det här alternativet är aktiverat sammanfogas data i kundprofilen i realtid när data hämtas till datauppsättningar som baseras på det här schemat.

   * Om du vill inkludera strömmande mediedata måste du [konfigurera ditt schema så att det kan importera och använda strömmande data](/help/data-ingestion/streaming.md).

1. [Skapa en datauppsättning i Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Valfritt) Om du använder klassificeringsdata i Adobe Analytics kan du lägga till klassificeringsdata i datauppsättningen i Customer Journey Analytics.

   Det gör du genom att [skapa en uppslagsdatauppsättning för varje dimension som innehåller klassificeringsdata](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. För Adobe Analytics-implementeringar som använder AppMeasurement eller Analytics-tillägget (taggar) [skapar du ett datastam i Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   För Adobe Analytics-implementeringar som använder Web SDK finns det redan ett datastream. Mer information finns i [Konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till plattformen](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Lägg till Adobe Experience Platform som en tjänst i ditt datastream](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Valfritt) Om du vill integrera Customer Journey Analytics med Adobe Journey Optimizer använder du personaliseringsobjektet i implementeringen för användning i Adobe Journey Optimizer.

1. Expandera avsnittet som beskriver hur du vill implementera Experience Platform Web SDK för din Customer Journey Analytics-implementering och slutför sedan de tillhörande stegen:

   +++Manuell implementering (JS-fil)

   1. [Lägg till alloy.js på din plats](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Fyll i ett XDM-objekt och skicka det till datastream.

+++

   +++Taggar

   1. [Skapa en taggegenskap och lägg till Adobe Experience Platform Web SDK-tillägget](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Lägg till Adobe Experience Platform Web SDK-tillägget i taggegenskapen](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implementera inläsartaggen på din plats](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Lägg till logik för XDM-datainsamling i taggen ](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Använd Edge Network-API:t för att skicka data till önskat datastream.

+++

1. [Verifiera att din Web SDK-implementering skickar data till en datamängd](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Skapa en anslutning i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Valfritt) Koppla webbdata till data från andra kanaler, som callcenter-data.

   Du uppnår detta genom att lägga till ytterligare datauppsättningar till din Customer Journey Analytics-anslutning, vilket beskrivs i [Importera callcenter och webbdata](/help/use-cases/cross-channel/call-center.md).

1. [Skapa en datavy i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Verifiera att data flödar in i datavyn i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. I din Adobe Analytics-miljö [använder du Analytics Inventory](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory) för att se en omfattande översikt över din Adobe Analytics-miljö, inklusive antalet projekt och komponenter, rapportsviter, användare och mycket mer.

1. [Migrera projekt och komponenter](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Valfritt) Om du använder marknadsföringskanaler i Adobe Analytics kan du [skapa ett marknadsföringskanalhärlett fält i Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Härledda fält är en viktig aspekt av realtidsrapporter i Customer Journey Analytics. Med ett härlett fält kan du definiera (ofta komplexa) dataändringar direkt, via en anpassningsbar regelbyggare.

   Ett sätt att använda härledda fält är att definiera ett härlett fält för marknadsföringskanal som fastställer rätt marknadsföringskanal baserat på ett eller flera villkor (till exempel URL-parameter, sidadress eller sidnamn).

   Använd [marknadsföringskanalernas funktionsmall](/help/data-views/derived-fields/derived-fields.md#marketing-channels) i härledda fält för att snabbt skapa ett härlett fält för marknadsföringskanaler.

1. Jämför data i Adobe Analytics från din gamla implementering med data i Customer Journey Analytics från din nya implementering och se till att du förstår eventuella skillnader och varför de finns. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Hämta historiska data från Adobe Analytics med Analytics-källkopplingen:

   >[!NOTE]
   >
   >Följ de här stegen om du inte tidigare har skapat någon källkoppling för Analytics.
   >
   >Om du redan använder Analytics-källkopplingen med Customer Journey Analytics följer du stegen i [Övergång från Analytics-källkopplingen till Web SDK för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Skapa ett XDM-schema för Analytics-källkopplingen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Om du inte redan har en Analytics-källkoppling [skapar du Analytics-källkopplingen och mappar fält till XDM-schemat](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      eller

      Om du redan har en Analytics-källkoppling mappar [fält från källkopplingen till ditt XDM-schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Planera användarnas introduktion.

   Precis som i Adobe Analytics är Analysis Workspace det viktigaste användarvänliga verktyget i Customer Journey Analytics. Det finns dock vissa viktiga skillnader när det gäller att använda Analysis Workspace i Customer Journey Analytics som användare måste vara medvetna om.

   Du bör ge dina användare god tid (3-6 månader) att bekanta sig med de viktigaste skillnaderna mellan Analysis Workspace i Customer Journey Analytics.

   Mer information om några av de viktigaste skillnaderna mellan Adobe Analytics och Customer Journey Analytics finns i [Användarhandbok för Adobe Analytics-användare](/help/getting-started/aa-to-cja-user.md).

1. Läs mer om stöd för [funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). De flesta Adobe Analytics-funktioner stöds i Customer Journey Analytics och många andra funktioner finns i Customer Journey Analytics.

1. Inaktivera Adobe Analytics när implementeringen av Customer Journey Analytics Web SDK är klar och du känner dig trygg med de data du samlar in.

   Adobe rekommenderar att du håller Adobe Analytics-miljön igång under en tid efter att du har implementerat Customer Journey Analytics.

   Mer information om hur Adobe Analytics används under och efter en uppgradering, samt den föreslagna tidpunkten för inaktivering av Adobe Analytics, finns i [Utvärdera hur länge du behöver Adobe Analytics efter uppgradering till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Generera uppgraderingssteg dynamiskt för organisationen

Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen som beskrivs i [Förstå de rekommenderade uppgraderingsstegen](#recommended-upgrade-steps-for-most-organizations) inte är praktiska för din organisation. I så fall kan du dynamiskt generera uppgraderingssteg för organisationens unika omständigheter. Hur du genererar dessa steg varierar beroende på om du redan har tillgång till Customer Journey Analytics.

### För kunder som har tillgång till Customer Journey Analytics

Så här genererar du uppgraderingssteg dynamiskt för organisationens unika omständigheter:

1. Fyll i Customer Journey Analytics Upgrade Guide.

   I Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.

   När du är klar med uppgraderingsguiden får du stegvisa instruktioner som beskriver de optimala uppgraderingsstegen som är unika för organisationens behov. Detta är de uppgraderingssteg som bäst passar din befintliga Adobe Analytics-miljö och dina mål för Customer Journey Analytics. Uppgraderingsstegen är tillgängliga som en delbar länk eller som en hämtningsbar CSV-fil.

1. Följ de stegvisa instruktionerna för att uppgradera till Customer Journey Analytics.

### För kunder som ännu inte har tillgång till Customer Journey Analytics

Så här genererar du uppgraderingssteg dynamiskt för organisationens unika omständigheter:

1. Kontakta Adobe Account Team för att slutföra uppgraderingshandboken för Customer Journey Analytics.

   Adobe Account Team kan ta dig igenom uppgraderingsguiden och förse dig med en CSV-fil som innehåller frågor, svar och de dynamiskt genererade uppgraderingsstegen som är unika för din organisation.

   Innan du kontaktar ditt Adobe-kontoteam bör du bekanta dig med de frågor som finns i uppgraderingshandboken för Customer Journey Analytics och få svar. Customer Journey Analytics Upgrade Guide innehåller följande frågor och svar:


   | Fråga | Tillgängliga svar | Ytterligare information |
   |---------|----------|---------|
   | Välj det alternativ som beskriver din nuvarande Adobe Analytics-implementering. Den här informationen kan påverka andra uppgraderingsalternativ som kan vara tillgängliga när du uppgraderar till Customer Journey Analytics. | Välj en: <ul><li>**AppMeasurement:**<br/> En JavaScript-implementering som läser in AppMeasurement.js på en sida och skickar data till Adobe med objektet s (till exempel s.eVar1).</li><li>**Adobe Analytics-tillägg (taggar):** <br/>En taggimplementering som läser in Adobe Experience Platform Data Collection (kallades tidigare Launch). Taggen har tillägget Adobe Analytics installerat.</li><li>**Experience Platform Web SDK-tillägg (taggar):**<br/> En taggimplementering som läser in Adobe Experience Platform Data Collection (kallades tidigare Launch). Taggen har Web SDK-tillägget installerat.</li><li>**Experience Platform Web SDK (alloy.js):** En JavaScript-implementering som läser in Web SDK-biblioteket (alloy.js) på en sida och skickar data till Adobe med en JSON-nyttolast.</li><li>**API för datainfogning i grupp:**<br/> En implementering som använder API:t för datainfogning eller API:t för satsvis datainfogning.</li><li>**Experience Platform Mobile SDK:**<br/> En implementering som använder Adobe Experience Platform Mobile SDK.</li><li>**AppMeasurement som använder ett tagghanteringsverktyg från tredje part:**<br/> En implementering som använder ett tagghanteringsverktyg från tredje part.</li><li>**En produkt som inte är från Adobe Analytics:**<br/> En implementering som samlar in data för en annan produkt än Adobe Analytics, till exempel Google Analytics. Om du väljer det här alternativet inaktiveras flera alternativ i uppgraderingsguiden som inte gäller när du uppgraderar till Customer Journey Analytics från en produkt som inte är från Adobe Analytics. </li><li>**Jag vet inte:**<br/> Om du inte är den person som hanterar implementeringen kan du tillfälligt välja det här alternativet.</li></ul><p>Välj om tillämpligt:<ul><li>**I vår implementering används för närvarande Analytics-källanslutningen:**<br/> Med Analytics-källkopplingen kan du enkelt få värde från Customer Journey Analytics, men du måste betala för både Adobe Analytics och Customer Journey Analytics. Den här guiden hjälper dig att gå mot en oberoende implementering av SDK för webben.</li></ul></p> | <ul><li>[Förstå implementeringen av Adobe Analytics och hur den påverkar din uppgradering till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Övergång från Analytics-källkopplingen till Web SDK för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | De flesta Adobe Analytics-funktioner är tillgängliga i Customer Journey Analytics. Följande funktioner måste dock beaktas under uppgraderingsprocessen. Välj något som du tänker använda. | Markera allt som gäller:<ul><li>**Historiska data från Adobe Analytics:**</br> Lägg in tidigare data från Adobe Analytics rapportsvit i Adobe Experience Platform och Customer Journey Analytics.</li><li>**Komponenter och projekt från Adobe Analytics:**</br> Komponenter från Adobe Analytics omfattar: Projekt (med tillhörande frihandstabeller och visualiseringar), segment och beräknade värden.</li><li>**Aktivitetskarta - övertäckning och länkspårning:**</br> Ett webbläsartillägg som gör att du kan visa länkspårningsdata som en övertäckning på webbplatsen.</li><li>**Klassificeringsdata:**</br> Gruppera eller kategorisera data som separata dimensioner.</li><li>**Marknadskanaler:**</br> Skapa regler som kategoriserar hur kunderna kommer till din webbplats.</li><li>**Data Warehouse:**</br> Exportera bearbetade data från Adobe Analytics i kalkylbladsformat.</li><li>**Dataflöden:**Det finns ännu ingen exakt ersättning för datafeeds i Customer Journey Analytics. Liknande funktionalitet kan dock uppnås med funktioner som fullständig tabellexport, export av plattformsdatauppsättningar, integrering med BI-verktyg och API:t för rapportering.</br></li><li>**Direktuppspelande mediedata:**</br> Ett tillägg till Adobe Analytics och Customer Journey Analytics som specialiserar sig på datainsamling av media, till exempel ljud, video eller direktuppspelat innehåll.</li></ul> | <ul><li>[Förstå Adobe Analytics funktionssupport vid uppgradering till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | De flesta nya funktioner är tillgängliga i Customer Journey Analytics. Följande funktioner måste dock beaktas under uppgraderingsprocessen. Välj något som du tänker använda. | Markera allt som gäller:<ul><li>**Lägg samman insamlade data med data från andra källor (t.ex. kontaktcenterdata):**</br>(Rekommenderas) Koppla data från olika webb-, mobil- och offlineegenskaper för att skapa en enda, konsoliderad vy över kundbeteenden. Denna möjlighet att kombinera analysdata från andra kanaler är det primära användningsområdet för Customer Journey Analytics.</li><li>**Häftar träffar från andra datauppsättningar med en anpassad dimension:**<br/> Om någon av dina datauppsättningar inte delar någon primär identifierare (till exempel ett Experience Cloud-id) kan du ändå sammanfoga dessa data med en annan dimension, till exempel inloggningsanvändarnamn eller e-postadress.</li><li>**Integrera med Adobe Journey Optimizer:**<br/> Leverera sammankopplade, kontextuella och personaliserade upplevelser till kunder.</li><li>**Integrera med Adobe Real-Time CDP:**<br/> Kombinera profildata från flera källor för att generera målgrupper och segment baserat på användaregenskaper.</li><li>**Integrera med Adobe Target (A4T):**<br/> Adobe rekommenderar integrering med Adobe Journey Optimizer för användningsfall inom personalisering. Det är möjligt att integrera med Adobe Target, men det är en kortsiktig lösning.</li><li>**Integrera med Adobe Audience Manager:**<br/> Adobe rekommenderar integrering med Adobe CDP i realtid för målgruppsbaserade användningsfall. Det är möjligt att integrera med Audience Manager, men det är en kortsiktig lösning.</li></ul> | [Förstå unika funktioner för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Ange hur du tänker använda Adobe Analytics och Customer Journey Analytics i slutändan: | Välj en: <ul><li>**Jag tänker flytta helt till Customer Journey Analytics från Adobe Analytics:**<br/>(rekommenderas) Adobe rekommenderar att du går över från Adobe Analytics till Customer Journey Analytics. Under övergångsperioden bör du köra Adobe Analytics tillsammans med Customer Journey Analytics för att kunna jämföra data sida vid sida. När du känner dig trygg med data kan du inaktivera Adobe Analytics.</li><li>**Jag tänker behålla båda Analytics-produkterna:**<br/>(rekommenderas inte) Om du väljer det här alternativet innehåller ditt avtal med Adobe både Adobe Analytics och Customer Journey Analytics, vilket kan vara dyrare för din organisation över tid.</li></ul> | [Utvärdera när Adobe Analytics ska inaktiveras efter uppgradering till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Ange hur du vill konfigurera ditt Customer Journey Analytics-schema: | Välj en: <ul><li>**Jag vill använda ett schema som är anpassat till min organisation:**</br>(Rekommenderas) Om du anpassar ditt schema kan din organisation bara spåra det du behöver och undvika de overheadfält som är kopplade till röriga och onödiga fält. Det här alternativet inkluderar fältgrupper som lagts till av Web SDK och fältgrupper som är anpassade efter din organisation.</li><li>**Jag vill använda standardschemat för Adobe Analytics:**</br>(rekommenderas inte) Adobe Analytics-schemat innehåller fler än tusen fält, vilket kan leda till ett rörigt och komplext schema. Din organisation måste fortsätta att följa konceptet med props och eVars, som är ett gammalt koncept som inte används i Customer Journey Analytics. Det är svårare att integrera med andra Adobe Experience Platform-tjänster.</li></ul> | [Välj ditt schema för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Välj det sätt du vill implementera Customer Journey Analytics på: | <ul><li>**Manuell implementering (alloy.js):**<br/> Inkludera SDK-webbbiblioteket (alloy.js) på varje sida på webbplatsen.</li><li>**Taggar:**<br/>(Rekommenderas) Installera tagginläsaren på din plats om du inte använder taggar än. Om du redan använder taggar kan du lägga till tillägget Web SDK i taggegenskapen. Det här alternativet inkluderar implementeringar med hjälp av taggar i Adobe Experience Platform Data Collection och tagghanteringssystem från tredje part.</li><li>**API:**<br/> Använd API:t för datainsamling för att skicka data direkt till en datastam. Både icke-autentiserade (klient-till-server) och autentiserade (server-till-server) typer stöds.</li></ul> | [Förstå implementeringsalternativ för SDK på webben när du uppgraderar till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (Valfritt) Välj en alternativ uppgraderingsmetod | <ul><li>**Använd Analytics-källkopplingen**<br/>(rekommenderas inte) Du kan använda Analytics-källkopplingen som enda implementeringsväg för Customer Journey Analytics.<p>Med det här alternativet sparar du implementeringstid genom att snabbt skicka data till Customer Journey Analytics. Den innehåller dock olika brister, till exempel högre latens och svårigheter att flytta bort från Adobe Analytics i framtiden.</p></li><li>**Jag vill använda min AppMeasurement-logik med Web SDK:**<br/> Skicka alla dina variabler i AppMeasurement-format via dataobjektet i stället för att skicka data via ett XDM-objekt.<p>Det här alternativet sparar implementeringstid genom att du kan mappa din AppMeasurement-logik till XDM i stället för att fylla i ett XDM-objekt från grunden. Men det ger ytterligare komplexitet över tid eftersom alla fält som du lägger till i framtiden måste mappas till XDM i datastream.</p></li><li>**Jag vill skicka datalagret till Adobe utan ytterligare konfiguration:**<br/> I stället för att skicka data via ett XDM-objekt kan du skicka hela datalagret till Adobe via dataobjektet.<p>Det här alternativet sparar implementeringstid genom att du kan mappa datalagret till XDM i stället för att fylla i ett XDM-objekt från grunden. Den här mappningen är dock mycket viktig eftersom det kommer att finnas en stor mängd data som Adobe inte kan tolka på ett enkelt sätt. Med det här alternativet blir det också mer komplicerat över tid eftersom alla fält som du lägger till i dina data senare i framtiden måste mappas till XDM i datastream.</p></li></ul> | <ul><li>[Uppgraderingsalternativ: Använd Analytics-källkopplingen enbart för att uppgradera till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[Uppgraderingsalternativ: Använd AppMeasurement datainsamling med Experience Platform Web SDK och Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Uppgraderingsalternativ: Skicka datalagret till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   När du är klar med uppgraderingsguiden för ditt Adobe-kontoteam får du en CSV-fil med frågor, svar och dynamiskt genererade uppgraderingssteg som är anpassade efter din befintliga Adobe Analytics-miljö och dina mål för Customer Journey Analytics.

1. Följ de steg-för-steg-instruktioner som skapas i CSV-filen för att uppgradera till Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
