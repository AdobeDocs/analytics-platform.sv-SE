---
title: Skapa ett schema för Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 41965bcd5ae8252fbf2ceda0d2b633ec6dc0e9a3
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# Skapa ett datastream som ska användas med Customer Journey Analytics

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web och Mobile SDK implementeras. När data samlas in med Adobe Experience Platform SDK:er skickas data till Adobe Experience Platform Edge Network. Det är datastream som avgör vilka tjänster som data vidarebefordras till.

I din konfiguration vill du konfigurera datastream för att skicka insamlade data till datauppsättningen i Adobe Experience Platform.

>[!NOTE]
>
>Följande steg krävs bara för Adobe Analytics-implementeringar som använder AppMeasurement eller Analytics-tillägg (taggar).
>
>Om din Adobe Analytics-implementering använder Web SDK eller Web SDK Extension finns datastream redan i din Adobe Analytics-miljö.

Så här konfigurerar du datastream:

1. I Adobe Experience Platform väljer du **[!UICONTROL Datastreams]** från [!UICONTROL DATA COLLECTION] i den vänstra listen.

1. Välj **[!UICONTROL New Datastream]**.

1. Namnge och beskriv ditt datastream. Välj ditt schema i listan [!UICONTROL Event Schema].

   ![Ny datastream](assets/new-datastream.png)

1. Välj **[!UICONTROL Save]**.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
