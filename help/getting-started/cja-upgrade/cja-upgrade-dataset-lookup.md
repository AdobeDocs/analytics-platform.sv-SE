---
title: Skapa ett schema för Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Skapa uppslagsdatauppsättningar för att klassificera data i Customer Journey Analytics

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

På samma sätt som med klassificeringsdata i Adobe Analytics är uppslagsuppsättningar en metod för att klassificera data i Customer Journey Analytics.

När du använder Analytics-källkopplingen tillämpas vissa standardsökdatauppsättningar automatiskt vid rapporttillfället. Mer information finns i [Lägga till standardsökningar i dina datauppsättningar](/help/connections/standard-lookups.md).

För att kunna klassificera data med en ny implementering av Experience Platform Web SDK måste du skapa en uppslagsdatauppsättning för varje dimension som innehåller data som du vill klassificera.

Så här skapar du uppslagsdatauppsättningar för användning i Customer Journey Analytics:

1. Skapa ett nytt schema i AEP. Det här är ett nytt schema som är specifikt för uppslagsdatauppsättningar. Du kan inte använda ett befintligt schema.

1. Du måste skapa en ny schemaklass för uppslag.

1. Skapa en uppslagsdatauppsättning av det.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
