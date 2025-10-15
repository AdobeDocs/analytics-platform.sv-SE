---
description: Lär dig hur du skickar ett Analysis Workspace-projekt direkt eller enligt ett schema för e-postleverans.
keywords: Analysis Workspace
title: Skicka och schemalägg projekt
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: 973e999b611d578da12018e60becf48efd7a76f8
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# Skicka och schemalägg projekt

Du kan skicka Customer Journey Analytics-projekt som filer till utvalda användare via e-post. Du kan skicka filer för hand eller konfigurera projekt som ska skickas enligt ett schema.

Tänk på följande när du skickar filer:

* Filer kan skickas i CSV- eller PDF-format.

* Alla märkord som används i projektet används automatiskt vid exporten.

Det finns även andra metoder för att exportera Customer Journey Analytics-data, vilket beskrivs i [Översikt över export](/help/analysis-workspace/export/export-project-overview.md).

![Skicka fil](assets/send-file.png)

## Skicka fil

Så här skickar du en fil till mottagarna via e-post:

1. Välj **[!UICONTROL Share]>[!UICONTROL Send file]**.
1. Ange filtyp:
   * [!UICONTROL **CSV**]: Välj det här alternativet om du vill ha textdata.
   * [!UICONTROL **PDF**]: Välj det här alternativet om du vill att den hämtade filen ska innehålla alla tabeller och visualiseringar som visas i projektet.
1. (Valfritt) Använd **[!UICONTROL Description]** för att lägga till en beskrivning som ska inkluderas i e-postmeddelandet.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. (Endast för sjukvårdskunder) Ange ett lösenord för att [lösenordsskydda en schemalagd rapport](#password-protect-a-new-scheduled-project).
1. (Valfritt) Välj **[!UICONTROL Show scheduling options]** om du vill [schemalägga en filexport](#schedule-file-export).
1. Klicka på **[!UICONTROL Send Now]**. Välj **[!UICONTROL Cancel]** om du vill avbryta.


## Schemalägg filexport {#schedule}

Så här skickar du en fil enligt ett schema till mottagarna via e-post:

1. Välj **[!UICONTROL Share]>[!UICONTROL Schedule file export]**.
1. Ange filtyp:
   * [!UICONTROL **CSV**]: Välj det här alternativet om du vill ha textdata.
   * [!UICONTROL **PDF**]: Välj det här alternativet om du vill att den hämtade filen ska innehålla alla tabeller och visualiseringar som visas i projektet.
1. (Valfritt) Använd **[!UICONTROL Description]** för att lägga till en beskrivning som ska inkluderas i e-postmeddelandet.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. (Endast för sjukvårdskunder) Ange ett lösenord för att [lösenordsskydda en schemalagd rapport](#password-protect-a-new-scheduled-project).
1. Kontrollera att **[!UICONTROL Show scheduling options]** är markerat.
1. Välj en **[!UICONTROL Frequency]**. Du kan välja mellan:

   | Frekvens | Alternativ |
   |---|---|
   | **[!UICONTROL Send hourly]** | Ange ett värde för **[!UICONTROL Send every number of hours]**. |
   | **[!UICONTROL Send daily]** | Välj en **[!UICONTROL Daily frequency]**: **[!UICONTROL Send every day]**, **[!UICONTROL Send every weekday]** eller **[!UICONTROL Custom frequency]**.<br/>Om du väljer **[!UICONTROL Custom frequency]** anger du ett värde för **[!UICONTROL Send every number of days]**. |
   | **[!UICONTROL Send weekly]** | Ange ett värde för **[!UICONTROL Send every number of weeks]**. Och välj en **[!UICONTROL Day of week]**. |
   | **[!UICONTROL Send monthly by day of the week]** | Välj **[!UICONTROL Day of week]** och **[!UICONTROL Week of month]**. |
   | **[!UICONTROL Send monthly by day of the month]** | Välj ett värde från **[!UICONTROL Send on this day of the month]**. |
   | **[!UICONTROL Send yearly by day of the month]** | Välj en **[!UICONTROL Day of week]**, markera en **[!UICONTROL Week of month]** och välj en **[!UICONTROL Monthly of year]**. |
   | **[!UICONTROL Send yearly by specific date]** | Välj en **[!UICONTROL Month of year]** och välj ett värde från **[!UICONTROL Send on this day of the month]**. |

1. Ange ett startdatum i **[!UICONTROL Starting on]**. Du kan också välja ![Kalender](/help/assets/icons/Calendar.svg) om du vill välja ett startdatum från kalendern.

1. Ange ett slutdatum i **[!UICONTROL Ending on]**. Du kan också välja ![Kalender](/help/assets/icons/Calendar.svg) om du vill välja ett slutdatum från kalendern.
1. Välj **[!UICONTROL Send on schedule]**. Välj **[!UICONTROL Cancel]** om du vill avbryta.


## Lösenordsskydda ett schemalagt projekt {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="Lösenordskryptering"
>abstract="Det angivna lösenordet används för att kryptera filen för det schemalagda projektet. Säkerhetskraven för din organisation kräver lösenordskryptering."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Alternativet att lösenordsskydda ett schemalagt projekt visas bara för Customer Journey Analytics-kunder som har köpt tilläggsprodukten [Healthcare Shield](https://business.adobe.com/se/solutions/industries/healthcare.html) .

Adobe använder lösenordet för att kryptera schemalagda projekt, oavsett om de skickas i .pdf- eller .csv-format.

När ditt företag har köpt SKU:n för hälso- och sjukvårdsskölden och aktiverats för den visas uppmaningen att skapa ett lösenord för ett schemalagt projekt under följande omständigheter:

* När någon skapar ett nytt schemalagt projekt.

* När ett befintligt schemalagt projekt ska skickas. Det aktuella schemalagda projektet är inaktiverat tills lösenordsskydd finns på plats. Ägaren till det schemalagda projektet får ett e-postmeddelande som informerar dem om detta krav.

### Lösenordskrav

Lösenordskraven uppfyller Adobe-standarderna och kräver minst 8 tecken med minst en siffra och ett specialtecken.

### Lösenordsskydda ett nytt schemalagt projekt

1. När du har sparat projektet går du till **[!UICONTROL Share]** > **[!UICONTROL Send file now]** eller **[!UICONTROL Share]** > **[!UICONTROL Send file on schedule]**.
1. Följ instruktionerna ovan, under [Skicka filen nu](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/t-schedule-report.html?lang=sv-SE#now) eller [Skicka filen enligt schema](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/t-schedule-report.html?lang=sv-SE#schedule).

### Lösenordsskydda ett befintligt schemalagt projekt

När du lösenordsskyddar ett befintligt schemalagt projekt får projektägaren ett e-postmeddelande som liknar detta:

![E-postmeddelandet från Customer Journey Analytics om lösenordskryptering krävs för din organisation.](assets/email-password.png)

1. Logga in på Customer Journey Analytics.
1. Välj **[!UICONTROL View Scheduled Project]**.
1. Ange och ange ett lösenord igen i dialogrutan **[!UICONTROL Edit scheduled project]**.
1. Informera mottagarna av det schemalagda projektet om det här lösenordet. Distribuera inte lösenordet till personer som inte är mottagare av det schemalagda projektet.



## Schemalagd projektledare {#manager}

Schemalagda Analysis Workspace-projekt kan hanteras från huvudgränssnittet med **[!UICONTROL Components]** > **[!UICONTROL Scheduled Projects]**. Mer information finns i [Schemalagda projekt](/help/components/scheduled-projects-manager.md).
