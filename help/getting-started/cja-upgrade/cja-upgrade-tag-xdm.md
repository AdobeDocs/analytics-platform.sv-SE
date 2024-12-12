---
title: Lägg till logik för XDM-datainsamling i taggen
description: Lär dig hur du lägger till logik för XDM-datainsamling i taggen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: 9849d686e886426124842ce210b423ac6c74fb89
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 0%

---

# Lägg till logik för XDM-datainsamling i taggen

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

När du har [skapat taggen och lagt till Web SDK-tillägget](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) måste du konfigurera den med dataelement och regler, beroende på hur du vill spåra din webbplats och skicka data till Adobe Experience Platform. När du har konfigurerat dataelement och regler för taggen kan du skapa och publicera den.

## Konfigurera dataelement

Dataelement är byggstenarna för dataordlistan (eller datamappningen). Använd dataelement för att samla in, ordna och leverera data över marknadsförings- och annonseringsteknologier. Du ställer in dataelement i taggen som läser från datalagret och kan användas för att leverera data till Adobe Experience Platform.

Det finns olika typer av dataelement. Först ställer du in ett dataelement för att hämta det sidnamn som personer tittar på på din webbplats. Ställ sedan in ett dataelement som refererar till Experience Cloud-ID:t. Definiera slutligen ett XDM-objektdataelement.

### Dataelement för sidnamn

Så här definierar du ett dataelement för sidnamn:

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. Markera den nyligen skapade taggen i listan med [!UICONTROL Tag Properties] för att öppna den.

1. Välj **[!UICONTROL Data Elements]** i den vänstra listen.

1. Välj **[!UICONTROL Add Data Element]**.

1. Ange följande information i dialogrutan [!UICONTROL Create Data Element]:

   * **[!UICONTROL Name]**: Namnet på dataelementet. Till exempel `Page Name`.

   * **[!UICONTROL Extension]**: Välj **[!UICONTROL Core]** i listan.

   * **[!UICONTROL Data Element Type]**: Välj **[!UICONTROL Page Info]** i listan.

   * **[!UICONTROL Attribute]**: Välj **[!UICONTROL Title]** i listan.

     ![Skapa datumelement med sidinformation](assets/create-dataelement-1.png)

     Du kan också ha använt värdet från en variabel i datalagret, till exempel `pageName` och dataelementtypen [!UICONTROL JavaScript Variable] för att definiera dataelementet.

     ![Skapa dataelement med JavaScript-variabel](assets/create-dataelement-2.png)

1. Välj **[!UICONTROL Save]**.

   Nu vill du ställa in ett dataelement som refererar till det Experience Cloud-ID som automatiskt tillhandahålls av Adobe Experience Platform Web SDK och som är tillgängligt via tillägget för Experience Cloud ID-tjänsten.

1. Fortsätt med [ECID-dataelementet](#ecid-data-element).

### ECID-dataelement

Så här definierar du ett ECID-dataelement:

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. Markera den nyligen skapade taggen i listan med [!UICONTROL Tag Properties] för att öppna den.

1. Välj **[!UICONTROL Data Elements]** i den vänstra listen.

1. Välj **[!UICONTROL Add Data Element]**.

1. Ange följande information i dialogrutan [!UICONTROL Create Data Element]:

   * **[!UICONTROL Name]**: Namnet på dataelementet. Till exempel `ECID`.

   * **[!UICONTROL Extension]**: Välj **[!UICONTROL Experience Cloud ID Service]** i listan.

   * **[!UICONTROL Data Element Type]**: Välj **[!UICONTROL ECID]** i listan.

     ![ECID-dataelement](assets/ecid-dataelement.png)

1. Välj **[!UICONTROL Save]**.

1. Fortsätt med [XDM-objektdataelementet](#xdm-object-data-element).

### XDM-objektdataelement

Slutligen vill du nu mappa något av dina specifika dataelement till det schema du definierade tidigare. Du definierar ett annat dataelement som tillhandahåller en representation av XDM-schemat.

Så här definierar du ett XDM-objektdataelement:

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. Markera den nyligen skapade taggen i listan med [!UICONTROL Tag Properties] för att öppna den.

1. Välj **[!UICONTROL Data Elements]** i den vänstra listen.

1. Välj **[!UICONTROL Add Data Element]**.

1. Ange följande information i dialogrutan [!UICONTROL Create Data Element]:

   * **[!UICONTROL Name]**: Namnet på dataelementet. Till exempel `XDM - Page View`.

   * **[!UICONTROL Extension]**: Välj **[!UICONTROL Adobe Experience Platform Web SDK]** i listan.

   * **[!UICONTROL Data Element Type]**: Välj **[!UICONTROL XDM Object]** i listan.

   * **[!UICONTROL Sandbox]**: Välj din sandlåda i listan.

   * **[!UICONTROL Schema]**: Välj ditt schema i listan.

1. Mappa attributet `identification > core > ecid`, som definierats i ditt schema, till ECID-dataelementet. Välj cylinderikonen för att enkelt välja ECID-dataelementet från listan med dataelement.

   ![Välj ECID-dataelement](assets/pick-ecid-dataelement.png)

   ![Mappa ECID-dataelement](assets/map-ecid.png)


1. Mappa attributet `web > webPageDetails > name`, som definierats i ditt schema, till dataelementet för sidnamn.

   ![Mappa dataelement för sidnamn](assets/map-pagename.png)

1. Välj **[!UICONTROL Save]**.

1. Fortsätt med [Konfigurera regler](#configure-rules).

## **Konfigurera regler**

Taggar i Adobe Experience Platform följer ett regelbaserat system. De letar efter användarinteraktion och tillhörande data. När villkoren som beskrivs i reglerna är uppfyllda utlöser regeln det tillägg, skript eller den klientkod som du identifierade. Du kan använda regler för att skicka data (som ett XDM-objekt) till Adobe Experience Platform med tillägget Adobe Experience Platform Web SDK.

Så här definierar du en regel:

>[!NOTE]
>
>Följande steg är ett exempel på hur du definierar en regel som skickar XDM-data, som innehåller värden från andra dataelement, till Adobe Experience Platform.
>
>Du kan använda regler på olika sätt i taggen för att hantera variabler (med dataelementen).
>
>Mer information finns i [Regler](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html).

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. Markera den nyligen skapade taggen i listan med [!UICONTROL Tag Properties] för att öppna den.

1. Välj **[!UICONTROL Rules]** i den vänstra listen.

1. Välj **[!UICONTROL Create New Rule]**.

1. Ange följande information i dialogrutan [!UICONTROL Create Rule]:

   * **[!UICONTROL Name]**: Namnet på regeln. Till exempel `Page View`.

   * **[!UICONTROL Events]**: Välj **[!UICONTROL + Add]**. Ange sedan följande information i dialogrutan [!UICONTROL Event Configuration]. När du är klar väljer du **[!UICONTROL Keep Changes]**.

      * **[!UICONTROL Extension]**: Välj **[!UICONTROL Core]** i listan.

      * **[!UICONTROL Event Type]**: Välj **[!UICONTROL Window Loaded]** i listan.

        ![Regel - händelsekonfiguration](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL Actions]**: Välj **[!UICONTROL + Add]**. Ange sedan följande information i dialogrutan [!UICONTROL Action Configuration]. När du är klar väljer du **[!UICONTROL Keep Changes]**.

      * **[!UICONTROL Extension]**: Välj **[!UICONTROL Adobe Experience Platform Web SDK]** i listan.

      * **[!UICONTROL Action Type]**: Välj **[!UICONTROL Send Event]** i listan.

      * **[!UICONTROL Type]**: Välj **[!UICONTROL web.webpagedetails.pageViews]** i listan.

      * **[!UICONTROL XDM data]**: Välj cylinderikonen och välj sedan **[!UICONTROL XDM - Page View]** i listan med dataelement.

        ![Regel - åtgärdskonfiguration](assets/action-pageview-xdm.png)

        Regeln ska se ut så här:

        ![Skapa regel](assets/rule-pageview.png)

1. Välj **[!UICONTROL Save]**.

## Bygg och publicera taggen

När du har definierat dataelement och regler måste du skapa och publicera taggen. När du skapar en biblioteksversion måste du tilldela den till en miljö. Byggnadens tillägg, regler och dataelement kompileras sedan och placeras i den tilldelade miljön. Varje miljö har en unik inbäddningskod som gör att du kan integrera den tilldelade inbäddningen på din plats.

Adobe Experience Platform Tags hanterar enkla till komplexa publiceringsflöden som passar din användning av Adobe Experience Platform Web SDK. Mer information finns i [Översikt över publicering](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html).

Så här skapar och publicerar du en tagg:

1. Logga in på experience.adobe.com med dina Adobe ID-uppgifter.

1. Gå till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]** i Adobe Experience Platform.

1. Markera den nyligen skapade taggen i listan med [!UICONTROL Tag Properties] för att öppna den.

1. Välj **[!UICONTROL Publishing Flow]** i den vänstra listen.

1. Välj **[!UICONTROL Select a working library]** följt av **[!UICONTROL Add Library…]**.

1. Ange följande information i dialogrutan [!UICONTROL Create Library]:

   * **[!UICONTROL Name]**: Bibliotekets namn.

   * **[!UICONTROL Environment]**: Välj **[!UICONTROL Development (development)]** i listan.

1. Välj **[!UICONTROL + Add All Changed Resources]**.

   ![Publish - Skapa bibliotek](assets/create-library-aep.png)

1. Välj **[!UICONTROL Save & Build to Development]**.

   Taggen sparas och är utformad för din utvecklingsmiljö. En grön punkt visar att taggen har skapats på utvecklingsmiljön.

1. Du kan välja **[!UICONTROL ...]** om du vill återskapa biblioteket eller flytta biblioteket till en staging- eller produktionsmiljö.

   ![Publish - Bygg bibliotek](assets/build-library.png)
