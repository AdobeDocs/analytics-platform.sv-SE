---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Redigera poster i Data Dictionary
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Redigera komponentposter i Data Dictionary

Customer Journey Analytics-administratörer kan redigera komponentposter i datamappningen för en viss datavy. Alla ändringar som görs är synliga för alla som använder datavyn.

Så här redigerar du en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill redigera.

1. Markera ikonen **Dataordlista** på knapppanelen i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i Åtkomst till dataordlistan i [Översikt över dataordlistan](/help/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![Vyn Administratör för dataordlista visar ordlistehälsa](assets/data-dictionary-admin.png)

1. Kontrollera att rätt datavy är markerad i listrutan. Som standard visas datavyn som du redan befinner dig i.

1. (Valfritt) I sökfältet börjar du skriva namnet på komponenten som du vill redigera.

   Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension-ikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) är orange, **Filter** ![Segmentikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) är blå, **Datumintervall** ![Datumintervallikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) är lila och **Mätvärden** ![Målikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) är gröna. Ikonen Adobe anger antingen en beräknad mätmall eller en filtermall, och räkningsikonen ![Beräkningsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indikerar ett beräknat mätresultat som har skapats av en Analysadministratör i din organisation.

   {{dd-filter-criteria}}

1. (Valfritt) Välj ikonen **Sortera** ![Sortera komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) och välj sedan något av följande filteralternativ för att sortera komponentlistan:

{{components-sort-options}}

1. Markera den komponent som du vill redigera i listan med komponenter.

1. Välj ikonen **Redigera** ![Redigera datamordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) bredvid komponentnamnet.

1. Redigera någon av följande information om komponenten:

{{dd-component-information}}

1. Klicka på ikonen **Spara** ![Spara i datamordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) för att spara ändringarna.
