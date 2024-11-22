---
title: Skapa ditt schema för användning med Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# Skapa ditt schema för användning med Customer Journey Analytics

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

Adobe rekommenderar att du skapar ett XDM-schema (Experience Data Model) när du uppgraderar till Customer Journey Analytics. Ett XDM-schema möjliggör ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder. När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.

Granska följande avsnitt när du börjar skapa XDM-schemat.

## Undvik Adobe Analytics-begränsningar i XDM-schemat

Den underliggande arkitekturen i Customer Journey Analytics ger mycket större flexibilitet än Adobe Analytics. Att skapa ett nytt XDM-schema är ett viktigt sätt att låsa upp den flexibiliteten. När du uppgraderar till Customer Journey Analytics bör du se till att du inte överför onödiga Adobe Analytics-begränsningar till ditt schema.

| Adobe Analytics dataarkitektur | XDM-schemaarkitektur |
|---------|----------|
| Enskilda mätvärden läggs till i Analytics-dataarkitekturen.<br/>I Adobe Analytics har du till exempel olika eVar för varje händelse. | Skapa enskilda mått i datavyn i stället för i XDM-schemat. Det ger större flexibilitet om du behöver göra ändringar vid ett senare tillfälle.<br/>I Customer Journey Analytics har du till exempel en enda händelse i schemat och använder create-händelser i datavyn. |
| Props och eVars krävs för att skapa anpassade variabler. | B2 |
| A3 | B3 |

## Identifiera ert datateam och andra intressenter i hela organisationen


## Överväg andra Adobe Experience Platform-program som används i er organisation



1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
