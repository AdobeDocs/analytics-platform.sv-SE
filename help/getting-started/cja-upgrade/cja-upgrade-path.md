---
title: Välj uppgraderingsväg för Customer Journey Analytics
description: Lär dig fördelarna och nackdelarna med de möjliga uppgraderingsmöjligheterna när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '2975'
ht-degree: 0%

---

# Steg 2: Välj uppgraderingsväg

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större uppgraderingsprocessen. Se till att alla tidigare uppgraderingssteg är slutförda.

Innan du fortsätter med det här avsnittet bör du kontrollera att du har slutfört alla tidigare uppgraderingsuppgifter.

Informationen på den här sidan omfattar steg 2 i uppgraderingsprocessen, vilket framgår av tabellen nedan:

| Uppgradering | Information |
|---------|----------|
| **Steg 1: [Kom igång med uppgradering](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Lär dig fördelarna med att uppgradera till Customer Journey Analytics och den grundläggande uppgraderingsprocessen. |
| <span class="preview">**Steg 2: Välj uppgraderingssökvägen**</span> | <span class="preview">Det finns olika metoder för uppgradering till Customer Journey Analytics. Välj den metod som är bäst för din organisation, beroende på din organisations aktuella Adobe Analytics-miljö och långsiktiga mål.</span> |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken uppgraderingsväg du väljer i steg 2. |
| **Steg 4: [Behåll historiska data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 5: [Utför ytterligare implementeringsuppgifter](/help/getting-started/cja-getting-started.md)** | I uppgraderingsprocessen måste du utföra olika uppgifter innan Customer Journey Analytics-miljön kan användas.<p>Dessa ytterligare uppgifter gäller uppgraderingar från Adobe Analytics och nya Customer Journey Analytics-implementeringar.</p><p>Bland dessa uppgifter finns:</p><ul><li>Lägg in andra data i Experience Platform</li><li>Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics</li><li>Skapa datavyer</li><li>Portar för API-användning för rapportering</li><li>Redovisning av datafeeds och Data Warehouse</li><li>Migrera projekt och komponenter</li><li>Planera användarintroduktion</li></ul> <p>Mer information finns i [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Informationen på den här sidan ersätts med följande mer omfattande uppgraderingsinformation: <ul><li>**Rekommenderade uppgraderingssteg**<p>Mer information finns i [Rekommenderad sökväg vid uppgradering från Adobe Analytics till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>Det finns en ny uppgraderingsguide som dynamiskt genererar uppgraderingssteg som är skräddarsydda för just er organisation och era unika omständigheter.</p><p>Om du vill få åtkomst till guiden från Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.</p></li></ul>


När du har bestämt dig för att uppgradera till Customer Journey Analytics måste du fastställa den optimala uppgraderingsvägen för din organisation.

Vilken uppgradering du väljer från Adobe Analytics till Customer Journey Analytics beror på följande faktorer:

* Din befintliga Adobe Analytics-implementering

* Dina mål för framtiden

Använd informationen på den här sidan för att se vilket uppgraderingsalternativ för Customer Journey Analytics som bäst passar er organisations nuvarande implementering och framtida mål.

Följande avsnitt ska läsas sekventiellt för att avgöra vilken uppgraderingsväg som är bäst för din organisation:

1. [förstår först uppgraderingssökvägarna som är tillgängliga](#understand-upgrade-paths).

1. [utvärdera sedan vilka uppgraderingssökvägar som är tillgängliga för dig](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Och slutligen, [väger för- och nackdelarna med varje uppgraderingssökväg](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you).

## Förstå uppgraderingsmöjligheterna

Det finns olika uppgraderingsalternativ för uppgradering från Adobe Analytics till Customer Journey Analytics.

I allmänhet skiljer sig varje uppgraderingsväg åt när det gäller den nivå på arbetsinsatsen som krävs för att genomföra uppgraderingen och den långsiktiga lönsamhet som uppnås när uppgraderingen är klar.

I följande tabell visas varje uppgraderingsväg, dess ansträngningsnivå och dess långsiktiga lönsamhet:

| Uppgraderingssökväg | Ansträngningsnivå | Långsiktig lönsamhet |
|---------|----------|---------|
| **Ny implementering av Experience Platform Web SDK med Analytics-källkopplingen**</br> Du kan börja använda Customer Journey Analytics genom att göra en ny implementering av Experience Platform Web SDK. På så sätt kan du börja skicka data till Adobe Experience Platform Edge Network och Customer Journey Analytics. Dessutom använder ni Analytics-källkopplingen för att hämta historiska data till Customer Journey Analytics.<p>För organisationer som ännu inte använder Web SDK är uppgraderingsprocessen kanske den enklaste när det gäller att hämta data till Edge Network eftersom den kräver så få steg som möjligt. Men eftersom allt arbete görs i förväg (till exempel att skapa XDM-schemat) kräver det en större inledande insats.</p><p>De grundläggande stegen är:</p><ol><li>Skapa ett XDM-schema för din organisation.</li><li>Implementera Web SDK.</li><li>Skicka data till plattformen.</li><li>Konfigurera Analytics-källkopplingen.</br>Analysens källanslutning används för att hämta historiska Adobe Analytics-data till Customer Journey Analytics.<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | Hög | Hög |
| **Ny implementering av Experience Platform Web SDK**</br> Du kan börja använda Customer Journey Analytics genom att göra en ny implementering av Experience Platform Web SDK. På så sätt kan du börja skicka data till Adobe Experience Platform Edge Network och Customer Journey Analytics. <p>För organisationer som ännu inte använder Web SDK är uppgraderingsprocessen kanske den enklaste när det gäller att hämta data till Edge Network eftersom den kräver så få steg som möjligt. Men eftersom allt arbete görs i förväg (till exempel att skapa XDM-schemat) kräver det en större inledande insats.</p><p>De grundläggande stegen är:</p><ol><li>Skapa ett XDM-schema för din organisation.</li><li>Implementera Web SDK.</li><li>Skicka data till plattformen.</li></ol> | Hög | Hög |
| **Migrera din Adobe Analytics-implementering till Web SDK**</br> Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget kan du migrera den till Adobe Experience Platform Web SDK för att börja skicka data till Edge Network och Adobe Analytics innan du skickar den till Customer Journey Analytics.<p>För organisationer som ännu inte använder Web SDK är detta det enklaste och smidigaste sättet att hämta data till Edge Network. Det kräver fler steg, men erbjuder en mer metodik övergång från Adobe Analytics till Customer Journey Analytics, med mer konkreta milstolpar.</p><p>De grundläggande stegen är:</p><ol><li>Flytta din befintliga Adobe Analytics-implementering till Web SDK och validera att allt fungerar i Adobe Analytics.</li><li>Skapa ett XDM-schema för din organisation när du har tid.</li><li>Använd Datastream-mappning för att mappa alla fält i dataobjektet till ditt XDM-schema.</li><li>Skicka data till plattformen.</li></ol> | Måttlig | Hög |
| **Konfigurera din befintliga Adobe Analytics Web SDK-implementering**</br> Om din Adobe Analytics-implementering redan använder Adobe Experience Platform Web SDK kan du börja skicka data till Platform genom att konfigurera en datastream. Eller om du redan skickar data till Platform behöver du bara skapa en anslutning mellan plattformsdatauppsättningar och Customer Journey Analytics.<p>Innan du skickar data till Platform för användning i Customer Journey Analytics bör du överväga att uppdatera Adobe Analytics-schemat efter specifika behov i organisationen och andra plattformsprogram som du använder.</p><p>De grundläggande stegen är:</p><ol><li>Börja skicka data till plattformen.<p>Om du redan skickar data till Platform med din Adobe Analytics-implementering är det här steget inte obligatoriskt. Du behöver bara skapa en anslutning mellan plattformsdatauppsättningar och Customer Journey Analytics, vilket beskrivs senare i den här processen.</p></li><li>(Valfritt) Skapa ett XDM-schema för din organisation när du har tid.</li><li>(Villkorligt) Om du skapade ett XDM-schema kan du mappa alla fält i dataobjektet till XDM-schemat med hjälp av datastreamappning.</li></ol> | Låg | Hög |
| **Använd Analytics Source Connector**</br> Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget kan du börja skicka data till en datavy i Customer Journey Analytics.<p>Detta är det enklaste sättet att få data till Customer Journey Analytics, men det är den minst användbara metoden på lång sikt.</p> <p>**Obs!** Den här uppgraderingssökvägen kan användas oberoende av varandra. För bästa resultat rekommenderar vi dock att du använder den här uppgraderingssökvägen tillsammans med en ny implementering av Experience Platform WebSDK. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | Låg | Låg |

{style="table-layout:auto"}

Använd följande diagram för att visualisera var varje uppgraderingsväg faller på spektrumet i fråga om ansträngningsnivå och långsiktig lönsamhet:

![cja-uppgraderingssökvägar](assets/cja-upgrade-path-chart.png)

## Utvärdera de uppgraderingsmöjligheter som är tillgängliga för dig baserat på din nuvarande Adobe Analytics-implementering

Alla uppgraderingsalternativ är inte tillgängliga för varje typ av Adobe Analytics-implementering.

Använd informationen nedan för att få en förståelse för vilken uppgraderingsväg som passar bäst för din organisation.

Kontakta Adobe om du behöver mer specifik rådgivning, vägledning eller support.

| Befintlig Adobe Analytics-implementering | Tillgängliga uppgraderingssökvägar |
|---------|----------|
| AppMeasurement | <ul><li>Ny implementering av Experience Platform Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Analytics Source Connector</li><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li></ul> |
| Adobe Analytics-tillägg | <ul><li>Ny implementering av Experience Platform Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Analytics Source Connector</li><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li></ul> |
| Web SDK | <ul><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li></ul> |

{style="table-layout:auto"}

## Väg upp fördelar och nackdelar med de uppgraderingsmöjligheter som finns för dig

Fördelarna och nackdelarna med en viss uppgradering skiljer sig åt beroende på vilken implementering du har av Adobe Analytics.

Innan du använder informationen nedan för att avgöra vilken uppgraderingsväg som är rätt för dig bör du läsa informationen i [Förstå uppgraderingssökvägar](#understand-migration-methods) om du inte redan gjort det.

>[!NOTE]
>
>Även om var och en av de uppgraderingssökvägar som beskrivs i följande avsnitt kan användas separat rekommenderar Adobe en tvådelad uppgraderingsmetod när du uppgraderar från Adobe Analytics till Customer Journey Analytics, oavsett din nuvarande Adobe Analytics-implementering: **Adobe Analytics-källkopplingen** och en **ny implementering av Experience Platform WebSDK**.
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### För Adobe Analytics-implementeringar med: AppMeasurement och Adobe Analytics

Här följer uppgraderingsmöjligheterna för organisationer som har implementerat Adobe Analytics med AppMeasurement eller Adobe Analytics. Expandera varje avsnitt för att se fördelarna och nackdelarna med varje uppgraderingsväg.

#### Uppgraderingsvägar

+++Ny implementering av Experience Platform Web SDK

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>**Tillhandahåller alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användning av personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=sv-SE)</li><li>Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul></li><li>**Framtidssäkra**: Framtida implementeringsuppdateringar är enklare.</li></ul> | <ul><li>**Kräver en ny implementering från början**: Kravet på att göra en ny implementering från början innebär följande nackdelar: </li><ul><li>**Tidsödande**: Det här är den mest tidskrävande och krävande uppgraderingsvägen eftersom du måste börja om från början med en ny implementering.</li><li>**Det fullständiga schemat måste återskapas i XDM**: Innan du kan börja implementera Web SDK måste du återskapa det fullständiga schemat i XDM.</li><li>**Regler och dataelement måste återskapas**: Innan du kan börja implementera Web SDK måste du återskapa regelvillkor och dataelement från din Adobe Analytics-implementering.</li></ul><li>**Behåller inte historiska data:** Adobe rekommenderar att du använder Analytics-källkopplingen i kombination med en ny implementering av Experience Platform Web SDK för att behålla historiska data efter uppgradering till Customer Journey Analytics. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**Beskriver inte att data från den ursprungliga implementeringen jämförs med data från den nya implementeringen:** Adobe rekommenderar att du använder Analytics-källkopplingen i kombination med en ny implementering av Experience Platform Web SDK för att jämföra data efter en uppgradering till Customer Journey Analytics. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++Migrera Adobe Analytics till Experience Platform Web SDK

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>**Tillhandahåller alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användning av personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=sv-SE)</li><li>Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din befintliga implementering**: Även om den här metoden kräver vissa implementeringsändringar krävs ingen helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken utan att påverka din befintliga Adobe Analytics-rapportering.</li><li>**Ger flexibilitet att skapa ett XDM-schema för din organisation vid ett senare tillfälle**: Du kan migrera din befintliga Adobe Analytics-implementering till att använda Web SDK och verifiera att allt fungerar i Adobe Analytics, och sedan skapa XDM-schemat. Tack vare den här flexibiliteten kan du uppgradera till Customer Journey Analytics på ett mer metodiskt och genomtänkt sätt.</li></ul> | <ul><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i dataobjektet är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li><li>**Teknisk skuld**: Eftersom den här metoden använder en modifierad form av din befintliga implementering kan det vara svårare att spåra implementeringslogik och utföra ändringar i framtiden vid behov. </li></ul> |

{style="table-layout:auto"}

+++

+++Använd Analytics Source Connector

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>Minst tidskrävande och krävande uppgraderingsalternativ. <p>Data migreras snabbt till Customer Journey Analytics med minimal investering</p></li></ul> | <ul><li>**Data skickas inte till Edge Network**: <p>Detta medför följande nackdelar:</p><ul><li>Den högsta nivån av [latens](/help/technotes/guardrails.md#latencies) i rapportering för alla uppgraderingssökvägar, inte optimerad för användning av personalisering i realtid.</li><li>Data kan inte delas med andra Adobe Experience Platform-program, utan begränsas till endast Customer Journey Analytics</li><li>Använder Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Svårt att gå över till Web SDK i framtiden**: Till slut vill du förmodligen ha tillgång till de fördelar som Experience Platform Web SDK ger. För att kunna börja använda Experience Platform Web SDK måste du göra en ny implementering.</li><li>**Använder fältgruppen Analytics Experience Event i ditt schema**: Den här fältgruppen lägger till många Adobe Analytics-händelser som inte behövs i ditt Customer Journey Analytics-schema.  Detta kan leda till ett mer rörigt, komplext schema än vad som annars behövs för Customer Journey Analytics.</li></ul><p>På grund av dessa nackdelar rekommenderar Adobe att du använder Analytics-källkopplingen tillsammans med en ny implementering av Experience Platform Web SDK. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### För Adobe Analytics-implementeringar med: Web SDK

Följande uppgraderingsalternativ är tillgängliga för organisationer som har implementerat Adobe Analytics med Experience Platform Web SDK.

När du väljer den här uppgraderingssökvägen måste du också välja ditt schema.

#### Uppgraderingssökväg

+++Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen

| Fördelar | Nackdelar |
|----------|---------|
| Detta är den rekommenderade uppgraderingsvägen om Adobe Analytics-implementeringen redan använder Web SDK.<ul><li>**Tillhandahåller alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användning av personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=sv-SE)</li><li>Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din befintliga implementering**: Även om den här metoden kräver vissa implementeringsändringar krävs ingen helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken utan att påverka din befintliga Adobe Analytics-rapportering.</li><li>**Tillhandahåller ett alternativ för att använda ett XDM-schema**: Du kan välja att använda ditt befintliga Adobe Analytics-schema eller skapa ett XDM-schema och mappa fält i dataobjektet till ditt XDM-schema. [XDM-scheman](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/home#xdm-schemas) är ett flexibelt schema för att definiera de fält som du behöver, och bara de fält som är relevanta. <p>Se &quot;Använda ditt eget XDM-schema&quot; nedan för mer information om fördelarna med att använda ditt eget XDM-schema.</p></li><li>**Bevarar regler och dataelement**: Även om det krävs nya regelåtgärder kan du återanvända befintliga dataelement och regelvillkor med minimala ändringar.</li><li>**Framtidssäkra**: Om du väljer att använda ditt eget XDM-schema är framtida implementeringsuppdateringar enklare.</li></ul> | Ingen |

{style="table-layout:auto"}

+++

#### Välj ditt schema

Om du väljer den uppgraderingssökväg som gör att du kan konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen, kan du välja det schema som du vill använda.

Du kan välja om du vill använda ditt befintliga Adobe Analytics-schema eller uppdatera till ditt eget XDM-schema så att det bättre passar organisationens behov när du börjar använda andra plattformstjänster.

+++Använd Adobe Analytics-schemat med Adobe Analytics Web SDK-implementeringen

| Fördelar | Nackdelar |
|----------|---------|
| <p>Fördelarna med att använda Adobe Analytics-schemat är bland annat:</p><ul><li>Enkel uppgradering<p>Om du redan skickar data till Adobe Analytics med Adobe Experience Platform Web SDK kan du lägga till ytterligare en tjänst i ditt datastam för att skicka data till Adobe Experience Platform (som sedan kan användas i din Customer Journey Analytics-konfiguration).</p></li></ul> | <p>Nackdelar med att använda Adobe Analytics-schemat är:</p><ul><li>När du använder Adobe Analytics-schemat begränsas du inte i termer av hur det kan användas med andra plattformsprogram, men det resulterar i ett schema som är mer komplext än det annars skulle kunna vara. Detta beror på att Adobe Analytics-schemat innehåller många objekt som är specifika för Adobe Analytics och som sannolikt inte kommer att användas av din organisation.<p>När du behöver ändra schemat måste du gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></li></ul> |

+++

+++Använd ditt eget XDM-schema med Adobe Analytics Web SDK-implementering

| Fördelar | Nackdelar |
|----------|---------|
| <ul><p>Fördelarna med att uppdatera till ditt eget XDM-schema är bland annat:</p><ul><li>Ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder.</li><p>När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></ul> | <p>Nackdelar med att uppdatera till ditt eget XDM-schema:</p><ul><li>Att uppdatera schemat är en tidsödande process som krävs innan du börjar skicka data till plattformen.</li></ul> |

+++

## Skicka sedan data till Adobe Experience Platform

När du har använt informationen ovan för att välja en uppgraderingssökväg kan du lära dig hur du [skickar data till Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md) beroende på vilken uppgraderingssökväg du väljer.
