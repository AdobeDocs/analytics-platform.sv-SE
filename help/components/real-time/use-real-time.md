---
description: Lär dig använda realtidsrapportering i Analysis Workspace.
title: Använd realtidsrapportering
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: 82aefce30834d6400d338896dc1968e37596393e
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 0%

---

# Använd realtidsrapportering

{{release-limited-testing}}

Om du vill använda realtidsrapportering aktiverar du alternativet **[!UICONTROL Real-time refresh]** på någon av följande paneler i ditt Workspace-projekt:



* [Tom panel](/help/analysis-workspace/c-panels/blank-panel.md)
* [Frihandsfigur](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Tillskrivning](/help/analysis-workspace/c-panels/attribution.md)
* [Nästa eller föregående objekt](/help/analysis-workspace/c-panels/next-previous.md)
* [Snabba insikter](/help/analysis-workspace/c-panels/quickinsight.md)

Du ser ett meddelande med tidsstämpeln för den senaste uppdateringen av data. Till exempel: [!UICONTROL  *Senast uppdaterad kl. 07:55*].

Välj den realtidsperiod som du vill rapportera om i listrutan. Tillgängliga alternativ är:

* [!UICONTROL Last 15 minutes]
* [!UICONTROL Last 30 minutes]
* [!UICONTROL Last hour]
* [!UICONTROL Last 8 hours]
* [!UICONTROL Last 24 hours]

Alla visualiseringar i panelen uppdateras nu varje minut i högst 30 minuter medan webbläsarfliken med panelen Uppdatera i realtid är aktiv.

![Realtidsuppdatering](assets/real-time-refresh.gif)

Efter 30 minuter, eller så snart webbläsarfliken blir inaktiv, inaktiveras **[!UICONTROL Real-time refesh]**-växlingen automatiskt och uppdateringar i realtid stoppas.
