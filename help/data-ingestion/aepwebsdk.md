---
title: Importera data via Adobe Experience Platform Web SDK och Edge Network
description: Förklara hur man importerar data till Customer Journey Analytics via Adobe Experience Platform Web SDK och Edge Network
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 0b595e9e-0dcf-4c70-ac6d-5a2322824328
source-git-commit: 3331f41590509ef38cb67802335414ca3de5ff94
workflow-type: tm+mt
source-wordcount: '3273'
ht-degree: 0%

---

# Importera data via Adobe Experience Platform Web SDK och Edge Network

Den här snabbstartsguiden förklarar hur du kan importera data för webbplatsspårning direkt till Adobe Experience Platform med Adobe Experience Platform Web SDK och Edge Network och sedan använda dessa data i Customer Journey Analytics.

För att uppnå detta måste du:

- **Konfigurera ett schema och en datauppsättning** i Adobe Experience Platform för att definiera modellen (schemat) för de data som du vill samla in och var data (datauppsättningen) ska samlas in.

- **Konfigurera en datastream** för att konfigurera Adobe Experience Platform Edge Network så att insamlade data dirigeras till datauppsättningen som du konfigurerade i Adobe Experience Platform.

- **Använd taggar** för att enkelt konfigurera regler och dataelement mot data i ditt datalager på din webbplats. Kontrollera sedan att data skickas till den dataström som är konfigurerad på Adobe Experience Platform Edge Network.

- **Distribuera och validera**. Ha en miljö där du kan iterera på taggutvecklingen och när allt har validerats publicerar du det direkt i produktionsmiljön.

- **Konfigurera en anslutning** i Customer Journey Analytics. Den här anslutningen bör (åtminstone) innehålla din Adobe Experience Platform-datauppsättning.

- **Konfigurera en datavy** i Customer Journey Analytics för att definiera mått och dimensioner som du vill använda i Analysis Workspace.

- **Konfigurera ett projekt** i Customer Journey Analytics för att skapa rapporter och visualiseringar.

>[!NOTE]
>
>Det här är en förenklad guide om hur du importerar data som samlats in från din webbplats till Adobe Experience Platform och använder dem i Customer Journey Analytics. Vi rekommenderar starkt att man studerar den ytterligare informationen när det hänvisas till.


## Konfigurera ett schema och en datauppsättning

Om du vill importera data till Adobe Experience Platform måste du först definiera vilka data du vill samla in. Alla data som hämtas in till Adobe Experience Platform måste överensstämma med en standardiserad, normaliserad struktur för att de ska kunna identifieras och hanteras av funktioner och funktioner längre fram i kedjan. Experience Data Model (XDM) är standardramverket som tillhandahåller den här strukturen i form av scheman.

När du har definierat ett schema använder du en eller flera datauppsättningar för att lagra och hantera datainsamlingen. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader).

Alla data som importeras till Adobe Experience Platform måste överensstämma med ett fördefinierat schema innan de kan sparas som en datauppsättning.

### Konfigurera ett schema

Du vill spåra minimala data från profiler som besöker webbplatsen, till exempel sidnamn och identifiering.
Därför måste du först definiera ett schema som modellerar dessa data.

Så här konfigurerar du ditt schema:

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Schemas]** inom [!UICONTROL DATA MANAGEMENT].

2. Välj **[!UICONTROL Create schema]**. Välj **[!UICONTROL XDM ExperienceEvent]** i listan med alternativ.

   ![Skapa ett schema](./assets/create-ee-schema.png)

   >[!INFO]
   >
   >    Ett Experience Event-schema används för att modellera _beteende_ för en profil (som sidvy, lägg till i kundvagn). Ett enskilt profilschema används för att modellera profilen _attributes_ (som namn, e-post, kön).


3. I [!UICONTROL Untitled schema] skärm:

   1. Ange ett visningsnamn för ditt schema och (valfritt) en beskrivning.

      ![Namnge ditt schema](./assets/name-schema.png)

   2. Välj **[!UICONTROL + Add]** in [!UICONTROL Field groups].

      ![Lägg till fältgrupp](./assets/add-field-group-button.png)

      Fältgrupper är återanvändbara samlingar av objekt och attribut som gör att du enkelt kan utöka ditt schema.

   3. I [!UICONTROL Add fields groups] väljer du **[!UICONTROL AEP Web SDK ExperienceEvent]** fältgrupp från listan.

      ![AEP Web SDK ExperienceEvent, fältgrupp](./assets/select-aepwebsdk-experienceevent.png)

      Du kan välja knappen Förhandsgranska om du vill se en förhandsgranskning av fälten som är en del av den här fältgruppen, som `web > webPageDetails > name`.

      ![AEP Web SDK ExperienceEvent, fältgruppförhandsgranskning](./assets/aepwebsdk-experiencevent-preview.png)

      Välj **[!UICONTROL Back]** för att stänga förhandsgranskningen.

   4. Välj **[!UICONTROL Add field groups]**.

4. Välj **[!UICONTROL +]** bredvid schemanamnet i [!UICONTROL Structure] -panelen.

   ![Knappen Lägg till fält i exempelschema](./assets/example-schema-plus.png)

5. I [!UICONTROL Field Properties] panel, ange `Identification` som namn, **[!UICONTROL Identification]** som [!UICONTROL Display name], markera **[!UICONTROL Object]** som [!UICONTROL Type] och markera **[!UICONTROL ExperienceEvent Core v2.1]** som [!UICONTROL Field Group].

   ![Identifieringsobjekt](./assets/identification-field.png)

   Detta lägger till identifieringsfunktioner i schemat. I ditt fall vill du identifiera profiler som besöker din webbplats med hjälp av Experience Cloud-ID och e-postadress. Det finns många andra attribut som du kan använda för att spåra din besökares identifiering (till exempel kund-ID, lojalitets-ID).

   Välj **[!UICONTROL Apply]** om du vill lägga till det här objektet i ditt schema.

6. Välj **[!UICONTROL ecid]** fält i det identifieringsobjekt som du just lade till, och markera **[!UICONTROL Identity]** och **[!UICONTROL Primary Identity]** och **[!UICONTROL ECID]** från [!UICONTROL Identity namespace] i den högra panelen.

   ![Ange ECID som identitet](./assets/specify-identity.png)

   Du anger Experience Cloud Identity som den primära identitet som Adobe Experience Platform Identity-tjänsten kan använda för att kombinera (sy ihop) beteendet hos profiler med samma ECID.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i attributet ecid.

7. Välj **[!UICONTROL email]** fält i det identifieringsobjekt som du just lade till, och markera **[!UICONTROL Identity]** och **[!UICONTROL Email]** från [!UICONTROL Identity namespace] i [!UICONTROL Field Properties] -panelen.

   ![Ange e-postadress som identitet](./assets/specify-email-identity.png)

   Du anger e-postadressen som en annan identitet som kan användas av tjänsten Adobe Experience Platform Identity för att kombinera (sammanfoga) beteendet för profiler.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i e-postattributet.

   Välj **[!UICONTROL Save]**.

8. Markera rotelementet i schemat som visar schemats namn och välj sedan **[!UICONTROL Profile]** byt.

   Du uppmanas att aktivera profilschemat. När data har aktiverats, när data har importerats till datauppsättningar som baseras på det här schemat, sammanfogas dessa data i kundprofilen i realtid.

   Se [Aktivera schemat för användning i kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) för mer information.

   >[!IMPORTANT]
   >
   >    När du har sparat ett schema som är aktiverat för profilen kan det inte längre inaktiveras för profilen.

   ![Aktivera schema för profil](./assets/enable-for-profile.png)

9. Välj **[!UICONTROL Save]** för att spara ditt schema.

Du har skapat ett minimalt schema som modellerar de data som du kan hämta från webbplatsen. Schemat gör det möjligt att identifiera profiler med hjälp av Experience Cloud-identitet och e-postadress. Genom att aktivera schemat för profil ser du till att data som hämtas från din webbplats läggs till i kundprofilen i realtid.

Bredvid beteendedata kan du även hämta profilattributdata från din webbplats (t.ex. information om profiler som prenumererar på ett nyhetsbrev).

Så här hämtar du profildata:

- Skapa ett schema baserat på klassen XDM Individual Profile.

- Lägg till fältgruppen Profilkärna v2 i schemat.

- Lägg till ett identifieringsobjekt baserat på fältgruppen Profile Core v2.

- Definiera e-post som primär identifierare och e-post som identifierare.

- Aktivera schemat för profilen

Se [Skapa och redigera scheman i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html) om du vill ha mer information om hur du lägger till och tar bort fältgrupper och enskilda fält i ett schema.

### Konfigurera en datauppsättning

Med ditt schema har du definierat din datamodell. Nu måste du definiera konstruktionen för att lagra och hantera data. Detta görs via datauppsättningar.

Så här konfigurerar du datauppsättningen:

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Datasets]** inom [!UICONTROL DATA MANAGEMENT].

2. Välj **[!UICONTROL Create dataset]**.

   ![Skapa datauppsättning](./assets/create-dataset.png)

3. Välj **[!UICONTROL Create dataset from schema]**.

   ![Skapa datauppsättning från schema](./assets/create-dataset-from-schema.png)

4. Markera schemat som du skapade tidigare och välj **[!UICONTROL Next]**.

5. Ge datauppsättningen ett namn och (valfritt) ge en beskrivning.

   ![Namndatauppsättning](./assets/name-your-datatest.png)

6. Välj **[!UICONTROL Finish]**.

7. Välj **[!UICONTROL Profile]** byt.

   Du uppmanas att aktivera datauppsättningen för profilen. När datauppsättningen är aktiverad berikas kundprofiler i realtid med inkapslade data.

   >[!IMPORTANT]
   >
   >    Du kan bara aktivera en datauppsättning för profilen när schemat, som datauppsättningen följer, också är aktiverat för profilen.

   ![Aktivera schema för profil](./assets/aepwebsdk-dataset-profile.png)

Se [Användargränssnittshandbok för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html) om du vill ha mer information om hur du visar, förhandsgranskar, skapar, tar bort en datauppsättning. Och hur man aktiverar en datauppsättning för kundprofil i realtid.

## Konfigurera en datastream

En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web och Mobile SDK implementeras. När du samlar in data med Adobe Experience Platform SDK:er skickas data till Adobe Experience Platform Edge Network. Det är datastream som avgör vilka tjänster som data vidarebefordras till.

I din konfiguration vill du att de data du samlar in från webbplatsen ska skickas till din datauppsättning i Adobe Experience Platform.

Så här konfigurerar du datastream:

1. I användargränssnittet för Adobe Experience Platform väljer du **[!UICONTROL Datastreams]** från [!UICONTROL DATA COLLECTION] till vänster.

2. Välj **[!UICONTROL New Datastream]**.

3. Namnge och beskriv ditt datastream. Välj ditt schema från [!UICONTROL Event Schema] lista.

   ![Ny datastream](./assets/new-datastream.png)

4. Välj **[!UICONTROL Save]**.

5. Välj **[!UICONTROL Add Service]**.

6. I [!UICONTROL Add Service screen]:

   1. Välj **[!UICONTROL Adobe Experience Platform]** från [!UICONTROL Service] lista.

   2. Säkerställ **[!UICONTROL Enabled]** är markerat.

   3. Välj datauppsättning på [!UICONTROL Event Dataset] lista.

      ![Tjänsten Datastream AEP](./assets/datastream-aep-service.png)

   4. Lämna de andra inställningarna och välj **[!UICONTROL Save]** för att spara datastream.

Din datastream är nu konfigurerad för att vidarebefordra data som samlats in från din webbplats till din datauppsättning i Adobe Experience Platform.

Se [Översikt över datastreams](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en) om du vill ha mer information om hur du konfigurerar ett datastam och hur du hanterar känsliga data.



## Använd taggar

Använd taggfunktionen i Adobe Experience Platform för att implementera kod på din webbplats för att faktiskt samla in data. Med tagghanteringslösningen kan ni driftsätta kod tillsammans med andra taggningskrav. Taggar är sömlösa och integrerade med Adobe Experience Platform med tillägget Adobe Experience Platform Web SDK.

### Skapa en tagg

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Tags]** inom [!UICONTROL DATA COLLECTION].

2. Välj **[!UICONTROL New Property]**.

   Namnge taggen och markera **[!UICONTROL Web]** och ange ett domännamn. Välj **[!UICONTROL Save]** för att fortsätta.

   ![Skapa en egenskap](./assets/create-property.png)

### Konfigurera taggen

När du har skapat taggen måste du konfigurera den med rätt tillägg och konfigurera dataelement och regler efter hur du vill spåra webbplatsen och skicka data till Adobe Experience Platform.

Välj den nyligen skapade taggen i listan över [!UICONTROL Tag Properties] för att öppna den.


#### **Tillägg**

Lägg till Adobe Platform Web SDK-tillägget i taggen så att du kan skicka data till Adobe Experience Platform (via din datastream).

Så här skapar och konfigurerar du Adobe Experience Platform Web SDK-tillägget:

1. Välj **[!UICONTROL Extensions]** till vänster.

2. Välj **[!UICONTROL Catalog]** i det övre fältet.

3. Sök efter eller bläddra till Adobe Experience Platform Web SDK-tillägget och välj **[!UICONTROL Install]** för att installera den.

   <img src="./assets/aepwebsdk-extension.png" width="35%"/>

4. Välj din sandlåda och din tidigare skapade datastream för din [!UICONTROL Production Environment] och (valfritt) [!UICONTROL Staging Environment] och [!UICONTROL Development Environment].

   ![Konfiguration av AEP Web SDK-tillägg](./assets/aepwebsk-extension-datastreams.png)

   Välj **[!UICONTROL Save]**.

Se [Konfigurera Adobe Experience Platform Web SDK-tillägget](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) för mer information.

Du vill också konfigurera Experience Cloud ID-tjänsttillägget så att du enkelt kan använda Experience Cloud-ID:t. Experience Cloud ID-tjänsten identifierar besökare i alla Adobe Experience Cloud-lösningar.

Så här skapar och konfigurerar du tjänsttillägget Experience Cloud ID:

1. Välj **[!UICONTROL Extensions]** till vänster.

2. Välj **[!UICONTROL Catalog]** i det övre fältet.

3. Sök efter eller bläddra till Experience Cloud ID-tjänsttillägget och välj **[!UICONTROL Install]** för att installera den.

   <img src="./assets/ecid-extension.png" width="35%"/>

4. Använd standardinställningarna för alla konfigurationer.

5. Välj **[!UICONTROL Save]**.

#### **Dataelement**

Dataelement är byggstenarna för dataordlistan (eller datamappningen). Använd dataelement för att samla in, ordna och leverera data över marknadsförings- och annonseringsteknologier. Du ställer in dataelement i taggen som läser från datalagret och kan användas för att leverera data till Adobe Experience Platform.

Det finns olika typer av dataelement. Du ställer först in ett dataelement för att fånga det sidnamn som besökarna visar på din webbplats.

Så här definierar du ett dataelement för sidnamn:

1. Välj **[!UICONTROL Data Elements]** till vänster.

2. Välj **[!UICONTROL Add Data Element]**.

3. I [!UICONTROL Create Data Element] dialog:

   - Ge dataelementet ett namn, till exempel `Page Name`.

   - Välj **[!UICONTROL Core]** från [!UICONTROL Extension] lista.

   - Välj **[!UICONTROL Page Info]** från [!UICONTROL Data Element Type] lista.

   - Välj **[!UICONTROL Title]** från [!UICONTROL Attribute] lista.

      ![Skapa datumelement med sidinformation](./assets/create-dataelement-1.png)

      Du kan också ha använt värdet från en variabel i datalagret, till exempel `pageName` och [!UICONTROL JavaScript Variable] dataelementtyp för att definiera dataelementet.

      ![Skapa dataelement med JavaScript-variabel](./assets/create-dataelement-2.png)

   - Välj **[!UICONTROL Save]**.

Nu vill du ställa in ett dataelement som refererar till det Experience Cloud-ID som automatiskt tillhandahålls av Adobe Experience Platform Web SDK och som är tillgängligt via tillägget Experience Cloud ID-tjänst.

Så här definierar du ett ECID-dataelement:

1. Välj **[!UICONTROL Data Elements]** till vänster.

2. Välj **[!UICONTROL Add Data Element]**.

3. I [!UICONTROL Create Data Element] dialog:

   - Ge dataelementet ett namn, till exempel `ECID`.

   - Välj **[!UICONTROL Experience Cloud ID Service]** från [!UICONTROL Extension] lista.

   - Välj **[!UICONTROL ECID]** från [!UICONTROL Data Element Type] lista.

      ![ECID-dataelement](./assets/ecid-dataelement.png)

   - Välj **[!UICONTROL Save]**.

Slutligen vill du nu mappa något av dina specifika dataelement till det schema du definierade tidigare. Du definierar ett annat dataelement som tillhandahåller en representation av XDM-schemat.

Så här definierar du ett XDM-objektdataelement:

1. Välj **[!UICONTROL Data Elements]** till vänster.

2. Välj **[!UICONTROL Add Data Element]**.

3. I [!UICONTROL Create Data Element] dialog:

   - Ge dataelementet ett namn, till exempel `XDM - Page View`.

   - Välj **[!UICONTROL Adobe Experience Platform Web SDK]** från [!UICONTROL Extension] lista.

   - Välj **[!UICONTROL XDM Object]** från [!UICONTROL Data Element Type] lista.

   - Välj din sandlåda i [!UICONTROL Sandbox] lista.

   - Välj ditt schema från [!UICONTROL Schema] lista.

   - Mappa `identification > core > ecid` -attribut, som definieras i ditt schema, till ECID-dataelementet. Välj cylinderikonen för att enkelt välja ECID-dataelementet från listan med dataelement.

      ![Välj ECID-dataelement](./assets/pick-ecid-dataelement.png)

      ![Mappa ECID-dataelement](./assets/map-ecid.png)


   - Mappa `web > webPageDetails > name` -attribut, som definieras i ditt schema, till dataelementet Sidnamn.

      ![Mappa dataelement för sidnamn](./assets/map-pagename.png)

   - Välj **[!UICONTROL Save]**.


#### **Regler**

Taggar i Adobe Experience Platform följer ett regelbaserat system. De letar efter användarinteraktion och tillhörande data. När villkoren som beskrivs i reglerna är uppfyllda utlöser regeln det tillägg, skript eller den klientkod som du identifierade. Du kan använda regler för att skicka data (som ett XDM-objekt) till Adobe Experience Platform med tillägget Adobe Experience Platform Web SDK.

Så här definierar du en regel:

1. Välj **[!UICONTROL Rules]** till vänster.

2. Välj **[!UICONTROL Create New Rule]**.

3. I [!UICONTROL Create Rule] dialog:

   - Namnge regeln, till exempel `Page View`.

   - Välj **[!UICONTROL + Add]** under [!UICONTROL Events].

   - I [!UICONTROL Event Configuration] dialog:

      - Välj **[!UICONTROL Core]** från [!UICONTROL Extension] lista.

      - Välj **[!UICONTROL Window Loaded]** från [!UICONTROL Event Type] lista.

         ![Regel - händelsekonfiguration](./assets/event-windowloaded-pageview.png)

      - Välj **[!UICONTROL Keep Changes]**.
   - Välj **[!UICONTROL + Add]** under [!UICONTROL Actions].

   - I [!UICONTROL Action Configuration] dialog:

      - Välj **[!UICONTROL Adobe Experience Platform Web SDK]** från [!UICONTROL Extension] lista.

      - Välj **[!UICONTROL Send Event]** från [!UICONTROL Action Type] lista.

      - Välj **[!UICONTROL web.webpagedetails.pageViews]** från [!UICONTROL Type] lista.

      - Markera cylinderikonen bredvid  [!UICONTROL XDM data] och välj **[!UICONTROL XDM - Page View]** från listan med dataelement.

         ![Regel - åtgärdskonfiguration](./assets/action-pageview-xdm.png)

      - Välj **[!UICONTROL Keep Changes]**.
   - Regeln ska se ut så här:

      ![Skapa regel](assets/rule-pageview.png)

   - Välj **[!UICONTROL Save]**.





Detta är bara ett exempel på hur man definierar en regel som skickar XDM-data, som innehåller värden från andra dataelement, till Adobe Experience Platform.

Du kan använda regler på olika sätt i taggen för att hantera variabler (med dataelementen).

Se [Regler](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) för mer information.

### Skapa och publicera taggen

När du har definierat dataelement och regler måste du skapa och publicera taggen. När du skapar en biblioteksversion måste du tilldela den till en miljö. Byggnadens tillägg, regler och dataelement kompileras sedan och placeras i den tilldelade miljön. Varje miljö har en unik inbäddningskod som gör att du kan integrera den tilldelade inbäddningen på din plats.

Så här skapar och publicerar du en tagg:

1. Välj **[!UICONTROL Publishing Flow]** från den vänstra listen.

2. Välj **[!UICONTROL Select a working library]**, följt av **[!UICONTROL Add Library…]**.

3. I [!UICONTROL Create Library] dialog:

   - Namnge biblioteket.

   - Välj **[!UICONTROL Development (development)]** från [!UICONTROL Environment] lista.

   - Välj **[!UICONTROL + Add All Changed Resources]**.

      ![Publicera - Skapa bibliotek](./assets/create-library-aep.png)

   - Välj **[!UICONTROL Save & Build to Development]**.

   Detta sparar och skapar taggen för din utvecklingsmiljö. En grön punkt visar att taggen har skapats på utvecklingsmiljön.

4. Du kan välja **[!UICONTROL ...]** för att återskapa biblioteket eller flytta biblioteket till en staging- eller produktionsmiljö.

   ![Publicera - Bygg bibliotek](./assets/build-library.png)

Adobe Experience Platform Tags stöder enkla till komplexa publiceringsarbetsflöden som passar din användning av Adobe Experience Platform Web SDK.

Se [Översikt över publicering](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) för mer information.


### Hämta din taggkod

Slutligen måste du installera taggen på den webbplats som du vill spåra. Det innebär att du måste placera kod i rubriktaggen för webbplatsens mall.

Så här hämtar du koden som refererar till din tagg:

1. Välj **[!UICONTROL Environments]** till vänster.

2. Välj rätt installationsknapp i listan över miljöer.

   I [!UICONTROL Web Install Instructions] markerar du kopieringsknappen bredvid skriptkoden som ska se ut så här:

   ```javascript
   <script src="https://assets.adobedtm.com/2a518741ab24/806645a0b9bb/launch-716db315b4e2-development.min.js" async></script>
   ```

   ![Miljö](./assets/environment.png)

3. Välj **[!UICONTROL Close]**.

I stället för koden för utvecklingsmiljön kan du ha valt en annan miljö (staging, production) baserat på var du håller på att distribuera Adobe Experience Platform Web SDK.

Se [Miljö](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?) för mer information.

## Distribuera och validera

Nu kan du distribuera koden till utvecklingsversionen av webbplatsen inifrån `<head>` -tagg. När webbplatsen distribueras börjar den samla in data till Adobe Experience Platform.

Validera implementeringen, korrigera den där det behövs och installera den sedan korrekt i staging- och produktionsmiljön med publiceringsfunktionen i Tags.

## Konfigurera en anslutning

Om du vill använda Adobe Experience Platform-data i Customer Journey Analytics skapar du en anslutning som innehåller de data som är resultatet av konfigurationen av ditt schema, din datauppsättning och ditt arbetsflöde.

Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om dessa datauppsättningar måste du först skapa en anslutning mellan datauppsättningar i Adobe Experience Platform och Workspace.

Så här skapar du en anslutning:

1. I användargränssnittet för Customer Journey Analytics väljer du **[!UICONTROL Connections]** i den övre navigeringen.

2. Välj **[!UICONTROL Create new connection]**.

3. I [!UICONTROL Untitled connection] skärm:

   Namnge och beskriva anslutningen i [!UICONTROL Connection Settings].

   Välj rätt sandlåda i dialogrutan [!UICONTROL Sandbox] lista i [!UICONTROL Data settings] och välj antalet dagliga händelser i dialogrutan [!UICONTROL Average number of daily events] lista.

   ![Anslutningsinställningar](./assets/cja-connections-1.png)

   Välj **[!UICONTROL Add datasets]**.

   I [!UICONTROL Select datasets] steg in [!UICONTROL Add datasets]:

   - Välj den datauppsättning som du skapade tidigare (`Example dataset`) och andra datauppsättningar som du vill inkludera i anslutningen.

      ![Lägg till datauppsättningar](./assets/cja-connections-2b.png)

   - Välj **[!UICONTROL Next]**.
   I [!UICONTROL Datasets settings] steg in [!UICONTROL Add datasets]:

   - För varje datauppsättning:

      - Välj en [!UICONTROL Person ID] från de tillgängliga identiteter som definieras i datauppsättningsscheman i Adobe Experience Platform.

      - Välj rätt datakälla på menyn [!UICONTROL Data source type] lista. Om du anger **[!UICONTROL Other]** lägger du sedan till en beskrivning av datakällan.

      - Ange **[!UICONTROL Import all new data]** och **[!UICONTROL Dataset backfill existing data]** enligt dina önskemål.

      ![Konfigurera datauppsättningar](./assets/cja-connections-3.png)

   - Välj **[!UICONTROL Add datasets]**.
   Välj **[!UICONTROL Save]**.

Se [Anslutningar - översikt](../connections/overview.md) om du vill ha mer information om hur du skapar och hanterar en anslutning och hur du väljer och kombinerar datauppsättningar.

## Konfigurera en datavy

En datavy är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en anslutning ska tolkas. Här anges alla mått och mätvärden som är tillgängliga i Analysis Workspace och vilka kolumner som måtten och mätvärdena hämtar data från. Datavyer definieras som förberedelser för rapportering i Analysis Workspace.

Så här skapar du en datavy:

1. I användargränssnittet för Customer Journey Analytics väljer du **[!UICONTROL Data views]** i den övre navigeringen.

2. Välj **[!UICONTROL Create new data view]**.

3. I [!UICONTROL Configure] steg:

   Välj din anslutning på menyn [!UICONTROL Connection] lista.

   Namn och (eventuellt) beskrivning av anslutningen.

   ![Konfigurera datavy](./assets/cja-dataview-1.png)

   Välj **[!UICONTROL Save and continue]**.

4. I [!UICONTROL Components] steg:

   Lägg till alla schemafält och/eller standardkomponenter som du vill inkludera i [!UICONTROL METRICS] eller [!UICONTROL DIMENSIONS] komponentrutor.

   ![Datavy-komponenter](./assets/cja-dataview-2.png)

   Välj **[!UICONTROL Save and continue]**.

5. I [!UICONTROL Settings] steg:

   ![Inställningar för datavy](./assets/cja-dataview-3.png)

   Låt inställningarna vara som de är och välj **[!UICONTROL Save and finish]**.

Se [Översikt över datavyer](../data-views/data-views.md) för mer information om hur du skapar och redigerar en datavy, vilka komponenter som är tillgängliga för dig och hur du använder filter- och sessionsinställningar.


## Konfigurera ett projekt

Analysis Workspace är ett flexibelt webbläsarverktyg som gör att du snabbt kan skapa analyser och dela insikter baserat på dina data. Du använder Workspace-projekt för att kombinera datakomponenter, tabeller och visualiseringar för att skapa analyser och dela dem med vem som helst i organisationen.

Så här skapar du ditt projekt:

1. I användargränssnittet för Customer Journey Analytics väljer du **[!UICONTROL Projects]** i den övre navigeringen.

2. Välj **[!UICONTROL Projects]** i den vänstra navigeringen.

3. Välj **[!UICONTROL Create project]**.

   ![Arbetsyteprojekt](./assets/cja-projects-1.png)

   Välj **[!UICONTROL Blank project]**.

   ![Arbetsyta - Tomt projekt](./assets/cja-projects-2.png)

4. Välj datavyn i listan.

   ![Vyn Välj data på arbetsytan](./assets/cja-projects-3.png).

5. Börja dra och släppa mått och mätvärden på [!UICONTROL Freeform table] i [!UICONTROL Panel] för att skapa din första rapport. Dra som ett exempel `Program Points Balance` och `Page View` som mått och `email` som en dimension för att få en snabb översikt över profiler som har besökt er webbplats och som ingår i lojalitetsprogrammet som samlar in förmånspoäng.

   ![Arbetsyta - första rapporten](./assets/cja-projects-5.png)

Se [Analysis Workspace - översikt](../analysis-workspace/home.md) om du vill ha mer information om hur du skapar projekt och bygger din analys med hjälp av komponenter, visualiseringar och paneler.

>[!SUCCESS]
>
>Du har slutfört alla steg. Börja med att definiera vilka data du vill samla in (schema) och var de ska lagras (datauppsättning) i Adobe Experience Platform. Du konfigurerade en datastam i Edge Network för att säkerställa att data kan vidarebefordras till den datauppsättningen. Sedan definierade och distribuerade du taggen som innehåller tilläggen (Adobe Experience Platform Web SDK, Experience Cloud ID Service), dataelement och regler för att hämta data från webbplatsen och skicka dessa data till din datastam. Du har definierat en anslutning i Customer Journey Analytics för att använda data för webbplatsspårning och andra data. Med datavyns definition kan ni ange vilken dimension och vilka mätvärden som ska användas och slutligen skapa ert första projekt som visualiserar och analyserar era data.
