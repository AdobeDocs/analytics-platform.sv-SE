---
title: Importera data via Adobe Experience Platform Mobile SDK
description: Förklara hur man importerar data till Customer Journey Analytics via Adobe Experience Platform Mobile SDK och Edge Network
solution: Customer Journey Analytics
feature: Basics
exl-id: fb48b031-e093-4490-b457-69dbb5debe8d
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '3089'
ht-degree: 0%

---

# Hämta in data via Mobile SDK

Den här snabbstartsguiden förklarar hur du kan importera spårningsdata för mobilappar direkt till Adobe Experience Platform med Adobe Experience Platform Mobile SDK och Edge Network. Använd sedan dessa data i Customer Journey Analytics.

För att uppnå detta måste du:

- **Konfigurera ett schema och en datauppsättning** i Adobe Experience Platform för att definiera modellen (schemat) för de data som du vill samla in och var data (datauppsättningen) ska samlas in.

- **Konfigurera en datastream** för att konfigurera Adobe Experience Platform Edge Network att dirigera dina insamlade data till datauppsättningen som du konfigurerade i Adobe Experience Platform.

- **Använd taggar** för att enkelt konfigurera regler och dataelement mot data i ditt mobilprogram. Kontrollera sedan att data skickas till den dataström som är konfigurerad på Adobe Experience Platform Edge Network.

- **Distribuera och validera**. Ha en miljö där du kan iterera på taggutvecklingen och när allt har validerats publicerar du det direkt i produktionsmiljön.

- **Konfigurera en anslutning** i Customer Journey Analytics. Den här anslutningen bör (åtminstone) innehålla din Adobe Experience Platform-datauppsättning.

- **Konfigurera en datavy** i Customer Journey Analytics för att definiera mått och dimensioner som du vill använda i Analysis Workspace.

- **Konfigurera ett projekt** i Customer Journey Analytics för att skapa rapporter och visualiseringar.

>[!NOTE]
>
>Den här snabbstartsguiden är en förenklad guide om hur du importerar data som samlats in från ditt program till Adobe Experience Platform och använder dem i Customer Journey Analytics. Vi rekommenderar starkt att man studerar den ytterligare informationen när det hänvisas till.


## Konfigurera ett schema och en datauppsättning

Om du vill importera data till Adobe Experience Platform måste du först definiera vilka data du vill samla in. Alla data som hämtas in till Adobe Experience Platform måste överensstämma med en standardiserad, normaliserad struktur för att de ska kunna identifieras och hanteras av funktioner och funktioner längre fram i kedjan. Experience Data Model (XDM) är standardramverket som tillhandahåller en struktur i form av scheman.

När du har definierat ett schema använder du en eller flera datauppsättningar för att lagra och hantera datainsamlingen. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd (vanligtvis en tabell) som innehåller ett schema (kolumner) och fält (rader).

Alla data som importeras till Adobe Experience Platform måste överensstämma med ett fördefinierat schema innan de kan sparas som en datauppsättning.

### Konfigurera ett schema

Du vill spåra minimala data från profiler som använder din mobilapp, till exempel scennamn och identifiering.
Först måste du definiera ett schema som modellerar dessa data.

Så här konfigurerar du ditt schema:

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Schemas]** i [!UICONTROL DATA MANAGEMENT] till vänster.

1. Välj **[!UICONTROL Create schema]**.
.
1. I steget Välj en klass i guiden Skapa schema:

   1. Välj **[!UICONTROL Experience Event]**.

      ![Skapa ett schema](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Ett Experience Event-schema används för att modellera _beteendet_ för en profil (som scennamn, push-knapp som läggs till i kundvagnen). Ett enskilt profilschema används för att modellera profilen _attribut_ (som namn, e-post, kön).

   1. Välj **[!UICONTROL Next]**.


1. I [!UICONTROL Name and review step] i guiden [!UICONTROL Create schema]:

   1. Ange en **[!UICONTROL Schema display name]** för ditt schema och (valfritt) en **[!UICONTROL Description]**.

      ![Namnge ditt schema](./assets/create-ee-schema-wizard-step-2.png)

   1. Välj **[!UICONTROL Finish]**.

1. På fliken Struktur i exempelschemat:

   1. Välj **[!UICONTROL + Add]** i [!UICONTROL Field groups].

      ![Lägg till fältgrupp](./assets/add-field-group-button.png)

      Fältgrupper är återanvändbara samlingar av objekt och attribut som gör att du enkelt kan utöka ditt schema.

   1. I dialogrutan [!UICONTROL Add fields groups] väljer du fältgruppen **[!UICONTROL AEP Mobile SDK ExperienceEvent]** i listan.

      ![AEP Mobile Lifecycle Details, fältgrupp](./assets/select-aepmobilesdk-experienceevent.png)

      Du kan välja knappen för förhandsgranskning om du vill se en förhandsgranskning av fälten som ingår i den här fältgruppen, till exempel `application > name`.

      ![AEP Mobile Lifecycle Details (fältgruppsförhandsgranskning)](./assets/aepmobilesdk-experienceevent-preview.png)

      Välj **[!UICONTROL Back]** om du vill stänga förhandsgranskningen.

   1. Välj **[!UICONTROL Add field groups]**.

1. Välj **[!UICONTROL +]** bredvid schemanamnet på panelen [!UICONTROL Structure].

   ![Knappen Lägg till fält i exempelschema](./assets/example-mobileschema-plus.png)

1. På panelen [!UICONTROL Field Properties] anger du `identification` som [!UICONTROL Field name], **[!UICONTROL Identification]** som [!UICONTROL Display name], väljer **[!UICONTROL Object]** som [!UICONTROL Type] och väljer **[!UICONTROL ExperienceEvent Core v2.1]** som [!UICONTROL Field Group].

   >[!NOTE]
   >
   >Om fältgruppen inte är tillgänglig söker du efter en annan fältgrupp som innehåller identitetsfält. Eller [skapa en ny fältgrupp](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=sv-SE) och [lägg till nya identitetsfält](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=sv-SE#define-a-identity-field) (som `ecid`, `crmId` och andra som du behöver) i fältgruppen och markera den nya fältgruppen.

   ![Identifieringsobjekt](./assets/identification-field-mobile.png)

   Identifieringsobjektet lägger till identifieringsfunktioner i ditt schema. I så fall vill du identifiera profiler med din mobilapp med hjälp av Experience Cloud ID och e-postadress. Det finns många andra attribut som du kan använda för att spåra din persons ID (till exempel kundens ID, lojalitets-ID).

   Välj **[!UICONTROL Apply]** om du vill lägga till det här objektet i ditt schema.

1. Markera fältet **[!UICONTROL ecid]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]**, **[!UICONTROL Primary Identity]** och **[!UICONTROL ECID]** i listan [!UICONTROL Identity namespace] i den högra panelen.

   ![Ange ECID som identitet](./assets/specify-identity-mobile.png)

   Du anger Experience Cloud Identity som den primära identitet som Adobe Experience Platform Identity-tjänsten kan använda för att kombinera (sammanfoga) beteendet hos profiler med samma ECID.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i attributet ecid.

1. Markera fältet **[!UICONTROL email]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]** och **[!UICONTROL Email]** i listan [!UICONTROL Identity namespace] på panelen [!UICONTROL Field Properties].

   ![Ange e-postadress som identitet](./assets/specify-email-identity-mobile.png)

   Du anger e-postadressen som en annan identitet som kan användas av tjänsten Adobe Experience Platform Identity för att kombinera (sammanfoga) beteendet för profiler.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i e-postattributet.

   Välj **[!UICONTROL Save]**.

1. Markera rotelementet i schemat som visar schemats namn och välj sedan växeln **[!UICONTROL Profile]**.

   Du uppmanas att aktivera schemat för profilen. När data har aktiverats, när data har importerats till datauppsättningar som baseras på detta schema, sammanfogas dessa data i kundprofilen i realtid.

   Mer information finns i [Aktivera schemat för användning i kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE#profile).

   >[!IMPORTANT]
   >
   >    När du har sparat ett schema som är aktiverat för profilen kan det inte längre inaktiveras för profilen.

   ![Aktivera schema för profilen](./assets/enable-for-profile.png)

1. Välj **[!UICONTROL Save]** om du vill spara ditt schema.

Du har skapat ett minimalt schema som modellerar de data du kan hämta från ditt mobilprogram. Schemat gör det möjligt att identifiera profiler med hjälp av Experience Cloud Identity och e-postadress. Genom att aktivera schemat för profilen ser du till att data som hämtas från mobilappen läggs till i kundprofilen i realtid.

Bredvid beteendedata kan du även hämta profilattributdata från ditt mobilprogram (till exempel information om profiler som prenumererar på ett nyhetsbrev).

Så här hämtar du profildata:

- Skapa ett schema baserat på klassen XDM Individual Profile.

- Lägg till fältgruppen Profilkärna v2 i schemat.

- Lägg till ett identifieringsobjekt baserat på fältgruppen Profile Core v2.

- Definiera Experience Cloud ID som primär identifierare och e-postadress som identifierare.

- Aktivera schemat för profilen

Mer information om hur du lägger till och tar bort fältgrupper och enskilda fält i ett schema finns i [Skapa och redigera scheman i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=sv-SE).

### Konfigurera en datauppsättning

Med ditt schema har du definierat din datamodell. Nu måste du definiera konstruktionen för att lagra och hantera data med hjälp av datauppsättningar.

Så här konfigurerar du datauppsättningen:

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Datasets]** i [!UICONTROL DATA MANAGEMENT] till vänster.

2. Välj **[!UICONTROL Create dataset]**.

   ![Skapa datauppsättning](./assets/create-dataset.png)

3. Välj **[!UICONTROL Create dataset from schema]**.

   ![Skapa datauppsättning från schema](./assets/create-dataset-from-schema.png)

4. Markera schemat som du skapade tidigare och välj **[!UICONTROL Next]**.

5. Ge datauppsättningen ett namn och (valfritt) ge en beskrivning.

   ![Namndatauppsättning](./assets/name-your-datatest.png)

6. Välj **[!UICONTROL Finish]**.

7. Välj växeln **[!UICONTROL Profile]**.

   Du uppmanas att aktivera datauppsättningen för profilen. När datauppsättningen är aktiverad berikas kundprofiler i realtid med inkapslade data.

   >[!IMPORTANT]
   >
   >    Du kan bara aktivera en datauppsättning för profilen när schemat, som datauppsättningen följer, också är aktiverat för profilen.

   ![Aktivera schema för profilen](./assets/aepwebsdk-dataset-profile.png)

Mer information om hur du visar, förhandsgranskar, skapar och tar bort en datauppsättning finns i [Användargränssnittshandbok för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=sv-SE). Och hur man aktiverar en datauppsättning för kundprofil i realtid.

## Konfigurera en datastream

En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web och Mobile SDK implementeras. När du samlar in data med Adobe Experience Platform SDK:er skickas data till Adobe Experience Platform Edge Network. Det är datastream som avgör vilka tjänster som data vidarebefordras till.

I din konfiguration vill du att de data du samlar in från mobilappen ska skickas till din datauppsättning i Adobe Experience Platform.

Så här konfigurerar du datastream:

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Datastreams]** från [!UICONTROL DATA COLLECTION] i den vänstra listen.

2. Välj **[!UICONTROL New Datastream]**.

3. Namnge och beskriv ditt datastream. Välj ditt schema i listan [!UICONTROL Event Schema].

   ![Ny datastream](./assets/new-datastream.png)

4. Välj **[!UICONTROL Save]**.

5. Välj **[!UICONTROL Add Service]**.

6. I [!UICONTROL Add Service screen]:

   1. Välj **[!UICONTROL Adobe Experience Platform]** i listan [!UICONTROL Service].

   2. Kontrollera att **[!UICONTROL Enabled]** är markerat.

   3. Välj datauppsättningen i listan [!UICONTROL Event Dataset].

      ![Datastream AEP-tjänst](./assets/datastream-aep-service.png)

   4. Lämna de andra inställningarna och välj **[!UICONTROL Save]** för att spara dataströmmen.

Din datastream är nu konfigurerad för att vidarebefordra data som samlats in från din mobilapp till datauppsättningen i Adobe Experience Platform.

Mer information om hur du konfigurerar ett datastam och hur du hanterar känsliga data finns i [Översikt över datastreams](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=sv-SE).



## Använd taggar

Om du vill implementera kod på din webbplats för att samla in data använder du taggfunktionen i Adobe Experience Platform. Med tagghanteringslösningen kan ni driftsätta kod tillsammans med andra taggningskrav. Taggar är sömlöst integrerade med Adobe Experience Platform med tillägget Adobe Experience Platform Mobile SDK.

### Skapa en tagg

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Tags]** i [!UICONTROL DATA COLLECTION] till vänster.

2. Välj **[!UICONTROL New Property]**.

   Ge taggen ett namn och välj **[!UICONTROL Mobile]**. Välj **[!UICONTROL Save]** om du vill fortsätta.

   ![Skapa en egenskap](./assets/create-mobile-property.png)

### Konfigurera taggen

När du har skapat taggen måste du konfigurera den med rätt tillägg och konfigurera dataelement och regler efter hur du vill spåra webbplatsen och skicka data till Adobe Experience Platform.

Om du vill konfigurera väljer du den nyligen skapade taggen i listan med [!UICONTROL Tag Properties].


#### **Tillägg**

Lägg till tillägget Adobe Platform Edge Network i taggen så att du kan skicka data till Adobe Experience Platform (via din datastream).

Så här skapar och konfigurerar du tillägget Adobe Experience Platform Mobile SDK:

1. Välj **[!UICONTROL Extensions]** i den vänstra listen. Du ser att tilläggen Mobile Core och Profile redan är tillgängliga.

1. Välj **[!UICONTROL Catalog]** i det övre fältet.

1. Sök efter eller bläddra till tillägget **[!UICONTROL Adobe Experience Platform Edge Network]** och välj **[!UICONTROL Install]** i den högra rutan för att installera det.

1. Välj din sandlåda och din tidigare skapade datastam för [!UICONTROL Production Environment] och (valfritt) [!UICONTROL Staging Environment] och [!UICONTROL Development Environment].

   ![Tilläggskonfiguration för AEP Mobile SDK](./assets/aepmobilesdk-extension-datastream.png)

1. Ange **[!UICONTROL Edge Network domain]** under [!UICONTROL Domain configuration]. Använd vanligtvis `<organizationName>.data.adobedc.net`.

1. Välj **[!UICONTROL Save]**.

Mer information finns i [Konfigurera Adobe Experience Platform Edge Network-tillägget](https://developer.adobe.com/client-sdks/documentation/edge-network).

Du vill också konfigurera följande tillägg från katalogen:

- Identitet.
- AEP Assurance.
- Godkännande.

Se [Konfigurera en taggegenskap](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html?lang=sv-SE) i självstudiekursen för mobilappar för Experience-plattformen för mer information om tillägg och deras konfiguration.

#### **Dataelement**

Dataelement är byggstenarna för dataordlistan (eller datamappningen). Använd dataelement för att samla in, ordna och leverera data över marknadsförings- och annonseringsteknologier. Du ställer in dataelement i taggen som läser från mobilappsdata eller händelser och kan användas för att leverera data till Adobe Experience Platform.

Du vill till exempel samla in transportföretagsnamnet från mobilappen.

Så här definierar du ett dataelement för transportföretagsnamn:

1. Välj **[!UICONTROL Data Elements]** i den vänstra listen.

2. Välj **[!UICONTROL Add Data Element]**.

3. I dialogrutan [!UICONTROL Create Data Element]:

   - Ge dataelementet ett namn, till exempel `Carrier Name`.

   - Välj **[!UICONTROL Mobile Core]** i listan [!UICONTROL Extension].

   - Välj **[!UICONTROL Carrier Name]** i listan [!UICONTROL Data Element Type].


     ![Skapa datumelement med sidinformation](./assets/create-dataelement-mobile.png)

   - Välj **[!UICONTROL Save]**.

Du kan skapa så många dataelement du vill och använda dem i regler.


#### **Regler**

Taggar i Adobe Experience Platform följer ett regelbaserat system. De letar efter användarinteraktion och tillhörande data. När villkoren som beskrivs i reglerna är uppfyllda utlöser regeln det tillägg, skript eller den klientkod som du identifierade. Du kan använda regler för att skicka data (som ett XDM-objekt) till Adobe Experience Platform med tillägget Adobe Experience Platform Edge Network.

Du vill till exempel skicka händelsedata när mobilappen används (i förgrunden) och när mobilappen inte används (överförs tillbaka till bakgrunden).

Så här definierar du en regel:

1. Välj **[!UICONTROL Rules]** i den vänstra listen.

2. Välj **[!UICONTROL Create New Rule]**.

3. I dialogrutan [!UICONTROL Create Rule]:

   - Namnge regeln, till exempel `Application Status`.

   - Välj **[!UICONTROL + Add]** under [!UICONTROL Events].

   - I dialogrutan [!UICONTROL Event Configuration]:

      - Välj **[!UICONTROL Mobile Core]** i listan [!UICONTROL Extension].

      - Välj **[!UICONTROL Foreground]** i listan [!UICONTROL Event Type].

      - Välj **[!UICONTROL Keep Changes]**.

   - Klicka på ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg) bredvid [!UICONTROL Mobile Core - Foreground].

      - Välj **[!UICONTROL Mobile Core]** i listan [!UICONTROL Extension].

      - Välj **[!UICONTROL Background]** i listan [!UICONTROL Event Type].

      - Välj **[!UICONTROL Keep Changes]**.

   - Klicka på ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg) Lägg till under [!UICONTROL ACTIONS]. I dialogrutan [!UICONTROL Action Configuration]:

      - Välj **[!UICONTROL Adobe Experience Platform Edge Network]** i listan [!UICONTROL Extension].

      - Välj **[!UICONTROL Forward event to Edge Network]** i listan [!UICONTROL Action Type].

      - Välj **[!UICONTROL Keep Changes]**.

   - Regeln ska se ut så här:

     ![Skapa regel](assets/rule-appstatus.png)

   - Välj **[!UICONTROL Save]**.

Ovanstående är bara ett exempel på en regel som skickar XDM-data med programstatus till Adobe Edge Network och till Adobe Experience Platform.

Du kan använda regler på olika sätt i taggen för att hantera variabler (med dataelementen).

Mer information finns i [Regler](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/#configure-a-rule-to-forward-lifecycle-metrics-to-platform).

### Skapa och publicera taggen

När du har definierat dataelement och regler måste du skapa och publicera taggen. När du skapar en biblioteksversion måste du tilldela den till en miljö. Byggnadens tillägg, regler och dataelement kompileras sedan och placeras i den tilldelade miljön. Varje miljö har en unik inbäddningskod som gör att du kan integrera den tilldelade inbäddningen på din plats.

Så här skapar och publicerar du en tagg:

1. Välj **[!UICONTROL Publishing Flow]** i den vänstra listen.

2. Välj **[!UICONTROL Select a working library]** följt av **[!UICONTROL Add Library…]**.

3. I dialogrutan [!UICONTROL Create Library]:

   - Namnge biblioteket.

   - Välj **[!UICONTROL Development (development)]** i listan [!UICONTROL Environment].

   - Välj **[!UICONTROL + Add All Changed Resources]**.

     ![Publicera - Skapa bibliotek](./assets/build-library-mobile.png)

   - Välj **[!UICONTROL Save & Build to Development]**.

   Taggen sparas och är utformad för din utvecklingsmiljö. En grön punkt visar att taggen har skapats på utvecklingsmiljön.

4. Du kan välja **[!UICONTROL ...]** om du vill återskapa biblioteket eller flytta biblioteket till en staging- eller produktionsmiljö.

Adobe Experience Platform Tags hanterar enkla till komplexa publiceringsarbetsflöden som passar er användning av Adobe Experience Platform Edge Network.

Mer information finns i [Översikt över publicering](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).


### Hämta din taggkod

Slutligen måste du använda taggen i den mobilapp du vill spåra.

Så här får du kodanvisningar som förklarar hur du konfigurerar din mobilapp och använder taggen i appen:

1. Välj **[!UICONTROL Environments]** i den vänstra listen.

2. Välj rätt installationsknapp ![Box](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Box_18_N.svg) i listan över miljöer.

   Välj lämplig plattform ([!UICONTROL iOS], [!UICONTROL Android]) i dialogrutan [!UICONTROL Mobile Install Instructions]. Använd sedan knappen ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) bredvid vart och ett av de relevanta kodfragmenten som du vill använda för att konfigurera och initiera din mobilapp:

   ![Miljö](./assets/environment-mobile.png)

3. Välj **[!UICONTROL Close]**.

I stället för koden för utvecklingsmiljön kan du ha valt en annan miljö (staging, production) baserat på var du håller på att distribuera Adobe Experience Platform Mobile SDK.

Mer information finns i [Miljö](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=sv-SE&).

## Distribuera och validera

Nu kan du distribuera koden i din mobilapp. När appen distribueras börjar den samla in data till Adobe Experience Platform.

Validera implementeringen, korrigera den där det behövs och installera den sedan korrekt i din staging- och produktionsmiljö med publiceringsarbetsflödesfunktionen i Tags.

Se självstudiekursen [Implementera Adobe Experience Cloud i mobilappar](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=sv-SE) för mer detaljerad information.

## Konfigurera en anslutning

Om du vill använda Adobe Experience Platform-data i Customer Journey Analytics skapar du en anslutning som innehåller de data som är resultatet av konfigurationen av ditt schema, din datauppsättning och ditt arbetsflöde.

Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om dessa datauppsättningar måste du först upprätta en anslutning mellan datauppsättningar i Adobe Experience Platform och Workspace.

Så här skapar du en anslutning:

1. I Customer Journey Analytics-gränssnittet väljer du **[!UICONTROL Connections]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.

2. Välj **[!UICONTROL Create new connection]**.

3. På skärmen [!UICONTROL Untitled connection]:

   Namnge och beskriv din anslutning i [!UICONTROL Connection Settings].

   Välj rätt sandlåda i listan [!UICONTROL Sandbox] i [!UICONTROL Data settings] och välj antalet dagliga händelser i listan [!UICONTROL Average number of daily events].

   ![Anslutningsinställningar](./assets/cja-connections-1.png)

   Välj **[!UICONTROL Add datasets]**.

   I steget [!UICONTROL Select datasets] i [!UICONTROL Add datasets]:

   - Välj datauppsättningar som du har skapat tidigare och/eller andra relevanta datauppsättningar som du vill inkludera i din anslutning (till exempel data för Push Tracking Experience Events och Push Profile från Adobe Journey Optimizer)

     ![Lägg till datauppsättningar](./assets/cja-connections-ajopush.png)

   - Välj **[!UICONTROL Next]**.

   I steget [!UICONTROL Datasets settings] i [!UICONTROL Add datasets]:

   - För varje datauppsättning:

      - Välj en [!UICONTROL Person ID] bland de tillgängliga identiteter som definieras i datauppsättningsscheman i Adobe Experience Platform.

      - Välj rätt datakälla i listan [!UICONTROL Data source type]. Om du anger **[!UICONTROL Other]** lägger du till en beskrivning för datakällan.

      - Ange **[!UICONTROL Import all new data]** och **[!UICONTROL Dataset backfill existing data]** enligt dina inställningar.

     ![Konfigurera datauppsättningar](./assets/cja-connections-ajopushid.png)

   - Välj **[!UICONTROL Add datasets]**.

   Välj **[!UICONTROL Save]**.

Mer information om hur du skapar och hanterar en anslutning och hur du väljer och kombinerar datauppsättningar finns i [Anslutningsöversikt](../connections/overview.md).

## Konfigurera en datavy

En datavy är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en anslutning ska tolkas. Här anges alla mått och mätvärden som är tillgängliga i Analysis Workspace och vilka kolumner som måtten och mätvärdena hämtar data från. Datavyer definieras som förberedelser för rapportering i Analysis Workspace.

Så här skapar du en datavy:

1. I Customer Journey Analytics-gränssnittet väljer du **[!UICONTROL Data views]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.

2. Välj **[!UICONTROL Create new data view]**.

3. I steget [!UICONTROL Configure]:

   Välj din anslutning i listan [!UICONTROL Connection].

   Namn och (eventuellt) beskrivning av anslutningen.

   ![Konfigurera datavy](./assets/cja-dataview-1.png)

   Välj **[!UICONTROL Save and continue]**.

4. I steget [!UICONTROL Components]:

   Lägg till alla schemafält och/eller standardkomponenter som du vill inkludera i komponentrutorna [!UICONTROL METRICS] eller [!UICONTROL DIMENSIONS].

   ![Datavykomponenter](./assets/cja-dataview-2-mobile.png)

   Välj **[!UICONTROL Save and continue]**.

5. I steget [!UICONTROL Settings]:

   ![Datavy settings](./assets/cja-dataview-3.png)

   Låt inställningarna vara som de är och välj **[!UICONTROL Save and finish]**.

Mer information om hur du skapar och redigerar en datavy finns i [Översikt över datavyer](../data-views/data-views.md), vilka komponenter som är tillgängliga för dig och hur du använder inställningar för segment och sessioner.


## Konfigurera ett projekt

Analysis Workspace är ett flexibelt webbläsarverktyg som gör att du snabbt kan skapa analyser och dela insikter baserat på dina data. Du använder Workspace-projekt för att kombinera datakomponenter, tabeller och visualiseringar för att skapa analyser och dela dem med vem som helst i organisationen.

Så här skapar du ditt projekt:

1. I Customer Journey Analytics-gränssnittet väljer du **[!UICONTROL Projects]** på den översta menyn.

2. Välj **[!UICONTROL Projects]** i den vänstra navigeringen.

3. Välj **[!UICONTROL Create project]**.

   ![Workspace Project](./assets/cja-projects-1.png)

   Välj **[!UICONTROL Blank project]**.

   ![Workspace - Tomt projekt](./assets/cja-projects-2.png)

4. Välj datavyn i listan.

   ![Workspace Select Data view](./assets/cja-projects-3.png).

5. Om du vill skapa din första rapport börjar du dra och släppa dimensioner och mått på [!UICONTROL Freeform table] i [!UICONTROL Panel] . Du kan till exempel dra `Events` som mått och `Push Title` som dimension, uppdelat efter `Event Type`, för att få en översikt över dina push-meddelanden för din mobilapp och vad som hände med dem.

   ![Workspace - första rapporten](./assets/cja-projects-5-mobile.png)

Mer information om hur du skapar projekt och bygger analyser med komponenter, visualiseringar och paneler finns i [Översikt över Analysis Workspace](../analysis-workspace/home.md) .

>[!SUCCESS]
>
>Du har slutfört alla steg. Börja med att definiera vilka data du vill samla in (schema) och var de ska lagras (datauppsättning) i Adobe Experience Platform. Du konfigurerade en datastam på Edge Network för att se till att data kan vidarebefordras till den datauppsättningen. Sedan definierade och distribuerade du taggen som innehåller tilläggen (Adobe Experience Platform Edge Network med flera), dataelementen och reglerna för att hämta data från mobilappen och skicka dessa data till din dataram. Du har definierat en anslutning i Customer Journey Analytics för att använda push-meddelandespårningsdata för mobilappar och andra data. Med datavyns definition kan ni ange vilken dimension och vilka mätvärden som ska användas och slutligen skapa ert första projekt som visualiserar och analyserar era mobilappsdata.
