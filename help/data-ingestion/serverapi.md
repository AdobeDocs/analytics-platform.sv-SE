---
title: Infoga data via Adobe Experience Platform Edge Network Server API
description: Förklara hur data importeras till Customer Journey Analytics via Adobe Experience Platform Edge Network Server API och Edge Network
solution: Customer Journey Analytics
feature: Basics
exl-id: 6bfb7254-5bb7-45c6-86a2-0651a0d222fa
role: Admin
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '2180'
ht-degree: 0%

---

# Infoga data via Edge Network Server-API

Den här snabbstartsguiden förklarar hur du kan importera spårningsdata från enheter som IoT-enheter, digitalboxar, spelkonsoler och datorprogram direkt till Adobe Experience Platform med Adobe Experience Platform Edge Network Server API och Edge Network. Använd sedan dessa data i Customer Journey Analytics.

För att uppnå detta måste du:

- **Konfigurera ett schema och en datauppsättning** i Adobe Experience Platform för att definiera modellen (schemat) för de data som du vill samla in och var data (datauppsättningen) ska samlas in.

- **Konfigurera en datastream** för att konfigurera Adobe Experience Platform Edge Network att dirigera dina insamlade data till datauppsättningen som du konfigurerade i Adobe Experience Platform.

- **Använd Server-API:t** om du vill skicka data direkt från programmet eller spelet som körs på en stationär dator, spelkonsol, IoT-enhet eller digitalbox till datastream.

- **Distribuera och validera**. Ha en miljö där du kan iterera på utvecklingen och publicera den live i produktionsmiljön när allt har validerats.

- **Konfigurera en anslutning** i Customer Journey Analytics. Den här anslutningen bör (åtminstone) innehålla din Adobe Experience Platform-datauppsättning.

- **Konfigurera en datavy** i Customer Journey Analytics för att definiera mått och dimensioner som du vill använda i Analysis Workspace.

- **Konfigurera ett projekt** i Customer Journey Analytics för att skapa rapporter och visualiseringar.

>[!NOTE]
>
>Den här snabbstartsguiden är en förenklad guide om hur man importerar data som samlats in från ett program eller spel som körs på en IoT-enhet, digitalbox, spelkonsol eller dator till Adobe Experience Platform och använder i Customer Journey Analytics. Vi rekommenderar starkt att man studerar den ytterligare informationen när det hänvisas till.


## Konfigurera ett schema och en datauppsättning

Om du vill importera data till Adobe Experience Platform måste du först definiera vilka data du vill samla in. Alla data som hämtas in till Adobe Experience Platform måste överensstämma med en standardiserad, normaliserad struktur för att de ska kunna identifieras och hanteras av funktioner och funktioner längre fram i kedjan. Experience Data Model (XDM) är standardramverket som tillhandahåller en struktur i form av scheman.

När du har definierat ett schema använder du en eller flera datauppsättningar för att lagra och hantera datainsamlingen. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd (vanligtvis en tabell) som innehåller ett schema (kolumner) och fält (rader).

Alla data som importeras till Adobe Experience Platform måste överensstämma med ett fördefinierat schema innan de kan sparas som en datauppsättning.

### Konfigurera ett schema

Du vill spåra minimala data från profiler som spelar ditt spel på en konsol, till exempel identifiering, bakgrundsmusik, förlopp och annan information.
Du måste först definiera ett schema som modellerar dessa data.

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

   1. I dialogrutan [!UICONTROL Add fields groups] väljer du fältgruppen **[!UICONTROL Blinding Light]** i listan. Den här fältgruppen skapas för att spåra användarförloppet i ett fiktivt spel med namnet Blinding Light på en konsol.

      ![Ljust fältgrupp för blinkning](assets/schema-fieldgroup-blindinglight.png)

      Du kan välja knappen för förhandsgranskning om du vill se en förhandsgranskning av fälten som ingår i den här fältgruppen, till exempel `scores > afterMatch`.

      ![Förhandsvisning av fältgruppen Ljus blinkning](assets/schema-fieldgroup-blindinglight-preview.png)

      Välj **[!UICONTROL Back]** om du vill stänga förhandsgranskningen.

   1. Välj **[!UICONTROL Add field groups]**.

1. Välj **[!UICONTROL +]** bredvid schemanamnet.

   ![Knappen Lägg till fält i exempelschema](./assets/example-gamingschema-plus.png)

1. På panelen [!UICONTROL Field Properties] anger du `identification` som [!UICONTROL Field name], **[!UICONTROL Identification]** som [!UICONTROL Display name], väljer **[!UICONTROL Object]** som [!UICONTROL Type] och väljer **[!UICONTROL ExperienceEvent Core v2.1]** som [!UICONTROL Field Group].

   >[!NOTE]
   >
   >Om fältgruppen inte är tillgänglig söker du efter en annan fältgrupp som innehåller identitetsfält. Eller [skapa en ny fältgrupp](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) och [lägg till nya identitetsfält](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (som `ecid`, `crmId` och andra som du behöver) i fältgruppen och markera den nya fältgruppen.

   ![Identifieringsobjekt](./assets/identification-field-gaming.png)

   Identifieringsobjektet lägger till identifieringsfunktioner i ditt schema. I så fall vill du identifiera profiler som spelar ditt spel med hjälp av det Experience Cloud-ID och den e-postadress som de använder för att logga in på spelkonsolen. Det finns många andra attribut för att spåra din persons identifiering.

   Välj **[!UICONTROL Apply]** om du vill lägga till det här objektet i ditt schema.

1. Markera fältet **[!UICONTROL ecid]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]**, **[!UICONTROL Primary Identity]** och **[!UICONTROL ECID]** i listan [!UICONTROL Identity namespace] i den högra panelen.

   ![Ange ECID som identitet](./assets/specify-identity-gaming.png)

   Du anger Experience Cloud Identity som den primära identitet som Adobe Experience Platform Identity-tjänsten kan använda för att kombinera (sammanfoga) beteendet hos profiler med samma ECID.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i attributet ecid.

1. Markera fältet **[!UICONTROL email]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]** och **[!UICONTROL Email]** i listan [!UICONTROL Identity namespace] på panelen [!UICONTROL Field Properties].

   ![Ange e-postadress som identitet](./assets/specify-email-identity-gaming.png)

   Du anger e-postadressen som en annan identitet som kan användas av tjänsten Adobe Experience Platform Identity för att kombinera (sammanfoga) beteendet för profiler.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i e-postattributet.

   Välj **[!UICONTROL Save]**.

1. Markera rotelementet i schemat som visar schemats namn och välj sedan växeln **[!UICONTROL Profile]**.

   Du uppmanas att aktivera schemat för profilen. När data har aktiverats, när data har importerats till datauppsättningar som baseras på detta schema, sammanfogas dessa data i kundprofilen i realtid.

   Mer information finns i [Aktivera schemat för användning i kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >    När du har sparat ett schema som är aktiverat för profilen kan det inte längre inaktiveras för profilen.

   ![Aktivera schema för profilen](./assets/enable-for-profile.png)

1. Välj **[!UICONTROL Save]** om du vill spara ditt schema.

Du har skapat ett minimalt schema som modellerar de data du kan hämta från ditt spel. Schemat gör det möjligt att identifiera profiler med hjälp av Experience Cloud Identity och e-postadress. Genom att aktivera schemat för profilen ser du till att data som hämtats från ditt konsolspel läggs till i kundprofilen i realtid.

Bredvid beteendedata kan du även hämta profilattributdata från konsolen (t.ex. information om profiler som har loggats in i konsolen).

Så här hämtar du profildata:

- Skapa ett schema baserat på klassen XDM Individual Profile.

- Lägg till fältgruppen Profilkärna v2 i schemat.

- Lägg till ett identifieringsobjekt baserat på fältgruppen Profile Core v2.

- Definiera Experience Cloud ID som primär identifierare och e-postadress som identifierare.

- Aktivera schemat för profilen

Mer information om hur du lägger till och tar bort fältgrupper och enskilda fält i ett schema finns i [Skapa och redigera scheman i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html).

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

Mer information om hur du visar, förhandsgranskar, skapar och tar bort en datauppsättning finns i [Användargränssnittshandbok för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html). Och hur man aktiverar en datauppsättning för kundprofil i realtid.

## Konfigurera en datastream

En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web och Mobile SDK implementeras och Adobe Experience Platform Edge Network Server API. När data samlas in med Adobe Experience Platform SDK:er och Edge Network Server-API:er skickas data till Adobe Experience Platform Edge Network. Det är datastream som avgör vilka tjänster som data vidarebefordras till.

I din konfiguration vill du att de data du samlar in från spelet ska skickas till din datauppsättning i Adobe Experience Platform.

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

Din datastream är nu konfigurerad för att vidarebefordra data som samlats in från ditt spel till datauppsättningen i Adobe Experience Platform.

Mer information om hur du konfigurerar ett datastam och hur du hanterar känsliga data finns i [Översikt över datastreams](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html).

## Använd Edge Network Server-API

Under spelets utveckling kan du lägga till relevanta anrop till Adobe Experience Platform Edge Network Server API där det är lämpligt.

Om du till exempel vill uppdatera spelarens musikspår använder du:

```
curl -X POST "https://server.adobedc.net/ee/v2/interact?dataStreamId={DATASTREAM_ID}"
-H "Authorization: Bearer {TOKEN}"
-H "x-gw-ims-org-id: {ORG_ID}"
-H "x-api-key: {API_KEY}"
-H "Content-Type: application/json"
-d '{
   "event": {
      "xdm": {
         "identityMap": {
            "Email_LC_SHA256": [
               {
                  "id": "0c7e6a405862e402eb76a70f8a26fc732d07c32931e9fae9ab1582911d2e8a3b",
                  "primary": true
               }
            ]
         },
         "eventType": "game.scoreUpdate",
         "{sandbox}": {
            "scores": {
               "afterMatch": 132391",
            }
         },
         "timestamp": "2021-08-09T14:09:20.859Z"
      }
   }
}'
```

I exemplet på POST-begäran pekar `{DATASTREAM_ID}` på identifieraren för det exempeldataflöde som du konfigurerade tidigare. `{sandbox}` är det unika namnet på din sandlåda som identifierar sökvägen till den anpassade fältgruppen Ljus lutning.

Se [Interaktiv datainsamling](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html) och [Icke-interaktiv datainsamling](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html) om du vill ha mer information om hur du använder Edge Network Server-API:t.

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

   - Välj datauppsättningar som du har skapat tidigare och/eller andra relevanta datauppsättningar som du vill inkludera i anslutningen

   - Välj **[!UICONTROL Next]**.

   I steget [!UICONTROL Datasets settings] i [!UICONTROL Add datasets]:

   - För varje datauppsättning:

      - Välj en [!UICONTROL Person ID] bland de tillgängliga identiteter som definieras i datauppsättningsscheman i Adobe Experience Platform.

      - Välj rätt datakälla i listan [!UICONTROL Data source type]. Om du anger **[!UICONTROL Other]** lägger du till en beskrivning för datakällan.

      - Ange **[!UICONTROL Import all new data]** och **[!UICONTROL Dataset backfill existing data]** enligt dina inställningar.

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

   Välj **[!UICONTROL Save and continue]**.

5. I steget [!UICONTROL Settings]:

   ![Datavy settings](./assets/cja-dataview-3.png)

   Låt inställningarna vara som de är och välj **[!UICONTROL Save and finish]**.

Mer information om hur du skapar och redigerar en datavy finns i [Översikt över datavyer](../data-views/data-views.md), vilka komponenter som är tillgängliga för dig och hur du använder inställningar för filter och sessioner.


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

5. Om du vill skapa din första rapport börjar du dra och släppa dimensioner och mått på [!UICONTROL Freeform table] i [!UICONTROL Panel].

Mer information om hur du skapar projekt och bygger analyser med komponenter, visualiseringar och paneler finns i [Översikt över Analysis Workspace](../analysis-workspace/home.md) .

>[!SUCCESS]
>
>Du har slutfört alla steg. Börja med att definiera vilka data du vill samla in (schema) och var de ska lagras (datauppsättning) i Adobe Experience Platform. Du har konfigurerat en datastream på Edge Network för att säkerställa att data kan vidarebefordras till den datauppsättningen. Sedan använde du Edge Network Server-API:t för att skicka data till din datastam. Du har definierat en anslutning i Customer Journey Analytics för att använda speldata och andra data. Med datavyns definition kan ni ange vilken dimension och vilka mätvärden som ska användas och slutligen skapa ert första projekt som visualiserar och analyserar speldata.
