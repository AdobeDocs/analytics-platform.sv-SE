---
title: Använd taggar för att implementera Web SDK för Customer Journey Analytics
description: Lär dig hur du använder taggar för att implementera Web SDK för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# Använd taggar för att implementera Web SDK för Customer Journey Analytics

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

Du kan använda taggfunktionen i Adobe Experience Platform för att implementera kod på din webbplats för att samla in data. Med tagghanteringslösningen kan ni driftsätta kod tillsammans med andra taggningskrav. Taggar är sömlösa och integrerade med Adobe Experience Platform med tillägget Adobe Experience Platform Web SDK.

## Skapa en tagg

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Tags]** i [!UICONTROL DATA COLLECTION] till vänster.

2. Välj **[!UICONTROL New Property]**.

   Namnge taggen, markera **[!UICONTROL Web]** och ange ett domännamn. Välj **[!UICONTROL Save]** om du vill fortsätta.

   ![Skapa en egenskap](assets/create-property.png)

## Konfigurera taggen

När du har skapat taggen måste du konfigurera den med rätt tillägg och konfigurera dataelement och regler efter hur du vill spåra webbplatsen och skicka data till Adobe Experience Platform.

Markera den nyligen skapade taggen i listan med [!UICONTROL Tag Properties] för att öppna den.


### **Tillägg**

För att vara säker på att du kan skicka data till Adobe Experience Platform (via din datastream) lägger du till Adobe Platform Web SDK-tillägget i taggen.

Så här skapar och konfigurerar du Adobe Experience Platform Web SDK-tillägget:

1. Välj **[!UICONTROL Extensions]** i den vänstra listen.

1. Välj **[!UICONTROL Catalog]** i det övre fältet.

1. Sök efter eller bläddra till Adobe Experience Platform Web SDK-tillägget och välj **[!UICONTROL Install]** för att installera det.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Välj din sandlåda och din tidigare skapade datastam för [!UICONTROL Production Environment] och (valfritt) [!UICONTROL Staging Environment] och [!UICONTROL Development Environment].

   ![Tilläggskonfiguration för AEP Web SDK](assets/aepwebsk-extension-datastreams.png)

   Välj **[!UICONTROL Save]**.

Mer information finns i [Konfigurera Adobe Experience Platform Web SDK-tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html).

Web SDK innehåller [!UICONTROL Adobe Experience Cloud ID Service] internt, så du behöver inte lägga till ID-tjänsttillägget i taggen.

### **Dataelement**

Dataelement är byggstenarna för dataordlistan (eller datamappningen). Använd dataelement för att samla in, ordna och leverera data över marknadsförings- och annonseringsteknologier. Du ställer in dataelement i taggen som läser från datalagret och kan användas för att leverera data till Adobe Experience Platform.

Det finns olika typer av dataelement. Du ställer först in ett dataelement för att fånga det sidnamn som personer tittar på på din webbplats.

Så här definierar du ett dataelement för sidnamn:

1. Välj **[!UICONTROL Data Elements]** i den vänstra listen.

2. Välj **[!UICONTROL Add Data Element]**.

3. I dialogrutan [!UICONTROL Create Data Element]:

   - Ge dataelementet ett namn, till exempel `Page Name`.

   - Välj **[!UICONTROL Core]** i listan [!UICONTROL Extension].

   - Välj **[!UICONTROL Page Info]** i listan [!UICONTROL Data Element Type].

   - Välj **[!UICONTROL Title]** i listan [!UICONTROL Attribute].

     ![Skapa datumelement med sidinformation](assets/create-dataelement-1.png)

     Du kan också ha använt värdet från en variabel i datalagret, till exempel `pageName` och dataelementtypen [!UICONTROL JavaScript Variable] för att definiera dataelementet.

     ![Skapa dataelement med JavaScript-variabel](assets/create-dataelement-2.png)

   - Välj **[!UICONTROL Save]**.

Nu vill du ställa in ett dataelement som refererar till det Experience Cloud-ID som automatiskt tillhandahålls av Adobe Experience Platform Web SDK och som är tillgängligt via tillägget Experience Cloud ID-tjänst.

Så här definierar du ett ECID-dataelement:

1. Välj **[!UICONTROL Data Elements]** i den vänstra listen.

2. Välj **[!UICONTROL Add Data Element]**.

3. I dialogrutan [!UICONTROL Create Data Element]:

   - Ge dataelementet ett namn, till exempel `ECID`.

   - Välj **[!UICONTROL Experience Cloud ID Service]** i listan [!UICONTROL Extension].

   - Välj **[!UICONTROL ECID]** i listan [!UICONTROL Data Element Type].

     ![ECID-dataelement](assets/ecid-dataelement.png)

   - Välj **[!UICONTROL Save]**.

Slutligen vill du nu mappa något av dina specifika dataelement till det schema du definierade tidigare. Du definierar ett annat dataelement som tillhandahåller en representation av XDM-schemat.

Så här definierar du ett XDM-objektdataelement:

1. Välj **[!UICONTROL Data Elements]** i den vänstra listen.

2. Välj **[!UICONTROL Add Data Element]**.

3. I dialogrutan [!UICONTROL Create Data Element]:

   - Ge dataelementet ett namn, till exempel `XDM - Page View`.

   - Välj **[!UICONTROL Adobe Experience Platform Web SDK]** i listan [!UICONTROL Extension].

   - Välj **[!UICONTROL XDM Object]** i listan [!UICONTROL Data Element Type].

   - Välj din sandlåda i listan [!UICONTROL Sandbox].

   - Välj ditt schema i listan [!UICONTROL Schema].

   - Mappa attributet `identification > core > ecid`, som definierats i ditt schema, till ECID-dataelementet. Välj cylinderikonen för att enkelt välja ECID-dataelementet från listan med dataelement.

     ![Välj ECID-dataelement](assets/pick-ecid-dataelement.png)

     ![Mappa ECID-dataelement](assets/map-ecid.png)


   - Mappa attributet `web > webPageDetails > name`, som definierats i ditt schema, till dataelementet för sidnamn.

     ![Mappa dataelement för sidnamn](assets/map-pagename.png)

   - Välj **[!UICONTROL Save]**.


### **Regler**

Taggar i Adobe Experience Platform följer ett regelbaserat system. De letar efter användarinteraktion och tillhörande data. När villkoren som beskrivs i reglerna är uppfyllda utlöser regeln det tillägg, skript eller den klientkod som du identifierade. Du kan använda regler för att skicka data (som ett XDM-objekt) till Adobe Experience Platform med tillägget Adobe Experience Platform Web SDK.

Så här definierar du en regel:

1. Välj **[!UICONTROL Rules]** i den vänstra listen.

1. Välj **[!UICONTROL Create New Rule]**.

1. I dialogrutan [!UICONTROL Create Rule]:

   - Namnge regeln, till exempel `Page View`.

   - Välj **[!UICONTROL + Add]** under [!UICONTROL Events].

   - I dialogrutan [!UICONTROL Event Configuration]:

      - Välj **[!UICONTROL Core]** i listan [!UICONTROL Extension].

      - Välj **[!UICONTROL Window Loaded]** i listan [!UICONTROL Event Type].

        ![Regel - händelsekonfiguration](assets/event-windowloaded-pageview.png)

      - Välj **[!UICONTROL Keep Changes]**.



   - Välj **[!UICONTROL + Add]** under [!UICONTROL Actions].

   - I dialogrutan [!UICONTROL Action Configuration]:

      - Välj **[!UICONTROL Adobe Experience Platform Web SDK]** i listan [!UICONTROL Extension].

      - Välj **[!UICONTROL Send Event]** i listan [!UICONTROL Action Type].

      - Välj **[!UICONTROL web.webpagedetails.pageViews]** i listan [!UICONTROL Type].

      - Välj cylinderikonen bredvid [!UICONTROL XDM data] och välj **[!UICONTROL XDM - Page View]** i listan med dataelement.

     ![Regel - åtgärdskonfiguration](assets/action-pageview-xdm.png)

      - Välj **[!UICONTROL Keep Changes]**.

   - Regeln ska se ut så här:

     ![Skapa regel](assets/rule-pageview.png)

1. Välj **[!UICONTROL Save]**.

Ovanstående är bara ett exempel på en regel som skickar XDM-data, som innehåller värden från andra dataelement, till Adobe Experience Platform.

Du kan använda regler på olika sätt i taggen för att hantera variabler (med dataelementen).

Mer information finns i [Regler](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html).

## Bygg och Publish din tagg

När du har definierat dataelement och regler måste du skapa och publicera taggen. När du skapar en biblioteksversion måste du tilldela den till en miljö. Byggnadens tillägg, regler och dataelement kompileras sedan och placeras i den tilldelade miljön. Varje miljö har en unik inbäddningskod som gör att du kan integrera den tilldelade inbäddningen på din plats.

Så här skapar och publicerar du en tagg:

1. Välj **[!UICONTROL Publishing Flow]** i den vänstra listen.

2. Välj **[!UICONTROL Select a working library]** följt av **[!UICONTROL Add Library…]**.

3. I dialogrutan [!UICONTROL Create Library]:

   - Namnge biblioteket.

   - Välj **[!UICONTROL Development (development)]** i listan [!UICONTROL Environment].

   - Välj **[!UICONTROL + Add All Changed Resources]**.

     ![Publish - Skapa bibliotek](assets/create-library-aep.png)

   - Välj **[!UICONTROL Save & Build to Development]**.

   Taggen sparas och byggs för din utvecklingsmiljö. En grön punkt visar att taggen har skapats på utvecklingsmiljön.

4. Du kan välja **[!UICONTROL ...]** om du vill återskapa biblioteket eller flytta biblioteket till en staging- eller produktionsmiljö.

   ![Publish - Bygg bibliotek](assets/build-library.png)

Adobe Experience Platform Tags stöder enkla till komplexa publiceringsarbetsflöden som passar din användning av Adobe Experience Platform Web SDK.

Mer information finns i [Översikt över publicering](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html).


## Hämta din taggkod

Slutligen måste du installera taggen på den webbplats som du vill spåra, vilket innebär att du måste placera koden i rubriktaggen för webbplatsens mall.

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
