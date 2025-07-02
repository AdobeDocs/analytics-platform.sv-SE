---
description: Lär dig hur du hanterar aviseringar.
title: Hantera aviseringar
feature: Workspace Basics
role: User, Admin
exl-id: 174c3ebd-a77b-4403-ae9a-bb0cff4bcca6
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---

# Hantera aviseringar


Du kan filtrera, tagga, ta bort, byta namn på, kopiera, aktivera, inaktivera förnyelse och exportera aviseringar från ett centralt [!UICONTROL Alerts]-hanteringsgränssnitt. Så här hanterar du aviseringar:

* Välj **[!UICONTROL Components]** i huvudgränssnittet och välj sedan **[!UICONTROL Alerts]**.

Varningshanteraren är strukturerad som [Segmenthanteraren](/help/components/segments/seg-manage.md) och [hanteraren för beräknade värden](/help/components/calc-metrics/cm-workflow/cm-manager.md).


## Varningshanteraren

Varningshanteraren har följande gränssnittselement:

![Gränssnitt för filter](assets/alerts-manager.png)

### Varningslista

Aviseringslistan ➊ visar alla aviseringar som du äger, aviseringar som har omfattats av alla dina projekt och aviseringar som har delats med dig. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Välj om du vill prioritera ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) en varning. |
| **[!UICONTROL Title and description]** | Om du vill redigera varningen markerar du titellänken, som öppnar [Varningsverktyget](alert-builder.md#alert-builder). |
| **[!UICONTROL Type]** | Visar om aviseringen är en Customer Journey Analytics-datavarning eller en varning om användning av serversamtal. |
| **[!UICONTROL Enabled]** | Anger om aviseringen är aktiverad eller inaktiverad. |
| **[!UICONTROL Data view]** | De datavyer som den här varningen gäller för. |
| **[!UICONTROL Owner]** | Varningens ägare. Som icke-administratör visas endast aviseringar som du äger eller aviseringar som delas med dig. |
| **[!UICONTROL Tags]** | Taggarna för den här varningen. |
| **[!UICONTROL Expiration Date]** | Det datum och den tidpunkt då aviseringen förfaller. |
| **[!UICONTROL Date modified]** | Datum och tid då aviseringen senast ändrades. |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att ange vilka kolumner du vill visa.

### Åtgärdsfält

Du kan använda åtgärdsfältet ➋ för att utföra åtgärder för aviseringar. Åtgärdsfältet innehåller följande åtgärder:

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Lägg till ytterligare en avisering med [Varningsverktyget](alert-builder.md#alert-builder). |
| ![Sök](/help/assets/icons/Search.svg) | [!UICONTROL *Sök efter titel*] | Om ingen varning är markerad i listan söker du efter aviseringar med det här sökfältet. |
| ![Etikett](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Tagga de markerade varningarna. I dialogrutan **[!UICONTROL Tag Alert]** markerar eller avmarkerar du taggarna för de markerade aviseringarna. Välj **[!UICONTROL Save]** om du vill spara taggarna för de valda aviseringarna. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de markerade aviseringarna. Du uppmanas att bekräfta åtgärden. |
| ![Redigera](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Byt namn på en enskild markerad varning. Om du väljer det här alternativet kan du byta namn på aviseringen. |
| ![Kopiera](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Kopiera den markerade varningen. Nya aviseringar skapas med samma namn och suffix `(Copy)`. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Enable]** eller **[!UICONTROL Disable]** | Aktivera eller inaktivera de markerade aviseringarna. |
| ![Uppdatera](/help/assets/icons/Refresh.svg) | **[!UICONTROL Renew]** | Förnyar aviseringens förfallodatum. Utgångsdatumet är ett år från den dag du väljer det här alternativet, oavsett det ursprungliga förfallodatumet. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera aviseringarna till en `Alerts List.csv`-fil. |


### Aktivt filterfält

Filterfältet ➌ visar de aktiva filter som använts från filterpanelen till listan med varningar (om sådana finns). Du kan snabbt ta bort ett filter med ![CrossSize75](/help/assets/icons/CrossSize75.svg). Om fler än ett filter har angetts kan du ta bort alla filter med **[!UICONTROL Remove all]**.


### Panelen Filter

Du kan filtrera listan med varningar med hjälp av den vänstra panelen ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** ➍ . Filterpanelen visar typ av filter och antalet varningar som följer det specifika filtret.


1. Välj ![Filter](/help/assets/icons/Filter.svg) för att öppna panelen Filter. Om du behöver mer utrymme för varningslistan kan du välja ![Filter](/help/assets/icons/Filter.svg) en gång till för att stänga panelen.
1. Välj filter från något av de tillgängliga filteravsnitten.


#### Filteravsnitt för taggar

{{tagfiltersection}}


#### Filteravsnitt för datavy

{{dataviewfiltersection}}


#### Ägarfilteravsnitt

{{ownerfiltersection}}


#### Aktiverat statusfilteravsnitt

{{enabledstatusfiltersection}}


#### Textfilteravsnitt

{{typefiltersection}}


#### Andra filteravsnitt

{{otherfiltersfiltersection}}



## Redigera aviseringar

Du kan redigera en varning

* Markera aviseringens titel i listan [[!UICONTROL Alert]](#alerts-list).

Du använder [varningsverktyget](alert-builder.md#alert-builder) för att redigera varningen.

## Felsöka en varning

När du felsöker ett problem med en varning ska du ange JID-numret (Job Instance ID) till Adobe Support. JID-numret finns längst ned i det varningsmeddelande du får.

![Varningsmeddelande](assets/alerts-email.PNG)
