---
title: Konfigurera Content Analytics (fristående)
description: Stegvisa anvisningar för att konfigurera Adobe Content Analytics som en fristående lösning. Lär dig hur du ställer in scheman, datauppsättningar, datastreams och rapportering för omfattande information om innehållsprestanda utan en fullständig implementering av Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 35d63b7d-f35a-4a88-ae14-96724d32a931
source-git-commit: 1930e9da5d1cc8b5fb7ddc592535f035e4842a7b
workflow-type: tm+mt
source-wordcount: '2448'
ht-degree: 1%

---

# Fristående konfiguration

>[!IMPORTANT]
>
>Den här konfigurationsguiden är avsedd för kunder som har licensierat det fristående Adobe Content Analytics-paketet. Handboken förutsätter att du inte har använt eller planerar att använda Customer Journey Analytics eller något annat Experience Platform-program utöver Content Analytics funktioner. Se [Konfigurera Content Analytics](configuration.md) om du vill konfigurera och använda Content Analytics som en del av en befintlig Customer Journey Analytics-implementering.
>

Content Analytics licensieras som en fristående produkt, men konfigurationen sker i Experience Platform och Customer Journey Analytics. De här plattformarna tillhandahåller den infrastruktur för datainsamling och analys som Content Analytics kräver och använder. Den här guiden innehåller alla specifika anvisningar du behöver, även om du inte har använt Experience Platform eller Customer Journey Analytics tidigare.

Innan du börjar installera fristående Content Analytics bör du:

* Lär dig grundläggande kunskaper i webbanalysbegrepp, hur du känner till tagghanteringssystem och grundläggande kunskaper i JavaScript.
* Planera 4-6 timmar för den första konfigurationen, plus ytterligare tid för att testa och validera konfigurationen.

## Terminologi

I den här guiden används flera tekniska termer, från Experience Platform och Customer Journey Analytics, som du kanske inte känner till. Nedan följer en förklaring av dessa termer (med referenslänkar) i samband med Content Analytics:

| Term | Förklaring |
|---|---|
| **Schema** | Ett [schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition) är en uppsättning regler som representerar och validerar datastrukturen och dataformatet. På en hög nivå ger scheman en abstrakt definition av ett objekt i verkligheten, till exempel en händelse som inträffar på en webbplats, som ett klick. Och ange vilka data som ska inkluderas i varje instans av objektet. |
| **Datauppsättning** | En [datamängd](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview) är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader). En datauppsättning fungerar som en databastabell där varje rad är en händelse från webbplatsen. |
| **Datastream** | En [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview) representerar konfigurationen på serversidan som dirigerar data från din webbplats till rätt datauppsättning i Adobe Experience Platform. En datastream fungerar som en datastrålväg som ansluter platsen till ditt lagringsutrymme. |
| **Taggar** | [Taggar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/home) i Experience Platform är nästa generation av tagghanteringsfunktioner från Adobe. Taggar ger kunderna ett enkelt sätt att driftsätta och hantera de analyser, marknadsförings- och annonstaggar som behövs för att skapa relevanta kundupplevelser. I Content Analytics kan du med Adobe tagghanteringssystem distribuera spårningskod på din webbplats utan att du behöver redigera alla sidor på samma sätt. Funktionen Taggar liknar den funktion som du kan känna till från Google Tag Manager. |
| **Sandbox** | Experience Platform tillhandahåller [sandlådor](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) som partitionerar en enda Experience Platform-instans till separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Content Analytics använder vanligtvis sandlådan *Produktion*. |
| **Anslutning** | [Anslutningar](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview) definierar vilka Experience Platform-datauppsättningar som importeras. En anslutning definierar länken mellan datauppsättningen (där data lagras i AEP) och Customer Journey Analytics (där du analyserar den). En anslutning gör dina insamlade data tillgängliga för rapportering. |
| **Datavy** | En [datavy](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views) är en behållare som gör att du kan avgöra hur data från en anslutning ska tolkas. En datavy anger alla mått och mätvärden som är tillgängliga för dig att rapportera om. En datavy är som en konfiguration som avgör vilka rader och kolumner som du kan använda i analysen. |
| **Analysis Workspace** | [Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/home) är ett dra och släpp-gränssnitt som du använder för att skapa rapporter och analyser från Content Analytics. |
| **Upplevelse** | I Content Analytics avser en [upplevelse](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology) allt textinnehåll på en webbsida som kan hämtas och analyseras baserat på sidans URL. |
| **Resurs** | I Content Analytics är en [resurs](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology) en enskild och unik del av innehållet, som en bild. |


## Installationsöversikt

Den här konfigurationen vägleder dig vid konfigurationen av alla program som krävs för en fungerande **fristående** Content Analytics-implementering. Du kan dela upp konfigurationen i tre faser, där varje fas bygger på den föregående:

**Fas 1** - [Förbered miljön](#prepare-your-environment). I den här fasen skapar du användarbehörigheter och verifierar din datainfrastruktur. Utan rätt behörigheter och datastruktur kan du inte slutföra de återstående stegen. Följande steg ingår:

1. **Konfigurera åtkomstkontroll och behörigheter** för att stödja konfigurationen och implementeringen av Content Analytics.
1. **Konfigurera ett schema och en datauppsättning** för att definiera modellen (schemat) för de data som du vill samla in insikter om innehållsanalys från och var data (datauppsättningen) ska samlas in.

**Fas 2** - [Konfigurera datainsamling](#configure-data-collection). I den här fasen skapar du en pipeline som hämtar innehållsdata från din webbplats. Content Analytics vet alltså vilket innehåll besökarna interagerar med ert innehåll.

1. **Konfigurera en datastream** för att konfigurera hur dina insamlade data dirigeras till datauppsättningen.
1. **Använd webbplatstaggar** för att konfigurera regler och dataelement mot data i ditt datalager på din webbplats och för att se till att data skickas till den konfigurerade dataramängden.
1. **Distribuera** till en testmiljö **och validera** datainsamlingen innan du publicerar till en produktionsmiljö.

**Fas 3** - [Konfigurera rapportering](#set-up-reporting). I den här fasen ska du göra dina insamlade data tillgängliga för analys i rapporter. Så ni kan faktiskt få de insikter om innehållsprestanda ni vill få ut av Content Analytics.

1. **Konfigurera en anslutning** till datauppsättningen.
1. **Konfigurera en datavy** för att definiera mått och mått.
1. **Konfigurera och implementera Content Analytics**.
1. **Konfigurera ett projekt** för att skapa dina Content Analytics-rapporter och visualiseringar.


## Förbered din miljö

I den här fasen skapar du användarbehörigheter och verifierar din datainfrastruktur.

### Konfigurera åtkomstkontroll och behörigheter

I det här avsnittet beskrivs vilken åtkomst du behöver till produkten, produktprofiler och vilka behörigheter som krävs för att konfigurera och konfigurera fristående Content Analytics. Även om du bara är intresserad av funktionerna i Content Analytics så behöver du fortfarande åtkomst och behörigheter för andra Experience Platform-produkter för att den funktionen ska fungera korrekt.

#### Åtkomstkontroll

Åtkomstkontrollen avgör om du får åtkomst till en Experience Platform-produkt.

Du behöver antingen en systemadministratör eller en produktadministratör för att kunna lägga till dig som administratör för en produkt eller en produktprofil. En produktadministratör kan bara lägga till dig som administratör för den administrerade produkten (profil). En systemadministratör kan lägga till produktadministratörer för alla produkter (profil).

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Hantera användare för en produktprofil](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users){target="_blank"} för en demonstrationsvideo.


>[!ENDSHADEBOX]

Du måste vara produktadministratör för följande produkter och produktprofiler för fristående Content Analytics:

* Adobe Experience Platform
   * AEP-Default-All-Users (standardprofil för åtkomst till produktionssandlådan)

* Adobe Experience Platform Data Collection
   * Standarddatainsamling, all åtkomst

* Adobe Experience Platform Privacy Service

* Customer Journey Analytics (anpassad)
   * Customer Journey Analytics (eller någon annan standardproduktprofil som tillhandahålls)

Du definierar produktadministratörsåtkomst via Admin Console:

1. Åtkomst till [Admin Console](https://adminconsole.adobe.com).
1. Välj **[!UICONTROL Products]**.
1. Välj den specifika produkten.
1. Klicka på fliken **[!UICONTROL Admins]**.  
1. Välj **[!UICONTROL Add admin]** om du vill lägga till en administratör för produkten.
1. Ange ett eller flera e-postadresser eller användarnamn i dialogrutan **[!UICONTROL Add product administrators]**. Välj **[!UICONTROL Save]** att spara.


Du definierar administratörsåtkomst för produktprofiler via Admin Console:

1. Åtkomst till [Admin Console](https://adminconsole.adobe.com).
1. Välj **[!UICONTROL Products]**.
1. Välj den specifika produkten. Kontrollera att du redan har produktadministratörsåtkomst.
1. Välj **[!UICONTROL Product profiles]**.
1. Välj den specifika produktprofilen.
1. Klicka på fliken **[!UICONTROL Admins]**.  
1. Välj **[!UICONTROL Add admin]** om du vill lägga till en administratör i produktprofilen.
1. Ange ett eller flera e-postadresser eller användarnamn i dialogrutan **[!UICONTROL Add product profile administrators]**. Välj **[!UICONTROL Save]** att spara.


#### Behörigheter

Behörigheter definierar vad du kan göra i en produkt när du har tillgång till produkten.

Du definierar behörigheter för Experience Platform i [!UICONTROL Permissions]-gränssnittet och du använder attributbaserad åtkomstkontroll. För Customer Journey Analytics definierar du behörigheter via [!UICONTROL Admin Console].

##### Experience Platform

Gränssnittet [!UICONTROL Permissions] i Experience Platform baseras på definitionen av en roll. En roll är en samling resursbaserade behörigheter. I en ny provisionerad miljö finns två standardroller tillgängliga: **[!UICONTROL Default Production All Access]** och **[!UICONTROL Sandbox Administrators]**.

För Content Analytics måste du verifiera om följande resurser och tillhörande behörigheter har lagts till i de här rollerna:

* Standardroll för produktion, alla åtkomstroller

   * Datainsamling
      * Visa datastreams
      * Hantera datastreams

   * Datahantering
      * Visa datauppsättningar
      * Hantera datauppsättningar

   * Datamodellering
      * Visa scheman
      * Hantera scheman
      * Hantera identitetsmetadata


* Administratörsroll för sandlåda

   * Sandlådor
      * Prod
      * (alla andra sandlådor som du vill använda för Content Analytics)

   * Sandlådeadministration
      * Hantera paket
      * Hantera sandlådor
      * Återställ sandlåda
      * Visa sandlåda


I gränssnittet Behörigheter kan du verifiera både roller och associerade behörigheter. Och vilka användare som tillhör rollen.

1. Få tillgång till Experience Platform för er organisation.
1. I välkomstskärmen i **[!UICONTROL Quick access]** väljer du **[!UICONTROL View all]**.
1. Aktivera stiftet ![PinOn](/help/assets/icons/PinOn.svg) för **[!UICONTROL Permissions]**, så **[!UICONTROL Permissions]** blir tillgängligt i **[!UICONTROL Quick Access]** för framtida bruk.
1. Välj **[!UICONTROL Permissions]**.
1. Välj ![Användare](/help/assets/icons/User.svg) **[!UICONTROL Roles]**.
1. Välj den specifika roll som du vill verifiera (till exempel **[!UICONTROL Default Production All Access]**). Välj **[!UICONTROL View all]** om du vill se alla behörigheter.
1. På skärmen **[!UICONTROL Details]**:
   1. Verifiera **[!UICONTROL Resources]** som anges i **[!UICONTROL Permissions]**.
   1. Verifiera sandlådans namn i **[!UICONTROL Sandboxes]**.

   Om du vill göra några uppdateringar väljer du ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**.
   1. Om du vill lägga till en saknad resurs väljer du **[!UICONTROL Resource name]** ![Lägg till](/help/assets/icons/Add.svg) i den vänstra listen i **[!UICONTROL Resources]** > **[!UICONTROL Adobe Experience Platform]**.
   1. Om du vill lägga till en saknad behörighet väljer du ![ChevronDown](/help/assets/icons/ChevronDown.svg) i resursen som saknar behörighet i huvudpanelen och väljer den behörighet som saknas.

      ![Behörighetsgränssnitt](/help/content-analytics/assets/aep-permissions-ui.png)

   Välj **[!UICONTROL Save]** om du vill spara en uppdatering.

1. På skärmen Användare eller Användare:
   1. Kontrollera att rätt enskilda användare eller grupp av användare ingår i den här rollen.
      1. Välj ![UserAdd](/help/assets/icons/UserAdd.svg) Lägg till användare i Användare om du vill lägga till enskilda användare som du har definierat i Admin Console.
      1. Välj ![Lägg till](/help/assets/icons/Add.svg) i användargrupper om du vill lägga till användargrupper som du har definierat i Admin Console.


##### Customer Journey Analytics

Customer Journey Analytics stöder inte attributbaserad åtkomstkontroll. Om du vill ange behörigheter använder du Admin Console.

För Content Analytics måste du kontrollera om följande behörigheter för Customer Journey Analytics produktprofil ingår:

* Datavyer
   * Alla tillgängliga datavyer.

* Rapporteringsverktyg
   * Guided Analysis Access?
   * Skapa beräknade mätvärden
   * Skapa segment
   * Labs Access?
   * Skapa anteckning
   * Skapa målgrupper?
   * Målgruppsvy?
   * Åtkomst till granskningsloggar
   * Dela projektlänkar med vem som helst
   * Prognos
   * AI Assistant: Produktkunskap
   * Data Insights Agent
   * Intelligenta bildtexter
   * Data Storytelling?

* Datavy Tools
   * Fullständig tabellexport?
   * CJA BI-tillägg?

Så här verifierar och uppdaterar du dessa behörigheter för Customer Journey Analytics:

1. Åtkomst till [Admin Console](https://adminconsole.adobe.com).
1. Välj **[!UICONTROL Products]**.
1. Välj **[!UICONTROL Customer Journey Analytics]**-produkten.
1. Välj **[!UICONTROL Product profiles]**.
1. Välj den standardproduktprofil som är tillgänglig för Customer Journey Analytics. Till exempel: **[!UICONTROL Customer Journey Analytics]**.
1. Välj **[!UICONTROL Permissions]** på skärmen för produktprofilen.
1. Välj någon av ![Redigera](/help/assets/icons/Edit.svg)-knapparna för att redigera behörigheterna. I dialogrutan **[!UICONTROL Edit permissions for Customer Journey Analytics]**:

   ![Gränssnitt för CJA-behörigheter](../assets/cja-permissions-ui.png)

   1. Välj **[!UICONTROL Data Views]** och aktivera **[!UICONTROL Auto-include: On]**. Den här växlingen ser till att alla datavyer automatiskt är en del av **[!UICONTROL Included permission items]**.
   1. Välj **[!UICONTROL Reporting Tools]** och kontrollera att alla behörigheter ovan är en del av **[!UICONTROL Included permission items]**.
   1. Välj **[!UICONTROL Data View Tools]** och kontrollera att alla behörigheter ovan är en del av **[!UICONTROL Included permission items]**.

   Välj **[!UICONTROL Save]**.


### Konfigurera schema och datauppsättning

Om ni vill samla in data från er webbplats måste ni först definiera vilken typ av data ni vill samla in, med förbehåll för Content Analytics insikter. Och även hur dessa data lagras. Båda begreppen förklaras i snabbstartsguiden för [Konfigurera ett schema och en datamängd](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) i [Importera data via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


## Konfigurera datainsamling

I den här fasen skapar du en pipeline som hämtar innehållsdata från din webbplats.

### Konfigurera en datastream

Du har definierat vilka data som ska samlas in och hur dessa data ska lagras. Nästa steg är att se till att de data som samlas in från din webbplats dirigeras till datauppsättningen. Du måste konfigurera och konfigurera ett datastream, vilket beskrivs i [Konfigurera ett datastream](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) i snabbstartsguiden för [Infoga data via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Använd taggar

Du har definierat vilka data som ska samlas in (schema), hur data (datauppsättningen) ska lagras och hur insamlade data från din webbplats dirigeras till datauppsättningen (datastream). Som ett nästa steg måste du tagga din webbplats för att konfigurera regler och dataelement mot data i ditt datalager på din webbplats. Om du taggar webbplatsen ser du till att data skickas till den konfigurerade dataströmmen. Taggningen av din webbplats med hjälp av taggar beskrivs i [Använd taggar](/help/data-ingestion/aepwebsdk.md#use-tags) i snabbstartsguiden för [Infoga data via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Distribuera och validera

Du kan nu distribuera koden på utvecklingsversionen av webbplatsen i taggen `<head>`. När webbplatsen distribueras börjar den samla in data till Adobe Experience Platform. Dessa uppgifter omfattas sedan av Content Analytics.

Validera implementeringen, korrigera den vid behov och distribuera den till din staging- och produktionsmiljö med publiceringsarbetsflödesfunktionen i Taggar när du har korrigerat den


## Ställ in rapportering

I den här fasen gör du de insamlade data tillgängliga för analys i rapporter.

### Konfigurera en anslutning till datauppsättningen

Om du vill rapportera insamlade data och konfigurera dessa data för Content Analytics måste du skapa en anslutning i Customer Journey Analytics. Anslutningen ansluter till datauppsättningen som innehåller insamlade data. Hur du konfigurerar en anslutning beskrivs i [Konfigurera en anslutning](../../data-ingestion/aepwebsdk.md#set-up-a-connection) i snabbstartsguiden [Importera data via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) .


### Konfigurera en datavy

Det sista steget innan du konfigurerar Content Analytics är att definiera en datavy. En datavy är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en anslutning ska tolkas. Med en datavy kan du definiera mått och mått från data från en eller flera datauppsättningar som Customer Journey Analytics är anslutet till. Hur du konfigurerar en datavy beskrivs i [Konfigurera en datavy](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) i snabbstartsguiden för [Infoga data via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


### Konfigurera Content Analytics

Nu har du allt du behöver för att konfigurera Content Analytics.

#### Guidad konfiguration

Använd den [guidade konfigurationsguiden](guided.md) och välj datavyn som du skapade som en del av steget [Konfigurera en datavy](#set-up-a-data-view). Detta gör att Content Analytics konfigureras och implementeras utöver de data du samlar in från din webbplats.

Observera att följande ytterligare specifika Content Analytics-objekt konfigureras i guiden för guidad konfiguration:

* **Datauppsättning**, som konfigureras automatiskt för Content Analytics-händelser. Den här datauppsättningen använder ett specifikt Content Analytics-schema som redan har skapats och är tillgängligt.
* **Datastream**, som konfigureras automatiskt för att strömma Content Analytics-händelser till Content Analytics datamängd.
* **Taggegenskapen** som konfigureras automatiskt och konfigureras med Content Analytics-tillägget. Den här taggegenskapen ser till att din webbplats skickar Content Analytics-data till Content Analytics datastream och Content Analytics datamängd.

  >[!IMPORTANT]
  >
  >Se till att du väljer alternativet att skapa en ny taggegenskap som en del av steget [Datainsamling](guided.md#new-configuration-1) i guiden.
  >


#### Manuell konfiguration

Om du vill implementera Content Analytics för webbplatsen måste du publicera Content Analytics Tags-egenskapen [manuellt](manual.md).


### Konfigurera ett projekt

Konfigurera ett projekt i Customer Journey Analytics för att skapa dina [Content Analytics-rapporter och visualiseringar](/help/content-analytics/report/report.md). Du kan också använda en [Content Analytics-mall](/help/content-analytics/report/report.md#template) för att komma igång.
