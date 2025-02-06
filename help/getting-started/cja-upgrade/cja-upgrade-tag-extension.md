---
title: Skapa en taggegenskap och lägg till tillägget Web SDK
description: Lär dig hur du skapar en taggegenskap och lägger till Web SDK-tillägget
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# Lägg till tillägget Web SDK i taggen {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Lägg till tillägget Platform Web SDK i taggegenskapen"
>abstract="Lägg till Adobe Experience Platform Web SDK-tillägget i taggegenskapen. Tillägget Web SDK till taggegenskaperna är smidigt och tar bara några minuter att slutföra."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

Du kan använda taggfunktionen i Adobe Experience Platform för att implementera kod på din webbplats för att samla in data. Med tagghanteringslösningen kan ni driftsätta kod tillsammans med andra taggningskrav. Taggar är smidiga att integrera med Adobe Experience Platform via Adobe Experience Platform Web SDK.

Följande information beskriver hur du lägger till tillägget Web SDK i taggen. Ytterligare information finns i [Konfigurera SDK-taggtillägget för webben](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) i dokumentationen för Experience Platform. SDK-webben innehåller [!UICONTROL Adobe Experience Cloud ID Service] internt, så du behöver inte lägga till ID-tjänsttillägget till din tagg.

När du har [skapat en tagg](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) måste du konfigurera den med tillägget Adobe Experience Platform Web SDK. Detta garanterar att du kan skicka data till Adobe Experience Platform (via din datastream).

Så här lägger du till tillägget Web SDK i taggen:

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. Markera den nyligen skapade taggen i listan med [!UICONTROL Tag Properties] för att öppna den.

1. Välj **[!UICONTROL Extensions]** i den vänstra listen.

1. Välj **[!UICONTROL Catalog]** i det övre fältet.

1. Sök efter eller bläddra till **[!UICONTROL Adobe Experience Platform Web SDK extension]** och välj sedan **[!UICONTROL Install]** för att installera den.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Välj din sandlåda och din tidigare skapade datastam för [!UICONTROL Production Environment] och (valfritt) [!UICONTROL Staging Environment] och [!UICONTROL Development Environment].

   ![Tilläggskonfiguration för AEP Web SDK](assets/aepwebsk-extension-datastreams.png)

1. Välj **[!UICONTROL Save]**.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
