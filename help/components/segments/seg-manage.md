---
description: Lär dig hur du använder segmenthanteraren för att hantera segment, till exempel dela, filtrera, tagga, godkänna, kopiera, ta bort segment och markera segment som favoriter.
title: Hantera segment
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 0%

---

# Hantera segment


Du kan [dela](seg-share.md), [segment](seg-filter.md), [tagg](seg-tag.md), [godkänna](seg-approve.md), byta namn på, [kopiera](seg-copy.md), ta bort, exportera segment och markera segment som [favorit](seg-favorite.md) från ett centralt [!UICONTROL Segment]-hanteringsgränssnitt. Så här hanterar du segment:

* Välj **[!UICONTROL Components]** i huvudgränssnittet och välj sedan **[!UICONTROL Segments]**.


>[!NOTE]
>
>Snabbsegmenten som du skapar i ett visst Workspace-projekt visas inte i hanteraren för [!UICONTROL Segment], såvida du inte har gjort segmentet tillgängligt för alla dina projekt.
>

## Segmenthanterare

Segmenthanteraren har följande gränssnittselement:

![Segmentgränssnitt](assets/filters-manager.png)

### Segmentlista

Segmentlistan ➊ visar alla segment som du äger, de segment som har omfattats av alla dina projekt och de segment som har delats med dig. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Välj om du vill gynna ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) ett segment. Se [Markera segment som favorit](/help/components/segments/seg-favorite.md) |
| **[!UICONTROL Title and description]** | Om du vill redigera segmentet markerar du titellänken, som öppnar [segmentverktyget](seg-builder.md). Ett delat segment anges med ![Dela](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | De datavyer som det här segmentet gäller för. |
| **[!UICONTROL Owner]** | Segmentets ägare. Som användare ser du bara de segment som du äger eller de anteckningar som delas med dig. |
| **[!UICONTROL Tags]** | Taggarna för detta segment. |
| **[!UICONTROL Shared with]** | Hur många individer eller grupper du har delat segmentet med. Välj det här alternativet om du vill öppna dialogrutan **[!UICONTROL Share Component]**. Mer information finns i [Dela segment](seg-share.md). |
| **[!UICONTROL Date modified]** | Datum och tid då segmentet senast ändrades. |
| **[!UICONTROL Used in]** | Visa var segment används och hur många gånger de används i varje område. <p>Om segmentet till exempel används i 40 projekt och 2 varningar visas värdet för den här kolumnen som [!UICONTROL **42 komponenter**].</p> <p>Välj värdet i den här kolumnen för att se hur segmenten delas upp (till exempel [!UICONTROL **Projekt (40)**], [!UICONTROL **Mobila styrkort (2)**]). Dessutom kan du visa en lista med objekt där segmenten används. Se till exempel en lista över projekt där de används och välj länken [!UICONTROL **Projekt (40)**].</p><p>I vart och ett av följande områden visas antalet instanser av segment som används i det området:</p>  <ul><li>[!UICONTROL **Projekt**]<p>Innehåller segment som [har skapats i segmentbyggaren](/help/components/segments/seg-builder.md#) och som är tillgängliga för alla projekt.</p></li><li>[!UICONTROL **Ad hoc-komponenter**]<p>Innehåller segment som [har skapats som snabbsegment](/help/components/segments/seg-quick.md) och som endast är tillgängliga i ett enskilt projekt.</p></li><li>[!UICONTROL **Schemalagda projekt**]</li><li>[!UICONTROL **Mobil styrkort**]</li><li>[!UICONTROL **Anteckningar**]</li><li>[!UICONTROL **Beräknade värden**]</li><li>[!UICONTROL **Report Builder**]<p>Om du väljer det här alternativet hämtas en CSV-fil med följande datakolumner:</p><ul><li>Report Builder Name</li><li>Senast använd</li><li>Användar-ID för senast använda IMS</li><li>Användarnamn med senaste åtkomst</li></ul></li></ul><p>Den här informationen hjälper dig att avgöra om en komponent är värdefull för användare i organisationen, var komponenten används och om komponenten behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen är endast tillgänglig för systemadministratörer.</li><li>Kolumnen [!UICONTROL **Används i**] visas inte som standard. Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att konfigurera visningen av den här kolumnen.</li><li>Denna information inkluderar inte användning från API eller Data Warehouse.</li><li>Om det inte finns några data i den här kolumnen för en viss komponent, men komponenten har datumet [!UICONTROL **Senast använd**] , kan komponenten ha använts i en analys utan att sparas.</li><li>Användningsinformation finns tillgänglig från och med september 2023.</li></ul><p>Du kan använda [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation.</p> |
| **[!UICONTROL Last Used]** | När segmentet senast användes. |

Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att ange vilka kolumner du vill visa.

### Åtgärdsfält

Du kan vidta åtgärder för segment med åtgärdsfältet ➋. Åtgärdsfältet innehåller följande åtgärder:

| Åtgärd | Beskrivning |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Lägg till ett annat segment med hjälp av [segmentverktyget](seg-builder.md). |
| ![Sök](/help/assets/icons/Search.svg) [!UICONTROL *Sök efter titel*] | Om inget segment är markerat i listan söker du efter segment med det här sökfältet. |
| ![Etikett](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tagga de markerade segmenten. I dialogrutan **[!UICONTROL Tag Segment]** markerar eller avmarkerar du taggarna för de markerade segmenten. Välj **[!UICONTROL Save]** om du vill spara taggarna för de valda segmenten. Mer information finns i [Tagga segment](/help/components/segments/seg-tag.md). |
| ![Dela](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Dela de markerade segmenten. I dialogrutan **[!UICONTROL Share Segment]** kan du ![&#x200B; söka &#x200B;](/help/assets/icons/Search.svg) *söka efter enskilda personer eller grupper* eller välja **[!UICONTROL Organization]** eller **[!UICONTROL Groups]**. Välj **[!UICONTROL Save]** om du vill spara delningsinformation för de valda segmenten. Mer information finns i [Dela segment](seg-share.md). |
| ![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Ta bort markerade segment. Du uppmanas att bekräfta åtgärden. <br/>När du tar bort ett segment ska du tänka på följande: <ul><li>Schemalagda rapporter och projekt som använder det här segmentet fortsätter att fungera som vanligt.</li><li> Schemalagda rapporter uppdateras inte när du redigerar ett segment med samma namn.</li> </ul> |
| ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Byt namn på ett enskilt markerat segment. När du har markerat det här alternativet kan du byta namn på segmentet. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Godkänn de markerade segmenten. Mer information finns i [Godkänn segment](seg-approve.md). |
| ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** | Kopiera det markerade segmentet. Nya segment skapas med samma namn och suffix `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Exportera segmenten till en `Segments List.csv`-fil. |

### Aktivt filterfält

Filterfältet ➌ visar de aktiva segment som används från filterpanelen till listan med segment (om det finns några). Du kan snabbt ta bort ett filter med ![CrossSize75](/help/assets/icons/CrossSize75.svg). Om fler än ett filter har angetts kan du ta bort alla filter med **[!UICONTROL Remove all]**.

### Panelen Filter

Du kan filtrera listan med segment med hjälp av den vänstra panelen ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** ➍ . Filterpanelen visar typen av filter och antalet segment som använder det specifika filtret. Välj ![Filter](/help/assets/icons/Filter.svg) för att växla visningen av panelen Filter.

Mer information finns i [Filtrera listan med segment](seg-filter.md).
