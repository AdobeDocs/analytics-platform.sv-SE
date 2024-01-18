---
title: Åtkomstkontroll för Customer Journey Analytics
description: Lär dig hur du implementerar åtkomstkontroll i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: ae968e46c5822c9209ecf78735df0914f33cb0d2
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 0%

---

# Åtkomstkontroll för Customer Journey Analytics

Customer Journey Analytics styrs av tre behörighetsnivåer eller tre roller: produktadministratörsroll, administratörsroll för produktprofil och åtkomst på användarnivå. I det här avsnittet förklaras de här rollerna mer ingående.

Dessutom diskuterar vi mer detaljerade sätt att begränsa åtkomsten, t.ex. kurering av arbetsytor och radnivå samt åtkomstkontroll på värdenivå.

## Produktadministratörsroll

Användare som har tilldelats rollen Produktadministratör får som standard de behörigheter som krävs för att utföra de flesta åtgärder inom Customer Journey Analytics. För vissa uppgifter krävs dock ytterligare behörigheter.

Så här lägger du till en användare som produktadministratör:

1. Gå till [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Välj [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administratörer**] tab > [!UICONTROL **Lägg till administratör**].

   De användare du har lagt till får [Standardbehörigheter för produktadministratör](#product-admin-default-permissions). Du kan också ge dem [ytterligare behörigheter](#product-admin-additional-permissions) vid behov.

### Standardbehörigheter för produktadministratör

Produktadministratörer har behörighet att utföra de flesta åtgärder inom Customer Journey Analytics.

Produktadministratörer har som standard behörighet att utföra följande uppgifter:

* Skapa, uppdatera och ta bort datavyer
* Uppdatera och ta bort projekt, filter, beräknade värden, målgrupper, anteckningar eller filter som skapats av andra användare
* Dela arbetsyteprojekt till alla användare
* Hantera rapporteringsaktivitet i [Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity-overview.md)

### Ytterligare behörigheter för produktadministratör

Förutom att läggas till som produktadministratör i **Customer Journey Analytics produktprofil** i [Admin Console](https://adminconsole.adobe.com/enterprise/)krävs ytterligare tillstånd för att kunna utföra följande uppgifter i Customer Journey Analytics:

* Skapa, uppdatera och ta bort data [Anslutningar](/help/connections/overview.md)

  Användarna måste vara en del av en **Experience Platform produktprofil** som ger följande behörigheter:
   * Datamodellering: Visa scheman, Hantera scheman
   * Datahantering: Visa datauppsättningar, Hantera datauppsättningar
   * Inmatning av data: Hantera källor
   * Visa identitetsnamnutrymmen

     Mer information om behörigheter i Experience Platform finns i [Åtkomstkontroll i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

* Exportera datauppsättningar till molnet [Destinationer](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en)

  >[!AVAILABILITY]
  >
  >Möjligheten att exportera datauppsättningar till molnet är i den begränsade testfasen av releasen och är kanske inte tillgänglig än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).

  För att kunna utföra den här uppgiften behöver användare även följande behörigheter i Experience Platform:
   * Hantera mål
   * Aktivera destinationer

     Mer information om målbehörigheter i Experience Platform finns i [Översikt över destinationer](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=en#access-controls).

## Administratörsroll för produktprofil

En produktprofil är en uppsättning behörigheter. Produktprofiladministratörer kan

* Skapa och hantera enskilda produktprofiler, som att lägga till nya användare eller hantera användargrupper och deras tillhörande produktprofiler.

* I Customer Journey Analytics kan du redigera datavyer som ingår i en produktprofil som de hanterar. De kan inte skapa nya datavyer.

## Åtkomst på användarnivå

Användare i Customer Journey Analytics kan inte skapa, redigera eller visa datavyer eller anslutningar. Användare kan skapa filter, projekt, målgrupper och beräknade värden med specialbehörigheter i Admin Console.

## Projektstrukturering för arbetsyta

En annan åtkomstnivå kan användas på rapportnivån i arbetsytan. Du kan begränsa åtkomsten till specifika komponenter för vissa användare. Mer information om hur du begränsar komponenter (dimensioner, mått, filter, datumintervall) på projektnivån för arbetsytan och hur kurvan är kopplad till datavyer finns i [Kuratprojekt](/help/analysis-workspace/curate-share/curate.md).

## Ge åtkomst till enskilda mått eller mått

Du kan inte bevilja eller neka tillstånd för enskilda mått eller mått i Customer Journey Analytics på samma sätt som i vanliga Adobe Analytics. Mätvärden och dimensioner kan ändras i [datavyer](/help/data-views/data-views.md) och kan därför komma att ändras i Customer Journey Analytics. Om du ändrar dem ändras även rapporteringen retroaktivt.

## Användningsexempel

Här följer några exempel som visar hur åtkomstkontroll kan användas i realtidsscenarier.

### Åtkomst från tredje part

En tredje part som ditt företag arbetar med har en teamlead som kan göras till produktprofiladministratör. Den här administratören kan sedan lägga till användare i teamet till den här produktprofilen. Den här administratören kan ge åtkomst till specifika datavyer och lägga till andra användare i den här produktprofilen. De kan också ändra de datavyer som de har kontroll över så att de passar teamets behov.

### Åtkomstkontroll på radnivå

Säg att du bara vill ge användarna tillgång till data från en dag. Så här begränsar du åtkomsten till de raderna:

1. Skapa ett filter i Customer Journey Analytics där **[!UICONTROL Day]** är det datum som du vill att de ska ha dataåtkomst till.
1. I [!UICONTROL Data views] > [!UICONTROL Settings]lägger du till det filtret i datavyn.
1. Spara datavyn så tillämpas filtret automatiskt på datauppsättningen. Alla rader som inte passar filterdefinitionen exkluderas nu automatiskt från den redigerade datavyn.
1. Skapa en ny produktprofil i Admin Console, lägg till användare i den och begränsa deras åtkomst till den här datavyn.

### Åtkomstkontroll på värdenivå

Användare som har åtkomst till en datavy kan bara arbeta med de mått och mått som Admin har inkluderat i den här datavyn. Administratörer kan använda [Inkludera/exkludera funktioner](/help/data-views/component-settings/include-exclude-values.md) i datavyer för att t.ex. utesluta vissa dimensionsvärden från en datavy.

Här är ett vårdrelaterat exempel: Låt oss säga att du skapar ett mätvärde som kallas&quot;Hypertension&quot; i en datavy, från en datauppsättning som innehåller dessa data. Det faktum att det är ett mått skulle göra det möjligt att se det sammanlagda värdet av detta mätresultat, men inte de enskilda patienter som faller under det.

## Customer Journey Analytics behörigheter i Admin Console

The **[!UICONTROL Permissions]** är en del av varje produktprofil i [Admin Console](https://adminconsole.adobe.com/enterprise/). Du kan lägga till användare i specifika produktprofiler. Sedan tilldelar du rättigheter till specifika datavyer och anger vilka behörigheter användarna i en produktprofil har. Här är Customer Journey Analytics-specifika behörigheter:

![behörigheter för Admin Console](assets/permissions.png)

| Behörighet | Definition |
| --- | --- |
| **[!UICONTROL Data Views]** | Om du växlar **[!UICONTROL Auto-Include]** till **[!UICONTROL On]**, kan användare som är en del av den här produktprofilen visa alla befintliga och nyligen skapade datavyer. Om den här inställningen är **[!UICONTROL Off]** kan du välja särskilda datavyer som användarna har tillgång till. |
| **[!UICONTROL Reporting Tools]**: |   |
| **[!UICONTROL Audit Logs Access]** | Den här behörigheten tvingar behörighetskontrollen på [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) och användargränssnittet för granskningsloggar. |
| **[!UICONTROL Reporting Usage Admin]** | Låter användarna visa och ta bort alla rapporter som körs i deras företag. |
| **[!UICONTROL Reporting Usage View]** | Låter användarna se alla samtidiga rapporteringsbegäranden. |
| [!UICONTROL **Fullständig tabellexport**] | Tillåter användare [exportera hela tabeller till molnet](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Calculated Metrics Creation]** | Låter användarna skapa [beräknade värden](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter Creation]** | Låter användarna skapa [filter](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs Access]** | Ger användarna åtkomst till [Labs](/help/labs/labs.md) i Customer Journey Analytics. |
| **[!UICONTROL Annotation Creation]** | Låter användarna skapa [anteckningar](/help/components/annotations/overview.md). |
| **[!UICONTROL Audience Creation]** | Låter användarna skapa [målgrupper](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Audience View]** | Låter användarna visa [målgrupper](/help/components/audiences/audiences-overview.md). |

{style="table-layout:auto"}
