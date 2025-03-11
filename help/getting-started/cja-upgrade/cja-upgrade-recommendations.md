---
title: Uppgradera från Adobe Analytics till Customer Journey Analytics
description: Läs mer om rekommenderad uppgradering från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1616'
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

Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen som beskrivs i [Förstå de rekommenderade uppgraderingsstegen](#1-understand-the-recommended-upgrade-steps) inte är praktiska för din organisation.

Så här genererar du uppgraderingssteg dynamiskt för organisationens unika omständigheter:

1. Fyll i Customer Journey Analytics Upgrade Guide.

   Om du vill få åtkomst till guiden från Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.

   När du är klar med uppgraderingsguiden får du stegvisa instruktioner som beskriver de optimala uppgraderingsstegen som är unika för organisationens behov. Detta är de uppgraderingssteg som bäst passar din befintliga Adobe Analytics-miljö och dina mål för Customer Journey Analytics.

1. Följ de stegvisa instruktionerna för att uppgradera till Customer Journey Analytics.

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
