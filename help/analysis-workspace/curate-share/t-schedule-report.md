---
description: Skicka ett Analysis Workspace-projekt via e-post eller schemalägga det för leverans.
keywords: Analysis Workspace
title: Schemalagda projekt
topic: Reports and analytics
uuid: 9244d7b2-1b7e-4323-98ef-cf22de3b666a
translation-type: tm+mt
source-git-commit: c4c6bc367ba1a45146267b968edb88a634cbc7ae
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# Schemalagda projekt

Från arbetsytan **Dela-menyn** kan du skicka Analysis Workspace-projekt via e-post till valda mottagare. Filer kan skickas i CSV- eller PDF-format.

## Skicka filen nu

Så här skickar du en fil direkt till mottagarna via e-post:

1. Klicka **Dela > Skicka fil nu**.
1. Ange filtyp (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som kommer att ingå i e-postmeddelandet för att förklara den mottagna filen.
1. Lägg till mottagare eller grupper. E-postadresser kan också anges.
1. Klicka **Skicka nu**.
1. (Valfritt) Klicka på **Visa schemaläggningsalternativ** för att ange ett leveransschema.

## Skicka fil enligt schema

Så här skickar du en fil i ett återkommande schema till mottagarna via e-post:

1. Klicka **Dela > Skicka fil i schema**.
1. Ange filtyp (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som kommer att ingå i e-postmeddelandet för att förklara den mottagna filen.
1. Lägg till mottagare eller grupper. E-postadresser kan också anges.
1. Ange intervallet som schemat ska levereras över genom att ändra Start on och Ending on input. Slutdatumet måste infalla inom ett år från den dag då schemat skapas eller ändras.
1. Ange leveransfrekvens. Varje frekvens möjliggör olika anpassningar.
1. Klicka **Skicka enligt schema**.

## Projektansvarig för schemalagda projekt

Schemalagda Analysis Workspace-projekt kan hanteras under **Analys > Komponenter > Schemalagda projekt**.

I projekthanteraren för schemalagda projekt kan du redigera och ta bort återkommande projektscheman. Sök efter ett schema i sökfältet eller med hjälp av filteralternativen i den vänstra rälen. Du kan filtrera efter tagg, godkända scheman, ägare med mera.

Följande är vanliga åtgärder i projekthanteraren för schemalagda projekt:

| Åtgärd | Beskrivning |
|---|---|
| **Redigera schema** | Klicka på rubriken för schemat för att uppdatera dess leveransinställningar. |
| **Ta bort schema** | Markera det schemalagda projektet i listan och klicka sedan på Ta bort på menyn. Detta innebär att det valda schemat för projektet tas bort. själva projektet inte kommer att tas bort. |
| **Lägg till taggar** | Markera det schemalagda projektet i listan och välj sedan &quot;Tagg&quot; eller &quot;Godkänn&quot; för att ordna scheman och göra det enklare att söka efter dem. |
| **Visa misslyckade scheman** | Navigera till vänster räl > Andra filter > Det gick inte att visa scheman som har misslyckats. |
| **Visa förfallna scheman** | Navigera till vänster räl > Andra filter > Förfallit om du vill visa förfallna scheman. Klicka på schemats titel för att konfigurera ett nytt leveransschema. |
| **Visa schema-ID** | Navigera till kolumnalternativ längst upp till höger och lägg till kolumnen Schema-ID i tabellen. Det schemalagda ID:t är ofta användbart för felsökning. |

I projekthanteraren visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser. Schemalagd projektägarskap kan vara **överförd** till en ny användare enligt **Admin > Analytiska användare och tillgångar > Överför tillgångar**.
