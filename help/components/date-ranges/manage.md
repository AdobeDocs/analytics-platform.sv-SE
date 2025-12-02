---
title: Hantera datumintervall
description: Lär dig hantera datumintervall i Analysis Workspace.
feature: Calendar
exl-id: 694758c4-d740-4fd7-9fb0-3ff7f6b25a3d
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Hantera datumintervall


Du kan dela, filtrera, tagga, godkänna, kopiera, dela och ta bort datumintervall och markera datumintervall som favoriter från ett centralt [!UICONTROL Date ranges]-hanteringsgränssnitt. Så här hanterar du datumintervall:

* Välj **[!UICONTROL Components]** i huvudgränssnittet och välj sedan **[!UICONTROL Date ranges]**.


## Hanterare för datumintervall

Hanteraren för datumintervall har följande gränssnittselement:

![Gränssnitt för datumintervall](assets/date-ranges-manager.png)

### Datumintervalllista

I datumintervalllistan ➊ visas alla datumintervall. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
| --- | --- |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Välj om du vill prioritera ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) ett datumintervall. |
| **[!UICONTROL Title and description]** | Om du vill redigera titeln och beskrivningen markerar du titellänken, som öppnar [datumintervallsverktyget](/help/components/date-ranges/create.md#date-range-builder). |
| **[!UICONTROL Owner]** | Ägaren till datumintervallet. |
| **[!UICONTROL Tags]** | Taggarna för det här datumintervallet. |
| **[!UICONTROL Shared with]** | De personer eller grupper som du har delat datumintervallet med. Välj det här alternativet om du vill öppna dialogrutan **[!UICONTROL Share Date range]**. |
| **[!UICONTROL Date modified]** | Visar datum och tid då datumintervallet senast ändrades. |

{style="table-layout:auto"}

Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att ange vilka kolumner du vill visa.

### Åtgärdsfält

Du kan utföra åtgärder för datumintervall med åtgärdsfältet ➋. Åtgärdsfältet innehåller följande åtgärder:

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Lägg till ett annat datumintervall med hjälp av [datumintervallverktyget](create.md#date-range-builder). |
| ![Sök](/help/assets/icons/Search.svg) | [!UICONTROL *Sök efter titel*] | Om inget datumintervall är markerat i listan söker du efter datumintervall med det här sökfältet. |
| ![Etikett](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Tagga de markerade datumintervallen. I dialogrutan **[!UICONTROL Tag Date range]** markerar eller avmarkerar du taggarna för de markerade datumintervallen. Välj **[!UICONTROL Save]** om du vill spara taggarna för de valda datumintervallen. |
| ![Dela](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Share]** | Dela de markerade datumintervallen. I dialogrutan **[!UICONTROL Share Date range]** kan du ![&#x200B; söka &#x200B;](/help/assets/icons/Search.svg) *söka efter enskilda personer eller grupper* eller välja **[!UICONTROL Organization]** eller **[!UICONTROL Groups]**. Välj **[!UICONTROL Save]** om du vill spara delningsinformation för de valda datumintervallen. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de markerade datumintervallen. Du uppmanas att bekräfta åtgärden. |
| ![Redigera](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Byt namn på ett enstaka markerat datumintervall. När du har markerat det här alternativet kan du byta namn på datumintervallet. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** | Godkänn de valda datumintervallen. |
| ![Kopiera](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Kopiera de markerade datumintervallen. Nya datumintervall skapas med samma namn och suffix (Kopiera) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera de markerade datumintervallen till en `Date ranges List.csv`-fil. |

### Aktivt filterfält

Filterfältet ➌ visar de aktiva filtren (om sådana finns). Du kan snabbt ta bort ett filter med ![CrossSize75](/help/assets/icons/CrossSize75.svg). Om fler än ett filter anges använder du **[!UICONTROL Remove all]** för att ta bort alla filter.

### Panelen Filter

Du kan filtrera datumintervall med den **[!UICONTROL Filter]** vänstra panelen ➍. Filterpanelen visar typen av filter och antalet datumintervall som filtret gäller. Välj ![Filter](/help/assets/icons/Filter.svg) för att växla visningen av filterpanelen.

Så här filtrerar du filterlistan:

1. Välj ![Filter](/help/assets/icons/Filter.svg) för att öppna panelen Filter. Om du behöver mer utrymme för filterlistan kan du stänga panelen genom att välja ![Filter](/help/assets/icons/Filter.svg) en gång till.
1. Du kan filtrera datumintervallen med hjälp av någon av de tillgängliga [filteravsnitten](#filter-sections).

   >[!INFO]
   >
   >*Objekt* refererar till datumintervallobjekt som visas i listan [Datumintervall](#date-ranges-list).
   > 

#### Filtrera avsnitt

{{tagfiltersection}}
{{ownerfiltersection}}
{{otherfiltersfiltersection}}


Listan [Datumintervall](#date-ranges-list) uppdateras automatiskt baserat på din filterkonfiguration. Du kan se de konfigurerade filtren i det [aktiva filterfältet](#active-filter-bar).


## Redigera datumintervall

Du kan redigera ett datumintervall på två sätt:

* Använd ikonen [Komponentinformation](/help/components/use-components-in-workspace.md#component-info) i ett Workspace-projekt.

* Markera datumintervallets titel i listan [[!UICONTROL Date ranges]](#date-ranges-list).

Du använder [datumintervallverktyget](/help/components/date-ranges/create.md#date-range-builder) för att redigera datumintervallet.




Använd datumintervallhanteraren för att dela, byta namn på eller ta bort datumintervall. Så här når du datumhanteraren:

1. Logga in på [analytics.adobe.com](https://analytics.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
1. Navigera till [!UICONTROL Components] > [!UICONTROL Date Ranges].


<!--

## Interface

![Date Ranges with Example range highlighted.](../assets/date-range-ui.png)

The date range manager includes the following options:

* **Add**: Create a new date range. See [create a date range](create.md) for more information.
* **Search by title**: Search for a date range by title. Results are filtered based on text entered here.
* **Filter**: Filter date ranges using the left column. You can filter by custom tag, owner, created by you, your favorites, approved, or shared with you. You can also search for desired filters.
* **Favorite**: Click the ![star](../assets/star.png) icon next to a date range to add it to your favorites.
* **Customize columns**: Click the ![columns](../assets/columns.png) icon to show or hide columns in the date range manager.

Click the checkbox next to one or more date ranges for more options.

* **Tag**: Apply a tag to all selected date ranges. Tags help you organize date ranges, and let you filter them using the left column.
* **Share**: Share a date range to other Experience Cloud users. If you are a product administrator, you can also share to the entire organization or groups. Date ranges that are shared to other users in your organization include a ![shared](../assets/shared.png) icon next to the title.
* **Delete**: Permanently delete the selected date range(s).
* **Rename**: If a single date range is selected, you can change its title.
* **Approve**: If you are a product admin, you can add a stamp of approval to a date range. Approved date ranges inform users in your organization that they are 'official', differentiating them from date ranges created by other users in your organization. Approved date ranges include a ![approved](../assets/approved.png) icon next to the title.
* **Unapprove**: If you are a product admin and select a date range that is already approved, you can unapprove it.
* **Copy**: Create a copy of the selected date range(s). Copying date ranges appends `(Copy)` to the end of the title of the newly copied date range(s).
* **Export to CSV**: Exports all selected date ranges into a CSV file. Columns in the resulting CSV file include all visible columns in the date range manager.
-->