---
title: Hantera filter
description: Lär dig hur du hanterar filter i Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---

# Hantera filter


Du kan [dela](filters-share.md), [filter](filters-filter.md), [tagg](filters-tag.md), [godkänna](filters-approve.md), byta namn på, [kopiera](filters-copy.md), ta bort, exportera filter och markera filter som [favorit](filters-favorite.md) från ett centralt [!UICONTROL Filters]-hanteringsgränssnitt. Så här hanterar du filter:

* Välj **[!UICONTROL Components]** i huvudgränssnittet och välj sedan **[!UICONTROL Filters]**.


>[!NOTE]
>
>Snabbfiltren som du skapar i ett visst Workspace-projekt visas inte i hanteraren för [!UICONTROL Filters], såvida du inte har gjort filtret tillgängligt för alla dina projekt.
>

## Filterhantering

Filterhanteraren har följande gränssnittselement:

![Gränssnitt för filter](assets/filters-manager.png)

### Filterlista

Filterlistan ➊ alla filter som du äger, de filter som har omfattats av alla dina projekt och de filter som har delats med dig. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Välj om du vill prioritera ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) ett filter. Se [Markera filter som favorit](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Title and description]** | Om du vill redigera filtret markerar du titellänken, som öppnar [filterverktyget](filter-builder.md). Ett delat filter anges med ![Dela](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | De datavyer som det här filtret gäller för. |
| **[!UICONTROL Owner]** | Filtrets ägare. Som användare ser du bara de filter som du äger eller de anteckningar som delas med dig. |
| **[!UICONTROL Tags]** | Taggarna för detta filter. |
| **[!UICONTROL Shared with]** | Hur många individer eller grupper som du har delat filtret med. Välj det här alternativet om du vill öppna dialogrutan **[!UICONTROL Share Component]**. Mer information finns i [Dela filter](filters-share.md). |
| **[!UICONTROL Date modified]** | Datum och tid då filtret senast ändrades. |
| **[!UICONTROL Used in]** | Visa var filter används och hur många gånger de används i varje område. <p>Om filtret till exempel används i 40 projekt och 2 varningar visas värdet för den här kolumnen som [!UICONTROL **42 komponenter**].</p> <p>Välj värdet i den här kolumnen för att se hur de olika filtren används (till exempel [!UICONTROL **Projekt (40)**], [!UICONTROL **Mobila styrkort (2)**]). Dessutom kan du visa en lista med objekt där filtren används. Se till exempel en lista över projekt där de används och välj länken [!UICONTROL **Projekt (40)**].</p><p>I vart och ett av följande områden visas antalet förekomster av filter som används i det området:</p>  <ul><li>[!UICONTROL **Projekt**]<p>Innehåller filter som har [skapats i filterverktyget](/help/components/filters/filter-builder.md#) och som är tillgängliga för alla projekt.</p></li><li>[!UICONTROL **Ad hoc-komponenter**]<p>Innehåller filter som [har skapats som snabbfilter](/help/components/filters/quick-filters.md) och som endast är tillgängliga i ett enskilt projekt.</p></li><li>[!UICONTROL **Schemalagda projekt**]</li><li>[!UICONTROL **Mobil styrkort**]</li><li>[!UICONTROL **Anteckningar**]</li><li>[!UICONTROL **Beräknade värden**]</li><li>[!UICONTROL **Report Builder**]<p>Om du väljer det här alternativet hämtas en CSV-fil med följande datakolumner:</p><ul><li>Report Builder</li><li>Senast använd</li><li>Användar-ID för senast använda IMS</li><li>Användarnamn med senaste åtkomst</li></ul></li></ul><p>Den här informationen hjälper dig att avgöra om en komponent är värdefull för användare i organisationen, var komponenten används och om komponenten behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen är endast tillgänglig för systemadministratörer.</li><li>Kolumnen [!UICONTROL **Används i**] visas inte som standard. Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att konfigurera visningen av den här kolumnen.</li><li>Den här informationen inkluderar inte användning från API:t eller Datan Warehouse.</li><li>Om det inte finns några data i den här kolumnen för en viss komponent, men komponenten har datumet [!UICONTROL **Senast använd**] , kan komponenten ha använts i en analys utan att sparas.</li><li>Användningsinformation finns tillgänglig från och med september 2023.</li></ul><p>Du kan använda [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation.</p> |
| **[!UICONTROL Last Used]** | När filtret användes senast. |

{style="table-layout:auto"}

Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att ange vilka kolumner du vill visa.

### Åtgärdsfält

Du kan använda åtgärdsfältets ➋ för att utföra åtgärder på filter. Åtgärdsfältet innehåller följande åtgärder:

| Åtgärd | Beskrivning |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Lägg till ytterligare ett filter med [filterverktyget](filter-builder.md). |
| ![Sök](/help/assets/icons/Search.svg) [!UICONTROL *Sök efter titel*] | Om inget filter är markerat i listan söker du efter filter med det här sökfältet. |
| ![Etikett](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tagga de valda filtren. I dialogrutan **[!UICONTROL Tag Filter]** markerar eller avmarkerar du taggarna för de valda filtren. Välj **[!UICONTROL Save]** om du vill spara taggarna för de valda filtren. Mer information finns i [Taggfilter](/help/components/filters/filters-tag.md). |
| ![Dela](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Dela de valda filtren. I dialogrutan **[!UICONTROL Share Filter]** kan du ![ söka ](/help/assets/icons/Search.svg) *söka efter enskilda personer eller grupper* eller välja **[!UICONTROL Organization]** eller **[!UICONTROL Groups]**. Välj **[!UICONTROL Save]** om du vill spara delningsinformation för de valda filtren. Mer information finns i [Dela filter](filters-share.md). |
| ![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Ta bort de markerade filtren. Du uppmanas att bekräfta åtgärden. |
| ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Byt namn på ett enskilt markerat filter. När du har markerat det här alternativet kan du byta namn på filtret. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Godkänn de valda filtren. Mer information finns i [Godkänn filter](filters-approve.md). |
| ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** | Kopiera det markerade filtret. Nya filter skapas med samma namn och suffix `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Exportera filter till en `Filters List.csv`-fil. |

### Aktivt filterfält

➌ i filterfältet visas de aktiva filter som har använts från filterpanelen i listan med filter (om sådana finns). Du kan snabbt ta bort ett filter med ![CrossSize75](/help/assets/icons/CrossSize75.svg). Om fler än ett filter har angetts kan du ta bort alla filter med **[!UICONTROL Remove all]**.

### Panelen Filter

Du kan filtrera filterlistan med hjälp av den vänstra panelen ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** . Filterpanelen visar typen av filter och antalet filter som uppfyller det specifika filtret. Välj ![Filter](/help/assets/icons/Filter.svg) för att växla visningen av filterpanelen.

Mer information finns i [Filtrera listan med filter](filters-filter.md).
