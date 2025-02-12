---
title: Content Analytics-rapportering
description: Rapportera om innehållsanalys
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 7542e7a402c8e2f8d6e4c1e624f04ceb752cc27e
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 0%

---

# Översikt över Content Analytics-rapportering

>[!WARNING]
>
>Den här artikeln är ett preliminärt inofficiellt utkast till en kommande slutversion och ingår i Content Analytics-dokumentationen. Allt innehåll kan ändras och inga rättsliga skyldigheter kan härledas från den aktuella versionen av den här artikeln.
>

{{release-limited-testing}}

Rapportering om innehållsanalys görs i Analysis Workspace. En specifik Workspace [mall](#template) finns tillgänglig, så du kan omedelbart komma åt ett förifyllt Workspace-projekt med relevanta innehållsinsikter.

Så här börjar du rapportera om innehållsanalys från grunden:

1. [Skapa ett nytt](/help/analysis-workspace/build-workspace-project/create-projects.md) eller [öppna ett befintligt](/help/analysis-workspace/build-workspace-project/open-projects.md)-projekt i Workspace.
1. Dra en ![tabellvisualisering](/help/assets/icons/Table.svg) [Frihandsritabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) på arbetsytan.
1. Använd specifika dimensioner och mått för innehållsanalys och andra generiska [komponenter](/help/components/overview.md) (som filter, datumintervall, anteckningar) för att skapa insikter för innehållsanalyser.

## Miniatyrbilder

Baserat på de dimensioner av innehållsanalysen som du använder i ditt projekt visas miniatyrbilder för resurser och dimensioner.

![Miniatyrbilder för innehållsanalys](../assets/aca-thumbnails.png)

## Förhandsgranskningar

För dimensioner som har miniatyrbilder (som Resursnamn, Upplevelsenamn med flera) kan du öppna ett popup-fönster för förhandsvisning.

Så här öppnar du förhandsgranskningen med följande information:

* Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg). Du ser följande information.

  | Förhandsgranska upplevelse | Förhandsgranska resurs |
  |---|---|
  | ![Förhandsgranskning av upplevelse av innehållsanalys](../assets/aca-experience-preview.png) | ![Förhandsgranskning av innehållsanalysresurser](../assets/aca-asset-preview.png) |
  | **[!UICONTROL Name of the experience]** | **[!UICONTROL Name of the asset]** |
  | **[!UICONTROL Impressions (all times)]**: Antal visningar för upplevelsen. | **[!UICONTROL Impressions (all times)]**: Antal visningar för resursen. |
  | **[!UICONTROL Assets]**: Antal resurser som den här upplevelsen innehåller. Välj ![Uppdelning](/help/assets/icons/Breakdown.svg) för att inspektera resurserna. | **[!UICONTROL Experiences]**: Antal upplevelser där den här resursen visas. [Uppdelning](/help/assets/icons/Breakdown.svg) Uppdelning för att inspektera resurserna. |
  | **[!UICONTROL First impression]**: Datum för första intryck av upplevelsen. | **[!UICONTROL First impression]**: Datum för första exponering av resursen. |
  | **[!UICONTROL  Most recent impression]**: Datum för det senaste intrycket av upplevelsen. | **[!UICONTROL Most recent impression]**: Datum för det senaste intrycket av resursen. |
  | **[!UICONTROL Experience attributes]**: Attributen för upplevelsen. | **[!UICONTROL Asset attributes]**: Resursens attribut. |


## Mall

Information om mallar ...
