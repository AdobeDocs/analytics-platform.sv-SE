---
title: Implementera taggen loader för Web SDK-tillägget
description: Lär dig hur du implementerar Loader-taggen för Web SDK-tillägget
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Implementera taggen loader för Web SDK-tillägget {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="Implementera loader-taggen på din plats"
>abstract="Samarbeta med webbplatsens utvecklingsteam för att installera loader-taggen på alla sidor på webbplatsen.<br><br>Slutförandetiden för den här aktiviteten beror till stor del på svarstiden för det tekniker som du arbetar med för att distribuera koden. Vissa organisationer som har mycket anpassningsbara teknikerteam kan slutföra det här steget på några dagar, medan konstruktionsteam med en lång eftersläpning av uppgifter kan ta en månad eller längre."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Du måste installera taggen på den webbplats som du vill spåra, vilket innebär att du måste placera koden i rubriktaggen för webbplatsens mall.

I följande process beskrivs hur du hämtar koden som refererar till din tagg. Mer information finns i [Implementeringsguiderna för taggar och vidarebefordran av händelser](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) i Experience Platform-dokumentationen.

Så här hämtar du koden som refererar till din tagg:

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. På sidan **[!UICONTROL Tag Properties]** väljer du den nyligen skapade taggen i listan över egenskaper för att öppna den.

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
