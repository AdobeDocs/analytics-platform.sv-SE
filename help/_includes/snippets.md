---
source-git-commit: 486cd26bfacbae0072e14ec078ceca66909ac0ec
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 0%

---
# Fragment

## Begränsad testning av versionsfas {#release-limited-testing}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i den här artikeln är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).

## Frisläppningsfas, begränsad testsektion {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).

## Välj paket {#select-package}

>[!NOTE]
>
>Du måste ha **Välj** för att använda de funktioner som beskrivs i detta avsnitt. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.


## Filtervillkor för dataordlista {#dd-filter-criteria}

1. (Valfritt) Välj **Filter** icon ![Ikon för dataordlistefilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)väljer du sedan något av följande filteralternativ för att filtrera komponentlistan:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Godkänd**] | Visa endast komponenter som har markerats som Godkänd av en administratör. |
   | [!UICONTROL **Favoriter**] | Visa endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Komponenter - översikt](/help/components/overview.md). |
   | [!UICONTROL **Dimensioner**] | Visa endast komponenter som är Dimensioner. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
   | [!UICONTROL **Mätvärden**] | Visa endast komponenter som är mätvärden. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
   | [!UICONTROL **Filter**] | Visa endast komponenter som är filter. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Datumintervall**] | Visa endast komponenter som är datumintervall. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
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
| [!UICONTROL **Godkänd**] | <p>Anger att komponenten har granskats och godkänts av administratören.</p><p>Administratörer kan välja att [!UICONTROL **Ogodkänd**]. Om du väljer det här alternativet markeras komponenten som&quot;Inte godkänd&quot; för användarna.</p> |
| [!UICONTROL **Ej godkänt**] | <p>Anger att komponenten ännu inte har granskats och godkänts av administratören.</p><p>Administratörer kan välja att [!UICONTROL **Godkänn**]. Om du väljer det här alternativet markeras komponenten som&quot;Godkänd&quot; för användare.</p> |
| [!UICONTROL **Beskrivning**] | Beskriver komponentens avsedda funktion. (Den här informationen läggs till av Analytics-administratören, enligt beskrivningen i [Lägga till komponentbeskrivningar](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Används ofta tillsammans med**] | <p>Visar komponenter som används oftast med den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Filter och Datumintervall.</p><p>Listan baseras på data från de senaste 90 dagarna. Endast de komponenter som du har åtkomst till visas.</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**] nedrullningsbara fält. Innan du strukturerar de komponenter som användarna ser ska du först använda **Visa alla** för att säkerställa att du ser komponenter som inte delas med dig och som kan ha lagts till av en annan administratör.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Liknar**] | <p>Visar komponenter med liknande namn som den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Filter och Datumintervall.</p><p>Endast de komponenter som du har åtkomst till visas.</p><p>Alla dubblettkomponenter i datavyn visas här. Analysadministratörer bör identifiera och ta bort alla dubblettkomponenter, vilket beskrivs i [Övervaka dataordlistans hälsa](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**] nedrullningsbara fält. Innan du strukturerar de komponenter som användarna ser ska du först använda **Visa alla** för att säkerställa att du ser komponenter som inte delas med dig och som kan ha lagts till av en annan administratör.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBS!** För närvarande är **Liknar** -avsnittet innehåller bara komponenter som du skapar och inte de som tillhandahålls av Adobe. Komponenter som tillhandahålls av Adobe kommer att läggas till i en framtida version.</p> |
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
