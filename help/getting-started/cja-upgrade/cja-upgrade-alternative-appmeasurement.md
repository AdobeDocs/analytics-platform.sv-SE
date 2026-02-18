---
title: Alternativa metoder vid uppgradering till Customer Journey Analytics
description: Läs mer om alternativa metoder vid uppgradering till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 0%

---

# Uppgraderingsalternativ: Använd AppMeasurement datainsamling med Experience Platform Web SDK och Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Använd AppMeasurement-logik med Web SDK"
>abstract="I stället för att skicka data via ett XDM-objekt skickar du alla variabler i AppMeasurement-format via dataobjektet.<br><br>Det här alternativet sparar implementeringstid genom att du kan mappa din AppMeasurement-logik till XDM i stället för att fylla i ett XDM-objekt från grunden. Men det ger ytterligare komplexitet över tid eftersom alla fält som du lägger till i framtiden måste mappas till XDM i datastream."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="Ändra din AppMeasurement-logik så att den pekar på Web SDK"
>abstract="Det här steget visas eftersom du valde att ta en implementeringskortkommando. Kopiera eller ändra AppMeasurement-logiken för att fylla i dataobjektet i stället för dess objekt. Du kan till exempel ändra tilldelningen av s.eVar1 till data.__adobe.analytics.eVar1 och upprepa för alla Analytics-variabler."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

När du uppgraderar till Customer Journey Analytics rekommenderar Adobe [en ny implementering av Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen inte är praktiska för din organisation.

Du kan använda AppMeasurement- eller Analytics-tilläggets datainsamlingslogik med Web SDK för att skicka data till Platform och Customer Journey Analytics, i stället för att samla in data med XDM-objektet. Det här alternativet ger dock ytterligare komplexitet över tid.

## Fördelar och fördelar

Den här metoden utesluter varandra när [skickar hela datalagret till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), eftersom båda metoderna utför samma åtgärd. (Den här metoden är bättre än att skicka hela datalagret till Adobe. Det är mer avancerat eftersom props och evar alla går igenom data.__adobe.analytics._variabelnamn_.)

Tänk på följande fördelar och nackdelar med att använda detta uppgraderingsalternativ:

| Fördelar | Nackdelar |
|----------|---------|
| Detta är den rekommenderade uppgraderingsvägen om Adobe Analytics-implementeringen redan använder Web SDK.<ul><li>**Tillhandahåller alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användning av personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Konsolidera implementeringen för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP osv.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din befintliga implementering**: Även om den här metoden kräver vissa implementeringsändringar krävs ingen helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken utan att påverka din befintliga Adobe Analytics-rapportering.</li><li>**Tillhandahåller ett alternativ för att använda ett XDM-schema**: Du kan välja att använda ditt befintliga Adobe Analytics-schema eller skapa ett XDM-schema och mappa fält i dataobjektet till ditt XDM-schema. [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) är ett flexibelt schema för att definiera de fält som du behöver, och bara de fält som är relevanta. <p>Se &quot;Använda ditt eget XDM-schema&quot; nedan för mer information om fördelarna med att använda ditt eget XDM-schema.</p></li><li>**Bevarar regler och dataelement**: Även om det krävs nya regelåtgärder kan du återanvända befintliga dataelement och regelvillkor med minimala ändringar.</li><li>**Framtidssäkra**: Om du väljer att använda ditt eget XDM-schema är framtida implementeringsuppdateringar enklare.</li></ul> | <ul><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i dataobjektet är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li><li>**Lägger till ytterligare komplexitet över tid**: Alla fält som du lägger till i framtiden måste mappas till XDM i datastream.<p>När ett nytt fält läggs till i implementeringen kan du göra något av följande:</p><ul><li>**Alternativ 1:** Fyll i en ny godtycklig evar eller ny prop i dataobjektet och mappa det sedan till önskat XDM-fält.<p>Den här processen skapar enhetlighet för implementeringen på klientsidan, men kräver mappning.</p></li><li>**Alternativ 2:** Låt dataobjektet vara en äldre implementering och börja fylla i endast XDM-objektet för alla nya fält.<p>Den här processen kräver inte mappning, men det innebär att vissa av variablerna bara finns i ett dataobjekt, medan andra variabler bara finns i ett XDM-objekt. När du behöver felsöka implementeringen måste du gå till två platser. Se till att era interna arbetsflöden passar för detta.</p></li></ul> |

{style="table-layout:auto"}

## Grundläggande steg

De grundläggande stegen för att migrera en Adobe Analytics-implementering (antingen AppMeasurement eller Analytics-tillägget) till att använda Web SDK för att skicka data till Customer Journey Analytics är:

1. Migrera din Adobe Analytics-implementering till Adobe Experience Platform Web SDK och börja skicka data till Edge Network.

   I det här steget kan du migrera din befintliga Adobe Analytics-implementering till Web SDK. Du kan också skicka data till Adobe Analytics för att validera att allt fungerar i Adobe Analytics innan du skickar data till Customer Journey Analytics. När detta har konfigurerats och data i Adobe Analytics är tillräckliga kan du skicka data från Edge Network till Customer Journey Analytics.

   Tack vare den här flexibiliteten kan du uppgradera till Customer Journey Analytics på ett mer metodiskt och genomtänkt sätt.

   Mer information om hur du gör detta finns i följande artiklar i Adobe Analytics-dokumentationen:

   * [Migrera till Web SDK med hjälp av taggar](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrera till Web SDK med JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Börja skicka data från Edge Network till Platform.

   1. Skicka alla variabler i AppMeasurement-format via dataobjektet.

      Mer information finns i [Variabelmappning av dataobjekt till Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Välj ditt schema.

      Du kan välja om du vill använda ditt befintliga Adobe Analytics-schema eller skapa ett XDM-schema som bättre passar organisationens behov när du börjar använda andra plattformstjänster.

      Adobe rekommenderar att du skapar ett XDM-schema. Mer information finns i [Skapa ett anpassat schema som ska användas med din Customer Journey Analytics Web SDK-implementering](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

      +++Använda Adobe Analytics schema

      | Fördelar | Nackdelar |
      |----------|---------|
      | <p>Fördelarna med att använda Adobe Analytics-schemat är bland annat:</p><ul><li>Enkel uppgradering<p>Om du redan skickar data till Adobe Analytics med Adobe Experience Platform Web SDK kan du lägga till ytterligare en tjänst i ditt datastam för att skicka data till Adobe Experience Platform (som sedan kan användas i din Customer Journey Analytics-konfiguration).</p></li></ul> | <p>Nackdelar med att använda Adobe Analytics-schemat är:</p><ul><li>När du använder Adobe Analytics-schemat begränsas du inte i termer av hur det kan användas med andra plattformsprogram, men det resulterar i ett schema som är mer komplext än det annars skulle kunna vara. Detta beror på att Adobe Analytics-schemat innehåller många objekt som är specifika för Adobe Analytics och som sannolikt inte kommer att användas av din organisation.<p>När du behöver ändra schemat måste du gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></li></ul> |

      +++

      +++Skapa ett XDM-schema

      | Fördelar | Nackdelar |
      |----------|---------|
      | <ul><p>Fördelarna med att uppdatera till ditt eget XDM-schema är bland annat:</p><ul><li>Ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder.</li><p>När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></ul> | <p>Nackdelar med att uppdatera till ditt eget XDM-schema:</p><ul><li>Att uppdatera schemat är en tidsödande process som krävs innan du börjar skicka data till plattformen.</li></ul> |

      +++

   1. Använd datastream-mappning för att mappa alla fält i dataobjektet till ditt XDM-schema.

      Mer information finns i [Mappning](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) i [Datainsamling](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) i Experience Platform-dokumentationen.

{{upgrade-final-step}}.




