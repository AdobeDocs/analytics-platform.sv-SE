---
title: Åtkomstkontroll för Customer Journey Analytics
description: Lär dig hur du implementerar åtkomstkontroll i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 1a470345a6a2748b992263c3ad25e4cd7d3daa9e
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 0%

---

# Åtkomstkontroll för Customer Journey Analytics

Customer Journey Analytics styrs av tre behörighetsnivåer eller tre roller: produktadministratörsroll, administratörsroll för produktprofil och åtkomst på användarnivå. I det här avsnittet förklaras de här rollerna mer ingående.

I den här artikeln beskrivs också mer detaljerade sätt att begränsa åtkomsten, t.ex. Workspace-kurering och radnivå samt åtkomstkontroll på värdenivå.

## Produktadministratörsroll

Användare som har tilldelats rollen Produktadministratör får som standard de behörigheter som krävs för att utföra de flesta åtgärder inom Customer Journey Analytics. För vissa uppgifter krävs dock ytterligare behörigheter.

Så här lägger du till en användare som produktadministratör:

1. Gå till [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Välj [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administratörer**] > [!UICONTROL **Lägg till administratör**].

   De användare som du har lagt till får standardbehörigheten [Produktadministratör](#product-admin-default-permissions). Du kan även ge dem [ytterligare behörigheter](#product-admin-additional-permissions) om det behövs.

### Standardbehörigheter för produktadministratör

Produktadministratörer har behörighet att utföra de flesta åtgärder inom Customer Journey Analytics.

Produktadministratörer har som standard behörighet att utföra följande uppgifter:

* Skapa, uppdatera och ta bort datavyer
* Uppdatera och ta bort projekt, filter, beräknade värden, målgrupper, anteckningar eller filter som skapats av andra användare
* Dela Workspace-projekt med alla användare
* Hantera rapporteringsaktivitet i [Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportera fullständiga tabeller](/help/analysis-workspace/export/export-cloud.md) från Analysis Workspace

### Ytterligare behörigheter för produktadministratör

Utöver att läggas till som produktadministratör i **Customer Journey Analytics-produktprofilen** i [Admin Console](https://adminconsole.adobe.com/enterprise/) krävs ytterligare behörigheter för att kunna utföra följande åtgärder i Customer Journey Analytics:

* Skapa, uppdatera och ta bort data [Anslutningar](/help/connections/overview.md)

  För att kunna utföra den här åtgärden måste användare ingå i en **Experience Platform-produktprofil** som ger följande behörigheter:
   * Datamodellering: Visa scheman, Hantera scheman
   * Datahantering: Visa datauppsättningar, Hantera datauppsättningar
   * Inmatning av data: Hantera källor
   * Visa identitetsnamnutrymmen

     Mer information om behörigheter i Experience Platform finns i [Åtkomstkontroll i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

* Exportera datauppsättningar till molnet [Destinationer](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html)

  För att kunna utföra den här åtgärden behöver användare följande behörigheter i Experience Platform:

   * Hantera mål
   * Aktivera destinationer

     Mer information om målbehörigheter i Experience Platform finns i [Målöversikt](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home).

* Använd [BI-tillägget](../data-views/bi-extension.md)

  För användare att använda BI-tillägget, en produktadministratör

   * måste se till att användarbehörigheterna för Experience Platform omfattar en roll som har frågetjänstresursen med alternativen Hantera frågor och Hantera frågetjänstintegrering. Se [Hantera behörigheter för en produktprofil](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).
   * måste se till att användaren har rätt Customer Journey Analytics-behörigheter:
      * behörighet att få tillgång till relevanta datavyer. Se Datavyer i behörigheten [Customer Journey Analytics i Admin Console](#customer-journey-analytics-permissions-in-admin-console).
      * behörighet att komma åt CJA BI-tillägget. Se Datavy-verktyg i [Customer Journey Analytics behörigheter i Admin Console](#customer-journey-analytics-permissions-in-admin-console).

## Administratörsroll för produktprofil

En produktprofil är en uppsättning behörigheter. Produktprofiladministratörer kan

* Skapa och hantera enskilda produktprofiler. som att lägga till nya användare eller hantera användargrupper och deras tillhörande produktprofiler.

* I Customer Journey Analytics kan du redigera datavyer som ingår i en produktprofil som de hanterar. De kan inte skapa nya datavyer.

## Åtkomst på användarnivå

Tabellen nedan visar de viktigaste åtkomstbehörigheterna för olika Customer Journey Analytics-funktioner för icke-produktadministratörer och produktadministratörer i Customer Journey Analytics. Genom att förstå dessa behörigheter kan användarna effektivt navigera och använda Customer Journey Analytics utifrån sin roll och sitt ansvar inom organisationen.

| Funktioner | Icke-produktadministratörer (användare) | Produktadministratörer |
| --- | --- | --- |
| **Datavyer** | Kan inte visa/uppdatera/skapa/ta bort | Kan skapa/uppdatera/ta bort |
| **Anslutningar** | Kan inte visa/uppdatera/skapa/ta bort | Kan skapa/uppdatera/ta bort |
| **Filter** | Kan skapa | Kan skapa |
| **Projekt** | Kan skapa | Kan skapa/uppdatera/ta bort |
| **Publiker** | Kan skapas med specialbehörigheter i Admin Console | Kan skapa |
| **Beräknade värden** | Kan skapas med specialbehörigheter i Admin Console | Kan skapa |

{style="table-layout:auto"}

## Projektstrukturering för Workspace

En annan åtkomstkontrollnivå kan användas på rapportnivå i Workspace. Du kan begränsa åtkomsten till specifika komponenter för vissa användare. Mer information om hur du begränsar komponenter (dimensioner, mått, filter, datumintervall) på Workspace-projektnivå och hur du begränsar kurationen till datavyer finns i [Kuratprojekt](/help/analysis-workspace/curate-share/curate.md).

## Ge åtkomst till enskilda mått eller mått

Du kan inte bevilja eller neka tillstånd för enskilda mått eller mått i Customer Journey Analytics på samma sätt som i vanliga Adobe Analytics. Mätvärden och dimensioner kan ändras i [datavyer](/help/data-views/data-views.md) och kan ändras i Customer Journey Analytics. Om du ändrar dem ändras även rapporteringen retroaktivt.

## Användningsexempel

Här följer några exempel som visar hur åtkomstkontroll kan användas i realtidsscenarier.

### Åtkomst från tredje part

En tredje part som ditt företag arbetar med har en teamlead som kan göras till produktprofiladministratör. Den här administratören kan lägga till användare i företagets team i den här produktprofilen. Den här administratören kan ge åtkomst till specifika datavyer och lägga till andra användare i den här produktprofilen. De kan också ändra de datavyer som de har kontroll över så att de passar teamets behov.

### Åtkomstkontroll på radnivå

Säg att du bara vill ge användarna tillgång till data från en dag. Så här begränsar du åtkomsten till de raderna:

1. Skapa ett filter i Customer Journey Analytics där **[!UICONTROL Day]** är lika med det datum som du vill att de ska ha dataåtkomst till.
1. I [!UICONTROL Data views] > [!UICONTROL Settings] lägger du till det filtret i datavyn.
1. Spara datavyn så tillämpas filtret automatiskt på datauppsättningen. Alla rader som inte passar filterdefinitionen exkluderas nu automatiskt från den redigerade datavyn.
1. Skapa en ny produktprofil i Admin Console, lägg till användare i den och begränsa deras åtkomst till den här datavyn.

### Åtkomstkontroll på värdenivå

Användare som har åtkomst till en datavy kan bara arbeta med de mått och mått som Admin har inkluderat i den här datavyn. Administratörer kan använda funktionen [Inkludera/exkludera ](/help/data-views/component-settings/include-exclude-values.md) i datavyer för att exempelvis exkludera vissa dimensionsvärden från en datavy.

Här är ett vårdrelaterat exempel: Låt oss säga att du skapar ett mätvärde som kallas&quot;Hypertension&quot; i en datavy, från en datauppsättning som innehåller dessa data. Det faktum att det är ett mått skulle göra det möjligt att se det sammanlagda värdet av detta mätresultat, men inte de enskilda patienter som faller under det.

## Customer Journey Analytics behörigheter i Admin Console

Fliken **[!UICONTROL Permissions]** ingår i varje produktprofil i [Admin Console](https://adminconsole.adobe.com/enterprise/). Du kan lägga till användare i specifika produktprofiler. Sedan tilldelar du rättigheter till specifika datavyer och anger vilka behörigheter användarna i en produktprofil har. Här är Customer Journey Analytics-specifika behörigheter:

![behörigheter för Admin Console](assets/permissions.png)

| Behörighet | Definition |
| --- | --- |
| **[!UICONTROL Data Views]** | Om du växlar **[!UICONTROL Auto-Include]** till **[!UICONTROL On]** kan användare som är en del av den här produktprofilen visa alla befintliga och nyligen skapade datavyer. Om den här inställningen är **[!UICONTROL Off]** kan du välja särskilda datavyer som användarna har åtkomst till. |
| **[!UICONTROL Reporting Tools]**: |   |
| **[!UICONTROL Audit Logs Access]** | Den här behörigheten framtvingar behörighetskontrollen för [API](https://www.adobe.io/cja-apis/docs/endpoints/auditlogs/) och gränssnittet för granskningsloggar. |
| **[!UICONTROL Analysis Workspace Access]** | Ge användare tillgång till Analysis Workspace i Customer Journey Analytics. |
| [!UICONTROL **Guided Analysis Access**] | Låt användarna skapa [guidade analysprojekt](/help/guided-analysis/overview.md). |
| [!UICONTROL **Prognos**] | Ge användarna tillgång till funktionen Prognos i Analysis Workspace |
| **[!UICONTROL Reporting Usage Admin]** | Låt användarna visa och ta bort alla rapporter som körs i deras företag. |
| **[!UICONTROL Reporting Usage View]** | Låt användarna se alla begäranden om samtidig rapportering. |
| [!UICONTROL **Fullständig tabellexport**] | Låt användare [exportera fullständiga tabeller till molnet](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Calculated Metrics Creation]** | Låt användarna skapa [beräknade värden](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter Creation]** | Låt användarna skapa [filter](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs Access]** | Ge användarna åtkomst till fliken [Labs](/help/labs/labs.md) i Customer Journey Analytics. |
| **[!UICONTROL Annotation Creation]** | Låt användarna skapa [anteckningar](/help/components/annotations/overview.md). |
| **[!UICONTROL Audience Creation]** | Låt användare skapa [målgrupper](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Audience View]** | Låt användarna visa [målgrupper](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL **Dela projektlänkar med vem som helst**] | Låt användare [dela projekt med vem som helst.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| **[!UICONTROL Data View Tools]**: |   |
| [!UICONTROL **Fullständig tabellexport**] | Låt användare [exportera fullständiga tabeller till molnet](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL [!UICONTROL CJA BI Extension]]** | Låt användare använda [BI-tillägget](../data-views/bi-extension.md). |

{style="table-layout:auto"}
