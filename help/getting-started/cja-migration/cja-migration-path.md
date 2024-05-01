---
title: Välj migreringsväg för Customer Journey Analytics
description: Lär dig fördelarna och nackdelarna med möjliga migreringsvägar när du migrerar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '2422'
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
| **Ny implementering av Experience Platform Web SDK**</br>&#x200B;Även om detta inte är en migrering tekniskt sett kan du börja använda Customer Journey Analytics genom att göra en ny implementering av Experience Platform Web SDK. På så sätt kan du börja skicka data till Adobe Experience Platform Edge Network och Customer Journey Analytics. <p>För organisationer som ännu inte använder Web SDK är den här migreringsvägen kanske den enklaste när det gäller att hämta data till Edge Network eftersom den kräver så få steg som möjligt. Men eftersom allt arbete görs i förväg (till exempel att skapa XDM-schemat) kräver det en större inledande insats.</p><p>De grundläggande stegen är:</p><ol><li>Skapa ett XDM-schema för din organisation.</li><li>Implementera Web SDK.</li><li>Skicka data till plattformen.</li></ol> | Hög | Hög |
| **Migrera din Adobe Analytics-implementering till Web SDK**</br> Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget kan du migrera den och använda Adobe Experience Platform Web SDK för att börja skicka data till Edge Network och Adobe Analytics innan du skickar den till Customer Journey Analytics.<p>För organisationer som ännu inte använder Web SDK är detta det enklaste och smidigaste sättet att hämta data till Edge Network. Det kräver fler steg, men erbjuder en mer metodik övergång från Adobe Analytics till Customer Journey Analytics, med mer konkreta milstolpar.</p><p>De grundläggande stegen är:</p><ol><li>Flytta din befintliga Adobe Analytics-implementering till Web SDK och validera att allt fungerar i Adobe Analytics.</li><li>Skapa ett XDM-schema för din organisation när du har tid.</li><li>Använd Datastream-mappning för att mappa alla fält i dataobjektet till ditt XDM-schema.</li><li>Skicka data till plattformen.</li></ol> | Måttlig | Hög |
| **Konfigurera din befintliga Adobe Analytics Web SDK-implementering**</br> Om Adobe Analytics-implementeringen redan använder Adobe Experience Platform Web SDK kan du börja skicka data till Customer Journey Analytics med minimal insats.<p>Innan du skickar data till Customer Journey Analytics bör du överväga att uppdatera Adobe Analytics-schemat efter specifika behov i organisationen och andra plattformsprogram som du använder.</p><p>De grundläggande stegen är:</p><ol><li>Börja skicka data till Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Valfritt) Skapa ett XDM-schema för din organisation när du har tid.</li><li>(Villkorligt) Om du skapade ett XDM-schema kan du mappa alla fält i dataobjektet till XDM-schemat med hjälp av datastreamappning.</li></ol> | Låg | Hög |
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

#### Migreringssökvägar

+++Ny implementering av Experience Platform Web SDK

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>**Ger alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användningsexempel för personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Konsolidera implementeringen för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul></li><li>**Framtidssäkra**: Framtida implementeringsuppdateringar är enklare.</li></ul> | <ul><li>**Kräver en ny implementering från grunden**: Kravet på en ny implementering från grunden innebär följande nackdelar: </li><ul><li>**Tidsödande**: Detta är den mest tidskrävande och krävande migreringsvägen eftersom den kräver att du börjar om med en ny implementering.</li><li>**Det fullständiga schemat måste återskapas i XDM**: Innan du kan börja implementera Web SDK måste du återskapa det fullständiga schemat i XDM.</li><li>**Regler och dataelement måste återskapas**: Innan du kan börja implementera Web SDK måste du återskapa regelvillkor och dataelement från din Adobe Analytics-implementering.</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Migrera Adobe Analytics till Experience Platform Web SDK

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>**Ger alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användningsexempel för personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Konsolidera implementeringen för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din befintliga implementering**: Även om det här tillvägagångssättet kräver vissa implementeringsändringar behöver det inte finnas en helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken utan att påverka din befintliga Adobe Analytics-rapportering.</li><li>**Ger flexibilitet att skapa ett XDM-schema för din organisation vid ett senare tillfälle**: Du kan migrera din befintliga Adobe Analytics-implementering till Web SDK och validera att allt fungerar i Adobe Analytics och sedan skapa XDM-schemat. Denna flexibilitet möjliggör en mer metodik och genomtänkt migrering.</li></ul> | <ul><li>**Mappning krävs för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i dataobjektet är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li><li>**Teknisk skuld**: Eftersom den här metoden använder en modifierad form av din befintliga implementering kan det vara svårare att spåra implementeringslogik och utföra ändringar i framtiden vid behov. </li></ul> |

{style="table-layout:auto"}

+++

+++Använd Analytics Source Connector

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>Minst tidskrävande och krävande migreringsväg. <p>Data migreras snabbt till Customer Journey Analytics med minimal investering</p></li></ul> | <ul><li>**Data skickas inte till Edge Network**: <p>Detta medför följande nackdelar:</p><ul><li>Högsta nivån av [latens](/help/technotes/guardrails.md#latencies) i rapporter över alla migreringsvägar, inte optimerade för personalisering i realtid.</li><li>Data kan inte delas med andra Adobe Experience Platform-program, utan begränsas till endast Customer Journey Analytics</li><li>Använder Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Svårt att gå över till Web SDK i framtiden**: </li><li>**Använder fältgruppen Analytics Experience Event i ditt schema**: Den här fältgruppen lägger till många Adobe Analytics-händelser som inte behövs i ditt Customer Journey Analytics-schema.  Detta kan leda till ett mer rörigt, komplext schema än vad som annars behövs för Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

+++

### För Adobe Analytics-implementeringar med: Web SDK

Följande migreringsväg är tillgänglig för organisationer som har implementerat Adobe Analytics med Experience Platform Web SDK.

När du väljer den här migreringssökvägen måste du också välja ditt schema.

#### Migreringssökväg

+++Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till Customer Journey Analytics

| Fördelar | Nackdelar |
|----------|---------|
| Detta är den rekommenderade migreringsvägen om din Adobe Analytics-implementering redan använder Web SDK.<ul><li>**Ger alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användningsexempel för personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Konsolidera implementeringen för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din befintliga implementering**: Även om det här tillvägagångssättet kräver vissa implementeringsändringar behöver det inte finnas en helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken utan att påverka din befintliga Adobe Analytics-rapportering.</li><li>**Ger ett alternativ att använda ett XDM-schema**: Du kan välja att använda ditt befintliga Adobe Analytics-schema eller skapa ett XDM-schema och mappa fält i dataobjektet till ditt XDM-schema. [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) är ett flexibelt schema för att definiera de fält du behöver och bara de fält som är relevanta. <p>Se &quot;Använda ditt eget XDM-schema&quot; nedan för mer information om fördelarna med att använda ditt eget XDM-schema.</p></li><li>**Bevarar regler och dataelement**: Även om det kräver nya regelåtgärder kan du återanvända befintliga dataelement och regelvillkor med minimala ändringar.</li><li>**Framtidssäkra**: Om du väljer att använda ditt eget XDM-schema blir det enklare att implementera framtida uppdateringar.</li></ul> | Ingen |

{style="table-layout:auto"}

+++

#### Välj ditt schema

Om du väljer en migreringssökväg där du kan konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till Customer Journey Analytics kan du välja det schema som du vill använda.

Du kan välja om du vill använda ditt befintliga Adobe Analytics-schema eller uppdatera till ditt eget XDM-schema så att det bättre passar organisationens behov när du börjar använda andra plattformstjänster.

+++Använd Adobe Analytics-schemat med Adobe Analytics Web SDK-implementering

| Fördelar | Nackdelar |
|----------|---------|
| <p>Fördelarna med att använda Adobe Analytics-schemat är bland annat:</p><ul><li>Lätt att migrera<p>Om du redan skickar data till Adobe Analytics med Adobe Experience Platform Web SDK kan du lägga till ytterligare en tjänst i ditt datastream för att skicka data till Adobe Experience Platform (som sedan kan användas i din Customer Journey Analytics-konfiguration).</p></li></ul> | <p>Nackdelar med att använda Adobe Analytics-schemat är:</p><ul><li>När du använder Adobe Analytics-schemat begränsas du inte i termer av hur det kan användas med andra plattformsprogram, men det resulterar i ett schema som är mer komplext än det annars skulle kunna vara. Detta beror på att Adobe Analytics-schemat innehåller många objekt som är specifika för Adobe Analytics och som sannolikt inte kommer att användas av din organisation.<p>När du behöver ändra schemat måste du gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></li></ul> |

+++

+++Använd ditt eget XDM-schema med Adobe Analytics Web SDK-implementering

| Fördelar | Nackdelar |
|----------|---------|
| <ul><p>Fördelarna med att uppdatera till ditt eget XDM-schema är bland annat:</p><ul><li>Ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder.</li><p>När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></ul> | <p>Nackdelar med att uppdatera till ditt eget XDM-schema:</p><ul><li>Att uppdatera schemat är en tidsödande process som krävs innan du börjar skicka data till Customer Journey Analytics.</li></ul> |

+++

## Skicka sedan data till Adobe Experience Platform

Lär dig hur du använder informationen ovan för att välja en migreringsväg [skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) beroende på vilken migreringsväg du väljer.
