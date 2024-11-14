---
title: Implementera taggen loader för Web SDK-tillägget
description: Lär dig hur du implementerar taggen loader för Web SDK-tillägget
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 937a7f31361027438929194f8ccc5aee83c33bc0
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Implementera taggen loader för Web SDK-tillägget

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

Du måste installera taggen på den webbplats som du vill spåra, vilket innebär att du måste placera koden i rubriktaggen för webbplatsens mall.

I följande process beskrivs hur du hämtar koden som refererar till din tagg. Mer information finns i [Implementeringsguiderna för taggar och vidarebefordran av händelser](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) i Experience Platform-dokumentationen.

Så här hämtar du koden som refererar till din tagg:

1. Välj **[!UICONTROL Environments]** i den vänstra listen.

1. Välj rätt installationsknapp i listan över miljöer.

   I dialogrutan [!UICONTROL Web Install Instructions] väljer du kopieringsknappen bredvid skriptkoden som ska se ut så här:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Miljö](assets/environment.png)

1. Välj **[!UICONTROL Close]**.

   I stället för koden för utvecklingsmiljön kan du ha valt en annan miljö (staging, production) baserat på var du håller på att distribuera Adobe Experience Platform Web SDK.

   Mer information finns i [Miljö](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?).

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
