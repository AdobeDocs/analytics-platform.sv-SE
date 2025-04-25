---
title: Så här schemalägger du arbetsböcker med Report Builder i Customer Journey Analytics
description: Lär dig använda schemafunktionen i Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: 6dd8a70293161ff58361953a7e48a98834b7abe0
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 0%

---

# Schemalägg arbetsböcker

När du har sparat arbetsboken och slutfört analysen kan du dela arbetsboken med andra i teamet med hjälp av schemaläggningsfunktionen. Med schemafunktionen kan du skapa ett schema som automatiskt uppdaterar data i arbetsboken. Och mejlar Excel-arbetsboksfilen som en bifogad fil till den angivna målgruppen vid ett visst datum och en viss tidpunkt. När du konfigurerar ett schema får mottagarna automatiskt regelbundna uppdateringar. Du kan också använda schemafunktionen för att skicka ut arbetsboken en gång utan att schemalägga automatiska uppdateringar.

Du kan skapa flera scheman för en enskild arbetsbok. Du kan till exempel skapa två scheman för att skicka en arbetsbok till ditt team varje dag och till din chef en gång i veckan.

Med schemafunktionen kan du också ange lösenordsskydd för en arbetsbok och redigera tidigare schemalagda arbetsböcker.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Schemalägg arbetsböcker](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Schemalägg en arbetsbok

Så här schemalägger du en arbetsbok:

1. Välj **[!UICONTROL Schedule]** i Report Builder-hubben om du vill skapa ett schema så att du automatiskt kan distribuera en Excel-arbetsboksfil (.xlsx) till en individ eller grupp.

   ![Välj knappen Schema för att skapa ett schema.](./assets/schedule.png){zoomable="yes"}

1. Välj **[!UICONTROL Schedule Workbook]** eller ![Lägg till](/help/assets/icons/Add.svg) om du vill skapa en ny schemalagd arbetsbok.

   ![Arbetsboksfönstret Schemalägg.](./assets/schedule-workbook.png){zoomable="yes"}

   I schemaläggningsrutan visas viss fördefinierad information om arbetsboken, t.ex. arbetsbokens namn och det senaste datumet som arbetsboken ändrades.

### Fil

I avsnittet **[!UICONTROL File]** anger du information om filtyp, namn och lösenord för att skydda filen.

![Schemaläggningsfönstret.](./assets/schedule-pane.png){zoomable="yes"}

1. Använd ![TableSelect](/help/assets/icons/TableSelect.svg) för att välja den aktuella arbetsboken, om den inte redan är markerad.

1. (Valfritt) Ange **[!UICONTROL File name]**.

   Arbetsbokens filnamn är som standard arbetsbokens namn, men du kan ändra filnamnet om du vill.

1. Välj en **[!UICONTROL File type]**.

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   När du väljer **[!UICONTROL CSV]** bör du tänka på att den schemalagda arbetsboken skickas som en zip-bilaga. Vissa e-postadministrationer kan blockera e-post med postbilagor. Du ser en varning i enlighet med detta.

1. (Valfritt) Välj **[!UICONTROL Append time-stamp to file name]**.

   Du kan lägga till en tidsstämpel till filnamnet för att identifiera vilket datum arbetsboken uppdaterades. En tidsstämpel är användbar för att se vilken version av en arbetsbok som skickades på ett visst datum. När du har markerat det här alternativet kan du välja mellan:

   * **[!UICONTROL ISO Date format]**, vilket resulterar i att `YYYY-MM-DD` läggs till i filnamnet.
   * **[!UICONTROL ISO Date format + time stamp]**, vilket resulterar i att `YYYY-MM-DD_HH-MM-SS` läggs till i filnamnet.

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. Ange ett lösenord i **[!UICONTROL Password protect the workbook]**. Ett giltigt lösenord måste innehålla minst 8 tecken, en siffra och ett specialtecken. Välj ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) för att visa lösenordet och ![Visibility](/help/assets/icons/Visibility.svg) för att dölja lösenordet (standard).


### E-post

I avsnittet **[!UICONTROL Email]** anger du mottagare, ämne och beskrivning av e-postmeddelandet.

![Schemalägg e-postinställningar](assets/schedule-email.png){zoomable="yes"}

1. Ange **mottagare**. Du kan ange namnet på en person som är erkänd i din organisation. Eller så kan du ange en e-postadress till en person som inte finns i organisationen.

1. Ange **Ämne** för e-postmeddelandet och en beskrivning för mottagarna. Ämnet får som standard arbetsbokens filnamn, men du kan ändra ämnet om det behövs. Du kan lägga till information i beskrivningsavsnittet.

1. Du kan också ange en beskrivning i textområdet **[!UICONTROL Description]**.


### Schema

I avsnittet **[!UICONTROL Schedule]** kan du definiera schemat för att skicka e-postmeddelanden med arbetsboken till mottagarna.

![Schemadefinition](assets/schedule-enable.png){zoomable="yes"}

1. Välj **[!UICONTROL Show scheduling options]** om du vill definiera ett schema.

1. Ange ett startdatum i **[!UICONTROL Starting on]**. Du kan också välja ![Kalender](/help/assets/icons/Calendar.svg) om du vill välja ett startdatum från kalendern.

1. Ange ett slutdatum i **[!UICONTROL Ending on]**. Du kan också välja ![Kalender](/help/assets/icons/Calendar.svg) om du vill välja ett slutdatum från kalendern.

1. Välj en **[!UICONTROL Frequency]**. Beroende på vald frekvens har du ytterligare alternativ. Se tabellen nedan.

   | Frekvens | Alternativ |
   |---|---|
   | **[!UICONTROL Send hourly]** | Ange ett värde för **[!UICONTROL Send every number of hours]**. |
   | **[!UICONTROL Send daily]** | Välj en **[!UICONTROL Daily frequency]**: **[!UICONTROL Send every day]**, **[!UICONTROL Send every weekday]** eller **[!UICONTROL Custom frequency]**.<br/>Om du väljer **[!UICONTROL Custom frequency]** anger du ett värde för **[!UICONTROL Send every number of days]**. |
   | **[!UICONTROL Send weekly]** | Ange ett värde för **[!UICONTROL Send every number of weeks]**. Och välj en **[!UICONTROL Day of week]**. |
   | **[!UICONTROL Send monthly by day of the week]** | Välj **[!UICONTROL Day of week]** och **[!UICONTROL Week of month]**. |
   | **[!UICONTROL Send monthly by day of the month]** | Välj ett värde från **[!UICONTROL Send on this day of the month]**. |
   | **[!UICONTROL Send yearly by day of the month]** | Välj en **[!UICONTROL Day of week]**, markera en **[!UICONTROL Week of month]** och välj en **[!UICONTROL Monthly of year]**. |
   | **[!UICONTROL Send yearly by specific date]** | Välj en **[!UICONTROL Month of year]** och välj ett värde från **[!UICONTROL Send on this day of the month]**. |

### Skicka

Så här skickar du arbetsboken:

* Om du inte har definierat ett schema med **[!UICONTROL Show scheduling options]** väljer du **[!UICONTROL Send now]** för att skicka arbetsboken via e-post omedelbart.
* Om du har definierat ett schema med **[!UICONTROL Show scheduling options]** väljer du **[!UICONTROL Send on schedule]** om du vill skicka arbetsboken via e-post enligt det schema som du har definierat.

I båda fallen visas en bekräftelsetabell längst ned i Report Builder-navet.

Om du vill avbryta sändning av arbetsboken väljer du **[!UICONTROL Cancel]**.


## Visa och hantera schemalagda arbetsböcker

Du kan visa och hantera alla schemalagda arbetsböcker på fliken **[!UICONTROL Workbooks]**.

1. Välj **[!UICONTROL Schedule]** i Report Builder-hubben

1. Välj fliken **[!UICONTROL Workbooks]**. Du ser en lista över alla schemalagda arbetsböcker.

   ![Schemalagd arbetsbok](assets/scheduled-workbooks.png){zoomable="yes"}

   Du kan hålla muspekaren över ikonen om du vill visa statusen för en schemalagd arbetsbok.

   Använd ![Sök](/help/assets/icons/Search.svg) om du vill söka efter specifika schemalagda arbetsböcker.
Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att definiera vilka kolumner som ska visas.

1. Markera en eller flera arbetsböcker.

   ![Schemalägg arbetsböcker har valts](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   Följande alternativ är tillgängliga:

   | Alternativ | Beskrivning |
   |---|---|
   | ![Redigera](/help/assets/icons/Edit.svg) | Redigera schemat för en vald arbetsbok. |
   | ![Historik](/help/assets/icons/History.svg) | Visa historiken för valda arbetsböcker. |
   | ![Paus](/help/assets/icons/Pause.svg) | Pausa schemat för markerade arbetsböcker. |
   | ![Spela upp](/help/assets/icons/Play.svg) | Återuppta schemat för valda arbetsböcker. |
   | ![Hämta](/help/assets/icons/Download.svg) | Hämta den markerade arbetsboken till en ny arbetsbok. |
   | ![Ta bort](/help/assets/icons/Delete.svg) | Ta bort schemat för valda arbetsböcker. |


## Historik och status för schemalagda arbetsböcker

Du kan visa historik och status för schemalagda arbetsböcker på fliken **[!UICONTROL History]**.

1. Välj **[!UICONTROL Schedule]** i Report Builder-navet.

1. Välj fliken **[!UICONTROL History]**. Du ser en lista över alla schemalagda arbetsböcker.

   ![Schemalagd historik](assets/scheduled-workbooks-history.png){zoomable="yes"}

   Använd ![Sök](/help/assets/icons/Search.svg) om du vill söka efter specifika arbetsböcker i listan.
Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att definiera vilka kolumner som ska visas.

   På fliken **[!UICONTROL History]** kan du granska statusen för varje schemalagd aktivitet. En separat rad visar statusändringen för varje schemalagd aktivitet.

   * En ![CheckCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg) anger att arbetsboken har skickats.
   * Ett ![AlertRed](/help/assets/icons/AlertRed.svg) indikerar att ett fel har inträffat.

Du kan också välja ![Historik](/help/assets/icons/History.svg) för en eller flera markerade arbetsböcker på fliken **[!UICONTROL Workbooks]**. Den här åtgärden visar fliken **[!UICONTROL History]** med en lista filtrerad efter din markering. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort ett filter.
