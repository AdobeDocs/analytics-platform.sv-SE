---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Redigera poster i Data Dictionary
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Redigera komponentposter i Data Dictionary

Customer Journey Analytics-administratörer kan redigera komponentposter i datamappningen för en viss datavy. Alla ändringar som görs är synliga för alla som använder datavyn.

Så här redigerar du en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill redigera.

1. Välj **Dataordlista** ikonen till vänster i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i&quot;Åtkomst till dataordlistan&quot; i [Översikt över dataordlistan](/help/components/data-dictionary/data-dictionary-overview.md).)

Fönstret Data Dictionary visas.

![Administratörsvy för datamordlista](assets/data-dictionary-admin.png)

1. Kontrollera att rätt datavy är markerad i listrutan. Som standard visas datavyn som du redan befinner dig i.

1. (Valfritt) I sökfältet börjar du skriva namnet på komponenten som du vill redigera.

Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension, ikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) är orange, **Filter** ![Segmentikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) är blå, **Datumintervall** ![Ikon för datumintervall](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) är lila, och **Mått** ![Mätningsikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) är gröna. Ikonen Adobe anger antingen en mall för beräknade mätvärden eller en filtermall och räkneikonen ![Beräkningsikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) har angett ett beräknat mått som har skapats av en Analytics-administratör i organisationen.

{{dd-filter-criteria}}

1. (Valfritt) Välj **Sortera** icon ![Ikon för att sortera komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)väljer du sedan något av följande filteralternativ för att sortera komponentlistan:

{{components-sort-options}}

1. Markera den komponent som du vill redigera i listan med komponenter.

1. Välj **Redigera** icon ![Ikon för redigering av dataordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) bredvid komponentnamnet.

1. Redigera någon av följande information om komponenten:

{{dd-component-information}}

1. Klicka på **Spara** icon ![Ikonen Spara i datamordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) för att spara ändringarna.
