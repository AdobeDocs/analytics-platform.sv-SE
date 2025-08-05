---
description: Lär dig använda realtidsrapportering i Analysis Workspace.
title: Använd realtidsrapportering
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: 8f19ed6b4214c434dd4ca2dbb5e311c62da109c0
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 0%

---

# Använd realtidsrapportering {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="Uppdatering i realtid"
>abstract="Gör det möjligt att uppdatera data och visualiseringar i den här panelen i realtid."

{{release-limited-testing}}

Om du vill använda realtidsrapportering aktiverar du alternativet **[!UICONTROL Real-time refresh]** på någon av följande paneler i ditt Workspace-projekt:

* [Tom panel](/help/analysis-workspace/c-panels/blank-panel.md)
* [Frihandsfigur](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Tillskrivning](/help/analysis-workspace/c-panels/attribution.md)
* [Nästa eller föregående objekt](/help/analysis-workspace/c-panels/next-previous.md)

Du ser ett meddelande med tidsstämpeln för den senaste uppdateringen av data. Till exempel: [!UICONTROL  *Senast uppdaterad 07:55 pm*].

Välj den realtidsperiod som du vill rapportera om i listrutan. Tillgängliga alternativ är:

* [!UICONTROL Last 15 minutes]
* [!UICONTROL Last 30 minutes]
* [!UICONTROL Last hour]
* [!UICONTROL Last 8 hours]
* [!UICONTROL Last 24 hours]

Alla visualiseringar i panelen uppdateras nu varje minut i högst 30 minuter medan webbläsarfliken med panelen Uppdatera i realtid är aktiv.

Som exempel kan du se en ögonblicksbild av **[!UICONTROL Real-time reporting panel]** som uppdaterar **[!UICONTROL Total Revenue / Hour]** bar-visualiseringen och **[!UICONTROL Total Revenue / Hour]** friformstabellen när tiden går från **[!UICONTROL *06:26pm*]** till **[!UICONTROL *06:27 pm *]**.

![Realtidsuppdatering](assets/real-time-refresh.gif)

Efter 30 minuter, eller så snart webbläsarfliken blir inaktiv, inaktiveras **[!UICONTROL Real-time refesh]**-växlingen automatiskt och uppdateringar i realtid stoppas.
