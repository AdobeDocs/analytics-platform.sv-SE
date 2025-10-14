---
title: Vad är Report Builder Hub i Customer Journey Analytics?
description: Beskriver Report Builder Hub-komponenterna
role: User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
source-git-commit: 065cf61d80ceb3c921ea666ba299e56fb044335b
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# Report Builder nav

Report Builder-navet är den högra rutan som visas i Excel-arbetsboken när du väljer ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** i menyfliksområdet i Excel.

Använd Report Builder nav för att skapa, uppdatera, ta bort och hantera datablock.

Report Builder-hubben innehåller knapparna ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**, ![&#x200B; TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** och ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** , **[!UICONTROL Commands]**-panelen och **[!UICONTROL Quick edit]**-panelen.

![Report Builder-nav](assets/hub51.png){zoomable="yes"}


Välj

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]** för att [skapa nya datablock](create-a-data-block.md).
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** för att [hantera befintliga datablock](manage-reportbuilder.md).
* ![Kalender](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** för att [hantera scheman för att skicka din arbetsbok via e-post](schedule-reportbuilder.md).

## Panelen Kommandon

Använd panelen **[!UICONTROL Commands]** för att komma åt kommandon som är kompatibla med de markerade cellerna eller en tidigare åtgärd.

| Kommandon | Tillgängligt när.. | Syfte |
|------|------------------|--------|
| ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit data block]** | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att redigera ett datablock. |
| ![Uppdatera](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** | Markeringen innehåller minst ett datablock. Kommandot uppdaterar bara datablocken i markeringen. | Används för att uppdatera ett eller flera datablock. |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** | Arbetsboken innehåller ett eller flera datablock. | Används för att uppdatera alla datablock i arbetsboken |
| ![Skicka](/help/assets/icons/Send.svg) **[!UICONTROL Send workbook]** | Arbetsboken innehåller ett eller flera datablock. | Används för att skicka arbetsboken som en fil via e-post. |
| ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy data block]** | Det markerade cellområdet eller cellområdet ingår i ett eller flera datablock. | Används för att kopiera ett datablock. |
| ![Klipp ut](/help/assets/icons/Cut.svg) **[!UICONTROL Cut data block]** | Det markerade cellområdet eller cellområdet ingår i ett eller flera datablock. | använda för att klippa ut ett datablock. |
| ![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete data block]** | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att ta bort ett datablock |

## Snabbredigeringspanel

När du markerar ett eller flera datablock i ett kalkylblad visas panelen **[!UICONTROL Quick edit]** i Report Builder. Du kan använda panelen **[!UICONTROL Quick edit]** om du vill ändra parametrar i ett eller flera datablock samtidigt.

De ändringar du gör när du använder **[!UICONTROL Quick Edit]**-avsnitten gäller alla markerade datablock.

### Datavyer

Datablocken hämtar data från en markerad datavy. Om flera datablock är markerade i ett kalkylblad och de inte hämtar data från samma datavy, visas länken **Datavyer** **[!UICONTROL _Flera_]**.

När du ändrar datavyn används den nya datavyn för alla datablock i markeringen. Komponenterna i datablocket matchas mot den nya datavyn baserat på ID. Om en komponent inte hittas i ett datablock tas komponenten bort och ersätts med **[!UICONTROL Invalid value]**, annars visas en ![AlertRed](/help/assets/icons/AlertRed.svg) för den specifika komponenten.

Om du vill ändra datavyn väljer du en ny datavy i listrutan **[!UICONTROL Data view]**.


### Datumintervall

**Datumintervallet** visar datumintervallet för de markerade datablocken. Om flera datablock har markerats med flera datumintervall visas **[!UICONTROL Date range]**-länken **[!UICONTROL _Flera_]**.

### Segment

Länken **Segment** visar en sammanfattningslista över de segment som används av de markerade datablocken. Om flera datablock har markerats med flera segment visas länken **Segment** **[!UICONTROL _Flera_]**.

>[!MORELIKETHIS]
>
>[Välj datavyer](select-data-view.md)
>[Välj ett datumintervall &#x200B;](select-date-range.md)
>[Arbeta med filter](work-with-filters.md)
>
