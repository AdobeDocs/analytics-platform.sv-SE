---
title: Importera och använda strömmande data
description: Förklara hur man importerar och använder strömmande data i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 9984200a-71e6-4697-b46f-f53e8d4c507f
role: Admin
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 0%

---

# Importera och använda strömmande data

Den här snabbstartsguiden förklarar hur du kan importera strömmande data till Adobe Experience Platform och sedan använda dessa data i Customer Journey Analytics.

För att uppnå detta måste du:

- **Konfigurera ett schema och en datauppsättning** i Adobe Experience Platform för att definiera modellen (schemat) för de data som du vill samla in och var data (datauppsättningen) ska samlas in.

- **Använd HTTP API-källkopplingen** för att enkelt strömma dina data till datauppsättningen som konfigurerats i Adobe Experience Platform.

- **Konfigurera en anslutning** i Customer Journey Analytics. Den här anslutningen bör (åtminstone) innehålla din Adobe Experience Platform-datauppsättning.

- **Konfigurera en datavy** i Customer Journey Analytics för att definiera mått och dimensioner som du vill använda i Analysis Workspace.

- **Konfigurera ett projekt** i Customer Journey Analytics för att skapa rapporter och visualiseringar.


>[!NOTE]
>
>Den här snabbstartsguiden är en förenklad guide om hur man importerar strömmande data till Adobe Experience Platform och använder dem i Customer Journey Analytics. Vi rekommenderar starkt att man studerar den ytterligare informationen när det hänvisas till.

## Konfigurera ett schema och en datauppsättning

Om du vill importera data till Adobe Experience Platform måste du först definiera vilka data du vill samla in. Alla data som hämtas in till Adobe Experience Platform måste överensstämma med en standardiserad, normaliserad struktur för att de ska kunna identifieras och hanteras av funktioner och funktioner längre fram i kedjan. Experience Data Model (XDM) är standardramverket som tillhandahåller den här strukturen i form av scheman.

När du har definierat ett schema använder du en eller flera datauppsättningar för att lagra och hantera datainsamlingen. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd (vanligtvis en tabell) som innehåller ett schema (kolumner) och fält (rader).

Alla data som importeras till Adobe Experience Platform måste överensstämma med ett fördefinierat schema innan de kan sparas som en datauppsättning.

### Konfigurera ett schema

För den här snabbstarten vill du samla in en del lojalitetsdata, till exempel lojalitets-ID, förmånspoäng och lojalitetsstatus.
Du måste först definiera ett schema som modellerar dessa data.

Så här konfigurerar du ditt schema:

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Schemas]** i [!UICONTROL DATA MANAGEMENT] till vänster.

1. Välj **[!UICONTROL Create schema]**.
.
1. I steget Välj en klass i guiden Skapa schema:

   1. Välj **[!UICONTROL Individual Profile]**.

      ![Skapa ett schema](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Ett Experience Event-schema används för att modellera _beteendet_ för en profil (som scennamn, push-knapp som läggs till i kundvagnen). Ett enskilt profilschema används för att modellera profilen _attribut_ (som namn, e-post, kön).

   1. Välj **[!UICONTROL Next]**.


1. I [!UICONTROL Name and review step] i guiden [!UICONTROL Create schema]:

   1. Ange en **[!UICONTROL Schema display name]** för ditt schema och (valfritt) en **[!UICONTROL Description]**.

      ![Namnge ditt schema](./assets/create-pr-schema-wizard-step-2.png)

   1. Välj **[!UICONTROL Finish]**.

1. På fliken Struktur i exempelschemat:

   1. Välj **[!UICONTROL + Add]** i [!UICONTROL Field groups].

      ![Lägg till fältgrupp](./assets/add-field-group-button.png)

      Fältgrupper är återanvändbara samlingar av objekt och attribut som gör att du enkelt kan utöka dina scheman.

   1. I dialogrutan [!UICONTROL Add fields groups] väljer du fältgruppen **[!UICONTROL Loyalty Details]** i listan.

      ![AEP Web SDK ExperienceEvent, fältgrupp](./assets/loyalty-fieldgroup.png)

      Du kan välja knappen Förhandsgranska om du vill se en förhandsvisning av de fält som är en del av den här fältgruppen.

      ![AEP Web SDK ExperienceEvent, förhandsgranskning av fältgrupp](./assets/loyalty-fieldgroup-preview.png)

      Välj **[!UICONTROL Back]** om du vill stänga förhandsgranskningen.

   1. Välj **[!UICONTROL Add field groups]**.

1. Välj **[!UICONTROL +]** bredvid schemanamnet på panelen [!UICONTROL Structure].

   ![Knappen Lägg till fält i exempelschema](./assets/example-loalty-schema-plus.png)

1. På panelen [!UICONTROL Field Properties] anger du `Identification` som namn, **[!UICONTROL Identification]** som [!UICONTROL Display name], väljer **[!UICONTROL Object]** som [!UICONTROL Type] och väljer **[!UICONTROL Profile Core v2]** som [!UICONTROL Field Group].

   ![Identifieringsobjekt](./assets/identifcation-loyalty-field.png)

   Det här identifieringsobjektet lägger till identifieringsfunktioner i ditt schema. I ditt fall vill du identifiera lojalitetsinformation med e-postadressen i gruppdata.

   Välj **[!UICONTROL Apply]** om du vill lägga till det här objektet i ditt schema.

1. Markera fältet **[!UICONTROL email]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]** och **[!UICONTROL Email]** i [!UICONTROL Identity namespace] på panelen [!UICONTROL Field Properties].

   ![Ange e-postadress som identitet](./assets/specify-email-loyalty-id.png)

   Du anger e-postadressen som den identitet som tjänsten Adobe Experience Platform Identity kan använda för att kombinera (sammanfoga) beteendet för profiler.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i e-postattributet.

1. Välj rotnivån för ditt schema (med schemanamnet) och välj sedan växeln **[!UICONTROL Profile]**.

   Du uppmanas att aktivera schemat för profilen. När data har aktiverats, när data har importerats till datauppsättningar som baseras på detta schema, sammanfogas dessa data i kundprofilen i realtid.

   Mer information finns i [Aktivera schemat för användning i kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >    När du har sparat ett schema som är aktiverat för profilen kan det inte längre inaktiveras för profilen.

   ![Aktivera schema för profilen](./assets/enable-for-profile.png)

1. Välj **[!UICONTROL Save]** om du vill spara ditt schema.

Du har skapat ett minimalt schema som modellerar de lojalitetsdata som du kan importera till Adobe Experience Platform. Schemat gör att profiler kan identifieras med e-postadressen. Genom att aktivera schemat för profilen ser du till att data från din strömningskälla läggs till i kundprofilen i realtid.

Mer information om hur du lägger till och tar bort fältgrupper och enskilda fält i ett schema finns i [Skapa och redigera scheman i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html).

### Konfigurera en datauppsättning

Med ditt schema har du definierat din datamodell. Nu måste du definiera konstruktionen för att lagra och hantera data, vilket sker via datauppsättningar.

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

   ![Aktivera schema för profilen](./assets/loyalty-dataset-profile.png)

Mer information om hur du visar, förhandsgranskar, skapar och tar bort en datauppsättning finns i [Användargränssnittshandbok för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html). Och hur man aktiverar en datauppsättning för kundprofil i realtid.


## Konfigurera en HTTP API-direktuppspelningsanslutning

Källprogrammet strömmar data som överensstämmer med det schema som du skapade och ser ut som.

```json
{
    ...
    "_demosystem4": {
        "identification": {
            "core": {
                "email": "abrocking0@blog.com",
                "loyaltyId": "793406",
            }
        }
    },
    "loyalty": {
        "loyaltyID": [
            "793406"
        ],
        "points": 82.16,
        "status": "Silver"
    }
    ...
}
```

Om du vill direktuppspela dessa data i den datauppsättning som du skapade måste du definiera en direktuppspelningsslutpunkt för de data som ska skickas till. En direktuppspelningsslutpunkt skapas med en HTTP API-källanslutning.

Så här skapar du en HTTP API-källkoppling:

1. I Experience Platform-gränssnittet väljer du **[!UICONTROL Sources]** under [!UICONTROL CONNECTIONS] i den vänstra listen.

2. Välj **[!UICONTROL Streaming]** i listan med [!UICONTROL CATEGORIES].

3. Välj **Konfigurera** i rutan [!UICONTROL HTTP API].

   ![Konfigurera HTTP API-panel](./assets/httpapi-tile.png)

4. I steget [!UICONTROL Authentication] på skärmen [!UICONTROL Add data]:

   Ange ett namn och en beskrivning för HTTP API-anslutningen.

   Välj **[!UICONTROL XDM compatible]** om du vill ange att dataströmmen är kompatibel med ett befintligt XDM-schema.

   Välj **[!UICONTROL Connect to source]**. När anslutningen är klar visas [!UICONTROL Connected].

   ![HTTP API-autentisering](./assets/httpapi-authentication.png)

   Välj **[!UICONTROL Next]** om du vill fortsätta.

5. I steget [!UICONTROL Dataflow detail] på skärmen [!UICONTROL Add data]:

   Välj **[!UICONTROL Existing dataset]**, markera datauppsättningen i datauppsättningslistan och ge [!UICONTROL Dataflow name] ett namn.

   ![Information om dataflöde](./assets/httpapi-dataflowdetail.png)

   Välj **[!UICONTROL Next]**.

6. [!UICONTROL Review]-steget på skärmen [!UICONTROL Add data] ger dig en översikt över HTTP API-anslutningen.

   ![Information om dataflöde](./assets/httpapi-review.png)

   Välj **[!UICONTROL Finish]**.

7. Du ser den slutliga definitionen av slutpunkten för HTTP API-direktuppspelning.

   ![Slutpunkt för HTTP API-direktuppspelning](./assets/httpapi-streamingendpoint.png)

Du kan kopiera URL:en för direktuppspelningsslutpunkten och använda den för att konfigurera ditt lojalitetsprogram så att data direktuppspelas i Adobe Experience Platform lojalitetsdatauppsättning.

Se [Skapa en HTTP API-direktuppspelningsanslutning med användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/streaming/http.html) för en mer utförlig självstudiekurs som förklarar:

- hur autentisering används,
- hur du mappar data när dina inkommande data inte är kompatibla med ditt XDM-schema, och
- hur du skapar en datauppsättning som en del av konfigurationen av direktuppspelningskopplingen.


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

   - Markera datauppsättningen som du skapade tidigare (`Example Loyalty Dataset`) och alla andra datauppsättningar som du vill ta med i anslutningen.

     ![Lägg till datauppsättningar](./assets/cja-connections-2.png)

   - Välj **[!UICONTROL Next]**.

   I steget [!UICONTROL Datasets settings] i [!UICONTROL Add datasets]:

   - För varje datauppsättning:

      - Välj en [!UICONTROL Person ID] bland de tillgängliga identiteter som definieras i datauppsättningsscheman i Adobe Experience Platform.

      - Välj rätt datakälla i listan [!UICONTROL Data source type]. Om du anger **[!UICONTROL Other]** lägger du till en beskrivning för datakällan.

      - Ange **[!UICONTROL Import all new data]** och **[!UICONTROL Dataset backfill existing data]** enligt dina inställningar.

     ![Konfigurera datauppsättningar](./assets/cja-connections-3.png)

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

   ![Datavykomponenter](./assets/cja-dataview-2.png)

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

5. Om du vill skapa din första rapport börjar du dra och släppa dimensioner och mått på [!UICONTROL Freeform table] i [!UICONTROL Panel] . Dra till exempel `Program Points Balance` och `Page View` som mått och `email` som mått för att få en snabb översikt över profiler som har besökt din webbplats och som ingår i lojalitetsprogrammet som samlar in förmånspoäng.

   ![Workspace - första rapporten](./assets/cja-projects-5.png)

Mer information om hur du skapar projekt och bygger analyser med komponenter, visualiseringar och paneler finns i [Översikt över Analysis Workspace](../analysis-workspace/home.md) .

>[!SUCCESS]
>
>Du har slutfört alla steg. Börja med att definiera vilka lojalitetsdata som du vill samla in (schema) och var de ska lagras (datauppsättning) i Adobe Experience Platform, så konfigurerade du en HTTP API-källanslutning för att strömma lojalitetsdata direkt till datauppsättningen. Med datavyns definition kan ni ange vilken dimension och vilka mätvärden som ska användas och slutligen skapa ert första projekt som visualiserar och analyserar era data.
