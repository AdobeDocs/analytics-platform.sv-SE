---
title: Skapa ditt schema för användning med Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Skapa ditt schema för användning med Customer Journey Analytics

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

Adobe rekommenderar att du skapar ett XDM-schema (Experience Data Model) när du uppgraderar till Customer Journey Analytics. Ett XDM-schema möjliggör ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder. När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.

Innan du börjar skapa XDM-schemat:

1. Identifiera ert datateam och andra intressenter i hela organisationen.

1. Bestäm din organisations idealiska schemadesign för Customer Journey Analytics, samtidigt som du tar hänsyn till andra Adobe Experience Platform-program som används i din organisation.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).

