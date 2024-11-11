---
title: Rekommenderad sökväg vid uppgradering från Adobe Analytics till Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: ae2f9220829c897c8f1e0425ec192035dcf0097d
workflow-type: tm+mt
source-wordcount: '1489'
ht-degree: 0%

---

# Uppgradera från Adobe Analytics till Customer Journey Analytics

När du uppgraderar från Adobe Analytics till Customer Journey Analytics rekommenderar Adobe en ny implementering av Experience Platform Web SDK, tillsammans med Analytics-källkopplingen, enligt beskrivningen i [Rekommenderade uppgraderingssteg för de flesta organisationer](#recommended-upgrade-steps-for-most-organizations).

Beroende på flera faktorer, t.ex. tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen inte är praktiska för din organisation. I så fall använder du uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) för att dynamiskt generera uppgraderingssteg som är anpassade efter organisationens unika förhållanden.

## Rekommenderade uppgraderingssteg för de flesta organisationer

>[!NOTE]
>
>Uppgraderingsstegen som beskrivs i detta avsnitt är de rekommenderade uppgraderingssteg som en organisation kan använda för att uppgradera från Adobe Analytics till Customer Journey Analytics.
>
>Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen inte är praktiska för din organisation. I så fall använder du uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) för att dynamiskt generera uppgraderingssteg som är anpassade efter organisationens unika förhållanden.

Den rekommenderade processen att uppgradera från Adobe Analytics till Customer Journey Analytics är en ny implementering av Experience Platform Web SDK, vilket är den bästa datainsamlingsmetoden för Customer Journey Analytics. I kombination med Web SDK rekommenderar Adobe också att du använder Analytics-källkopplingen för att underlätta övergången till Customer Journey Analytics. Använd Analytics-källkopplingen för att bevara historiska Adobe Analytics-data och för att utföra datavämning sida vid sida.

Efter fullständig övergång till Customer Journey Analytics kan Analytics-källkopplingen stängas av och Experience Platform Web SDK kan användas exklusivt.

### Rekommenderad uppgraderingsprocess på hög nivå

1. **Implementera Experience Platform Web SDK**

   En ny implementering av Experience Platform Web SDK är det bästa sättet att samla in data för Customer Journey Analytics. Det är den bästa grunden för att få ut så mycket som möjligt av Customer Journey Analytics, eftersom det är den mest kraftfulla, enkla och framtidssäkra metoden för implementering av Customer Journey Analytics.

   * Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för personalisering i realtid

   * Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)

   * Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)

1. **Konfigurera Adobe Analytics-källkopplingen**

   För att underlätta övergången till Experience Platform Web SDK med Customer Journey Analytics rekommenderar Adobe också att du använder Adobe Analytics källanslutning. På så sätt kan du spara historiska data och visa data från din befintliga Adobe Analytics-implementering i Customer Journey Analytics, sida vid sida med data från din nya Experience Platform Web SDK-implementering.

   Med Analytics-källkopplingen kan ni:

   * Lägg in data från Adobe Analytics historiska rapportsserie i Adobe Experience Platform och Customer Journey Analytics.

     Du kan låta Analytics-källkopplingen vara igång så länge du behöver behålla tidigare Adobe Analytics-data.

   * Visa de data som samlats in med den ursprungliga Adobe Analytics-implementeringen (antingen AppMeasurement, Analytics Extension eller Web SDK Extension) i Customer Journey Analytics. Du kan jämföra dessa data sida vid sida med den som finns i den nya Web SDK-implementeringen.

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

1. För Adobe Analytics-implementeringar med AppMeasurement eller Analytics-tillägg (taggar) skapar [ett datastödram i Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   För Adobe Analytics-implementeringar som använder Web SDK finns redan ett datastream.

1. [Lägg till Adobe Experience Platform som en tjänst i ditt datastream](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Valfritt) Om du vill integrera Customer Journey Analytics med Adobe Journey Optimizer använder du personaliseringsobjektet i implementeringen för användning i Adobe Journey Optimizer.

1. (Valfritt) Hämta historiska data från Adobe Analytics med Analytics-källkopplingen.

   Mer information finns i [Använd en källkoppling](/help/data-ingestion/sources.md#use-a-source-connector) i [Importera och använda data med hjälp av källanslutningar](/help/data-ingestion/sources.md).

1. Expandera avsnittet som beskriver hur du vill implementera Experience Platform Web SDK för implementeringen av Customer Journey Analytics och slutför sedan de associerade stegen:

   +++Manuell implementering (JS-fil)

   1. [Lägg till alloy.js på din plats](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Fyll i ett XDM-objekt och skicka det till datastream.

+++

   +++Taggar

   1. [Implementera inläsartaggen på din plats](/help/getting-started/cja-upgrade/cja-upgrage-tag-loader.md).

   1. [Skapa en taggegenskap och lägg till Adobe Experience Platform Web SDK-tillägget](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Lägg till logik för XDM-datainsamling i taggen ](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Använd Edge Network-API:t för att skicka data till önskat datastream.

+++

1. Verifiera att din Web SDK-implementering skickar data till en datauppsättning.

1. [Skapa en anslutning i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Valfritt) Koppla webbdata till data från andra kanaler, som callcenter-data.

   Du uppnår detta genom att lägga till ytterligare datauppsättningar till din Customer Journey Analytics-anslutning.

1. [Skapa en datavy i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Verifiera att data flödar till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migrera projekt och komponenter](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

1. (Valfritt) Om du använder marknadsföringskanaler i Adobe Analytics kan du [skapa ett marknadsföringskanalhärlett fält i Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Härledda fält är en viktig aspekt av realtidsrapporteringen i Customer Journey Analytics. Med ett härlett fält kan du definiera (ofta komplexa) dataändringar direkt, via en anpassningsbar regelbyggare.

   Ett sätt att använda härledda fält är att definiera ett härlett fält för marknadsföringskanal som fastställer rätt marknadsföringskanal baserat på ett eller flera villkor (till exempel URL-parameter, sidadress, sidnamn).

   Använd [marknadsföringskanalernas funktionsmall](/help/data-views/derived-fields/derived-fields.md#marketing-channels) i härledda fält för att snabbt skapa ett härlett fält för marknadsföringskanaler.

1. Jämför data från den gamla implementeringen med data från den nya implementeringen och se till att du förstår alla skillnader och varför de finns.

1. Läs mer om stöd för [funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). De flesta Adobe Analytics-funktioner stöds i Customer Journey Analytics och många andra funktioner finns i Customer Journey Analytics.

1. Planera användarnas introduktion.

   Precis som i Adobe Analytics är Analysis Workspace det viktigaste användarvänliga verktyget i Customer Journey Analytics. Men det finns vissa viktiga skillnader mellan Analysis Workspace i Customer Journey Analytics som användare måste vara medvetna om.

   Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics.

   Mer information om några av de viktigaste skillnaderna mellan Adobe Analytics och Customer Journey Analytics finns i [Användarhandbok för Adobe Analytics-användare](/help/getting-started/aa-to-cja-user.md).

1. Inaktivera datainsamling av AppMeasurement.

1. Inaktivera Analytics-källkopplingen.

   I och med implementeringen av Experience Platform Web SDK behövs bara Analytics-källkopplingen för tidigare Adobe Analytics-data och för att jämföra data från den ursprungliga implementeringen med den nya implementeringen.

   När ni har tillräckligt med historiska data från den nya implementeringen och känner till rapporteringsskillnaderna i Customer Journey Analytics bör ni inaktivera källkopplingen för Analytics.

## Generera uppgraderingssteg dynamiskt för organisationen

Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen som beskrivs i [Förstå de rekommenderade uppgraderingsstegen](#1-understand-the-recommended-upgrade-steps) inte är praktiska för din organisation.

Så här genererar du uppgraderingssteg dynamiskt för organisationens unika omständigheter:

1. Fyll i uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   När du fyllt i enkäten får du stegvisa instruktioner som beskriver de optimala uppgraderingsstegen som är unika för organisationens behov. Detta är de uppgraderingssteg som bäst passar din befintliga Adobe Analytics-miljö och dina mål för Customer Journey Analytics.

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
