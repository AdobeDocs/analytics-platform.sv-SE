---
source-git-commit: d903745e105edb11ef6f43b6137e1e03d43e5e07
workflow-type: tm+mt
source-wordcount: '1253'
ht-degree: 0%

---
# Fragment

## Begränsad testning av versionsfas {#release-limited-testing}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i den här artikeln är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).

## Frisläppningsfas, begränsad testsektion {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).

## Välj paket {#select-package}

>[!NOTE]
>
>Du måste ha paketet **Select** eller senare för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

## Prime-paket {#prime-package}

>[!NOTE]
>
>Du måste ha paketet **Prime** eller senare för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

## Ultimat paket {#ultimate-package}

>[!NOTE]
>
>Du måste ha paketet **Ultimate** för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.


## Filtervillkor för dataordlista {#dd-filter-criteria}

1. (Valfritt) Markera ikonen **Filter** ![Datamordlistefilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) och välj sedan något av följande filteralternativ för att filtrera komponentlistan:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Godkänd**] | Visa endast komponenter som har markerats som Godkänd av en administratör. |
   | [!UICONTROL **Favoriter**] | Visa endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Komponentöversikt](/help/components/overview.md). |
   | [!UICONTROL **Dimensioner**] | Visa endast komponenter som är Dimensioner. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
   | [!UICONTROL **Mätvärden**] | Visa endast komponenter som är mätvärden. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
   | [!UICONTROL **Filter**] | Visa endast komponenter som är filter. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Datumintervall**] | Visa endast komponenter som är datumintervall. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
   | [!UICONTROL **Visa alla**] | Visa alla komponenter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Ej godkänt**] | Visa endast komponenter som ännu inte har markerats som Godkända av en administratör. Som administratör är detta användbart när du identifierar komponenter som kräver granskning och godkännande. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Beskrivning saknas**] | Visa endast komponenter som ännu inte har någon beskrivning i fältet Beskrivning. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Visa dubbletter**] | Visa bara komponenter som har antingen samma namn eller samma beskrivning som en annan komponent i den markerade datavyn. Detta omfattar både komponenter du skapar och de som tillhandahålls av Adobe. Namn eller beskrivningar måste vara exakta matchningar för att kunna visas som dubbletter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Inga senaste data**] | Visa endast komponenter som inte har samlat in några data under de senaste 90 dagarna. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Skapad av Adobe**] <!-- I don't see this option--> | Visa endast komponenter som har skapats av Adobe. Komponenter som har skapats av en administratör eller en annan användare i organisationen visas inte. |

   {style="table-layout:auto"}

## Komponentinformation för dataordlista {#dd-component-information}

| Alternativ | Funktion |
|---------|----------|
| [!UICONTROL **Godkänd**] | <p>Anger att komponenten har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **inte godkänna**]. Om du väljer det här alternativet markeras komponenten som&quot;Inte godkänd&quot; för användarna.</p> |
| [!UICONTROL **Inte godkänt**] | <p>Anger att komponenten ännu inte har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **godkänna**]. Om du väljer det här alternativet markeras komponenten som&quot;Godkänd&quot; för användare.</p> |
| [!UICONTROL **Beskrivning**] | Beskriver komponentens avsedda funktion. (Den här informationen läggs till av Analytics-administratören, enligt beskrivningen i [Lägg till komponentbeskrivningar](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Används ofta med**] | <p>Visar komponenter som används oftast med den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Filter och Datumintervall.</p><p>Listan baseras på data från de senaste 90 dagarna. Endast de komponenter som du har åtkomst till visas.</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**]. Innan du strukturerar de komponenter som visas för användarna måste du först tillämpa filtret **Visa alla** för att se om några komponenter som inte delas med dig har lagts till av en annan administratör.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Liknar**] | <p>Visar komponenter med liknande namn som den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Filter och Datumintervall.</p><p>Endast de komponenter som du har åtkomst till visas.</p><p>Alla dubblettkomponenter i datavyn visas här. Analysadministratörer bör identifiera och ta bort alla dubblettkomponenter, vilket beskrivs i [Övervaka dataordlistehälsa](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**]. Innan du strukturerar de komponenter som visas för användarna måste du först tillämpa filtret **Visa alla** för att se om några komponenter som inte delas med dig har lagts till av en annan administratör.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBS!** För närvarande innehåller avsnittet **Liknande** bara komponenter som du skapar och inte de som tillhandahålls av Adobe. Komponenter som tillhandahålls av Adobe kommer att läggas till i en framtida version.</p> |
| [!UICONTROL **Produktkompatibilitet**] | Anger var i Customer Journey Analytics det här beräknade måttet kan användas. <p>Möjliga värden är:</p><ul><li>[!UICONTROL **Överallt i Customer Journey Analytics**]: Det beräknade måttet kan användas i hela Customer Journey Analytics, inklusive i Analysis Workspace, Report Builder och så vidare.</li><li>[!UICONTROL **Överallt i Customer Journey Analytics (utom experiment)**]: Det beräknade måttet kan användas i hela Customer Journey Analytics, utom på panelen Experimentation.</li> <p>Mer information om villkoren som avgör om ett beräknat mätresultat kan användas för experimenterande finns i [Använd beräknade mätvärden på panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) i [panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| [!UICONTROL **Taggar**] | Visar alla taggar som har tillämpats på komponenten. Användare med administratörsbehörighet kan lägga till taggar när komponenten redigeras. |
| [!UICONTROL **Komponenttyp**] | Visar vilken typ av komponent det är, oavsett om det är en Dimension, ett mått, ett filter eller ett datumintervall. |
| [!UICONTROL **Skapad av**] | Visar namnet på den användare som skapade komponenten. |
| [!UICONTROL **Förhandsgranska**] | Visar en förhandsgranskning av hur komponenten ser ut i Analysis Workspace. |
| [!UICONTROL **Senast ändrad**] | Visar den dag som komponenten senast ändrades. Det här avsnittet visas när du visar filter, mått, beräknade värden och datumintervall. |

{style="table-layout:auto"}

## Alternativ för komponentsortering {#components-sort-options}

| Alternativ | Funktion |
|---------|----------|
| [!UICONTROL **Rekommenderas**] | Sorterar komponenter med de som rekommenderas högst upp i listan. Komponenter som du eller andra i organisationen använder oftast och senast visas högst upp i listan. |
| [!UICONTROL **Alfabetiskt**] | Sorterar komponenterna i bokstavsordning. |
| [!UICONTROL **Kategorisisk**] | Sorterar komponenter efter komponenttyp (dimension, mått, filter, datumintervall). |

{style="table-layout:auto"}

## Tidsjämförelse {#apply-time-comparison}

Du kan jämföra den aktuella tidsperioden med en tidigare tidsperiod. Om du väljer ett alternativ på den här menyn får alla datapunkter en motsvarande streckad motsvarighet i färg. Den här motsvarigheten representerar samma mått i det valda föregående datumintervallet. Om du anger det här alternativet dubbleras antalet objekt i diagrammet och raderna i tabellen.

Tillgängliga tidsjämförelsealternativ omfattar föregående period, 13 veckor före, 52 veckor före och ett anpassat datumintervall. Om du väljer Anpassat datumintervall visas ytterligare alternativ så att du kan välja antal och detaljrikedom. Om du väljer Ingen tas datumjämförelsen bort.
