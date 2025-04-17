---
title: Importera och använda data med hjälp av källkopplingar
description: Förklara hur man importerar och använder data med hjälp av källanslutningar i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 813d3213-86b3-431a-821c-174e5e36d032
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '1888'
ht-degree: 0%

---

# Importera och använda data med hjälp av källkopplingar

Den här snabbstartsguiden förklarar hur du kan importera data till Adobe Experience Platform med en källanslutning till en DataProvider och sedan använda dessa data i Customer Journey Analytics.

För att uppnå detta måste du:

- **Konfigurera ett schema och en datauppsättning** i Adobe Experience Platform för att definiera modellen (schemat) för de data som du vill samla in och var data (datauppsättningen) ska samlas in.

- **Använd en källanslutning** i Adobe Experience Platform för att hämta data till den konfigurerade datauppsättningen.

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

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Schemas]** i [!UICONTROL DATA MANAGEMENT] till vänster.

1. Välj **[!UICONTROL Create schema]**.
.
1. I steget Välj en klass i guiden Skapa schema:

   1. Välj **[!UICONTROL Individual Profile]**.

      ![Skapa ett schemafönster med Enskild profil markerad](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Ett Experience Event-schema används för att modellera _beteendet_ för en profil (som scennamn, push-knapp som läggs till i kundvagnen). Ett enskilt profilschema används för att modellera profilen _attribut_ (som namn, e-post, kön).

   1. Välj **[!UICONTROL Next]**.


1. I [!UICONTROL Name and review step] i guiden [!UICONTROL Create schema]:

   1. Ange en **[!UICONTROL Schema display name]** för ditt schema och (valfritt) en **[!UICONTROL Description]**.

      ![Skapa schemafönster med fälten för att namnge schemat ](./assets/create-pr-schema-wizard-step-2.png)

   1. Välj **[!UICONTROL Finish]**.

1. På fliken Struktur i exempelschemat:

   1. Välj **[!UICONTROL + Add]** i [!UICONTROL Field groups].

      ![Skapa schemafönster som visar gruppen Lägg till fält](./assets/add-field-group-button.png)

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


## Använda en källkoppling

Beroende på varifrån du får lojalitetsdata väljer du den relevanta källkopplingen som är tillgänglig i Adobe Experience Platform.

Ni kan importera data från en mängd olika källor. Nedan följer bara några av alla tillgängliga källor:

- Adobe-program (källanslutningar omfattar [Adobe Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics), [Adobe Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/audience-manager) med flera)

- Molnlagring (källanslutningar omfattar [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/cloud-storage/s3), [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/cloud-storage/blob) med flera)

- Databaser (källanslutningar omfattar [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake), [Microsoft SQL Server](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/sql-server) med flera)

Så här konfigurerar du en källkoppling:

1. I Adobe Experience Platform väljer du **[!UICONTROL Sources]** från [!UICONTROL CONNECTIONS] i den vänstra listen.

1. Välj din källanslutning i listan över tillgängliga källanslutningar.

   Varje koppling följer ett liknande arbetsflöde:

   1. **[!UICONTROL Authentication]**. Du anger autentiseringsinformation för att komma åt datakällan.

   1. **[!UICONTROL Select data]**: Du väljer de källdata som du vill importera.

   1. **[!UICONTROL Dataflow detail]**: Du anger ytterligare information om dataflödet, till exempel namn och vilken datauppsättning som ska användas.

   1. **[!UICONTROL Mapping]**: Du mappar inkommande källdatafält till attribut i schemat som är associerat med den datamängd som du har valt.

   1. **[!UICONTROL Scheduling]**: Om det är tillgängligt kan du schemalägga inmatningen av data.

   1. **[!UICONTROL Review]**: En granskning av definitionen av källkopplingen visas.

1. Varje koppling ger detaljerad dokumentation. Så här öppnar du den här dokumentationen:

   1. Markera **[!UICONTROL ...]** bredvid [!UICONTROL Set up] eller [!UICONTROL Add data] på kopplingsplattan.

      ![Visa dokumentation](./assets/sourceconnector-documentation.png)

   1. Välj **[!UICONTROL View documentation]**.

Mer information om hur du använder Adobe Analytics-källkopplingen finns i [Importera och använda data från traditionella Adobe Analytics](./analytics.md).

Mer information om hur du använder HTTP API-källkopplingen finns i [Importera och använda direktuppspelade data](./streaming.md).

Se [Översikt över Source Connectors](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html#terms-and-conditions) för en översikt över källanslutningar, inklusive länkar till mer information för varje anslutning.


## Konfigurera en anslutning

Om du vill använda Adobe Experience Platform-data i Customer Journey Analytics skapar du en anslutning som innehåller de data som är resultatet av konfigurationen av ditt schema, din datauppsättning och ditt arbetsflöde.

Med en anslutning kan du integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om dessa datauppsättningar måste du först upprätta en anslutning mellan datauppsättningar i Adobe Experience Platform och Workspace.

Så här skapar du en anslutning:

1. I Customer Journey Analytics-gränssnittet väljer du **[!UICONTROL Connections]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.

1. Välj **[!UICONTROL Create new connection]**.

1. På skärmen **[!UICONTROL Untitled connection]**:

   1. Namnge och beskriv din anslutning i **[!UICONTROL Connection Settings]**.

   1. Välj rätt sandlåda i listan **[!UICONTROL Sandbox]** i **[!UICONTROL Data settings]** och välj antalet dagliga händelser i listan **[!UICONTROL Average number of daily events]**.

      ![Anslutningsinställningar](./assets/cja-connections-1.png)

   1. Välj **[!UICONTROL Add datasets]**.

1. I steget **[!UICONTROL Select datasets]** i **[!UICONTROL Add datasets]**:

   1. Markera datauppsättningen som du skapade tidigare (`Example Loyalty Dataset`) och alla andra datauppsättningar som du vill ta med i anslutningen.

      ![Lägg till datauppsättningar](./assets/cja-connections-2.png)

   1. Välj **[!UICONTROL Next]**.

1. I steget **[!UICONTROL Datasets settings]** i **[!UICONTROL Add datasets]**:

   För varje datauppsättning:

   1. Välj en [!UICONTROL Person ID] bland de tillgängliga identiteter som definieras i datauppsättningsscheman i Adobe Experience Platform.

   1. Välj rätt datakälla i listan [!UICONTROL Data source type]. Om du anger **[!UICONTROL Other]** lägger du till en beskrivning för datakällan.

   1. Ange **[!UICONTROL Import all new data]** och **[!UICONTROL Dataset backfill existing data]** enligt dina inställningar.

      ![Konfigurera datauppsättningar](./assets/cja-connections-3.png)

   1. Välj **[!UICONTROL Add datasets]**.

   1. Välj **[!UICONTROL Save]**.

När du har skapat en [anslutning](/help/connections/overview.md) kan du utföra olika hanteringsåtgärder, till exempel [markera och kombinera datauppsättningar](/help/connections/combined-dataset.md), [kontrollera status för en anslutnings datauppsättningar och status för dataöverföring](/help/connections/manage-connections.md), med mera.

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

5. Om du vill skapa din första rapport börjar du dra och släppa dimensioner och mått på [!UICONTROL Freeform table] i [!UICONTROL Panel] . Dra till exempel `Program Points Balance` och `Page View` som mått och `email` som mått för att få en snabb översikt över profiler som har besökt din webbplats och som ingår i lojalitetsprogrammet som samlar in förmånspoäng.

   ![Workspace - första rapporten](./assets/cja-projects-5.png)

Mer information om hur du skapar projekt och bygger analyser med komponenter, visualiseringar och paneler finns i [Översikt över Analysis Workspace](../analysis-workspace/home.md) .

>[!SUCCESS]
>
>Du har slutfört alla steg. Börja med att definiera vilka lojalitetsdata du vill samla in (schema) och var de ska lagras (datauppsättning) i Adobe Experience Platform, och du konfigurerade rätt källanslutning för att ge dig lojalitetsdata. Du har definierat en anslutning i Customer Journey Analytics för att använda inkapslade lojalitetsdata och andra data. Med datavyns definition kan ni ange vilken dimension och vilka mätvärden som ska användas och slutligen skapa ert första projekt som visualiserar och analyserar era data.
