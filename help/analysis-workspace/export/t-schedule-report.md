---
description: Skicka ett Analysis Workspace-projekt via e-post eller schemalägg det för leverans.
keywords: Analysis Workspace
title: Skicka rapporter till andra via e-post
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 0%

---

# Skicka filer till andra

Du kan skicka Customer Journey Analytics-rapporter som filer till utvalda användare via e-post. Du kan skicka filer för hand eller konfigurera filer som ska skickas enligt ett schema. Filer kan skickas i CSV- eller PDF-format.

Alla märkord som används i projektet används automatiskt vid exporten.

Det finns även andra metoder för att exportera Customer Journey Analytics-data, vilket beskrivs i [Översikt över export](/help/analysis-workspace/export/export-project-overview.md).

## Skicka filen nu {#now}

Så här skickar du en fil direkt till mottagarna via e-post:

1. Klicka på **[!UICONTROL Share]>[!UICONTROL Export file]**.
1. Ange filtyp:
   * [!UICONTROL **CSV**]: Välj det här alternativet om du vill ha textdata.
   * [!UICONTROL **PDF**]: Välj det här alternativet om du vill att den hämtade filen ska innehålla alla tabeller och visualiseringar som visas i projektet.
1. (Valfritt) Lägg till en beskrivning som ska ingå i e-postmeddelandet för att förklara filen som tas emot.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. (Endast för vårdsköldens kunder) Ange ett lösenord. Se avsnittet Lösenordsskydda en schemalagd rapport.
1. (Valfritt) Klicka på **[!UICONTROL Show scheduling options]** om du vill ange ett leveransschema.
1. Klicka på **[!UICONTROL Send Now]**.

![Fönstret Skicka fil och knappen Skicka nu.](assets/send-file-no-scheduling-options.JPG)

## Skicka fil enligt schema {#schedule}

Så här skickar du en fil i ett återkommande schema till mottagarna via e-post:

1. Klicka på **[!UICONTROL Share]>[!UICONTROL Schedule file export]**.
1. Ange filtypen (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som ska inkluderas i e-postmeddelandet för att förklara filen som tas emot.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. (Endast för vårdsköldens kunder) Ange ett lösenord. Se avsnittet Lösenordsskydda en schemalagd rapport.
1. Ange intervallet som schemat ska levereras över genom att ändra Inledande och Avslutande på indata. Slutdatumet måste vara inom ett år från den dag då schemat skapas eller ändras.
1. Ange leveransfrekvens. Varje frekvens tillåter olika anpassningar.
1. Klicka på **[!UICONTROL Send on schedule]**.

![Fönstret Skicka-fil och schemaläggningsalternativen visas för att visa inställningarna för start, slut på datum och daglig frekvens.](assets/send-file.JPG)

## Schemalagd projektledare {#manager}

Schemalagda Analysis Workspace-projekt kan hanteras under **[!UICONTROL Analytics]> [!UICONTROL Components] >[!UICONTROL Scheduled Projects]**.

I Hanteraren för schemalagda projekt kan du redigera och ta bort återkommande projektscheman. Sök efter ett schema i sökfältet eller med filteralternativen i den vänstra panelen. Du kan filtrera efter tagg, godkända scheman, ägare med mera.

| Fält | Beskrivning |
| --- | --- |
| [!UICONTROL Favorites] | Om du väljer stjärnikonen blir schemat en favorit. |
| [!UICONTROL Schedule ID] | Detta ID används främst för felsökning. |
| [!UICONTROL Title and Description] | Projektets namn och beskrivning. |
| [!UICONTROL Owner] | Personen som skapade och äger projektet. |
| [!UICONTROL Tags] | (valfritt) Taggning är ett bra sätt att ordna projekt. Alla användare kan skapa taggar och använda en eller flera taggar i ett projekt. Men du kan bara se taggar för de projekt som du äger eller som har delats med dig. |
| [!UICONTROL Delivered To] | Mottagare av det här schemalagda projektet. |
| [!UICONTROL Expiration Date] | Du kan ange ett förfallodatum till upp till ett år, oavsett hur ofta schemat används. |
| [!UICONTROL Frequency] | Hur ofta du vill att det här schemaprojektet ska skickas till mottagarna. |
| [!UICONTROL Execution Time] | Vid vilken tidpunkt på dagen det här schemalagda projektet skickas. |
| [!UICONTROL Number of Queries] | Antalet frågor mot det här projektet. |

Följande är vanliga åtgärder i hanteraren för schemalagda projekt:

| Åtgärd | Beskrivning |
|---|---|
| **[!UICONTROL Edit schedule]** | Klicka på schemats rubrik för att uppdatera dess leveransinställningar. |
| **[!UICONTROL Delete schedule]** | Markera det schemalagda projektet i listan och klicka sedan på Ta bort på menyn. Detta tar bort det valda schemat för projektet. Själva projektet tas inte bort. |
| **[!UICONTROL Add tags]** | Markera det schemalagda projektet i listan och välj sedan Tagga eller Godkänn för att ordna dina scheman och göra dem enklare att söka efter. |
| **[!UICONTROL View failed schedules]** | Navigera till den vänstra panelen > Andra filter > Misslyckade för att se misslyckade scheman. |
| **[!UICONTROL View expired schedules]** | Navigera till den vänstra panelen > Andra filter > Förfallen om du vill visa scheman som har upphört att gälla. Klicka på schemats rubrik för att ställa in ett nytt leveransschema. |
| **[!UICONTROL View schedule ID]** | Navigera till kolumnalternativen längst upp till höger och lägg till kolumnen Schedule-ID i tabellen. Det schemalagda ID:t är ofta användbart vid felsökning. |

I Hanteraren för schemalagda projekt visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser.
Mer information finns i [Schemalagda projekt](/help/components/scheduled-projects-manager.md).

## Lösenordsskydda ett schemalagt projekt {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="Lösenordskryptering"
>abstract="Det angivna lösenordet används för att kryptera filen för det schemalagda projektet. Säkerhetskraven för din organisation kräver lösenordskryptering."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Alternativet att lösenordsskydda ett schemalagt projekt visas bara för Customer Journey Analytics-kunder som har köpt tilläggsprodukten [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html).

Adobe använder lösenordet för att kryptera schemalagda projekt, oavsett om de skickas i .pdf- eller .csv-format.

När ditt företag har köpt SKU:n för hälso- och sjukvårdsskölden och aktiverats för den visas uppmaningen att skapa ett lösenord för ett schemalagt projekt under följande omständigheter:

* När någon skapar ett nytt schemalagt projekt.

* När ett befintligt schemalagt projekt ska skickas. Det aktuella schemalagda projektet är inaktiverat tills lösenordsskydd finns på plats. Ägaren till det schemalagda projektet får ett e-postmeddelande som informerar dem om detta krav.

![Det schemalagda projektfönstret och lösenordskrypteringsmeddelandet som anger att din organisation kräver lösenordskryptering.](assets/password.png)

### Lösenordskrav

Lösenordskraven uppfyller Adobe-standarderna och kräver minst 8 tecken med minst en siffra och ett specialtecken.

### Lösenordsskydda ett nytt schemalagt projekt

1. När du har sparat projektet går du till **[!UICONTROL Share]** > **[!UICONTROL Send file now]** eller **[!UICONTROL Share]** > **[!UICONTROL Send file on schedule]**.
1. Följ instruktionerna ovan, under [Skicka filen nu](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=sv-SE#now) eller [Skicka filen enligt schema](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=sv-SE#schedule).

### Lösenordsskydda ett befintligt schemalagt projekt

Innan ett projekt är schemalagt får projektägaren ett e-postmeddelande som liknar detta:

![E-postmeddelandet från Customer Journey Analytics som anger lösenordskryptering krävs för din organisation.](assets/email-password.png)

1. Logga in på Customer Journey Analytics.
1. Välj **[!UICONTROL View Scheduled Project]**.
1. Ange och ange ett lösenord igen i dialogrutan **[!UICONTROL Edit scheduled project]**.
1. Informera mottagarna av det schemalagda projektet om det här lösenordet. Distribuera inte lösenordet till personer som inte är mottagare av det schemalagda projektet.
