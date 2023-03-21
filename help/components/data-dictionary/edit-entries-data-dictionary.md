---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Redigera poster i Data Dictionary
feature: Components
role: Admin
source-git-commit: 733e0e358aa34ce126687f01ffb6d89f9b0c4210
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Redigera komponentposter i Data Dictionary

Customer Journey Analytics-administratörer kan redigera komponentposter i Data Dictionary för en given Report Suite. Alla ändringar som görs är synliga för alla användare av Report Suite.

Så här redigerar du en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill redigera.

1. Välj **Dataordlista** ikonen till vänster i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i&quot;Åtkomst till dataordlistan&quot; i [Översikt över dataordlistan](/help/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![Administratörsvy för datamordlista](assets/data-dictionary-admin.png)

1. Kontrollera att rätt Report Suite är markerat i listrutan. Som standard visas den rapportsvit som du redan ingår i.

1. (Valfritt) I sökfältet börjar du skriva namnet på komponenten som du vill redigera.

   Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension, ikon](assets/dimension-icon.png) är orange, **Segment** ![Segmentikon](assets/segment-icon.png) är blå, **Datumintervall** ![Ikon för datumintervall](assets/date-range-icon.png) är lila, och **Mått** ![Mätningsikon](assets/default-metric-icon.png) är gröna. Ikonen Adobe ![Adobe, ikon](assets/default-calc-metric-icon.png) anger antingen en mall för beräknade mätvärden eller en segmentmall och räknikonen ![Beräkningsikon](assets/calculated-metric-icon-created.png) har angett ett beräknat mått som har skapats av en Analytics-administratör i organisationen.

{{dd-filter-criteria}}

1. Markera den komponent som du vill redigera i listan med komponenter.

1. Välj **Redigera** icon ![Ikon för redigering av dataordlista](assets/data-dictionary-edit-icon.png) bredvid komponentnamnet.

1. Redigera någon av följande information om komponenten:

   {{dd-component-information}}

1. Klicka på **Spara** icon ![Ikonen Spara i datamordlista](assets/data-dictionary-save-icon.png) för att spara ändringarna.
