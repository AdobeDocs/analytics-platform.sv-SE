---
title: Välj schema för Customer Journey Analytics
description: Läs mer om vilka alternativ som är tillgängliga när du väljer ett schema för Customer Journey Analytics och om för- och nackdelarna med det
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---

# Välj schema för Customer Journey Analytics {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="Använd ett anpassat schema"
>abstract="(Rekommenderas) Om du anpassar ditt schema kan din organisation bara spåra det du behöver och undvika de overheadkostnader som är kopplade till dumma och onödiga fält. Det här alternativet inkluderar fältgrupper som lagts till av Web SDK och fältgrupper som är anpassade efter din organisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="Använd standardschemat"
>abstract="(Rekommenderas inte) Adobe Analytics-schemat innehåller mer än tusen fält, vilket kan leda till rörigt och komplext schema. Din organisation måste fortsätta att följa konceptet med props och eVars, som är ett gammalt koncept som inte används i Customer Journey Analytics. Det är svårare att integrera med andra Adobe Experience Platform-tjänster."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Den här dokumentationen bör användas som en del av uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

När du uppgraderar till Customer Journey Analytics rekommenderar Adobe att du skapar ett anpassat Experience Data Model-schema (XDM) som bättre motsvarar organisationens behov när du börjar använda andra plattformstjänster. Du kan också välja att använda ditt befintliga Adobe Analytics-schema.

Tänk på fördelarna och nackdelarna med var och en av dem.

## Skapa ett anpassat schema som är anpassat till din organisation (rekommenderas)

Adobe rekommenderar att du skapar ett anpassat schema när du uppgraderar till Customer Journey Analytics.

| Fördelar | Nackdelar |
|----------|---------|
| <ul><p>Fördelarna med att uppdatera till ditt eget anpassade schema är bland annat:</p><ul><li>Ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder.</li><p>När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></ul> | <p>Nackdelar med att uppdatera till ditt eget anpassade schema:</p><ul><li>Att uppdatera schemat är en tidsödande process som krävs innan du börjar skicka data till plattformen.</li></ul> |

## Använd ditt befintliga Adobe Analytics-schema

Alternativet att använda ditt befintliga Adobe Analytics-schema med Customer Journey Analytics är bara tillgängligt om din Adobe Analytics-implementering har konfigurerats med Adobe Experience Platform Web SDK. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Fördelar | Nackdelar |
|----------|---------|
| <p>Fördelarna med att använda Adobe Analytics-schemat är bland annat:</p><ul><li>Enkel uppgradering<p>Om du redan skickar data till Adobe Analytics med Adobe Experience Platform Web SDK kan du lägga till ytterligare en tjänst i ditt datastam för att skicka data till Adobe Experience Platform (som sedan kan användas i din Customer Journey Analytics-konfiguration).</p></li></ul> | <p>Nackdelar med att använda Adobe Analytics-schemat är:</p><ul><li>När du använder Adobe Analytics-schemat begränsas du inte i termer av hur det kan användas med andra plattformsprogram, men det resulterar i ett schema som är mer komplext än det annars skulle kunna vara. Detta beror på att Adobe Analytics-schemat innehåller många objekt som är specifika för Adobe Analytics och som sannolikt inte kommer att användas av din organisation.<p>När du behöver ändra schemat måste du gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.</p></li></ul> |




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
