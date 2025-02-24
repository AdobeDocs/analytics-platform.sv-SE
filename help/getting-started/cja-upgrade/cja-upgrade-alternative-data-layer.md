---
title: Alternativa metoder vid uppgradering till Customer Journey Analytics
description: Läs mer om alternativa metoder vid uppgradering till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# Uppgraderingsalternativ: Skicka datalagret till Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Skicka datalager till Adobe"
>abstract="I stället för att skicka data via ett XDM-objekt kan du skicka hela datalagret till Adobe via dataobjektet.<br><br>Det här alternativet sparar implementeringstid genom att du kan mappa datalagret till XDM i stället för att fylla i ett XDM-objekt från grunden. Den här mappningen är dock mycket viktig eftersom det kommer att finnas en stor mängd data som Adobe inte kan tolka på ett enkelt sätt. Med det här alternativet blir det också mer komplicerat över tid eftersom alla fält som du lägger till i dina data senare i framtiden måste mappas till XDM i datastream."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="Skicka datalagret till Adobe"
>abstract="Konfigurera implementeringen för att skicka data till Adobe vid önskad tidpunkt och konfigurera JSON-nyttolasten så att den blir hela datalagret."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="Tilldela varje datalagerelement till XDM"
>abstract="Mappa alla datalagerelement till önskat XDM-fält. Alla datalagerelement som inte är mappade till ett XDM-fält tas bort permanent eftersom Adobe inte vet var och hur data ska lagras."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i [checklistan för uppgradering av Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

När du uppgraderar till Customer Journey Analytics rekommenderar Adobe [en ny implementering av Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen inte är praktiska för din organisation.

Du kan skicka hela datalagret till Customer Journey Analytics i stället för att samla in data med XDM-objektet. Det här alternativet ger dock ytterligare komplexitet över tid.

## Fördelar och fördelar

Den här metoden kan inte användas samtidigt med [om du använder AppMeasurement datainsamlingslogik med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), eftersom båda metoderna utför samma åtgärd.

Nedan följer fördelar och nackdelar med att använda detta uppgraderingsalternativ:

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>**Tillhandahåller alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användning av personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din aktuella datalagerlogik**: Den här metoden använder din aktuella datalagerlogik i stället för en vanlig Web SDK-implementering. Den här metoden kräver en viss konfiguration, men den kräver ingen helt ny implementering från början och kräver ingen ifyllning av dataelement eller taggregler. Det gör att du kan mappa data från datalagret till XDM i stället för att fylla i ett XDM-objekt från grunden.</li></ul> | <ul><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. <p>Eftersom du med det här alternativet kan placera hela datalagret på klientsidan i dataobjektet och skicka det till Adobe, resulterar det i en avsevärd mängd data som Adobe inte kan tolka på ett enkelt sätt. Om du vill att Adobe ska kunna tolka data måste du använda datastream-mappning för att mappa varje enskilt fält till önskat XDM-fält.</p></li><li>**Rigid-implementering**: Implementeringen begränsas till vad datalagret ger när träffen skickas. Detta kan vara godtagbart för organisationer med grundläggande databehov, men de flesta organisationer bör undvika den här typen av stelbent implementering till förmån för en mer flexibel implementering som tillåter ifyllandet av dataelement.</li><li>**Framtida ändringar är svårare att implementera**: Alla fält som du lägger till i dina data senare i framtiden måste mappas till XDM i datastream.</li></ul> |

{style="table-layout:auto"}

## Grundläggande steg

De grundläggande stegen för att skicka hela datalagret till Customer Journey Analytics är:

1. Konfigurera implementeringen för att skicka data till Adobe vid önskad tidpunkt och konfigurera JSON-nyttolasten så att den blir hela datalagret.

1. Mappa alla datalagerelement till önskat XDM-fält.

   Alla datalagerelement som inte är mappade till ett XDM-fält tas bort permanent eftersom Adobe inte vet var och hur data ska lagras.



