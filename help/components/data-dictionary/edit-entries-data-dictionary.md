---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Redigera komponentposter
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1195'
ht-degree: 0%

---

# Redigera komponentposter

Customer Journey Analytics-administratörer kan redigera komponentposter i Data Dictionary för en viss datavy. Alla ändringar som görs är synliga för alla som använder datavyn.

Så här redigerar du en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill redigera.

1. Markera ikonen **Dataordlista** på knapppanelen i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i Åtkomst till dataordlistan i [Översikt över dataordlistan](/help/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![Vyn Administratör för dataordlista visar ordlistehälsa](assets/data-dictionary-admin.png)

1. Kontrollera att rätt datavy är markerad i listrutan. Som standard visas datavyn som du redan befinner dig i.

1. (Valfritt) I sökfältet börjar du skriva namnet på komponenten som du vill redigera.

   Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension-ikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) är orange, **Segment** ![Segmentikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) är blå, **Datumintervall** ![Datumintervallikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) är lila och **Mätvärden** ![Mätningsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) är gröna. Adobe-ikonen indikerar antingen en beräknad mätmall eller en segmentmall, och räkningsikonen ![Beräkningsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indikerar ett beräknat mätresultat som har skapats av en Analysadministratör i din organisation.

1. (Valfritt) Markera ikonen **Filter** ![Dataglexikonfilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) och välj sedan något av följande segmentalternativ för att segmentera komponentlistan:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Godkänd**] | Visa endast komponenter som har markerats som Godkänd av en administratör. |
   | [!UICONTROL **Favoriter**] | Visa endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Komponentöversikt](/help/components/overview.md). |
   | [!UICONTROL **Dimensioner**] | Visa endast komponenter som är dimensioner. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbsegment**] när du först kommer åt datamappningslistan.) |
   | [!UICONTROL **Mätvärden**] | Visa endast komponenter som är mätvärden. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbsegment**] när du först kommer åt datamappningslistan.) |
   | [!UICONTROL **Segment**] | Visa endast komponenter som är segment. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbsegment**] när du först kommer åt datamappningslistan.) |
   | [!UICONTROL **Datumintervall**] | Visa endast komponenter som är datumintervall. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbsegment**] när du först kommer åt datamappningslistan.) |
   | [!UICONTROL **Visa alla**] | Visa alla komponenter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Ej godkänt**] | Visa endast komponenter som ännu inte har markerats som Godkända av en administratör. Som administratör är detta användbart när du identifierar komponenter som kräver granskning och godkännande. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Beskrivning saknas**] | Visa endast komponenter som ännu inte har någon beskrivning i fältet Beskrivning. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Visa dubbletter**] | Visa bara komponenter som har antingen samma namn eller samma beskrivning som en annan komponent i den markerade datavyn. Detta omfattar såväl komponenter du skapar som komponenter från Adobe. Namn eller beskrivningar måste vara exakta matchningar för att kunna visas som dubbletter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Inga senaste data**] | Visa endast komponenter som inte har samlat in några data under de senaste 90 dagarna. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Skapad av Adobe**] <!-- I don't see this option--> | Visa endast komponenter som har skapats av Adobe. Komponenter som har skapats av en administratör eller en annan användare i organisationen visas inte. |

   {style="table-layout:auto"}

1. (Valfritt) Välj ikonen **Sortera** ![Sortera komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) och välj sedan något av följande segmentalternativ för att sortera komponentlistan:

{{components-sort-options}}

1. Markera den komponent som du vill redigera i listan med komponenter.

1. Välj ikonen **Redigera** ![Redigera datamordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) bredvid komponentnamnet.

1. Redigera någon av följande information om komponenten:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Godkänd**] | <p>Anger att komponenten har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **inte godkänna**]. Om du väljer det här alternativet markeras komponenten som&quot;Inte godkänd&quot; för användarna.</p> |
   | [!UICONTROL **Inte godkänt**] | <p>Anger att komponenten ännu inte har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **godkänna**]. Om du väljer det här alternativet markeras komponenten som&quot;Godkänd&quot; för användare.</p> |
   | [!UICONTROL **Beskrivning**] | Beskriver komponentens avsedda funktion. (Den här informationen läggs till av Analytics-administratören, enligt beskrivningen i [Lägg till komponentbeskrivningar](/help/components/add-component-descriptions.md).) |
   | [!UICONTROL **Används ofta med**] | <p>Visar komponenter som används oftast med den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Segment och Datumintervall.</p><p>Listan baseras på data från de senaste 90 dagarna. Endast de komponenter som du har åtkomst till visas.</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**]. Innan du strukturerar de komponenter som användarna ser ska du först tillämpa segmentet **Visa alla** för att se om du ser komponenter som inte delas med dig och som kan ha lagts till av en annan administratör.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | [!UICONTROL **Liknar**] | <p>Visar komponenter med liknande namn som den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Segment och Datumintervall.</p><p>Endast de komponenter som du har åtkomst till visas.</p><p>Alla dubblettkomponenter i datavyn visas här. Analysadministratörer bör identifiera och ta bort alla dubblettkomponenter, vilket beskrivs i [Övervaka dataordlistehälsa](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**]. Innan du strukturerar de komponenter som användarna ser ska du först tillämpa segmentet **Visa alla** för att se om du ser komponenter som inte delas med dig och som kan ha lagts till av en annan administratör.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**OBS!** För närvarande innehåller avsnittet **Liknande** bara komponenter som du skapar och inte komponenter från Adobe. Komponenter som tillhandahålls av Adobe kommer att läggas till i en framtida version.</p> |
   | [!UICONTROL **Produktkompatibilitet**] | Anger var i Customer Journey Analytics det här beräknade måttet kan användas. <p>Möjliga värden är:</p><ul><li>[!UICONTROL **Överallt i Customer Journey Analytics**]: Det beräknade måttet kan användas i hela Customer Journey Analytics, inklusive Analysis Workspace, Report Builder och så vidare.</li><li>[!UICONTROL **Överallt i Customer Journey Analytics (utom experimenterande)**]: Det beräknade måttet kan användas i hela Customer Journey Analytics, förutom på panelen Experimentation.</li> <p>Mer information om villkoren som avgör om ett beräknat mätresultat kan användas för experimenterande finns i [Använd beräknade mätvärden på panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) i [panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | [!UICONTROL **Taggar**] | Visar alla taggar som har tillämpats på komponenten. Användare med administratörsbehörighet kan lägga till taggar när komponenten redigeras. |
   | [!UICONTROL **Komponenttyp**] | Visar vilken typ av komponent det är, oavsett om det är en Dimension, ett mått, ett segment eller ett datumintervall. |
   | [!UICONTROL **Skapad av**] | Visar namnet på den användare som skapade komponenten. |
   | [!UICONTROL **Förhandsgranska**] | Visar en förhandsgranskning av hur komponenten ser ut i Analysis Workspace. |
   | [!UICONTROL **Senast ändrad**] | Visar den dag som komponenten senast ändrades. Det här avsnittet visas när du visar segment, mått, beräknade värden och datumintervall. |

   {style="table-layout:auto"}

1. Klicka på ikonen **Spara** ![Spara i datamordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) för att spara ändringarna.
