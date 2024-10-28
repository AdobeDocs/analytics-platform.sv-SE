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
source-wordcount: '221'
ht-degree: 0%

---

# Skapa ett datastream som ska användas med Customer Journey Analytics

>[!NOTE]
>
>Den här dokumentationen bör användas när uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) har slutförts.
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare steg som har genererats dynamiskt för din organisation.
>
>När du är klar med stegen på den här sidan fortsätter du med uppgraderingsstegen som har skapats dynamiskt för din organisation från uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web och Mobile SDK implementeras. När data samlas in med Adobe Experience Platform SDK:er skickas data till Adobe Experience Platform Edge Network. Det är datastream som avgör vilka tjänster som data vidarebefordras till.

I din konfiguration vill du att de data du samlar in från webbplatsen ska skickas till din datauppsättning i Adobe Experience Platform.

Så här konfigurerar du datastream:

1. I Adobe Experience Platform väljer du **[!UICONTROL Datastreams]** från [!UICONTROL DATA COLLECTION] i den vänstra listen.

1. Välj **[!UICONTROL New Datastream]**.

1. Namnge och beskriv ditt datastream. Välj ditt schema i listan [!UICONTROL Event Schema].

   ![Ny datastream](assets/new-datastream.png)

1. Välj **[!UICONTROL Save]**.

1. Följ uppgraderingsstegen som har skapats dynamiskt för din organisation från uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

