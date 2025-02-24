---
title: Alternativa metoder vid uppgradering till Customer Journey Analytics
description: Läs mer om alternativa metoder vid uppgradering till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 2b66e2db9b22bab5304fe981e58828d4ae9fabbd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 0%

---

# Uppgraderingsalternativ: Använd AppMeasurement datainsamling med Experience Platform Web SDK och Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Använd AppMeasurement-logik med Web SDK"
>abstract="I stället för att skicka data via ett XDM-objekt skickar du alla variabler i AppMeasurement-format via dataobjektet.<br><br>Det här alternativet sparar implementeringstid genom att du kan mappa din AppMeasurement-logik till XDM i stället för att fylla i ett XDM-objekt från grunden. Men det ger ytterligare komplexitet över tid eftersom alla fält som du lägger till i framtiden måste mappas till XDM i datastream."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i [checklistan för uppgradering av Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

När du uppgraderar till Customer Journey Analytics rekommenderar Adobe [en ny implementering av Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen inte är praktiska för din organisation.

Du kan använda AppMeasurement- eller Analytics-tilläggets datainsamlingslogik med Web SDK för att skicka data till Platform och Customer Journey Analytics, i stället för att samla in data med XDM-objektet. Det här alternativet ger dock ytterligare komplexitet över tid.

## Fördelar och fördelar

Den här metoden utesluter varandra när [skickar hela datalagret till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), eftersom båda metoderna utför samma åtgärd. (Den här metoden är bättre än att skicka hela datalagret till Adobe. Det är mer avancerat eftersom props och evar alla går igenom data.__adobe.analytics._variabelnamn_.)

Tänk på följande fördelar och nackdelar med att använda detta uppgraderingsalternativ:

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>**Tillhandahåller alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användning av personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte begränsat till Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din befintliga implementering**: Även om den här metoden kräver vissa implementeringsändringar krävs ingen helt ny implementering från början. Det gör att du kan mappa din AppMeasurement-logik till XDM i stället för att fylla i ett XDM-objekt från grunden.</li></ul> | <ul><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i dataobjektet är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li><li>**Lägger till ytterligare komplexitet över tid**: Alla fält som du lägger till i framtiden måste mappas till XDM i datastream.<p>När ett nytt fält läggs till i implementeringen kan du göra något av följande:</p><ul><li>**Alternativ 1:** Fyll i en ny godtycklig evar eller ny prop i dataobjektet och mappa det sedan till önskat XDM-fält.<p>Den här processen skapar enhetlighet för implementeringen på klientsidan, men kräver mappning.</p></li><li>**Alternativ 2:** Låt dataobjektet vara en äldre implementering och börja fylla i endast XDM-objektet för alla nya fält.<p>Den här processen kräver inte mappning, men det innebär att vissa av variablerna bara finns i ett dataobjekt, medan andra variabler bara finns i ett XDM-objekt. När du behöver felsöka implementeringen måste du gå till två platser. Se till att era interna arbetsflöden passar för detta.</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## Grundläggande steg

De grundläggande stegen för att migrera en Adobe Analytics-implementering (antingen AppMeasurement eller Analytics-tillägget) till att använda Web SDK för att skicka data till Customer Journey Analytics är:

1. (Valfritt) Migrera din Adobe Analytics-implementering till Adobe Experience Platform Web SDK och börja skicka data till Edge Network.

   Detta är ett valfritt steg som gör att du kan migrera din befintliga Adobe Analytics-implementering till att använda Web SDK och validera att allt fungerar i Adobe Analytics. När detta har konfigurerats och data i Adobe Analytics är tillräckliga kan du skicka data från Edge Network till Customer Journey Analytics.

   Tack vare den här flexibiliteten kan du uppgradera till Customer Journey Analytics på ett mer metodiskt och genomtänkt sätt.

   Mer information om hur du gör detta finns i följande artiklar i Adobe Analytics-dokumentationen:

   * [Migrera till Web SDK med hjälp av taggar](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrera till Web SDK med JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Skicka data från Edge Network till Customer Journey Analytics.

   1. Skicka alla variabler i AppMeasurement-format via dataobjektet.

      Mer information finns i [Variabelmappning av dataobjekt till Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Om du inte redan gjort det skapar du ett XDM-schema för din organisation.

      Mer information finns i [Skapa ett anpassat schema som ska användas med din Customer Journey Analytics Web SDK-implementering](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   1. Använd datastream-mappning för att mappa alla fält i dataobjektet till ditt XDM-schema.

      Mer information finns i [Mappning](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) i [Datainsamling](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) i Experience Platform-dokumentationen.

