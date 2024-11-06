---
title: Förstå hur Adobe Analytics implementeras och hur det påverkar din uppgradering till Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Förstå hur Adobe Analytics implementeras och hur det påverkar din uppgradering till Customer Journey Analytics

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

Det finns olika sätt att uppgradera till Customer Journey Analytics, men det finns inte alla uppgraderingsalternativ för varje typ av Adobe Analytics-implementering. Den rekommenderade uppgraderingssökvägen är dock tillgänglig oavsett hur Adobe Analytics implementeras i din organisation.

Använd informationen nedan för att få en förståelse för vilka uppgraderingsvägar som finns tillgängliga för din organisation.

Kontakta din Adobe-representant om du behöver mer specifik rådgivning, vägledning eller support.

| Befintlig Adobe Analytics-implementering | Beskrivning | Tillgängliga uppgraderingssökvägar |
|---------|----------|----------|
| AppMeasurement | AppMeasurement för JavaScript har tidigare varit ett vanligt sätt att implementera Adobe Analytics.<p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med AppMeasurementet för JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Ny implementering av Experience Platform Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Analytics Source Connector</li></ul> |
| Adobe Analytics-tillägg (taggar) | <p>Taggar i Adobe Experience Platform är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Adobe erbjuder integreringar med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.</p><p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Analytics-tillägget](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Ny implementering av Experience Platform Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Analytics Source Connector</li></ul> |
| Web SDK (alloy.js) | Experience Platform Web SDK är den metod som rekommenderas av Adobe för att implementera Adobe Analytics. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. <p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li></ul> |
| Web SDK-tillägg (taggar) | Experience Platform Web SDK är den metod som rekommenderas av Adobe för att implementera Adobe Analytics. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. <p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li></ul> |

{style="table-layout:auto"}

