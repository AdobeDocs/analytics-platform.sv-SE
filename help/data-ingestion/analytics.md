---
title: Importera och använda data från traditionella Adobe Analytics
description: Förklara hur man importerar data från traditionella Adobe Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 5cbfa922-6d6e-453a-9558-abfcfb80449d
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Importera och använda data från traditionella Adobe Analytics

Den här snabbstartsguiden förklarar hur du kan använda de data som samlas in av Adobe Analytics i Customer Journey Analytics.

>[!PREREQUISITES]
>
>Du har Adobe Analytics licensierat och driftsatt på en eller flera av dina webbplatser med någon av de dokumenterade implementeringsmetoderna:
>
>- [Implementera analyser med Experience Platform Edge](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=en)
>
>- [Implementera Analytics med Adobe Analytics-tillägg](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=en)
>
>- [Implementera Analytics med JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)

För att uppnå detta måste du:

- **Konfigurera en Adobe Analytics-källanslutning** i Adobe Experience Platform. Det här tar hand om inmatningen av aktuella Adobe Analytics-data i en datauppsättning i Adobe Experience Platform.

- **Konfigurera en anslutning** i Customer Journey Analytics. Den här anslutningen bör (åtminstone) innehålla din Adobe Experience Platform-datauppsättning.

- **Konfigurera en datavy** i Customer Journey Analytics för att definiera mått och dimensioner som du vill använda i Analysis Workspace.

- **Konfigurera ett projekt** i Customer Journey Analytics för att skapa rapporter och visualiseringar.


>[!NOTE]
>
>Det här är en förenklad guide om hur du importerar data, använder Adobe Analytics källanslutning och använder dessa data i Customer Journey Analytics. Vi rekommenderar starkt att man studerar den ytterligare informationen när det hänvisas till.


## Konfigurera en Adobe Analytics-källanslutning

Med Adobe Analytics källanslutning kan du överföra data från Adobe Analytics rapportsserie till Adobe Experience Platform.

Så här skapar du en Adobe Analytics-källanslutning:

1. Välj **[!UICONTROL Sources]**, från den vänstra listen.

2. Välj **[!UICONTROL Adobe applications]** i listan över [!UICONTROL CATEGORIES].

3. Välj **[!UICONTROL Set up]** eller **[!UICONTROL Add data]** i Adobe Analytics.

   ![Källor](./assets/sources-overview.png)

4. Välj **[!UICONTROL Report suite]**. Välj den som du vill använda i listan över rapportsviter.

   ![Rapportsviter](./assets/report-suites.png)

   Välj **[!UICONTROL Next]**.

5. Välj **[!UICONTROL Default schema]** som [!UICONTROL Target schema]. Adobe Experience Platform skapar automatiskt schemat och motsvarande datauppsättning för att mappa alla standardfält från den valda Adobe Analytics-rapportsviten.

   ![Standardschema](./assets/default-schema.png)

   Välj **[!UICONTROL Next]**.

6. Namnge dataflödet och (eventuellt) ge en beskrivning.

   ![Information om dataflöde](./assets/dataflow-detail.png)

   Välj **[!UICONTROL Next]**.

7. Granska anslutningen och välj **[!UICONTROL Finish]**.

   ![Granska](./assets/review.png)


När anslutningen har skapats skapas dataflödet automatiskt för att fylla i en datauppsättning med Adobe Analytics-data från rapportsviten, inklusive inmatning av upp till 13 månaders historiska data för produktionssandlådor. (Observera att från och med den 26 april 2023 är bakåtfyllnaden i icke-produktionssandlådor begränsad till tre månader.)

När det första intaget är slutfört kan Adobe Analytics-rapportsvitens data användas av Customer Journey Analytics.

Se [Skapa en Adobe Analytics-källanslutning i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) för en mycket mer omfattande självstudiekurs.


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

   - Markera datauppsättningen som skapas automatiskt av Adobe Analytics-källkopplingen och andra datauppsättningar som du vill ta med i anslutningen.

     ![Lägg till datauppsättningar](./assets/cja-connections-2a.png)

   - Välj **[!UICONTROL Next]**.

   I [!UICONTROL Datasets settings] steg in [!UICONTROL Add datasets]:

   - För varje datauppsättning:

      - Välj en [!UICONTROL Person ID] från de tillgängliga identiteter som definieras i datauppsättningsscheman i Adobe Experience Platform.

      - Välj rätt datakälla på menyn [!UICONTROL Data source type] lista. Om du anger **[!UICONTROL Other]** lägger du sedan till en beskrivning av datakällan.

      - Ange **[!UICONTROL Import all new data]** och **[!UICONTROL Dataset backfill existing data]** enligt dina önskemål.

     ![Konfigurera datauppsättningar](./assets/cja-connections-3a.png)

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
>Du har slutfört alla steg. Från och med att du konfigurerar Adobe Analytics datakällanslutning och konfigurerar den kopplingen för rapportsviten överförs dina Adobe Analytics-data automatiskt till Adobe Experience Platform. Du har definierat en anslutning i Customer Journey Analytics för att använda inmatade Adobe Analytics-data och andra data. Med datavyns definition kan ni ange vilken dimension och vilka mätvärden som ska användas och slutligen skapa ert första projekt som visualiserar och analyserar era data.

