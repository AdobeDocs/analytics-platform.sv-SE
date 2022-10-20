---
title: CJA-åtkomstkontroll
description: Lär dig hur du implementerar åtkomstkontroll i CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 8262d7f0ec56a792bfcd8fe94b7f7685ee5b5438
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 0%

---

# CJA-åtkomstkontroll

Customer Journey Analytics (CJA) styrs av tre behörighetsnivåer eller tre roller: Produktadministratörsroll, administratörsroll för produktprofil och åtkomst på användarnivå. I det här avsnittet förklaras de här rollerna mer ingående.

Dessutom diskuterar vi mer detaljerade sätt att begränsa åtkomsten, t.ex. kurering av arbetsytor och radnivå samt åtkomstkontroll på värdenivå.

## Produktadministratörsroll

Produktadministratörer har behörighet att utföra alla uppgifter som krävs inom CJA. Du måste läggas till som produktadministratör för **Customer Journey Analytics produktprofil** i [Admin Console](https://adminconsole.adobe.com/enterprise/) under [!UICONTROL Customer Journey Analytics] > [!UICONTROL Admins] tab > [!UICONTROL Add Admin]. Produktadministratörer har följande behörigheter:

* Skapa/uppdatera/ta bort anslutningar eller datavyer
* Uppdatera/ta bort projekt, filter, beräknade värden, målgrupper, anteckningar eller filter som skapats av andra användare
* Dela arbetsyteprojekt till alla användare

Att bli produktadministratör i Customer Journey Analytics räcker inte för att skapa, uppdatera eller ta bort en [anslutning](/help/connections/overview.md). Om du vill skapa en anslutning till en datauppsättning från Experience Platform måste du även ha Experience Platform-behörighet. Du måste vara en del av en **Experience Platform produktprofil** som ger dig följande behörigheter:

* Datamodellering: Visa scheman, hantera scheman
* Datahantering: Visa datauppsättningar, hantera datauppsättningar
* Dataintag: Hantera källor
* Visa identitetsnamnutrymmen

Mer information om behörigheter i Experience Platform finns i [Åtkomstkontroll i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

## Administratörsroll för produktprofil

En produktprofil är en uppsättning behörigheter. Produktprofiladministratörer kan

* Skapa och hantera enskilda produktprofiler, som att lägga till nya användare eller hantera användargrupper och deras tillhörande produktprofiler.

* I CJA redigerar du datavyer som ingår i en produktprofil som de hanterar. De kan inte skapa nya datavyer.

## Åtkomst på användarnivå

Användare i Customer Journey Analytics kan inte skapa, redigera eller visa datavyer eller anslutningar. Användare kan skapa filter, projekt, målgrupper och beräknade värden med specialbehörigheter i Admin Console.

## Projektstrukturering för arbetsyta

En annan åtkomstkontrollnivå kan användas på rapportnivån för arbetsytan. Du kan begränsa åtkomsten till specifika komponenter för vissa användare. Mer information om hur du begränsar komponenter (dimensioner, mått, segment, datumintervall) på projektnivån för arbetsytan och hur kursen är kopplad till datavyer finns i [Kuratprojekt](/help/analysis-workspace/curate-share/curate.md).

## Ge åtkomst till enskilda mått eller mått

Du kan inte bevilja eller neka tillstånd för enskilda mått eller mått i Customer Journey Analytics på samma sätt som i vanliga Adobe Analytics. Mätvärden och dimensioner kan ändras i [datavyer](/help/data-views/data-views.md) och kan därför komma att ändras i CJA. Om du ändrar dem ändras även rapporteringen retroaktivt.

## Användningsexempel

Här följer några exempel som visar hur åtkomstkontroll kan användas i realtidsscenarier.

### Åtkomst från tredje part

En tredje part som ditt företag arbetar med har en teamledare som kan bli produktprofiladministratör. Den här administratören kan sedan lägga till användare i teamet till den här produktprofilen. Den här administratören kan ge åtkomst till specifika datavyer och lägga till andra användare i produktprofilen. De kan också ändra de datavyer som de har kontroll över så att de passar teamets behov.

### Åtkomstkontroll på radnivå

Säg att du bara vill ge användarna tillgång till data från en dag. Så här begränsar du åtkomsten till de raderna:

1. Skapa ett filter i CJA där **[!UICONTROL Day]** är lika med det datum som du vill att de ska ha dataåtkomst till.
1. I [!UICONTROL Data views] > [!UICONTROL Settings]lägger du till det filtret i datavyn.
1. Spara datavyn så tillämpas filtret automatiskt på datauppsättningen. Alla rader som inte passar filterdefinitionen exkluderas nu automatiskt från den redigerade datavyn.
1. Skapa en ny produktprofil i Admin Console, lägg till användare i den och begränsa deras åtkomst till den här datavyn.

### Åtkomstkontroll på värdenivå

Användare som har åtkomst till en datavy kan bara arbeta med de mått och mått som Admin har inkluderat i den här datavyn. Administratörer kan använda [Inkludera/exkludera funktioner](/help/data-views/component-settings/include-exclude-values.md) i datavyer för att t.ex. utesluta vissa dimensionsvärden från en datavy.

Här är ett vårdrelaterat exempel: Låt oss säga att du skapar ett mätvärde som kallas&quot;Hypertension&quot; i en datavy, från en datauppsättning som innehåller dessa data. Det faktum att det är ett mått skulle göra det möjligt att se det sammanlagda värdet av detta mätresultat, men inte de enskilda patienter som faller under det.

## CJA-behörigheter i Admin Console

The **[!UICONTROL Permissions]** är en del av varje produktprofil i [Admin Console](https://adminconsole.adobe.com/enterprise/). Du kan lägga till användare i specifika produktprofiler. Sedan tilldelar du rättigheter till specifika datavyer och anger vilka behörigheter användarna i en produktprofil har. Här är de CJA-specifika behörigheterna:

![behörigheter för Admin Console](assets/permissions.png)

| Behörighet | Definition |
| --- | --- |
| **[!UICONTROL Data Views]** | Om du växlar **[!UICONTROL Auto-Include]** till **[!UICONTROL On]**, kan användare som är en del av den här produktprofilen visa alla befintliga och nyligen skapade datavyer. Om den här inställningen är inställd på **[!UICONTROL Off]** kan du välja särskilda datavyer som användarna har tillgång till. |
| **[!UICONTROL Reporting Tools]**: |  |
| **[!UICONTROL Audit Logs Access]** | Den här behörigheten tvingar behörighetskontrollen på [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) och [gränssnitt för granskningsloggar](/help/privacy/audit-log.md). |
| **[!UICONTROL Reporting Usage Admin]** | Låter användarna visa och ta bort alla rapporter som körs i deras företag. (Funktionen för rapportering av användning har ännu inte släppts.) |
| **[!UICONTROL Reporting Usage View]** | Låter användarna se alla samtidiga rapporteringsbegäranden. (Funktionen för rapportering av användning har ännu inte släppts.) |
| **[!UICONTROL Calculated Metrics Creation]** | Låter användarna skapa [beräknade värden](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter Creation]** | Låter användarna skapa [filter](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs Access]** | Ger användarna åtkomst till [Labs](/help/labs/labs.md) -fliken i CJA. |
| **[!UICONTROL Annotation Creation]** | Låter användarna skapa [anteckningar](/help/components/annotations/overview.md). |
| **[!UICONTROL Audience Creation]** | Låter användarna skapa [målgrupper](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Audience View]** | Låter användarna visa [målgrupper](/help/components/audiences/audiences-overview.md). |

{style=&quot;table-layout:auto&quot;}
