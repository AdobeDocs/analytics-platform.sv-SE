---
title: Konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till plattformen
description: Läs om hur du konfigurerar din befintliga Adobe Analytics Web SDK-implementering
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8fdc90ff3392b5d6884872d191a40a762cad6a3f
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 0%

---

# Konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till plattformen {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="Ta bort Adobe Analytics som en tjänst från datastream"
>abstract="Med Web SDK-data i full funktionalitet arbetar du tillsammans med plattformsadministratören för att ta bort Adobe Analytics som en tjänst från datastreammet. Innan du gör detta bör du kontrollera att dina användare har gått över från Adobe Analytics till Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Om Adobe Analytics-implementeringen redan använder Adobe Experience Platform Web SDK kan du börja skicka data till Platform genom att konfigurera en datastream. Eller om du redan skickar data till Platform behöver du bara skapa en anslutning mellan plattformsdatauppsättningar och Customer Journey Analytics.


## Fördelar och fördelar

Tänk på följande fördelar och nackdelar med att konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till Platform:

| Fördelar | Nackdelar |
|----------|---------|
| Detta är den rekommenderade uppgraderingsvägen om Adobe Analytics-implementeringen redan använder Web SDK.<ul><li>**Tillhandahåller alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användning av personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din befintliga implementering**: Även om den här metoden kräver vissa implementeringsändringar krävs ingen helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken utan att påverka din befintliga Adobe Analytics-rapportering.</li><li>**Tillhandahåller ett alternativ för att använda ett XDM-schema**: Du kan välja att använda ditt befintliga Adobe Analytics-schema eller skapa ett XDM-schema och mappa fält i dataobjektet till ditt XDM-schema. [XDM-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) är ett flexibelt schema för att definiera de fält som du behöver, och bara de fält som är relevanta. <p>Se &quot;Använda ditt eget XDM-schema&quot; nedan för mer information om fördelarna med att använda ditt eget XDM-schema.</p></li><li>**Bevarar regler och dataelement**: Även om det krävs nya regelåtgärder kan du återanvända befintliga dataelement och regelvillkor med minimala ändringar.</li><li>**Framtidssäkra**: Om du väljer att använda ditt eget XDM-schema är framtida implementeringsuppdateringar enklare.</li></ul> | <ul><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i dataobjektet är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li><li>**Lägger till ytterligare komplexitet över tid**: Alla fält som du lägger till i framtiden måste mappas till XDM i datastream.<p>När ett nytt fält läggs till i implementeringen kan du göra något av följande:</p><ul><li>**Alternativ 1:** Fyll i en ny godtycklig evar eller ny prop i dataobjektet och mappa det sedan till önskat XDM-fält.<p>Den här processen skapar enhetlighet för implementeringen på klientsidan, men kräver mappning.</p></li><li>**Alternativ 2:** Låt dataobjektet vara en äldre implementering och börja fylla i endast XDM-objektet för alla nya fält.<p>Den här processen kräver inte mappning, men det innebär att vissa av variablerna bara finns i ett dataobjekt, medan andra variabler bara finns i ett XDM-objekt. När du behöver felsöka implementeringen måste du gå till två platser. Se till att era interna arbetsflöden passar för detta.</p></li></ul> |

{style="table-layout:auto"}

## Implementeringssteg

1. Börja skicka data från Edge Network till Platform. Skicka alla variabler i AppMeasurement-format via dataobjektet.

   Mer information finns i [Variabelmappning av dataobjekt till Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

1. Välj ditt schema.

   Du kan välja om du vill använda ditt befintliga Adobe Analytics-schema eller skapa ett XDM-schema som bättre passar organisationens behov när du börjar använda andra plattformstjänster.

   Adobe rekommenderar att du skapar ett XDM-schema. Mer information finns i [Skapa ett anpassat schema som ska användas med din Customer Journey Analytics Web SDK-implementering](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   +++Använd Adobe Analytics-schemat

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

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).




