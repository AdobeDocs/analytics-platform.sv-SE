---
title: Användarinställningar
description: Lär dig hur du anger allmänna inställningar och projektinställningar för användare.
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: 518bebc18611136873fce5c23dd7041afafe1220
workflow-type: tm+mt
source-wordcount: '3889'
ht-degree: 0%

---

# Användarinställningar

Du kan hantera användarinställningar och -inställningar för Analysis Workspace och relaterade komponenter för alla nya projekt eller paneler som du skapar. Befintliga projekt och paneler påverkas inte.

## Redigera inställningar

Du kan uppdatera dina inställningar på följande sätt:

- Välj ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Edit preferences]** i Workspace huvudgränssnitt.
- Välj **[!UICONTROL Project]** > **[!UICONTROL User preferences]** på menyn när du arbetar i ett Workspace-projekt.
- Välj **[!UICONTROL Components]** > **[!UICONTROL Preferences]** på den övre menyraden i Customer Journey Analytics (endast tillgängligt för produktadministratörer).

## Konfigurera inställningar

Du kan konfigurera följande inställningar:

### Allmänna inställningar

Allmänna inställningar gäller för din Customer Journey Analytics-upplevelse i webbläsaren. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

| Inställningar | Alternativ |
| --- | --- |
| **[!UICONTROL Landing page]** | Välj vilken sida som ska visas som standardsida när du öppnar Customer Journey Analytics: <ul><li>Projektlista (standard)</li><li>Tomt projekt</li><li>Guidad analys av tomma trender</li><li>Specifikt projekt, valt från en lista</li></ul> |
| **[!UICONTROL Tips]** | Visar tips i en blå ruta längst ned till höger i Analysis Workspace. <p>Det här alternativet är aktiverat som standard.</p> |
| **[!UICONTROL Components displayed in left panel groups]** | Välj hur många av varje komponentgrupp som ska visas på komponentmenyn i den vänstra panelen. <p>Om du väljer 0 för en komponentgrupp är komponentgruppen inte längre tillgänglig från den vänstra panelen.</p><p>Som standard visas fem komponenter för var och en av följande komponentgrupper:</p> <ul><li>Mått</li><li>Mätvärden</li><li>Segment</li><li>Datumintervall</li></ul> <p>Mer information om komponenter i Analysis Workspace finns i [Komponentöversikt](/help/components/overview.md).</p> |

### IMS-organisationsinställningar {#ims-organization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Tillåt endast delning med Workspace-användare"
>abstract="När alternativet **[!UICONTROL Share with anyone]** är aktiverat är det inte längre tillgängligt för användare när de delar ett Analysis Workspace-projekt. Personer som tidigare fått åtkomst till ett projekt via det här delningsalternativet har inte längre åtkomst till projektet."

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Kräv Experience Cloud-autentisering"
>abstract="När det här alternativet är aktiverat måste personer som får åtkomst till ett projekt från alternativet **[!UICONTROL Share with anyone]** i Analysis Workspace autentisera med sina Experience Cloud-autentiseringsuppgifter."

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="Tillåt kommentarer i projekt"
>abstract="När det här alternativet är aktiverat finns det ett kommentarsområde till höger om varje projekt i Analysis Workspace."

<!-- markdownlint-enable MD034 -->

Du kan uppdatera företagsinställningarna som gäller för alla användare och projekt i organisationen. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Fliken Mallar** | | |
|  | Dölj fliken Mallar | Döljer fliken Mallar för alla användare i organisationen. |
| **Projektdelning** | | |
| | Tillåt endast delning med Workspace-användare | När det här alternativet är aktiverat kan användare i organisationen inte se alternativet **[!UICONTROL Share with anyone]** på menyn **[!UICONTROL Share]**. Det innebär att användare inte kan dela projekt med personer som inte har ett Analysis Workspace-konto i organisationen enligt beskrivningen i [Dela ett projekt med någon (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) i [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md).<br/>Det här alternativet är inaktiverat som standard för alla organisationer (vilket innebär att användare kan dela projekt med personer utanför organisationen) förutom för kunder som har licensierat vårdsköld. <p>Tänk på följande när du aktiverar eller inaktiverar det här alternativet:<ul><li>När du aktiverar det här alternativet kan personer som tidigare fått åtkomst till ett projekt via delningsalternativet [!UICONTROL Share with anyone] inte längre få åtkomst till projektet.</li><li>Om det här alternativet är aktiverat (för att endast tillåta delning med Workspace-användare) och sedan inaktiveras (för att tillåta delning med vem som helst), kommer personer som tidigare fått åtkomst till ett projekt via delningsalternativet [!UICONTROL Share with anyone] inte automatiskt att få tillgång till projektet. I det här fallet måste användaren som delade projektet aktivera alternativet [!UICONTROL **Link är aktivt**] som är tillgängligt när ett projekt delas med någon **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]**), vilket beskrivs i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) i [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md).</li><li>**För kunder som licensierar hälsovård:** Det här alternativet är aktiverat som standard och kan inte inaktiveras. Innan du kan inaktivera det här alternativet så att användare kan använda delningsalternativet [!UICONTROL Share with anyone] måste du först lägga till behörigheten [!UICONTROL Share project links with anyone] (som finns under [!UICONTROL Reporting Tools]) i Adobe Admin Console. När behörigheten har lagts till kan du inaktivera det här alternativet och sedan godkänna det juridiska meddelandet. Mer information om hur du lägger till en behörighet i Admin Console finns i [Hantera produktbehörigheter i Admin Console](https://helpx.adobe.com/se/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Kräv Experience Cloud-autentisering | När det här alternativet är aktiverat måste personer som får åtkomst till ett projekt från alternativet **[!UICONTROL Share with anyone]** i Analysis Workspace autentisera med sina Experience Cloud-autentiseringsuppgifter.<p>När det här alternativet är aktiverat aktiveras alternativet [!UICONTROL Share with anyone] i delningsdialogrutan när en användare delar ett projekt med delningsalternativet [!UICONTROL Require Experience Cloud authentication] och det kan inte inaktiveras av den användare som delar projektet. Mer information om hur användare kan dela projekt med vem som helst finns i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) i [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md). <p> <p>Tänk på följande när du aktiverar det här alternativet: <ul><li>När du aktiverar det här alternativet inaktiveras alla projekt som tidigare delats med delningsalternativet [!UICONTROL Share with anyone] och som inte har alternativet [!UICONTROL Require Experience Cloud authentication] aktiverat.<p>Om det här alternativet är aktiverat (för att kräva Experience Cloud-autentisering) och sedan inaktiverat (för att tillåta alla med länken att komma åt projektet), kommer personer som tidigare fått åtkomst till ett projekt via delningsalternativet [!UICONTROL Share with anyone] inte automatiskt att återfå sin åtkomst till projektet. I det här fallet måste användaren som delade projektet aktivera alternativet [!UICONTROL Link is active] som är tillgängligt när ett projekt delas med någon **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]** > **[!UICONTROL Link is active]**), vilket beskrivs i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) i [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md).</li><li>Det här alternativet är bara tillgängligt om enkel inloggning har implementerats i din organisation. Mer information om hur systemadministratörer kan aktivera enkel inloggning för din organisation finns i [Konfigurera identitet och enkel inloggning](https://helpx.adobe.com/se/enterprise/using/set-up-identity.html).</p><p>Om enkel inloggning har konfigurerats för din organisation kontrollerar du om någon typ av autokontoskapande har implementerats i konsolen. Vanligtvis konfigurerar en systemadministratör detta enligt beskrivningen i [Aktivera automatiskt skapande av konto](https://helpx.adobe.com/se/enterprise/using/automatic-account-creation.html).</li><li>Om din organisation licensierar hälso- och sjukvårdssköld är det här alternativet aktiverat som standard och kan inte inaktiveras.</li></ul> |
| Projektkommentarer | Tillåt kommentarer i projekt | När det här alternativet är aktiverat finns det ett kommentarsområde till höger om varje projekt i Analysis Workspace. <p>Projektägare kan inaktivera kommentarområdet för ett visst projekt, vilket beskrivs i [Skapa projekt](/help/analysis-workspace/build-workspace-project/create-projects.md).</p> <p>Mer information om hur du kommenterar i Analysis Workspace-projekt finns i [Lägga till och hantera kommentarer i projekt](/help/analysis-workspace/build-workspace-project/comment-projects.md).</p> |

{style="table-layout:auto"}

### Inställningar för projekt och analys {#project-and-analysis-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="Kategoriserad palett"
>abstract="Gäller många visualiseringar i Analysis Workspace och guidad analys. Varje färg representerar ett tydligt kategoriserat värde."

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="Förvrängningspalett"
>abstract="Används för kohorttabellen i Analysis Workspace och för guidad analys av användartillväxt. Den här paletten har en numerisk betydelse med två extremvärden och en baslinje i mitten."

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="Sekventiell palett"
>abstract="Används för den guidade analysen av frekvenstrender (staplade fält). Den här paletten har en numerisk innebörd från ljust till mörkt."

Du kan anpassa de här inställningarna för alla nya Analysis Workspace-projekt, nya Analysis Workspace-paneler och nya guidade analyser. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan även anpassas för enskilda projekt i Analysis Workspace, vilket beskrivs i [Projektöversikt](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Visning** | | |
|  | [Visa densitet](/help/analysis-workspace/build-workspace-project/view-density.md) | Välj hur mycket innehåll som ska visas på skärmen genom att minska den lodräta utfyllnaden för den vänstra panelen, frihandstabeller och kohorttabeller. <ul><li>Kompakt</li><li>Bekväm</li><li>Utökad (standard)</li></ul> |
| | [Färgpaletten](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Välj de visualiseringsfärgpaletter som används i Analysis Workspace och guidad analys. <ul><li> Kategoripalett: Används för många visualiseringar i Analysis Workspace och guidad analys. Varje färg representerar ett tydligt kategoriserat värde. Välj mellan alternativ som tillhandahålls av Adobe eller ange en anpassad palett som definieras av kommaavgränsade hexvärden.</li><li> Olika paletter: Används för tabellen Kohort i Analysis Workspace och vägledd analys av användartillväxt. Den här paletten har en numerisk betydelse med två extremvärden och en baslinje i mitten.<li> Sekventiell palett: Används för den guidade analysen av frekvenstrender (staplade fält). Den här paletten har en numerisk innebörd från ljust till mörkt.</li></ul> |
| **Data** | | |
|  | [Datavy](/help/analysis-workspace/c-panels/panels.md#data-view) | Välj de data där tabeller och visualiseringar hämtar data. <ul><li>Senaste (standard)</li><li>Specifik datavy vald från en lista</li></ul> |
|  | [Kalender](/help/analysis-workspace/c-panels/panels.md#calendar) | Välj i en lista över: <ul><li>Intervall som tillhandahålls av Adobe (standard är denna månad)</li><li>Du kan aktivera [!UICONTROL Make date range components relative to panel calendar by default].</li></ul> |
|  | [Paneltyp](/help/analysis-workspace/c-panels/panels.md#panel-types) | <ul><li>Frihandsfigur (standard)</li><li>Tom</li><li>Snabba insikter</li></ul> |
|  | Instansinventering | Aktivera [!UICONTROL Count repeat instances] om du vill ange om upprepade instanser ska räknas i rapporter. När du t.ex. aktiverar det här alternativet behandlas flera på varandra följande sidvyer som flera sidvyer. När det här alternativet är inaktiverat, räknas flera på varandra följande sidvyer till samma sida som en enda sidvy. <p>**Obs!** Den här inställningen påverkar bara vissa mått (till exempel sessioner) och den gäller inte för visualiseringar i flöde och utfall.</p> |
|  | Nummerformat | <ul><li>1 000,00 (standard)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV-avgränsningstecken | <ul><li>Komma (standard)</li><li>Semikolon</li><li>Colon</li><li>Pipe</li><li>Period</li><li>Blanksteg</li><li>Tabb</li></ul> |
|  | Visa anteckningar | Välj om anteckningar ska visas i dina projekt. Mer information om anteckningar finns i [Översikt över anteckningar](/help/components/annotations/overview.md). |


### Inställningar för frihandstabell {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="Visa avvikelser"
>abstract="Om du väljer **[!UICONTROL Show anomalies]** körs avvikelseidentifiering automatiskt på den första metriska kolumnen som läggs till i en tidsserievisualisering av frihandstabell."

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="Visa prognos"
>abstract="Om du väljer **[!UICONTROL Show forecast]** prognostiseras automatiskt den första måttkolumnen som läggs till i en tidsserie visualisering av friformstabell."


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="Standardtabellmått"
>abstract="Välj standardmåttet som ska användas för frihandstabeller. Om den markerade datavyn inte innehåller det valda standardmåttet växlar tabellen automatiskt till ett annat primärt mått."


Du kan anpassa inställningarna för frihandstabeller för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan även anpassas för enskilda tabeller.

Markera de länkade avsnittsrubrikerna om du vill ha mer information och kontext om de tillgängliga inställningarna.

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Tabell** | | |
| | Tabelltyp | <ul><li>Frihandsfigur</li><li>Table builder</li></ul> |
| | Standardtabellmått | <ul><li>Händelser</li><li>Sessioner</li><li>Folk</li></ul> |
| | Standardregisterdimension | Välj mellan Minute, Timme, Dag, Vecka, Månad, Kvartal eller År. |
| | Justera datum | Välj det här alternativet om du vill justera datum från varje kolumn så att alla börjar på samma rad. |
| **[Kolumn](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Radbryt rubriktext | Gör att du kan radbryta rubriktexten i frihandstabeller så att rubrikerna blir mer läsbara och tabellerna mer delbara. Detta är användbart för .pdf-återgivning och för mått med långa namn. Aktiverat som standard. |
| | Visa summor | Det här totalnumret är vanligtvis lika med eller en delmängd av [!UICONTROL Grand Total]. Det återspeglar alla tabellsegment som används i frihandstabellen, inklusive alternativet [!UICONTROL Include None]. |
| | Visa totalsummor | Det här totala antalet representerar alla händelser som har samlats in och kallas ibland *datavysumma*. När ett segment används antingen på panelnivå eller i friformstabellen justeras det totala värdet så att alla händelser som matchar segmentvillkoren återspeglas. Summan stöds inte för tabeller eller uppdelningar med [statiska rader](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Visa miniatyrdiagram | Visa eller dölj linjediagram längst ned i diagrammet. När teckenförklaringen är dold ändras den inte längre till att referera till raderna visuellt. |
| | Nummer | Avgör om en cell visar/döljer det numeriska värdet för måttet. Om måttet till exempel är Sidvyer är det numeriska värdet antalet sidvyer för radobjektet. |
| | Procent | Avgör om en cell visar/döljer procentvärdet för måttet. Om måttet till exempel är sidvyer är procentvärdet antalet sidvyer för radobjektet delat med de totala sidvyerna för kolumnen.  Obs! Du kan visa procentvärden som är större än 100 % för att vara mer exakt. Du kan också flytta den övre gränsen till 1 000 % för att försäkra dig om att kolumner kan växa i för stora bredder. |
| | Visa avvikelser <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Avgör om avvikelseidentifiering körs på värdena i den här kolumnen. |
| | Visa prognos | Avgör om prognosvärden visas automatiskt för den första måttkolumnen i en friformstabell för tidsserier som du skapar. |
| | Tolka noll som inget värde | För celler med värdet 0 anger om en 0-cell eller en tom cell ska visas. Det här är användbart när du tittar på data för varje dag i en månad, och vissa dagar har inte inträffat än.  I stället för att visa 0 för framtida datum kan tomma celler visas i stället. Diagram följer även den här inställningen (i kundvagnen visas t.ex. inte en linje eller en stapel med 0 värden när den här inställningen är markerad). |
| | Bakgrund | Anger om en cell visar/döljer all cellformatering, inklusive stapeldiagrammet och villkorsstyrd formatering <ul><li>Stolpdiagram</li> Visar ett vågrätt stolpdiagram som representerar cellens värde i förhållande till totalvärdet för kolumnen. <li>Villkorsstyrd formatering</li>Mer information om villkorlig formatering finns i Villkorsstyrd formatering i [Kolumninställningar](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Cellförhandsgranskning | Visar en förhandsvisning av hur varje cell visas med de valda formateringsalternativen. |
| **[Rad](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Uppdelning efter position | Välj det här alternativet om du vill att detaljerna ska ligga kvar vid objektets position i stället för själva objektet. Mer information om uppdelningar finns i [Dela upp dimensioner](/help/components/dimensions/t-breakdown-fa.md). |
| | Procentberäkning | <ul><li>Kolumn</li><li>Rad</li></ul> |
| | Kolumnsummor (endast statiska rader) | <ul><li>Visa summan av rader: Visar summan av enskilda radobjekt </li><li>Visa totalsumma: visar den borttagna dubblettsumman av rader.</li></ul> |

### Visualiseringsinställningar {#visalization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultflowcontainer"
>title="Standardbehållare"
>abstract="Välj standardbehållaren som ska användas för [!UICONTROL Flow]-visualiseringar. Om den markerade datavyn inte innehåller den valda standardbehållaren växlar visualiseringen [!UICONTROL Flow] automatiskt till en annan primär behållare."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultfalloutcontainer"
>title="Standardbehållare"
>abstract="Välj standardbehållaren som ska användas för [!UICONTROL Fallout]-visualiseringar. Om den markerade datavyn inte innehåller den valda standardbehållaren växlar visualiseringen [!UICONTROL Fallout] automatiskt till en annan primär behållare."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulthistogramcountingmethod"
>title="Standardmetod för inventering"
>abstract="Välj den standardräkningsmetod som ska användas för [!UICONTROL Histogram]-visualiseringar. Om den valda datavyn inte innehåller den valda standardmetoden för räkning, växlar visualiseringen [!UICONTROL Histogram] automatiskt till en annan primär metod för att räkna."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultjourneycanvascontainer"
>title="Standardbehållare"
>abstract="Välj standardbehållaren som ska användas för [!UICONTROL Journey canvas]-visualiseringar. Om den markerade datavyn inte innehåller den valda standardbehållaren växlar visualiseringen [!UICONTROL Journey canvas] automatiskt till en annan primär behållare."


Du kan uppdatera visualiseringsinställningarna för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan också anpassas för individuella visualiseringar.

Markera de länkade avsnittsrubrikerna om du vill ha mer information och kontext om de tillgängliga inställningarna.

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Allmänna standardinställningar** | | |
| | Procenttal | Visar värden i procent för alla visualiseringar. |
| | Förklaring synlig | Gör att du kan dölja förklaringstexten för alla visualiseringar. |
| | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln för alla visualiseringar. Den här inställningen kan vara användbar om du har en stor datauppsättning. |
| | Visa dubbelaxel (om tillämpligt) | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). Den här inställningen är användbar när plottade mätvärden har mycket olika förstoringsgrader. |
| | Normalisering (om tillämpligt) | Tvingar måtten att ha samma proportioner. Den här inställningen är användbar när plottade mätvärden har mycket olika förstoringsgrader. |
| | Fästpunkt Y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll, uppdateras y-axelns nederkant till ICKE-ZERO. Om du markerar den här rutan tvingas y-axeln till noll (och ritar om diagrammet). |
| | Ankaravvikelser för att skala Y-axeln | Y-axeln skalas med avvikande värden. |
| **[Linjediagram](/help/analysis-workspace/visualizations/line.md)** | | |
| | Procenttal | Visar värden i procent för linjevisualiseringar. |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för linjevisualiseringen. |
| | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i linjevisualiseringen. Den här inställningen kan vara användbar om du har en stor datauppsättning. |
| | Visa dubbelaxel (om tillämpligt) | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). Den här inställningen är användbar när plottade mätvärden har mycket olika förstoringsgrader. |
| | Normalisering (om tillämpligt) | Tvingar måtten att ha samma proportioner. Den här inställningen är användbar när plottade mätvärden har mycket olika förstoringsgrader. |
| | Visa x-axel | Visar x-axeln i linjediagrammet. |
| | Visa y-axel | Visar y-axeln i linjediagrammet. |
| | Fästpunkt Y-axel | Om alla värden som ritas upp i diagrammet ligger betydligt över noll återges standardvärdet för diagrammet längst ned på y-axeln, NON-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |
| | Tillåt avvikelser att skala Y-axeln | Om du har flera mätvärden i ett diagram måste du hovra över varje avvikelse för att se konfidensintervallet för det måttet. För att göra visualiseringen mer läsbar skalas inte y-axeln automatiskt i konfidensintervallet för avvikelseidentifiering. Med den här inställningen kan konfidensintervallet skalförändra visualiseringen. <p>Mer information finns i [Visa avvikelser i Analysis Workspace](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| | Tillåt prognos att skala Y-axeln | Om du har prognosvärden som ligger utanför de övre och nedre gränserna för de historiska värdena skalförändras inte dessa prognosticerade värden automatiskt med y-axeln. När alternativet är aktiverat skalförändras y-axeln korrekt för de prognostiserade värdena. |
| | Visa min | Täck över en minimivärdetikett för att snabbt markera värdena i ett mätresultat. Obs! Minsta värden härleds från synliga datapunkter i visualiseringen, inte från hela uppsättningen värden inom en dimension. |
| | Visa max | lägg över en maxvärdetikett för att snabbt markera topparna i ett mätresultat. Obs! De högsta värdena härleds från de synliga datapunkterna i visualiseringen, inte från hela uppsättningen värden inom en dimension. |
| | Visa trendlinje | Visa en regression eller en glidande medeltrendlinje i linjeserien. Trendlinjer hjälper till att beskriva ett tydligare mönster i data. |
| **[Kohort](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>Container | Välj önskad behållare för kohortanalys vid en kontobaserad [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}-anslutning. <p>Följande alternativ är tillgängliga:</p> <ul><li>Globala konton [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Konton [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Buying Groups [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Affärsmöjligheter [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Person</li></ul> |
| | Kornighet | För trendvisualiseringar kan du ändra tidgranulariteten (dag, vecka, månad, kvartal eller år). Den här ändringen gäller även för datakälltabellen. |
| | Visa endast procent | Tar bort talvärdet och visar bara procentvärdet. |
| | Avrunda procent till närmaste heltal | Avrundar procentvärdet till närmaste heltal i stället för att visa decimalvärdet. |
| | Visa genomsnittlig procentrad | Infogar en ny rad högst upp i tabellen och lägger sedan till medelvärdet för värdena i varje kolumn. |
| **[Kombinationsdiagram](/help/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Visa X-axel | Visar x-axeln i kombinationsdiagrammet. |
| | Visa Y-axel | Visar y-axeln i kombinationsdiagrammet. |
| | Visa streckade linjer | Visa streckade linjer i kombinationsdiagram. |
| **[Sammanfattning av nyckelmått](/help/analysis-workspace/visualizations/key-metric.md)** | | |
| | Visningstyp för sammanfattning | <ul><li>Betonar procentuell ändring</li><li>Betonar talvärde</li></ul> |
| | Visa miniatyrbilder | Visa eller dölj linjediagram längst ned i diagrammet. När teckenförklaringen är dold ändras den inte längre till att referera till raderna visuellt. |
| | Visa max och min för miniatyrbilder | Visa lägsta och högsta värden i primära och jämförande raddiagram. |
| | Visa jämförelse | Visa jämförelsedata. När det är dolt döljs både jämförelsetabellen och de sammanfattande ändringsobjekten. |
| | Alternativ för talvärde | I avsnittet [!UICONTROL **Sammanfattning av nyckelmått**] <ul><li>Visa procentuell ändring</li><li>Visa rådifferens</li>Rådifferens mellan det totala värdet för måttet i det primära datumintervallet och det sekundära datumintervallet</ul> |
| **[Utfall](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Behållare | Välj den behållare som ska analyseras. Den föredragna behållaren hjälper dig att förstå kontointeraktionen på olika B2B-behållarnivåer [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, personengagemang på personnivå (mellan sessioner) eller begränsa analysen till en enda session. <p>Följande alternativ är tillgängliga:</p> <ul><li>Globala konton [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Konton [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Buying Groups [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Affärsmöjligheter [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Session</li><li>Person</li></ul> |
| **[Flöde](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Behållare | Välj önskad behållare att analysera. Den föredragna behållaren hjälper dig att förstå kontointeraktionen på olika B2B-behållarnivåer [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, personengagemang på personnivå (mellan sessioner) eller begränsa analysen till en enda session. <p>Följande alternativ är tillgängliga:</p> <ul><li>Globala konton [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Konton [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Buying Groups [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Affärsmöjligheter [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Session</li><li>Person</li></ul> |
| | Radbryt etiketter | Etiketterna på Flow-elementen trunkeras normalt för att spara skärmutrymme, men du kan göra hela etiketten synlig genom att markera den här rutan. Standard = avmarkerat. |
| | Inkludera upprepade förekomster | Flödesvisualiseringar baseras på instanser av en dimension. Den här inställningen ger dig möjlighet att inkludera eller exkludera upprepade instanser, till exempel Sidomladdning. Det går dock inte att ta bort upprepningar från Flow-visualiseringar som innehåller flervärdesdimensioner, som listVars, listProps, s.product, merchandising eVars osv. Standard = avmarkerat. |
| | Visa verktygstips | Avgör om verktygstips, som innehåller noddata, ska visas när du hovrar över enskilda noder i en flödesvisualisering. |
| | Antal kolumner | Anger hur många kolumner du vill ha i flödesdiagrammet. |
| | Objekt utökade per kolumn | Hur många objekt du vill ha i varje kolumn. |
| **[Researbetsyta](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)** | | |
| | Behållare | Välj den behållare som ska analyseras. Den föredragna behållaren hjälper dig att förstå kontointeraktionen på olika B2B-behållarnivåer [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, personengagemang på personnivå (mellan sessioner) eller begränsa analysen till en enda session. <p>Följande alternativ är tillgängliga:</p> <ul><li>Globala konton [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Konton [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Buying Groups [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Affärsmöjligheter [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Session</li><li>Person</li></ul> |
| **Skiktade diagram** | | |
| | 100 % staplad | Den här inställningen för staplade ytor, staplade staplade staplar eller vågräta staplade visualiseringar gör att diagrammet blir en&quot;100 % staplade&quot; visualisering. <p>Mer information finns i [Stapel och stapel](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Histogram](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | Antal fickor | Välj antalet datumintervall (bucket) i visualiseringen. Det högsta antalet bucklor är 50. <p>Mer information finns i [Histogram](/help/analysis-workspace/visualizations/histogram.md).</p> |
| | Inventeringsmetod | Välj bland följande alternativ: <ul><li>Träff</li><li>Session</li><li>Person</li></ul> <p>Om du till exempel använder sidvyer kan du välja sidvyer per person, sidvyer för besök eller sidvyer per händelse. För Träff används&quot;Förekomster&quot; som y-axelmått i en friformstabell.</p> |
| **[Sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Värde | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Procentuell ändring</li><li>Rådifferens</li></ul> |
| | Procenttal | Visar värden i procent för visualiseringar av sammanfattningsändringar. |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för visualiseringen av Sammanfattningsändring. |
| **[Sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Procenttal | Visar värden i procent för visualiseringar av sammanfattningsnummer. |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för visualisering av sammanfattningsnummer. |
| | Sammanfattningsvärde per | Välj mellan Max, Min, Medel, Median och Summa. |
| | Förkortningsvärde | I avsnittet **[!UICONTROL Summary Number]** |
| **[Treemap-diagram](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | Procenttal | Visar värden i procent för Treemap-visualiseringar. |
| | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i Treemaps visualisering. Den här inställningen kan vara användbar om du har en stor datauppsättning. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** | | |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för Vennvisualiseringen. |
| **[Spridning](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Procenttal | Visar värden i procent för Spridningsvisualiseringar. |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för Spridningsvisualiseringen. |
| | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i Spridningsvisualiseringen.  Den här inställningen kan vara användbar om du har en stor datauppsättning. |
| | Fästpunkt y-axel vid noll | Om alla värden som ritas upp i diagrammet ligger betydligt över noll återges standardvärdet för diagrammet längst ned på y-axeln, NON-ZERO. Om du markerar den här rutan tvingas y-axeln till noll (och ritar om diagrammet). |

## Återställ standardinställningar

Du kan återställa alla dina användarinställningar till standardinställningarna. Den här inställningen påverkar inte administratörsinställningarna på fliken Företag.

Det går inte att ångra den här åtgärden.

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] **>** [!UICONTROL **Inställningar**] på den översta menyn. Eller välj **[!UICONTROL Project]** > **[!UICONTROL User settings]** på Workspace-menyn.

1. Välj **[!UICONTROL Restore defaults]** i det övre högra hörnet.

1. Välj **[!UICONTROL Restore defaults]** i **[!UICONTROL Restore system default settings]**.

## [!UICONTROL Dark theme]

Om du föredrar en mörk bakgrund för ditt Customer Journey Analytics-användargränssnitt kan du växla till [!UICONTROL Dark theme].

1. Välj Experience Cloud-ikonen längst upp till höger.

   ![mörkt-tema](assets/dark-theme.png)

1. Aktivera **[!UICONTROL Dark theme]**.

