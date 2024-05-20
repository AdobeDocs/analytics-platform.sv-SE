---
description: Läs om felmeddelandena i Adobe Analysis Workspace och dess tillhörande komponenter
title: Vanliga felmeddelanden i Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: 51a20b0a1f003d2e6ce8baf4d7cec16bfa2fe5b3
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# Vanliga felmeddelanden

Det kan uppstå fel vid interaktion med Analysis Workspace som också påverkar prestandan. Nedan visas de vanligaste feltyperna, varför de inträffar och optimeringar som kan göras.

| Felmeddelande | Varför inträffar detta? | Optimering |
| --- | --- | --- |
| [!UICONTROL The data view is currently exceeding its reporting capacity. Please simplify the request or try again later.] | Din rapporteringsförfrågan är för komplex och behöver förenklas. | Begränsa rapportvillkoren och försök igen. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe har ett problem som måste lösas. | Skicka felkoden till kundtjänst. |
| [!UICONTROL Error 500: Failed to load page] | Problem med ditt lokala nätverk, till exempel företag [brandväggsinställningar](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html), är en bidragande faktor till det här felet. Dessutom kan Adobe ha ett problem som måste lösas. | Försök logga in igen efter flera minuter. Om problemet kvarstår skickar du EIM-instans-ID-koden till Kundtjänst. |
| [!UICONTROL One of the filters or the search in this visualization contains a text search that returned too many results.] | Filterkriterierna eller rapportfiltret är för brett. | Begränsa sökvillkoren och försök igen. |
| [!UICONTROL The request is too complex.] | Din rapporteringsbegäran är för stor och kan inte utföras. Medarbetare till det här felet är timeout på grund av begärans storlek, för många matchade objekt i ett filter eller sökfilter, för många mätvärden, inkompatibla mått- och mätkombinationer osv. | Förenkla begäran genom att ta bort vissa kolumner eller rader i tabellen, eller dela upp tabellen i separata begäranden. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Tabellen innehåller för många frihandsceller (rad * kolumner). | Ta bort kolumner eller rader i tabellen eller dela upp tabellen i separata begäranden. |
