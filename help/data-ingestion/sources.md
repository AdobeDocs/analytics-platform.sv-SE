---
title: Importera och använda data med hjälp av källkopplingar
description: Förklara hur du importerar och använder data med hjälp av källanslutningar i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 813d3213-86b3-431a-821c-174e5e36d032
source-git-commit: 7ed28afa9d98a581e2d648dcfb438f960900f602
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 0%

---

# Importera och använda data med hjälp av källkopplingar.

Den här snabbstartsguiden förklarar hur du kan importera data till Adobe Experience Platform med hjälp av en källanslutning till en DataProvider och sedan använda dessa data i Customer Journey Analytics.

För att uppnå detta måste du:

- **Konfigurera ett schema och en datauppsättning** i Adobe Experience Platform för att definiera modellen (schemat) för de data som du vill samla in och var data (datauppsättningen) ska samlas in.

- **Använda en källkoppling** i Adobe Experience Platform för att hämta data till den konfigurerade datauppsättningen.

- **Konfigurera en anslutning** i Customer Journey Analytics. Den här anslutningen bör (åtminstone) innehålla din Adobe Experience Platform-datauppsättning.

- **Konfigurera en datavy** i Customer Journey Analytics för att definiera mått och dimensioner som du vill använda i Analysis Workspace.

- **Konfigurera ett projekt** i Customer Journey Analytics för att skapa rapporter och visualiseringar.



>[!NOTE]
>
>Den här snabbstartsguiden är en förenklad guide om hur du importerar data med en källanslutning till Adobe Experience Platform och använder den i Customer Journey Analytics. Vi rekommenderar starkt att man studerar den ytterligare informationen när det hänvisas till.


## Konfigurera ett schema och en datauppsättning

Om du vill importera data till Adobe Experience Platform måste du först definiera vilka data du vill samla in. Alla data som hämtas in till Adobe Experience Platform måste överensstämma med en standardiserad, normaliserad struktur för att de ska kunna identifieras och hanteras av funktioner och funktioner längre fram i kedjan. Experience Data Model (XDM) är standardramverket som tillhandahåller strukturen i form av scheman.

När du har definierat ett schema använder du en eller flera datauppsättningar för att lagra och hantera datainsamlingen. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd (vanligtvis en tabell) som innehåller ett schema (kolumner) och fält (rader).

Alla data som importeras till Adobe Experience Platform måste överensstämma med ett fördefinierat schema innan de kan sparas som en datauppsättning.

### Konfigurera ett schema

För den här snabbstarten vill du samla in en del lojalitetsdata, till exempel lojalitets-ID, förmånspoäng och lojalitetsstatus.
Du måste först definiera ett schema som modellerar dessa data.

Så här konfigurerar du ditt schema:

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Schemas]** inom [!UICONTROL DATA MANAGEMENT].

1. Välj **[!UICONTROL Create schema]**. .
1. I steget Välj en klass i guiden Skapa schema väljer du **[!UICONTROL Individual Profile]**.

   ![Skapa ett schema](./assets/create-pr-schema-wizard-step-1.png)

   >[!INFO]
   >
   >    Ett Experience Event-schema används för att modellera _beteende_ för en profil (som scennamn, tryck på knappen för att lägga till i kundvagnen). Ett enskilt profilschema används för att modellera profilen _attributes_ (som namn, e-post, kön).

   Välj **[!UICONTROL Next]**.


1. I [!UICONTROL Name and review step] i [!UICONTROL Create schema] guide:

   1. Ange en **[!UICONTROL Schema display name]** för ditt schema och (valfritt) en **[!UICONTROL Description]**.

      ![Namnge ditt schema](./assets/create-pr-schema-wizard-step-2.png)

   1. Välj **[!UICONTROL Finish]**.

1. På fliken Struktur i exempelschemat:

   1. Välj **[!UICONTROL + Add]** in [!UICONTROL Field groups].

      ![Lägg till fältgrupp](./assets/add-field-group-button.png)

      Fältgrupper är återanvändbara samlingar av objekt och attribut som gör att du enkelt kan utöka dina scheman.

   1. I [!UICONTROL Add fields groups] väljer du **[!UICONTROL Loyalty Details]** fältgrupp från listan.

      ![AEP Web SDK ExperienceEvent, fältgrupp](./assets/loyalty-fieldgroup.png)

      Du kan välja knappen Förhandsgranska om du vill se en förhandsvisning av de fält som är en del av den här fältgruppen.

      ![AEP Web SDK ExperienceEvent, fältgruppförhandsgranskning](./assets/loyalty-fieldgroup-preview.png)

      Välj **[!UICONTROL Back]** för att stänga förhandsgranskningen.

   1. Välj **[!UICONTROL Add field groups]**.

1. Välj **[!UICONTROL +]** bredvid schemanamnet i [!UICONTROL Structure] -panelen.

   ![Knappen Lägg till fält i exempelschema](./assets/example-loalty-schema-plus.png)

1. I [!UICONTROL Field Properties] panel, ange `Identification` som namn, **[!UICONTROL Identification]** som [!UICONTROL Display name], markera **[!UICONTROL Object]** som [!UICONTROL Type] och markera **[!UICONTROL Profile Core v2]** som [!UICONTROL Field Group].

   ![Identifieringsobjekt](./assets/identifcation-loyalty-field.png)

   Det här identifieringsobjektet lägger till identifieringsfunktioner i ditt schema. I ditt fall vill du identifiera lojalitetsinformation med e-postadressen i gruppdata.

   Välj **[!UICONTROL Apply]** om du vill lägga till det här objektet i ditt schema.

1. Välj **[!UICONTROL email]** fält i det identifieringsobjekt som du just lade till, och markera **[!UICONTROL Identity]** och **[!UICONTROL Email]** från [!UICONTROL Identity namespace] i [!UICONTROL Field Properties] -panelen.

   ![Ange e-postadress som identitet](./assets/specify-email-loyalty-id.png)

   Du anger e-postadressen som den identitet som tjänsten Adobe Experience Platform Identity kan använda för att kombinera (sammanfoga) beteendet för profiler.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i e-postattributet.

1. Välj rotnivån för schemat (med schemanamnet) och välj sedan **[!UICONTROL Profile]** byt.

   Du uppmanas att aktivera schemat för profilen. När data har aktiverats, när data har importerats till datauppsättningar som baseras på detta schema, sammanfogas dessa data i kundprofilen i realtid.

   Se [Aktivera schemat för användning i kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) för mer information.

   >[!IMPORTANT]
   >
   >    När du har sparat ett schema som är aktiverat för profilen kan det inte längre inaktiveras för profilen.

   ![Aktivera schema för profil](./assets/enable-for-profile.png)

1. Välj **[!UICONTROL Save]** för att spara ditt schema.

Du har skapat ett minimalt schema som modellerar de lojalitetsdata som du kan importera till Adobe Experience Platform. Schemat gör att profiler kan identifieras med e-postadressen. Genom att aktivera schemat för profilen ser du till att data från din strömningskälla läggs till i kundprofilen i realtid.

Se [Skapa och redigera scheman i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html) om du vill ha mer information om hur du lägger till och tar bort fältgrupper och enskilda fält i ett schema.

### Konfigurera en datauppsättning

Med ditt schema har du definierat din datamodell. Nu måste du definiera konstruktionen för att lagra och hantera data, vilket sker via datauppsättningar.

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

   ![Aktivera schema för profil](./assets/loyalty-dataset-profile.png)

Se [Användargränssnittshandbok för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html) om du vill ha mer information om hur du visar, förhandsgranskar, skapar, tar bort en datauppsättning. Och hur man aktiverar en datauppsättning för kundprofil i realtid.


## Använda en källkoppling

Beroende på varifrån du får lojalitetsdata väljer du den relevanta källkopplingen som är tillgänglig i Adobe Experience Platform.

Så här konfigurerar du en källkoppling:

1. I Adobe Experience Platform UI väljer du **[!UICONTROL Sources]** från [!UICONTROL CONNECTIONS] till vänster.

2. Välj din källanslutning i listan över tillgängliga källanslutningar. Varje koppling följer ett liknande arbetsflöde:

   - **[!UICONTROL Authentication]**. Du anger autentiseringsinformation för att komma åt datakällan.

   - **[!UICONTROL Select data]**: Du väljer de källdata som du vill importera.

   - **[!UICONTROL Dataflow detail]**: Du anger mer information om dataflödet, till exempel namn och vilken datauppsättning som ska användas.

   - **[!UICONTROL Mapping]**: Du mappar inkommande källdatafält till attribut i det schema som är associerat med den datamängd som du har valt.

   - **[!UICONTROL Scheduling]**: Om det är tillgängligt kan du schemalägga inmatningen av data.

   - **[!UICONTROL Review]**: En granskning av definitionen av källkopplingen visas.

   Varje koppling ger detaljerad dokumentation.

   Så här öppnar du den här dokumentationen:

   - På kopplingsplattan väljer du **[!UICONTROL ...]** nästa [!UICONTROL Set up] eller [!UICONTROL Add data].

     ![Visa dokumentation](./assets/sourceconnector-documentation.png)

   - Välj **[!UICONTROL View documentation]**.

Se [Importera och använda data från traditionella Adobe Analytics](./analytics.md) hur du använder Adobe Analytics källanslutning.

Se [Importera och använda strömmande data](./streaming.md) hur du använder HTTP API-källkopplingen.

Se [Översikt över Source Connectors](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en#terms-and-conditions) för en översikt över källanslutningar, inklusive länkar till mer information för varje koppling.


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

   I [!UICONTROL Select datasets] stega in [!UICONTROL Add datasets]:

   - Välj den datauppsättning som du skapade tidigare (`Example Loyalty Dataset`) och andra datauppsättningar som du vill inkludera i anslutningen.

     ![Lägg till datauppsättningar](./assets/cja-connections-2.png)

   - Välj **[!UICONTROL Next]**.

   I [!UICONTROL Datasets settings] stega in [!UICONTROL Add datasets]:

   - För varje datauppsättning:

      - Välj en [!UICONTROL Person ID] från de tillgängliga identiteter som definieras i datauppsättningsscheman i Adobe Experience Platform.

      - Välj rätt datakälla på menyn [!UICONTROL Data source type] lista. Om du anger **[!UICONTROL Other]** lägger du sedan till en beskrivning av datakällan.

      - Ange **[!UICONTROL Import all new data]** och **[!UICONTROL Dataset backfill existing data]** enligt dina önskemål.

     ![Konfigurera datauppsättningar](./assets/cja-connections-3.png)

   - Välj **[!UICONTROL Add datasets]**.

   Välj **[!UICONTROL Save]**.

Se [Anslutningar - översikt](../connections/overview.md) för mer information om hur du skapar och hanterar en anslutning och hur du väljer och kombinerar datauppsättningar.

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

5. Om du vill skapa din första rapport börjar du dra och släppa dimensioner och mätvärden på [!UICONTROL Freeform table] i [!UICONTROL Panel] . Dra som ett exempel `Program Points Balance` och `Page View` som mått och `email` som en dimension för att få en snabb översikt över profiler som har besökt er webbplats och som ingår i lojalitetsprogrammet som samlar in förmånspoäng.

   ![Arbetsyta - första rapporten](./assets/cja-projects-5.png)

Se [Analysis Workspace - översikt](../analysis-workspace/home.md) om du vill ha mer information om hur du skapar projekt och bygger din analys med hjälp av komponenter, visualiseringar och paneler.

>[!SUCCESS]
>
>Du har slutfört alla steg. Börja med att definiera vilka lojalitetsdata du vill samla in (schema) och var de ska lagras (datauppsättning) i Adobe Experience Platform, och du konfigurerade rätt källanslutning för att ge dig lojalitetsdata. Du definierade en anslutning i Customer Journey Analytics för att använda inkapslade lojalitetsdata och andra data. Med datavyns definition kan ni ange vilken dimension och vilka mätvärden som ska användas och slutligen skapa ert första projekt som visualiserar och analyserar era data.
