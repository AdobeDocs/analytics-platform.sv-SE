---
title: Välj migreringsväg för Customer Journey Analytics
description: Lär dig fördelarna och nackdelarna med möjliga migreringsvägar när du migrerar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 7d17ef31053bbf0d480bfa923fc961aeba4fc15e
workflow-type: tm+mt
source-wordcount: '1965'
ht-degree: 0%

---

# Steg 2: Välj migreringsväg

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större migreringsprocessen. Kontrollera att alla tidigare migreringssteg är slutförda.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar Steg 2 av migreringen, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| <span class="preview">**Steg 2: Välj migreringsväg**</span> | <span class="preview">Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål.</span> |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform varierar beroende på vilken migreringsväg du väljer i steg 2. |
| **Steg 4: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 5: [Utför ytterligare implementeringsuppgifter](/help/getting-started/cja-getting-started.md)** | I nuläget i migreringsprocessen måste du utföra olika åtgärder innan du kan använda Customer Journey Analytics-miljön.<p>Dessa ytterligare uppgifter gäller migreringar från Adobe Analytics och nya implementeringar i Customer Journey Analytics.</p><p>Bland dessa uppgifter finns:</p><ul><li>Placera andra data i Experience Platform</li><li>Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics</li><li>Skapa datavyer</li><li>Portar för API-användning för rapportering</li><li>Redovisning av datafeeds och Data Warehouse</li><li>Migrera projekt och komponenter</li><li>Planera användarintroduktion</li></ul> <p>Mer information finns i [Komma igång med Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

När du har bestämt dig för att migrera till Customer Journey Analytics måste du fastställa den optimala migreringsvägen för din organisation.

Vilken väg du väljer för migrering från Adobe Analytics till Customer Journey Analytics beror på följande faktorer:

* Din befintliga Adobe Analytics-implementering

* Dina mål för framtiden

Använd informationen på den här sidan för att avgöra vilken migreringsväg för Customer Journey Analytics som bäst passar organisationens nuvarande implementerings- och framtida mål.

För att fastställa den optimala migreringsvägen för din organisation bör följande avsnitt läsas sekventiellt:

1. Första, [förstå de migreringsvägar som är tillgängliga](#understand-migration-methods).

1. Sedan [bedöma vilka migreringsvägar som är tillgängliga för dig](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Och slutligen, [väga för- och nackdelar med varje migreringsväg](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## Förstå migreringsvägar

Det finns olika migreringsvägar för migrering från Adobe Analytics till Customer Journey Analytics.

I allmänhet skiljer sig varje migreringsväg åt när det gäller den ansträngning som krävs för att genomföra migreringen samt den långsiktiga lönsamhet som uppnås när migreringen har slutförts.

I följande tabell visas varje migreringsväg, dess ansträngningsnivå och dess långsiktiga lönsamhet:

| Migreringssökväg | Ansträngningsnivå | Långsiktig lönsamhet |
|---------|----------|---------|
| **Ny implementering av Experience Platform Web SDK**</br> Detta är inte en migrering av tekniska skäl, men du kan börja använda Customer Journey Analytics genom att göra en ny implementering av Experience Platform Web SDK för att börja skicka data till Adobe Experience Platform Edge Network. <p>För organisationer som ännu inte använder Web SDK är den här migreringsvägen kanske den enklaste när det gäller att hämta data till Edge Network eftersom den kräver så få steg som möjligt. Men eftersom allt arbete görs i förväg (till exempel att skapa XDM-schemat) kräver det en större inledande insats.</p><p>De grundläggande stegen är:</p><ol><li>Skapa ett XDM-schema för din organisation.</li><li>Implementera Web SDK.</li><li>Skicka data till plattformen.</li></ol> | Hög | Hög |
| **Migrera din Adobe Analytics-implementering till Web SDK**</br> Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget kan du migrera den och använda Adobe Experience Platform Web SDK för att börja skicka data till Edge Network och Adobe Analytics innan du skickar den till Customer Journey Analytics.<p>Detta är det enklaste och smidigaste sättet att få data till Edge Network. Det kräver fler steg, men erbjuder en mer metodik övergång från Adobe Analytics till Customer Journey Analytics, med mer konkreta milstolpar.</p><p>De grundläggande stegen är:</p><ol><li>Flytta din befintliga Adobe Analytics-implementering till Web SDK och validera att allt fungerar i Adobe Analytics.</li><li>Skapa ett XDM-schema för din organisation när du har tid.</li><li>Använd Datastream-mappning för att mappa alla fält i dataobjektet till ditt XDM-schema.</li><li>Skicka data till plattformen.</li></ol> | Måttlig | Hög |
| **Konfigurera din befintliga Adobe Analytics Web SDK-implementering**</br> Om Adobe Analytics-implementeringen redan använder Adobe Experience Platform Web SDK kan du börja skicka data till Customer Journey Analytics med minimal insats.<p>Innan du skickar data till Customer Journey Analytics bör du överväga att uppdatera Adobe Analytics-schemat efter specifika behov i organisationen och andra plattformsprogram som du kommer att använda.</p><p>De grundläggande stegen är:</p><ol><li>Börja skicka data till Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Valfritt) Skapa ett XDM-schema för din organisation när du har tid.</li><li>(Villkorligt) Om du skapade ett XDM-schema kan du mappa alla fält i dataobjektet till XDM-schemat med hjälp av datastreamappning.</li></ol> | Låg | Hög |
| **Använd Analytics Source Connector**</br> Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget kan du börja skicka data till en datavy i Customer Journey Analytics.<p>Detta är det enklaste sättet att få data till Customer Journey Analytics, men det är den minst användbara metoden på lång sikt.</p> | Låg | Låg |

{style="table-layout:auto"}

Använd följande diagram för att visualisera var varje migreringsväg faller på spektrumet i fråga om ansträngningsnivå och långsiktig lönsamhet:

![cja-migreringssökvägar](assets/cja-migration-methods.png)

## Utvärdera de migreringsvägar som är tillgängliga för dig baserat på din nuvarande Adobe Analytics-implementering

Alla migreringsvägar är inte tillgängliga för varje typ av Adobe Analytics-implementering.

Använd informationen nedan för att få en förståelse för vilken migreringsväg som passar din organisation bäst.

Kontakta din Adobe-representant om du behöver mer specifik rådgivning, vägledning eller support.

| Befintlig Adobe Analytics-implementering | Tillgängliga migreringssökvägar |
|---------|----------|
| AppMeasurement | <ul><li>Ny implementering av Experience Platform Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Källanslutning för analyser</li></ul> |
| Adobe Analytics-tillägg | <ul><li>Ny implementering av Experience Platform Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Källanslutning för analyser</li></ul> |
| Webb-SDK | <ul><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Väg in fördelarna och nackdelarna med de migreringsvägar som är tillgängliga för dig

Fördelarna och nackdelarna med en viss migreringsväg skiljer sig åt beroende på din befintliga Adobe Analytics-implementering.

Innan du använder informationen nedan för att avgöra vilken migreringsväg som är rätt för dig bör du granska informationen i [Förstå migreringsvägar](#understand-migration-methods) om du inte redan gjort det.

### För Adobe Analytics-implementeringar med: AppMeasurement och Adobe Analytics

Följande migreringsvägar är tillgängliga för organisationer som har implementerat Adobe Analytics med AppMeasurement eller Adobe Analytics-tillägget. Expandera varje avsnitt för att visa fördelarna och nackdelarna med varje migreringsväg.

**Migreringsvägar:**

+++Ny implementering av Experience Platform Web SDK

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>Använder ett XDM-schema, ett flexibelt schema för att definiera fält som du behöver, och endast de fält som är relevanta (gör att du kan flytta bort från Adobe Analytics Experience Event Field-gruppen)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li><li>Inga teckenbegränsningar (100 tecken för props)</li><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användningsexempel för personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Framtidssäkra (får alla de senaste funktionerna)</li><li>Konsolidera taggar för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP och så vidare)</li><li>[Enhets-ID:n från första part](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) för exaktare besöksidentifiering</li></ul> | <ul><li>Den mest tidskrävande och krävande migreringsvägen<p>Det fullständiga schemat måste återskapas i XDM innan du kan börja implementera Web SDK</p></li></ul> |

{style="table-layout:auto"}

+++

+++Migrera Adobe Analytics till Web SDK

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>Gör att du kan gå över till Web SDK utan att påverka dina befintliga Adobe Analytics-rapporter.</li><li>Bevarar regler och dataelement som redan konfigurerats i din Adobe Analytics-implementering (för organisationer som använder Analytics-tillägget).</li><li>Ger flexibilitet att skapa ett XDM-schema för din organisation vid ett senare tillfälle: ett flexibelt schema för att definiera de fält du behöver och endast de fält som är relevanta.</br>Adobe Analytics Experience Event Field-gruppen i Adobe Experience Platform krävs inte. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li><li>Inga teckenbegränsningar (100 tecken för props)</li><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användningsexempel för personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Framtidssäkra (får alla de senaste funktionerna)</li><li>Konsolidera taggar för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP och så vidare)</li><li>[Enhets-ID:n från första part](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) för exaktare besöksidentifiering</li></ul> | <ul><li>Måste överensstämma med ett XDM-schema vid någon tidpunkt i framtiden med hjälp av datastream-mappning.</li><li>Indrar en del tekniska skulder. Till exempel kan äldre AppMeasurement- eller Analytics-tilläggskod finnas kvar. </li></ul> |

{style="table-layout:auto"}

+++

+++Använd Analytics Source Connector

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>Minst tidskrävande och krävande migreringsväg. <p>Data migreras snabbt till Customer Journey Analytics med minimal investering</p></li></ul> | <ul><li>Data skickas inte till Edge Network och kan inte delas med andra Adobe Experience Platform-program. De begränsas endast till Customer Journey Analytics<li>Svårt att gå över till Web SDK i framtiden</li><li>Använder fältgruppen Analytics Experience Event i ditt schema.</br>Den här fältgruppen lägger till många Adobe Analytics-händelser som inte behövs i ditt Customer Journey Analytics-schema.  Detta kan leda till ett mer rörigt, komplext schema än vad som annars behövs för Customer Journey Analytics.</li><li>Högsta nivån av [latens](/help/admin/guardrails.md#latencies) alla implementeringsmetoder</li></ul> |

{style="table-layout:auto"}

+++

### För Adobe Analytics-implementeringar med: Web SDK

Följande migreringsväg är tillgänglig för organisationer som har implementerat Adobe Analytics med Experience Platform Web SDK:

**Migreringssökväg:**

+++Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till Customer Journey Analytics

| Fördelar | Nackdelar |
|----------|---------|
| Detta är den rekommenderade migreringsvägen om din Adobe Analytics-implementering redan använder Web SDK. <p>När du använder den här implementeringsmetoden kan du välja om du vill använda ditt befintliga Adobe Analytics-schema, eller om du kan uppdatera till XDM-schemat för att bättre anpassa dig till organisationens behov när du börjar använda andra plattformsprogram.</p><p>**Använda Adobe Analytics schema**</p><p>Fördelarna med att använda Adobe Analytics-schemat är bland annat:</p><ul><li>Lätt att migrera<p>Om du redan skickar data till Adobe Analytics med Adobe Experience Platform Web SDK kan du lägga till ytterligare en tjänst i ditt datastream för att skicka data till Adobe Experience Platform (som sedan kan användas i din Customer Journey Analytics-konfiguration).</p></li></ul><p>Nackdelar med att använda Adobe Analytics-schemat är:</p><ul><li>När du använder Adobe Analytics-schemat begränsas du inte i termer av hur det kan användas med andra plattformsprogram, men det resulterar i ett schema som är mer komplext än det annars skulle kunna vara. Detta beror på att Adobe Analytics-schemat innehåller många objekt som är specifika för Adobe Analytics och som troligen inte kommer att användas av din organisation.<p>När du behöver ändra schemat måste du gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></li></ul><p>**Använda XDM-schemat**</p><p>Fördelarna med att uppdatera XDM-schemat är bland annat:</p><ul><li>Ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder.</li><p>När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></ul><p>Nackdelar med att uppdatera XDM-schemat:</p><ul><li>Att uppdatera schemat är en tidsödande process som krävs innan du börjar skicka data till Customer Journey Analytics.</li></ul> | Ingen |

{style="table-layout:auto"}

+++

## Skicka sedan data till Adobe Experience Platform

Lär dig hur du använder informationen ovan för att välja en migreringsväg [skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) beroende på vilken migreringsväg du väljer.
