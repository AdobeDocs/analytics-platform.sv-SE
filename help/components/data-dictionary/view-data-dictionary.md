---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Visa dataordlistan
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Visa komponentinformation i Data Dictionary

Med Data Dictionary kan du visa information om en komponent, inklusive komponentbeskrivningen, liknande komponenter, andra komponenter som en komponent ofta används med, med mera.

Så här visar du information om en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill visa.

1. Välj [!UICONTROL **Dataordlista**] ikonen till vänster i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i&quot;Åtkomst till dataordlistan&quot; i [Översikt över dataordlistan](/help/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Kontrollera att datavyn som innehåller komponenten som du vill visa är markerad i listrutan. Som standard visas datavyn som du redan befinner dig i.

1. (Valfritt) I sökfältet börjar du med att skriva namnet på komponenten som du vill visa.

   Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension, ikon](assets/dimension-icon.png) är orange, **Segment** ![Segmentikon](assets/segment-icon.png) är blå, **Datumintervall** ![Ikon för datumintervall](assets/date-range-icon.png) är lila, och **Mått** ![Mätningsikon](assets/default-metric-icon.png) är gröna. Ikonen Adobe ![Adobe, ikon](assets/default-calc-metric-icon.png) anger antingen en mall för beräknade mätvärden eller en segmentmall och räknikonen ![Beräkningsikon](assets/calculated-metric-icon-created.png) har angett ett beräknat mått som har skapats av en Analytics-administratör i organisationen.

{{dd-filter-criteria}}

1. Välj den komponent du vill visa i listan med komponenter.

   Följande information om komponenten visas:

   {{dd-component-information}}

1. (Valfritt) Dra en komponent från Data Dictionary till Analysis Workspace.
