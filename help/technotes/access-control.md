---
title: Customer Journey Analytics Access Control
description: Lär dig hur du implementerar åtkomstkontroll i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: ea699bcacd985d9da1e3895f7770290dc77da537
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 0%

---

# Åtkomstkontroll

Tre behörighetsnivåer eller tre roller styr Customer Journey Analytics: produktadministratörsroll, administratörsroll för produktprofiler och åtkomst på användarnivå. I det här avsnittet förklaras de här rollerna mer ingående.

I den här artikeln beskrivs också mer detaljerade sätt att begränsa åtkomsten, t.ex. Workspace-kurering och radnivå samt åtkomstkontroll på värdenivå.

## Rollbaserad åtkomstkontroll

Följande rollbaserade åtkomstkontrollnivåer är tillgängliga.

### Produktadministratörsroll

Användare som har tilldelats rollen Produktadministratör får som standard de behörigheter som krävs för att utföra de flesta åtgärder inom Customer Journey Analytics. För vissa uppgifter krävs dock ytterligare behörigheter.

Lägga till en användare som produktadministratör:

1. Gå till [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Välj [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administratörer**] > [!UICONTROL **Lägg till administratör**].

   De användare som du har lagt till får standardbehörigheten [Produktadministratör](#product-admin-default-permissions). Du kan även ge dem [ytterligare behörigheter](#product-admin-additional-permissions) om det behövs.

#### Standardbehörigheter för produktadministratör

Produktadministratörer har behörighet att utföra de flesta uppgifter inom Customer Journey Analytics.

Produktadministratörer har som standard behörighet att utföra följande uppgifter:

* Uppdatera och ta bort projekt, segment, beräknade värden, målgrupper, anteckningar eller segment som skapats av andra användare
* Dela Workspace-projekt med alla användare
* Hantera rapporteringsaktivitet i [Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportera fullständiga tabeller](/help/analysis-workspace/export/export-cloud.md) från Analysis Workspace

#### Ytterligare behörigheter för produktadministratör

Utöver att läggas till som produktadministratör i **Customer Journey Analytics-produktprofilen** i [Admin Console](https://adminconsole.adobe.com/enterprise/) krävs ytterligare behörigheter för att kunna utföra följande åtgärder i Customer Journey Analytics:

* Skapa, uppdatera och ta bort [datavyer](/help/data-views/data-views.md).
* Skapa, uppdatera och ta bort [anslutningar](/help/connections/overview.md)

  För att utföra denna uppgift måste användare vara en del av en **Experience Platform Product Profile** som ger följande behörigheter:

  | Kategori | Behörighet | Beskrivning |
  |---|---|---|
  | [!UICONTROL Sandboxes] | [!UICONTROL At least one] | Tillgång till relevanta sandlådor för anslutningar. |
  | [!UICONTROL Data Modeling] | [!UICONTROL View Schemas] | Skrivskyddad åtkomst till scheman och relaterade resurser. |
  | [!UICONTROL Data Modeling] | [!UICONTROL Manage Schemas] | Åtkomst för att läsa, skapa, redigera och ta bort scheman och relaterade resurser. |
  | [!UICONTROL Data Management] | [!UICONTROL View Datasets] | Skrivskyddad åtkomst för datauppsättningar och scheman. |
  | [!UICONTROL Identity Management] | [!UICONTROL View Identity Namespaces] | Skrivskyddad åtkomst för identitetsnamnrymder. |

  För mer information om Experience Platform-behörigheter, se [Hantera behörigheter för en produktprofil](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).


* Om Journey Optimizer är integrerad med Customer Journey Analytics där Journey Optimizer-anslutningar finns, måste även resebehörigheter läggas till för att få tillgång till Connections:

  | Kategori | Behörighet | Beskrivning |
  |---|---|---|
  | [!UICONTROL Journeys] | [!UICONTROL View Journeys Events, Data Sources and Actions] | Skrivskyddad åtkomst till resehändelser, reseanpassade åtgärder och resedatakällor. |
  | [!UICONTROL Journeys] | [!UICONTROL Manage Journeys Events, Data Sources and Actions] | Läs, skapa, redigera och ta bort händelser, källor eller handlingar. |
  | [!UICONTROL Journeys] | [!UICONTROL View Journeys] | Skrivskyddad tillgång till resor. |
  | [!UICONTROL Journeys] | [!UICONTROL Manage Journeys] | Läs, skapa, redigera och ta bort resor. |

* Exportera dataset till [destinationer](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)

  För att kunna utföra den här åtgärden måste användarna ingå i en **Experience Platform-produktprofil** som ger följande behörigheter:

  | Kategori | Behörighet | Beskrivning |
  |---|---|---|
  | [!UICONTROL Destinations] | [!UICONTROL Manage Destinations] | Åtkomst för att läsa, skapa och ta bort målanslutningar och målkonton. |
  | [!UICONTROL Destinations] | [!UICONTROL Activate Destinations] | Låt användare aktivera segment till befintliga destinationer. Aktiverar kartläggningssteget i aktiveringsarbetsflödet. Denna behörighet kräver också att behörigheten Visa destinationer ges till användaren som vill aktivera data till destinationer. |

  För mer information om Experience Platform-behörigheter, se [Hantera behörigheter för en produktprofil](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

* Använd BI-tillägget [](../data-views/bi-extension.md)

  För användare att använda BI-tillägget finns en produktadministratör

   * måste säkerställa att användarens Experience Platform-behörigheter inkluderar en roll som har resursen Query Service med alternativen Hantera frågor och Hantera Query Service Integration. För mer information om Experience Platform-behörigheter, se [Hantera behörigheter för en produktprofil](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

     | Kategori | Behörighet | Beskrivning |
     |---|---|---|
     | [!UICONTROL Query Service] | [!UICONTROL Manage Queries] | Tillgång till att läsa, skapa, redigera och ta bort strukturerade SQL-frågor för plattformsdata. |
     | [!UICONTROL Query Service] | [!UICONTROL Manage Query Service Integration] | Åtkomst för att skapa, uppdatera och ta bort icke-utgångna uppgifter för åtkomst till Query Service. |

   * måste se till att rätt Customer Journey Analytics-behörigheter för användaren finns:
      * behörighet att få tillgång till relevanta datavyer. Se [!UICONTROL Data Views] i [Åtkomst på användarnivå](#user-level-access).
      * behörighet att komma åt Customer Journey Analytics BI-tillägget. Se [!UICONTROL Data View Tools] i [Åtkomst på användarnivå](#user-level-access).

### Administratörsroll för produktprofil

En produktprofil är en uppsättning behörigheter. Produktadministratörer skapar produktprofiler och kan tilldela produktprofiladministratörer för att hantera en eller flera produktprofiler. En produktprofiladministratör kan sedan:

* Hantera tilldelade produktprofiler. Du kan till exempel lägga till eller ta bort användare eller användargrupper och ändra behörigheter för produktprofilerna.

* I Customer Journey Analytics redigerar du datavyer som ingår i en tilldelad produktprofil. Produktprofiladministratörer kan inte skapa nya datavyer.

### Åtkomst på användarnivå

Tabellen nedan visar de viktigaste åtkomstbehörigheterna för olika Customer Journey Analytics-funktioner som du kan konfigurera för berörda användare. Du kan hantera olika nivåer av användaråtkomst via produktprofiler. En produktprofil innehåller ett antal behörigheter som du sedan kan tilldela till enskilda användare eller användargrupper.

Fliken **[!UICONTROL Permissions]** ingår i varje produktprofil i [Admin Console](https://adminconsole.adobe.com/enterprise/).

![behörigheter för Admin Console](assets/permissions.png)

| Kategori | Behörighet | Beskrivning |
| --- | --- | ---|
| [!UICONTROL Data Views] | *datavyns namn* | Om du växlar **[!UICONTROL Auto-Include]** till **[!UICONTROL On]** kan användare som är en del av den här produktprofilen visa alla befintliga och nyligen skapade datavyer. Om den här inställningen är **[!UICONTROL Off]** kan du välja särskilda datavyer som användarna har åtkomst till. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Analysis Workspace Access] | Låt användare få åtkomst till [Analysis Workspace](/help/analysis-workspace/home.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Guided Analysis Access] | Låt användare få tillgång till [guidad analys](/help/guided-analysis/overview.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Calculated Metrics Creation] | Låt användare skapa [beräknade mätvärden](/help/components/calc-metrics/calc-metr-overview.md). Användare kan tagga, dela, radera, byta namn på, godkänna eller inte godkänna endast de beräknade mätvärden de skapar eller de beräknade mätvärden som delas med dem. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Segment Creation] | Låt användare skapa [segment](/help/components/segments/seg-overview.md). Användare kan tagga, dela, radera, byta namn på, godkänna eller inte godkänna endast de segment de skapar eller de segment som delas med dem. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Labs Access] | Låt användare komma åt fliken [Labs](/help/labs/labs.md) i Customer Journey Analytics. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Annotation Creation] | Låt användare skapa [anteckningar](/help/components/annotations/overview.md). Användare kan endast tagga, dela, ta bort och byta namn på de anteckningar de skapar eller anteckningar som delas med dem. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audience View] | Låt användarna visa [målgrupper](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audience Creation] | Låt användare skapa [målgrupper](/help/components/audiences/audiences-overview.md). Kräver [Hantera segment](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home) i Adobe Experience Platform. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Data storytelling] | Låt användare [generera bildpresentationer baserat på Workspace-projekt.](/help/analysis-workspace/curate-share/generate-slides.md)<p>Data storytelling är i den begränsade testfasen av lanseringen och är kanske inte tillgänglig än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Customer Journey Analytics funktionsreleaser](/help/release-notes/releases.md).</p> |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audit Logs Access] | Tvinga behörighetskontrollen för användargränssnittet för [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) och granskningsloggarna. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Share Project Links With Anyone] | Låt användare [dela projekt med vem som helst.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Reporting Tools] | [!UICONTROL Forecasting] | Ge användarna tillgång till funktionen [Prognoser](../analysis-workspace/c-forecast/forecasting.md) i Analysis Workspace |
| [!UICONTROL Reporting Tools] | [!UICONTROL AI Assistant: Product Knowledge] | Ge användarna tillgång till [AI-assistenten](../ai-assistant.md) för produktinformation. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Intelligent Captions] | Låt användarna komma åt [Intelligenta bildtexter](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL Data View Tools] | [!UICONTROL Full Table Export] | Låt användare [exportera hela tabeller till molnet](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL Data View Tools] | [!UICONTROL CJA BI Extension] | Låt användare använda BI-tillägget[](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Kuratering av arbetsytor

En annan nivå av åtkomstkontroll kan användas på rapporteringsnivå för arbetsområdet. Du kan begränsa åtkomsten till specifika komponenter för vissa användare. För mer information om hur man begränsar komponenter (dimensioner, mätvärden, segment, datumintervall) på Workspace-projektnivå, och hur kuratering är kopplad till datavyer, se [Curate projects](/help/analysis-workspace/curate-share/curate.md).

## Ge åtkomst till enskilda mått eller mått

Du kan inte bevilja eller neka tillstånd för enskilda mått eller mått i Customer Journey Analytics på samma sätt som i traditionella Adobe Analytics. Mätvärden och dimensioner kan ändras i [datavyer](/help/data-views/data-views.md) och kan ändras i Customer Journey Analytics. Om du ändrar dem ändras även rapporteringen retroaktivt.

## Användningsexempel

Här följer några exempel som visar hur åtkomstkontroll kan användas i realtidsscenarier.

### Åtkomst från tredje part

Du kan ge tillgång till produktprofiladministration till en teamledare för en tredje part som ditt företag arbetar med. Denna administratör kan lägga till användare i företagets team i denna produktprofil. Denna produktprofiladministratör kan ge tillgång till specifika datavyer och lägga till andra användare inom tredje part till produktprofilen. Produktprofiladministratören kan modifiera datavyer för att passa tredjepartsteamets krav.

### Åtkomstkontroll på radnivå

Du vill ge användare tillgång till data från endast en dag. Så här begränsar du åtkomsten till de raderna:

1. Skapa ett segment i [!UICONTROL Settings] av en specifik datavy, där [!UICONTROL Day] motsvarar det datum du vill att de ska ha dataåtkomst till. Se [Skapa datavy](/help/data-views/create-dataview.md#settings-filters) för mer information.
1. Spara datavyn, som applicerar segmentet på datadelen av datamängderna i den underliggande anslutningen. Alla rader som inte passar segmentdefinitionen utesluts automatiskt från datavyn och är inte tillgängliga i Analysis Workspace när denna datavy används.
1. Skapa en ny [produktprofil](#product-profile-admin-role) i Admin Console, lägg till användare i produktprofilen och inkludera endast denna specifika datavy i produktprofilen.

### Åtkomstkontroll på värdenivå

Användare som har tillgång till en datavy kan endast arbeta med de mätvärden och dimensioner som administratören har inkluderat i denna datavy. Administratörer kan använda komponentinställningarna [Inkludera/exkludera funktioner](/help/data-views/component-settings/include-exclude-values.md) eller [Värdebuckning](../data-views/component-settings/value-bucketing.md) i en datavy för att exkludera eller aggregera vissa dimensionsvärden från en datavy.

Du kan till exempel skapa ett mätvärde som heter *Hypertension* i en datavy från en komponent som innehåller enskilda patientdata från datauppsättningen. Du använder värdepaketering för att bara ge åtkomst till paketerade värden, så att användarna av data inte ser de enskilda patientuppgifterna.
