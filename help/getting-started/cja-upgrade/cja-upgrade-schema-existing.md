---
title: Skapa ett schema för Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# Använd ditt Adobe Analytics-schema med Customer Journey Analytics

>[!NOTE]
>
>Den här dokumentationen bör användas som en del av uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- this page exists as the "Learn more" link in the info icon for the option "I am comfortable using my Adobe Analytics schema as a basis" -->

Alternativet att använda ett befintligt Adobe Analytics-schema med Customer Journey Analytics är bara tillgängligt om din Adobe Analytics-implementering har konfigurerats med Adobe Experience Platform Web SDK. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

Tänk på följande fördelar och nackdelar med att använda ditt Adobe Analytics-schema med Customer Journey Analytics:

| Fördelar | Nackdelar |
|----------|---------|
| <p>Fördelarna med att använda Adobe Analytics-schemat är bland annat:</p><ul><li>Enkel uppgradering<p>Om du redan skickar data till Adobe Analytics med Adobe Experience Platform Web SDK kan du lägga till ytterligare en tjänst i ditt datastream för att skicka data till Adobe Experience Platform (som sedan kan användas i din Customer Journey Analytics-konfiguration).</p></li></ul> | <p>Nackdelar med att använda Adobe Analytics-schemat är:</p><ul><li>När du använder Adobe Analytics-schemat begränsas du inte i termer av hur det kan användas med andra plattformsprogram, men det resulterar i ett schema som är mer komplext än det annars skulle kunna vara. Detta beror på att Adobe Analytics-schemat innehåller många objekt som är specifika för Adobe Analytics och som sannolikt inte kommer att användas av din organisation.<p>När du behöver ändra schemat måste du gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></li></ul> |

<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->