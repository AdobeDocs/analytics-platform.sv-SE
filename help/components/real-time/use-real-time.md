---
description: Lär dig använda realtidsrapportering i Analysis Workspace.
title: Använd realtidsrapportering
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---


# Använd realtidsrapportering

{{release-limited-testing}}

Om du vill använda realtidsrapportering aktiverar du alternativet **[!UICONTROL Real-time refresh]** på någon av följande paneler i ditt Workspace-projekt:



* [Tom panel](/help/analysis-workspace/c-panels/blank-panel.md)
* [Frihandspanelen](/help/analysis-workspace/c-panels/freeform-panel.md)
* ...

Du ser ett meddelande med tidsstämpeln för den senaste uppdateringen av data. Till exempel: [!UICONTROL &#x200B; *Senast uppdaterad kl. 07:55*].

Välj den realtidsperiod som du vill rapportera om i listrutan. Tillgängliga alternativ är:

* [!UICONTROL Last 15 minutes]
* [!UICONTROL Last 30 minutes]
* [!UICONTROL Last hour]
* [!UICONTROL Last 8 hours]
* [!UICONTROL Last 24 hours]

Alla visualiseringar uppdateras nu varje minut i högst 30 minuter medan webbläsarfliken med panelen Uppdatera i realtid är aktiv.

![Realtidsuppdatering](assets/real-time-refresh.gif)

Efter 30 minuter, eller så snart webbläsarfliken blir inaktiv, inaktiveras **[!UICONTROL Real-time refesh]**-växlingen automatiskt och uppdateringar i realtid stoppas.
