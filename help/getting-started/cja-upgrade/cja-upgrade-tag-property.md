---
title: Skapa en taggegenskap och lägg till tillägget Web SDK
description: Lär dig hur du skapar en taggegenskap och lägger till Web SDK-tillägget
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: cb6a439def7bf0fab1768fdd1c7d909b76b995d6
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# Skapa en tagg för din egenskap

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

Du kan använda taggfunktionen i Adobe Experience Platform för att implementera kod på din webbplats för att samla in data. Med tagghanteringslösningen kan ni driftsätta kod tillsammans med andra taggningskrav. Taggar är smidiga att integrera med Adobe Experience Platform via Adobe Experience Platform Web SDK.

Följande information beskriver hur du skapar en tagg för egenskapen. Ytterligare information finns i [Konfigurera SDK-taggtillägget för webben](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) i dokumentationen för Experience Platform. SDK-webben innehåller [!UICONTROL Adobe Experience Cloud ID Service] internt, så du behöver inte lägga till ID-tjänsttillägget till din tagg.

En egenskap är i princip en behållare som du fyller med tillägg, regler, dataelement och bibliotek när du distribuerar taggar till webbplatsen. Många människor skapar en egenskap för varje webbplats (eller grupp med närbesläktade webbplatser) där de vill distribuera samma uppsättning taggar. Mer information om egenskaper finns i [Egenskaper](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) i Experience Platform datainsamlingsdokumentation.

Så här skapar du en tagg för din egenskap:

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. Välj **[!UICONTROL New Property]**.

   Namnge taggen, markera **[!UICONTROL Web]** och ange ett domännamn. Välj **[!UICONTROL Save]** om du vill fortsätta.

   ![Skapa en egenskap](assets/create-property.png)

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
