---
title: Hantera anteckningar
description: Lär dig hantera anteckningar i Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 0%

---

# Hantera anteckningar

Du kan dela, filtrera, tagga, godkänna, kopiera, ta bort anteckningar och markera anteckningar som favoriter från ett centralt [!UICONTROL Annotations]-hanteringsgränssnitt. Så här hanterar du anteckningar:

* Välj **[!UICONTROL Components]** i huvudgränssnittet och välj sedan **[!UICONTROL Annotations]**.


>[!NOTE]
>
>Anteckningarna som du skapar i ett visst Workspace-projekt visas inte i hanteraren för [!UICONTROL Annotations], såvida du inte har gjort anteckningen tillgänglig för alla dina projekt.
>

## Anteckningshanteraren

Anteckningshanteraren har följande gränssnittselement:

![Anteckningsgränssnitt](assets/annotations-manager.png)

### Anteckningslista

Anteckningslistan ➊ visar alla anteckningar som du äger, anteckningarna som har omfattats av alla dina projekt och de anteckningar som har delats med dig. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Välj om du vill prioritera ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) en anteckning. |
| **[!UICONTROL Title and description]** | Finns i Annotations Builder. Om du vill redigera titeln och beskrivningen markerar du titellänken. [Anteckningsverktyget](/help/components/annotations/create-annotations.md#annotation-builder) öppnas. En delad anteckning har markerats med ![Dela](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | De datavyer som den här anteckningen gäller för. |
| **[!UICONTROL Owner]** | Anteckningens ägare. Som användare ser du bara de anteckningar du äger eller de anteckningar som delas med dig. |
| **[!UICONTROL Applied date range]** | Det datum eller datumintervall som den här anteckningen gäller för. |
| **[!UICONTROL Tags]** | Taggarna för anteckningen. |
| **[!UICONTROL Shared with]** | De personer eller grupper som du delade anteckningen med. Välj det här alternativet om du vill öppna dialogrutan **[!UICONTROL Share Component]**. |
| **[!UICONTROL Date modified]** | Visar datum och tid då anteckningen senast ändrades. |

{style="table-layout:auto"}

Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att ange vilka kolumner du vill visa.

### Åtgärdsfält

Du kan utföra åtgärder på anteckningar med åtgärdsfältet ➋. Åtgärdsfältet innehåller följande åtgärder:

| Ikon | Åtgärd | Beskrivning |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Lägg till en till anteckning med [Anteckningsverktyget](create-annotations.md#annotation-builder). |
| ![Sök](/help/assets/icons/Search.svg) | [!UICONTROL *Sök efter titel*] | Om ingen anteckning är markerad i listan söker du efter anteckningar med det här sökfältet. |
| ![Etikett](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Tagga de markerade anteckningarna. I dialogrutan **[!UICONTROL Tag Component]** markerar eller avmarkerar du taggarna för de markerade anteckningarna. Välj **[!UICONTROL Save]** om du vill spara taggarna för de markerade anteckningarna. |
| ![Dela](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Share]** | Dela de markerade anteckningarna. I dialogrutan **[!UICONTROL Share Component]** kan du ![ söka ](/help/assets/icons/Search.svg) *söka efter enskilda personer eller grupper* eller välja **[!UICONTROL Organization]** eller **[!UICONTROL Groups]**. Välj **[!UICONTROL Save]** om du vill spara delningsinformation för de valda anteckningarna. Mer information finns i [Dela anteckningar](#share-annotations). |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de markerade anteckningarna. Du uppmanas att bekräfta åtgärden. |
| ![Redigera](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Byt namn på en enskild markerad anteckning. När du väljer det här alternativet kan du byta namn på anteckningen. |
| ![Kopiera](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Kopiera de markerade anteckningarna. Nya anteckningar skapas med samma namn och suffix (Kopiera) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera anteckningarna till en `Annotations List.csv`-fil. |

### Aktivt filterfält

Filterfältet ➌ visar de aktiva filtren (om sådana finns). Du kan snabbt ta bort ett filter med ![CrossSize75](/help/assets/icons/CrossSize75.svg). Om fler än ett filter har angetts kan du ta bort alla filter med **[!UICONTROL Remove all]**.

### Panelen Filter

Du kan filtrera anteckningar med den vänstra panelen **[!UICONTROL Filter]** ➍. Filterpanelen visar typen av filter och antalet anteckningar som följer filtret. Välj ![Filter](/help/assets/icons/Filter.svg) för att växla visningen av filterpanelen.

Så här filtrerar du filterlistan:

1. Välj ![Filter](/help/assets/icons/Filter.svg) för att öppna panelen Filter. Om du behöver mer utrymme för filterlistan kan du stänga panelen genom att välja ![Filter](/help/assets/icons/Filter.svg) en gång till.
1. Du kan filtrera anteckningarna med någon av de tillgängliga [filteravsnitten](#filter-sections).

   >[!INFO]
   >
   >*Objekt* refererar till anteckningsobjekten som visas i [anteckningslistan](manage-annotations.md#annotations-list).
   > 

#### Filtrera avsnitt

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


[Anteckningslistan](manage-annotations.md#annotations-list) uppdateras automatiskt baserat på din filterkonfiguration. Du kan se de konfigurerade filtren i det [aktiva filterfältet](manage-annotations.md#active-filter-bar).


## Redigera anteckningar

Du kan redigera en anteckning på två sätt:

* Använd ikonen [Komponentinformation](/help/components/use-components-in-workspace.md#component-info) i ett Workspace-projekt.

* Markera anteckningens titel i listan [[!UICONTROL Annotations]](#annotations-list).

Du använder [Anteckningsverktyget](/help/components/annotations/create-annotations.md#annotation-builder) för att redigera anteckningen.

## Dela anteckningar

Följande gäller när du delar anteckningar eller arbetar med anteckningar som delas med dig:

* Anteckningar som bara är för projekt i ett projekt som du delar med andra användare visas för dessa användare. Användarna kan inte redigera eller ta bort de här anteckningarna som bara är för projekt.
* Om du sparar en anteckning och delar anteckningen direkt med en användare, kan den användaren bara redigera och ta bort anteckningen om användaren har administratörsbehörighet.

* Om ett projekt delas med dig visas anteckningar som skapats i det projektet bara i det projektet. Om en anteckning delas direkt med dig, visas anteckningen i alla projekt där anteckningen kan visas.

## Anteckningar och tidszoner

Alla anteckningar skapas med en tidsstämpel, men ingen timmes- eller tidszonsinformation. Vid rapporttillfället används tidszonen för datavyn som konfigurerats för panelen.
