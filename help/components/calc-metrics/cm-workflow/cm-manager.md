---
description: Med hanteraren för beräknade mätvärden kan du dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.
title: Beräknad måtthanterare
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 0%

---

# Hantera beräknade värden

Du kan dela, filtrera, tagga, godkänna, byta namn på, kopiera, ta bort, exportera beräknade värden och markera beräknade värden som favoriter från ett centralt [!UICONTROL Calculated metrics]-hanteringsgränssnitt. Så här hanterar du beräknade värden:


* Välj **[!UICONTROL Components]** i huvudgränssnittet och välj sedan **[!UICONTROL Calculated metrics]**.


## Beräknat måttansvarig

Den beräknade metadatahanteraren har följande gränssnittselement:


![Gränssnitt för filter](assets/calculated-metrics-manager.png)

### Filterlista

Filterlistan ➊ visar alla beräknade värden som du äger eller som har delats med dig. Listan innehåller följande kolumner:

<!-- I think this table incorrectly talks about quick calculated metrics -->

| Kolumn | Beskrivning |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Välj om du vill prioritera ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) ett beräknat mått. Se [Markera beräknat mått som favorit](/help/components/segments/seg-favorite.md) |
| **[!UICONTROL Title and description]** | Om du vill redigera det beräknade måttet väljer du titellänken, som öppnar verktyget [Beräknade mått](cm-build-metrics.md). Ett delat beräknat mått har indikerats med ![Dela](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | De datavyer som det här beräknade måttet gäller för. |
| **[!UICONTROL Owner]** | Ägare till det beräknade måttet. Som användare ser du bara de anteckningar du äger eller de anteckningar som delas med dig. |
| **[!UICONTROL Tags]** | Visar taggarna för det här beräknade måttet. |
| **[!UICONTROL Shared with]** | Visar hur många individer eller grupper du har delat det beräknade måttet med. Välj det här alternativet om du vill öppna dialogrutan **[!UICONTROL Share Calculated metric]**. Mer information finns i [Dela beräknade värden](cm-sharing.md). |
| **[!UICONTROL Date modified]** | Det datum och den tidpunkt då det beräknade måttet senast ändrades. |
| **[!UICONTROL Used in]** | Visar var beräknade mätvärden används och hur många gånger de används i varje område. <p>Om det beräknade måttet till exempel används i 40 projekt och 2 varningar visas värdet för den här kolumnen som [!UICONTROL **42 komponenter**]. <p>Välj värdet i den här kolumnen för att se hur de beräknade mätvärdena används (till exempel [!UICONTROL **Projekt (40)**], [!UICONTROL **Mobila styrkort (2)**]). Dessutom kan du visa en lista med objekt där de beräknade mätvärdena används. Se till exempel en lista över projekt där de används och välj länken [!UICONTROL **Projekt (40)**].</p><p>I vart och ett av följande områden visas antalet instanser av beräknade mätvärden som används i det området:</p> <ul><li>[!UICONTROL **Projekt**]<p>Innehåller beräknade mått som [har skapats i den beräknade metriska byggaren](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) och som är tillgängliga för alla projekt.</p></li><li>[!UICONTROL **Ad hoc-komponenter**]<p>Innehåller beräknade mått som [har skapats som snabbberäknade mått](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) och som endast är tillgängliga i ett enskilt projekt.</p></li><li>[!UICONTROL **Schemalagda projekt**]</li><li>[!UICONTROL **Mobil styrkort**]</li><li>[!UICONTROL **Anteckningar**]</li><li>[!UICONTROL **Report Builder**]<p>Om du väljer det här alternativet hämtas en CSV-fil med följande datakolumner:</p><ul><li>Report Builder Name</li><li>Senast använd</li><li>Användar-ID för senast använda IMS</li><li>Användarnamn med senaste åtkomst</li></ul></li></ul><p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen är endast tillgänglig för systemadministratörer.</li><li>Kolumnen [!UICONTROL **Används i**] visas inte som standard. Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att konfigurera visningen av den här kolumnen.</li><li>Denna information inkluderar inte användning från API eller Data Warehouse.</li><li>Om det inte finns några data i den här kolumnen för en viss komponent, men den har datumet [!UICONTROL **Senast använd**], kan komponenten ha använts i en analys utan att sparas.</li><li>Användningsinformation finns tillgänglig från och med september 2023.</li></ul><p>Du kan använda [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation.</p> |
| **[!UICONTROL Last Used]** | När det beräknade måttet senast användes. |

{style="table-layout:auto"}

Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att ange vilka kolumner du vill visa.

### Åtgärdsfält

Du kan använda åtgärdsfältet ➋ för att utföra åtgärder på filter. Åtgärdsfältet innehåller följande åtgärder:

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Lägg till ytterligare beräknade mått med hjälp av [verktyget Beräknade mätvärden](cm-build-metrics.md). |
| ![Sök](/help/assets/icons/Search.svg) | [!UICONTROL *Sök efter titel*] | Om inget beräknat mätvärde är markerat i listan söker du efter filter med det här sökfältet. |
| ![Etikett](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Tagga de valda beräknade måtten. I dialogrutan **[!UICONTROL Tag Calculated metric]** markerar eller avmarkerar du taggarna för det valda beräknade måttet. Välj **[!UICONTROL Save]** om du vill spara taggarna för de valda beräknade måtten. Mer information finns i [Tagga beräknade värden](cm-tagging.md). |
| ![Dela](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Share]** | Dela de valda beräknade måtten. I dialogrutan **[!UICONTROL Share Calculated metrics]** kan du ![ söka ](/help/assets/icons/Search.svg) *söka efter enskilda personer eller grupper* eller välja **[!UICONTROL Organization]** eller **[!UICONTROL Groups]**. Välj **[!UICONTROL Save]** om du vill spara delningsinformation för de valda beräknade måtten. Mer information finns i [Dela beräknade värden](cm-sharing.md). |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de valda beräknade måtten. Du uppmanas att bekräfta åtgärden. |
| ![Redigera](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Byt namn på ett enskilt valt beräknat mått. När du väljer det här alternativet kan du byta namn på det beräknade mätvärdet. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** | Godkänn de valda beräknade mätvärdena. Se [Godkänn beräknade värden](cm-approving.md). |
| ![Kopiera](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Kopiera de valda beräknade måtten. Nya beräknade värden har skapats med samma namn och suffix `(Copy)` |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera de beräknade måtten till en `Calculated  metric List.csv`-fil. |

### Aktivt filterfält

Filterfältet ➌ visar de aktiva filter som tillämpas från filterpanelen till listan med beräknade mått (om sådana finns). Du kan snabbt ta bort ett filter med ![CrossSize75](/help/assets/icons/CrossSize75.svg). Om fler än ett filter har angetts kan du ta bort alla filter med **[!UICONTROL Remove all]**.

### Panelen Filter

Du kan filtrera listan med beräknade mått med den vänstra panelen ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** ➍. Filterpanelen visar typen av filter och antalet beräknade värden som följer det specifika filtret. Välj ![Filter](/help/assets/icons/Filter.svg) för att växla visningen av filterpanelen.

Mer information finns i [Filtrera listan med beräknade värden](cm-filter.md).


<!-- OLD CONTENT 

The Calculated metric manager shows you all the filters you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. This overview presents the user interface and the capabilities of the Calculated metric manager.

![Calculated metrics window showing available filters.](assets/calc-metric-manager.png)

## Access the Calculated metrics manager

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, to see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a segment), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->