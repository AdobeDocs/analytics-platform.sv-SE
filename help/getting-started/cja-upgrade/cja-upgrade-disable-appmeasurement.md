---
title: Lägg till Analytics-källanslutningsdatauppsättningen i anslutningen
description: Lär dig hur du lägger till Analytics-källanslutningsdatauppsättningen i anslutningen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 9cfe89aef069d777424eb8a5d9ef8ae03a9d0486
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# Inaktivera Adobe Analytics {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Inaktivera AppMeasurement datainsamling"
>abstract="Med Web SDK-data i full funktionalitet kan du samarbeta med ditt utvecklarteam för att ta bort AppMeasurement.js från din webbplats eller egendom.<br><br>Det tar bara några minuter att ta bort AppMeasurement från en webbplats, men det tar tid för teknikteamet att slutföra åtgärden. Se dock till att era Analytics-användare använder Customer Journey Analytics och inte Adobe Analytics. Den här meddelandeprocessen för att flytta alla kan ta betydligt längre tid om ni inte redan har gjort det."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

Innan du inaktiverar Adobe Analytics bör du granska informationen i [Utvärdera när Adobe Analytics ska inaktiveras efter uppgradering till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

* **Taggar:** Inaktivera Adobe Analytics-tillägget

* **AppMeasurment:** Ersätt AppMeasurement.js-biblioteket s=newobject
