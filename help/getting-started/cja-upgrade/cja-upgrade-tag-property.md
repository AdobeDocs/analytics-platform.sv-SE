---
title: Skapa en taggegenskap och lägg till tillägget Web SDK
description: Lär dig hur du skapar en taggegenskap och lägger till Web SDK-tillägget
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Skapa en tagg för din egenskap {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Skapa en taggegenskap i Adobe Experience Platform Data Collection"
>abstract="Taggar är den typiska standarden för datainsamling. Skapa en tagg i Adobe Experience Platform-gränssnittet så att du kan uppdatera datainsamlingsvariablerna när du vill.<br><br>Skapandet av en taggegenskap kan slutföras med flera klick, vilket tar bara några minuter."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Du kan använda taggfunktionen i Adobe Experience Platform för att implementera kod på din webbplats för att samla in data. Med tagghanteringslösningen kan ni driftsätta kod tillsammans med andra taggningskrav. Taggar är smidiga att integrera med Adobe Experience Platform via Adobe Experience Platform Web SDK.

Följande information beskriver hur du skapar en tagg för egenskapen. Ytterligare information finns i [Konfigurera SDK-taggtillägget för webben](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) i Experience Platform-dokumentationen. SDK-webben innehåller [!UICONTROL Adobe Experience Cloud ID Service] internt, så du behöver inte lägga till ID-tjänsttillägget till din tagg.

En egenskap är i princip en behållare som du fyller med tillägg, regler, dataelement och bibliotek när du distribuerar taggar till webbplatsen. Många människor skapar en egenskap för varje webbplats (eller grupp med närbesläktade webbplatser) där de vill distribuera samma uppsättning taggar. Mer information om egenskaper finns i [Egenskaper](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) i dokumentationen för Experience Platform datainsamling.

Så här skapar du en tagg för din egenskap:

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. Välj **[!UICONTROL New Property]**.

   Namnge taggen, markera **[!UICONTROL Web]** och ange ett domännamn. Välj **[!UICONTROL Save]** om du vill fortsätta.

   ![Skapa en egenskap](assets/create-property.png)

{{upgrade-final-step}}
