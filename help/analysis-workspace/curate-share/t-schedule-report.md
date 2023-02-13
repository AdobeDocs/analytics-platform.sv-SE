---
description: Skicka ett Analysis Workspace-projekt via e-post eller schemalägg det för leverans.
keywords: Analysis Workspace
title: Schemalägg projekt
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 7ef67276dabca2afdc9e3e799aab5eb5d93d22fd
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---

# Schemalägg projekt

Från arbetsytan **Dela-menyn** kan du skicka Analysis Workspace-projekt via e-post till utvalda mottagare. Filer kan skickas i CSV- eller PDF-format.

## Skicka filen nu {#now}

Så här skickar du en fil direkt till mottagarna via e-post:

1. Klicka **Dela > Skicka fil nu**.
1. Ange filtypen (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som ska inkluderas i e-postmeddelandet för att förklara filen som tas emot.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. (Endast för vårdsköldens kunder) Ange ett lösenord. Se avsnittet Lösenordsskydda en schemalagd rapport.
1. Klicka **Skicka nu**.
1. (Valfritt) Klicka på **Visa schemaläggningsalternativ** för att ange ett leveransschema.

![Skicka filen nu](assets/send-file-no-scheduling-options.JPG)

## Skicka fil enligt schema {#schedule}

Så här skickar du en fil i ett återkommande schema till mottagarna via e-post:

1. Klicka **Dela > Skicka fil enligt schema**.
1. Ange filtypen (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som ska inkluderas i e-postmeddelandet för att förklara filen som tas emot.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. (Endast för vårdsköldens kunder) Ange ett lösenord. Se avsnittet Lösenordsskydda en schemalagd rapport.
1. Ange intervallet som schemat ska levereras över genom att ändra Inledande och Avslutande på indata. Slutdatumet måste vara inom ett år från den dag då schemat skapas eller ändras.
1. Ange leveransfrekvens. Varje frekvens tillåter olika anpassningar.
1. Klicka **Skicka enligt schema**.

![](assets/send-file.JPG)

## Schemalagd projekthanterare {#manager}

Schemalagda Analysis Workspace-projekt kan hanteras under **Analytics > Components > Scheduled Projects**.

I Hanteraren för schemalagda projekt kan du redigera och ta bort återkommande projektscheman. Sök efter ett schema i sökfältet eller med filteralternativen i den vänstra listen. Du kan filtrera efter tagg, godkända scheman, ägare med mera.

Följande är vanliga åtgärder i hanteraren för schemalagda projekt:

| Åtgärd | Beskrivning |
|---|---|
| **Redigera schema** | Klicka på schemats rubrik för att uppdatera dess leveransinställningar. |
| **Ta bort schema** | Markera det schemalagda projektet i listan och klicka sedan på Ta bort på menyn. Detta kommer att ta bort det valda schemat för projektet. själva projektet inte tas bort. |
| **Lägg till taggar** | Markera det schemalagda projektet i listan och välj sedan Tagga eller Godkänn för att ordna dina scheman och göra dem enklare att söka efter. |
| **Visa ej godkända scheman** | Navigera till den vänstra listen > Andra filter > Misslyckade för att se misslyckade scheman. |
| **Visa utgångna scheman** | Navigera till den vänstra listen > Andra filter > Förfallen om du vill visa scheman som har upphört att gälla. Klicka på schemats titel för att ställa in ett nytt leveransschema. |
| **Visa schema-ID** | Navigera till kolumnalternativen längst upp till höger och lägg till kolumnen Schedule-ID i tabellen. Det schemalagda ID:t är ofta användbart vid felsökning. |

I Hanteraren för schemalagda projekt visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser.

## Lösenordsskydda ett schemalagt projekt {#password}

>[!NOTE]
>
>Alternativet att lösenordsskydda ett schemalagt projekt visas bara för CJA-kunder som har köpt [Hälsovårdssköld](https://business.adobe.com/solutions/experience-cloud-for-healthcare.html) tilläggsprodukt.

Adobe använder lösenordet för att kryptera schemalagda projekt, oavsett om de skickas i .pdf- eller .csv-format.

När ditt företag har köpt SKU:n för hälso- och sjukvårdsskölden och aktiverats för den visas uppmaningen att skapa ett lösenord för ett schemalagt projekt under två omständigheter:

* När någon skapar ett nytt schemalagt projekt.

* När ett befintligt schemalagt projekt ska skickas. Det aktuella schemalagda projektet kommer att inaktiveras tills lösenordsskyddet är på plats. Ägaren till det schemalagda projektet kommer att få ett e-postmeddelande om detta.

![lösenordsskydd](assets/password.png)

### Lösenordskrav

Lösenordskraven uppfyller Adobe-standarden och kräver minst 8 tecken med minst en siffra och ett specialtecken.

### Lösenordsskydda ett nytt schemalagt projekt

1. När du har sparat projektet går du till **[!UICONTROL Share]** > **[!UICONTROL Send file now]**, eller [!UICONTROL Share] > **[!UICONTROL Send file on schedule]**.
1. Följ instruktionerna ovan, under [Skicka filen nu](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#now) eller [Skicka fil enligt schema](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#schedule).

### Lösenordsskydda ett befintligt schemalagt projekt

Före den tidpunkt då ett projekt är schemalagt får projektägaren ett e-postmeddelande som liknar detta:

![e-post](assets/email-password.png)

1. Logga in i Customer Journey Analytics igen.
1. Klicka på **[!UICONTROL View Scheduled Project]**.
1. I **[!UICONTROL Edit scheduled project]** anger och anger ett lösenord igen.
1. Låt (endast) mottagarna av det schemalagda projektet känna till det här lösenordet.


