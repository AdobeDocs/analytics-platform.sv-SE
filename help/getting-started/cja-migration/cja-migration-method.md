---
title: Välj migreringsmetod för Customer Journey Analytics
description: Lär dig fördelarna och nackdelarna med de möjliga migreringsmetoderna när du migrerar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '1914'
ht-degree: 0%

---

# Steg 2: Välj migreringsmetod för Customer Journey Analytics

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större migreringsprocessen. Kontrollera att alla tidigare migreringssteg är slutförda.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 2, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| <span class="preview">**Steg 2: [Välj migreringsmetod](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål.</span> |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken migreringsmetod du väljer i steg 1. |
| **Steg 4: [Mappa data till XDM-schemat](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) används i Adobe Experience Platform för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data.<p>De flesta flyttningsmetoder kräver att du antingen skapar ett nytt XDM-schema eller mappar ditt befintliga Adobe Analytics-schema till XDM med hjälp av datastream-mappning.</p> |
| **Steg 5: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 6: [Planera användarintroduktion](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Du bör ge dina användare god tid (3-6 månader) att bekanta sig med Analysis Workspace viktigaste skillnader i Customer Journey Analytics. |
| **Steg 7: [Portar för API-användning för rapportering](/help/getting-started/cja-migration/cja-migration-api.md)** | Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan slutpunkt. Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics. |
| **Steg 8: [Ersätt datafeeds och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Bestäm hur du ska använda de exportalternativ som är tillgängliga i Customer Journey Analytics för att ersätta de datafeeds och Data Warehouse som du använde i Adobe Analytics. |
| **Steg 9: [Migrera projekt och komponenter](/help/getting-started/cja-migration/cja-migration-projects.md)** | Med komponentmigreringsområdet i Adobe Analytics kan du migrera projekt och tillhörande komponenter från Adobe Analytics till Customer Journey Analytics. |

{style="table-layout:auto"}

+++

När du har bestämt dig för att migrera till Customer Journey Analytics måste du fastställa den optimala migreringsmetoden för din organisation.

Vilken metod du väljer för migrering från Adobe Analytics till Customer Journey Analytics beror på följande faktorer:

* Din befintliga Adobe Analytics-implementering

* Dina mål för framtiden

Använd följande avsnitt för att avgöra vilken migreringsmetod för Customer Journey Analytics som bäst passar organisationens nuvarande implementering och framtida mål:

## Förstå migreringsmetoder

Det finns olika migreringsmetoder för migrering från Adobe Analytics till Customer Journey Analytics.

I allmänhet skiljer sig varje migreringsmetod åt när det gäller den ansträngning som krävs för att genomföra migreringen och den långsiktiga lönsamhet som uppnås efter att migreringen har slutförts.

I följande tabell visas varje migreringsmetod, dess ansträngningsnivå och dess långsiktiga lönsamhet:

| Migreringsmetod | Ansträngningsnivå | Långsiktig lönsamhet |
|---------|----------|---------|
| **Ny implementering av Web SDK**</br> Du kan göra en ny implementering av Adobe Experience Platform Web SDK för att börja skicka data till Adobe Experience Platform Edge Network <!-- what is the correct branding -->. <p>För organisationer som ännu inte använder Web SDK är den här migreringsmetoden kanske den enklaste metoden när det gäller att hämta data till Edge Network (vilket kräver ett minsta antal steg), men allt arbete görs i förväg, till exempel att skapa XDM-schemat.</p><p>De grundläggande stegen är:</p><ol><li>Skapa ett XDM-schema för din organisation</li><li>Implementera Web SDK</li><li>Skicka data till plattformen</li></ol> | Hög | Hög |
| **Migrera din Adobe Analytics-implementering till Web SDK**</br> Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget kan du migrera den och använda Adobe Experience Platform Web SDK för att börja skicka data till Edge Network innan du skickar den till Customer Journey Analytics. <!-- what else? --><p>Detta är det enklaste och smidigaste sättet att få data till Edge Network. Det kräver fler steg, men erbjuder en mer metodik övergång med mer konkreta milstolpar.</p><p>De grundläggande stegen är:</p><ol><li>Flytta din befintliga Adobe Analytics-implementering till Web SDK och validera att allt fungerar där.</li><li>Skapa ett XDM-schema för din organisation när du har tid.</li><li>Använd dataströmsmappning för att mappa alla fält i dataobjektet till ditt XDM-schema.</li><li>Skicka data till plattformen</li></ol> | Måttlig | Hög |
| **Konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till Customer Journey Analytics**</br> Om Adobe Analytics-implementeringen redan använder Web SDK kan du börja skicka data till Customer Journey Analytics.<p>Innan du skickar data till Customer Journey Analytics bör du överväga att uppdatera Adobe Analytics-schemat efter specifika behov i organisationen och andra plattformsprogram som du kommer att använda.</p><p>De grundläggande stegen är:</p><ol><li>Börja skicka data till Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Valfritt) Skapa ett XDM-schema för din organisation när du har tid.</li><li>Använd dataströmsmappning för att mappa alla fält i dataobjektet till ditt XDM-schema.</li></ol> | Låg | Hög |
| **Källanslutning för analyser**</br> Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget kan du börja skicka data till en datavy i Customer Journey Analytics.<p>Detta är det enklaste sättet att få data till Customer Journey Analytics, men det är den minst användbara metoden på lång sikt.</p> | Låg | Låg |

{style="table-layout:auto"}

Använd följande diagram för att visualisera var varje migreringsmetod faller inom spektrumet i fråga om ansträngningsnivå och den långsiktiga viabilitet som varje metod klarar:

![cja-migreringsmetoder](assets/cja-migration-methods.png)

## Utvärdera de flyttningsmetoder som är tillgängliga för dig baserat på din nuvarande implementering av Adobe Analytics

Alla migreringsmetoder är inte tillgängliga för varje typ av Adobe Analytics-implementering.

Använd informationen nedan som allmänna riktlinjer för att få en förståelse för vilken migreringsmetod som är lämpligast för din organisation.

Kontakta din Adobe-representant om du behöver mer specifik rådgivning, vägledning eller support.

| Implementering av Adobe Analytics | Tillgängliga migreringsmetoder |
|---------|----------|
| AppMeasurement | <ul><li>Ny implementering av Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Källanslutning för analyser</li></ul> |
| Adobe Analytics-tillägg | <ul><li>Ny implementering av Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Källanslutning för analyser</li></ul> |
| Webb-SDK | <ul><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Väg in fördelarna och nackdelarna med de migreringsmetoder som är tillgängliga för dig

Fördelarna och nackdelarna med en viss migreringsmetod skiljer sig åt beroende på din befintliga Adobe Analytics-implementering.

Innan du använder informationen nedan för att avgöra vilken migreringsmetod som är rätt för dig bör du läsa informationen i [Förstå migreringsmetoder](#understand-migration-methods) om du inte redan gjort det.

### AppMeasurement och Adobe Analytics

Följande tabell visar vilka migreringsmetoder som är tillgängliga för organisationer som har implementerat Adobe Analytics med AppMeasurement eller Adobe Analytics-tillägget:

| Migreringsmetod | Fördelar | Nackdelar |
|---------|----------|---------|
| **Ny implementering av Web SDK** | <ul><li>Använder ett XDM-schema, ett flexibelt schema för att definiera de fält du behöver</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li><li>Inga teckenbegränsningar (100 tecken för props)</li><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användningsexempel för personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Framtidssäkra (får alla de senaste funktionerna)</li><li>Konsolidera taggar för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP osv.)</li><li>[Enhets-ID:n från första part](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) för exaktare besöksidentifiering</li></ul> | <ul><li>Den mest tidskrävande och krävande migreringsmetoden<p>Det fullständiga schemat måste återskapas i XDM innan du kan börja implementera Web SDK</p></li></ul> |
| **Migrera Adobe Analytics till Web SDK** | <ul><li>Bevarar regler och dataelement som redan konfigurerats i din Adobe Analytics-implementering.</li><li>Gör att du kan gå över till Web SDK utan att påverka dina befintliga Adobe Analytics-rapporter.</li><li>Ger flexibilitet att skapa ett XDM-schema för din organisation vid ett senare tillfälle.</br>Kräver inte Adobe Analytics Experience Event Field-gruppen i Customer Journey Analytics. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li><li>Inga teckenbegränsningar (100 tecken för props)</li><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användningsexempel för personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Framtidssäkra (får alla de senaste funktionerna)</li><li>Konsolidera taggar för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP osv.)</li><li>[Enhets-ID:n från första part](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) för exaktare besöksidentifiering</li></ul> | <ul><li>Måste överensstämma med ett XDM-schema vid någon tidpunkt i framtiden med hjälp av datastream-mappning.</li><li>Indrar en del tekniska skulder. Till exempel kan äldre AppMeasurement- eller Analytics-tilläggskod finnas kvar. </li></ul> |
| **Källanslutning för analyser** | <ul><li>Minst tidskrävande och krävande migreringsmetod. <p>Data migreras snabbt till Customer Journey Analytics med minimal investering</p></li></ul> | <ul><li>Data skickas inte till Edge Network och kan inte delas med andra Adobe Experience Platform-program. De begränsas endast till Customer Journey Analytics<li>Svårt att gå över till Web SDK i framtiden</li><li>Använder fältgruppen Analytics Experience Event i ditt schema.</br>Den här fältgruppen lägger till många Adobe Analytics-händelser som inte behövs i ditt Customer Journey Analytics-schema.  Detta kan leda till ett mer rörigt, komplext schema än vad som annars behövs för Customer Journey Analytics.</li><li>Högsta nivån av [latens](/help/admin/guardrails.md#latencies) alla implementeringsmetoder</li></ul> |

{style="table-layout:auto"}

### Webb-SDK

Följande tabell visar vilka flyttningsmetoder som är tillgängliga för organisationer som har implementerat Adobe Analytics med Web SDK:

| Migreringsmetod | Fördelar | Nackdelar |
|---------|----------|---------|
| **Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till Customer Journey Analytics** | Detta är den rekommenderade migreringsmetoden om din Adobe Analytics-implementering redan använder Web SDK. <p>När du använder den här implementeringsmetoden kan du välja om du vill använda ditt befintliga Adobe Analytics-schema, eller om du kan uppdatera till XDM-schemat för att bättre anpassa dig till organisationens behov när du börjar använda andra plattformsprogram.</p><p>**Använda Adobe Analytics schema**</p><p>Fördelarna med att använda Adobe Analytics-schemat är bland annat:</p><ul><li>Lätt att migrera<p>Om du redan skickar data till Adobe Analytics med Adobe Experience Platform Web SDK kan du lägga till ytterligare en tjänst i ditt datastream för att skicka data till Adobe Experience Platform (som sedan kan användas i din Customer Journey Analytics-konfiguration).</p></li></ul><p>Nackdelar med att använda Adobe Analytics-schemat är:</p><ul><li>När du använder Adobe Analytics-schemat begränsas du inte i termer av hur det kan användas med andra plattformsprogram, men det resulterar i ett schema som är mer komplext än det annars skulle kunna vara. Detta beror på att Adobe Analytics-schemat innehåller många objekt som är specifika för Adobe Analytics och som troligen inte kommer att användas av din organisation.<p>När du behöver ändra schemat måste du gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></li></ul><p>**Använda XDM-schemat**</p><p>Fördelarna med att uppdatera XDM-schemat är bland annat:</p><ul><li>Ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder.</li><p>När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></ul><p>Nackdelar med att uppdatera XDM-schemat:</p><ul><li>Att uppdatera schemat är en tidsödande process som krävs innan du börjar skicka data till Customer Journey Analytics.</li></ul> | Ingen |

{style="table-layout:auto"}

## Skicka sedan data till Adobe Experience Platform

Lär dig hur du använder informationen ovan för att välja en migreringsmetod [skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) beroende på vilken migreringsmetod du väljer.
