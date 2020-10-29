---
description: Skicka ett Analysis Workspace-projekt via e-post eller schemalägg det för leverans.
keywords: Analysis Workspace
title: Schemalägg projekt
translation-type: tm+mt
source-git-commit: 6f8973fe6277f3b28b13a61cd65d630398fb3aaa
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---


# Schemalägg projekt

Från arbetsytan **Dela-menyn** kan du skicka Analysis Workspace-projekt via e-post till utvalda mottagare. Filer kan skickas i CSV- eller PDF-format.

## Skicka filen nu

Så här skickar du en fil direkt till mottagarna via e-post:

1. Klicka **Dela > Skicka fil nu**.
1. Ange filtypen (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som ska inkluderas i e-postmeddelandet för att förklara filen som tas emot.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. Klicka **Skicka nu**.
1. (Valfritt) Klicka på **Visa schemaläggningsalternativ** för att ange ett leveransschema.

![Skicka filen nu](assets/send-file-now.png)

## Skicka fil enligt schema

Så här skickar du en fil i ett återkommande schema till mottagarna via e-post:

1. Klicka **Dela > Skicka fil enligt schema**.
1. Ange filtypen (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som ska inkluderas i e-postmeddelandet för att förklara filen som tas emot.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. Ange intervallet som schemat ska levereras över genom att ändra Inledande och Avslutande på indata. Slutdatumet måste vara inom ett år från den dag då schemat skapas eller ändras.
1. Ange leveransfrekvens. Varje frekvens tillåter olika anpassningar.
1. Klicka **Skicka enligt schema**.

![](assets/send-on-schedule.png)

## Schemalagd projekthanterare

Schemalagda Analysis Workspace-projekt kan hanteras under **Analytics > Components > Scheduled Projects**.

I Hanteraren för schemalagda projekt kan du redigera och ta bort återkommande projektscheman. Sök efter ett schema i sökfältet eller med filteralternativen i den vänstra listen. Du kan filtrera efter tagg, godkända scheman, ägare med mera.

![](assets/scheduled-project-manager.png)

Följande är vanliga åtgärder i hanteraren för schemalagda projekt:

| Åtgärd | Beskrivning |
|---|---|
| **Redigera schema** | Klicka på schemats rubrik för att uppdatera dess leveransinställningar. |
| **Ta bort schema** | Markera det schemalagda projektet i listan och klicka sedan på Ta bort på menyn. Detta kommer att ta bort det valda schemat för projektet. själva projektet inte tas bort. |
| **Lägg till taggar** | Markera det schemalagda projektet i listan och välj sedan Tagga eller Godkänn för att ordna dina scheman och göra dem enklare att söka efter. |
| **Visa ej godkända scheman** | Navigera till den vänstra listen > Andra filter > Misslyckade för att se misslyckade scheman. |
| **Visa utgångna scheman** | Navigera till den vänstra listen > Andra filter > Förfallen om du vill visa scheman som har upphört att gälla. Klicka på schemats titel för att ställa in ett nytt leveransschema. |
| **Visa schema-ID** | Navigera till kolumnalternativen längst upp till höger och lägg till kolumnen Schedule-ID i tabellen. Det schemalagda ID:t är ofta användbart vid felsökning. |

I Hanteraren för schemalagda projekt visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser. Schemalagd projektägare kan vara **överförd** till en ny användare under **Admin > Analytics Users &amp; Assets > Transfer Assets**.
