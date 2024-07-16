---
description: Läs om felmeddelandena i Adobe Analysis Workspace och dess tillhörande komponenter
title: Vanliga felmeddelanden i Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: fe089afb2022d8c4b50346bb81d6ba4ad6404014
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Vanliga felmeddelanden

Det kan uppstå fel vid interaktion med Analysis Workspace som också påverkar prestandan. Nedan visas de vanligaste feltyperna, varför de inträffar och optimeringar som kan göras.

| Felmeddelande | Varför inträffar detta? | Optimering |
| --- | --- | --- |
| [!UICONTROL The data view is experiencing unusually heavy reporting. Please try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss datavy. Medarbetare till det här felet är API-begäranden, schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för datavyn jämnare under dagen.<p>Administratörer kan använda [Rapporteringsaktivitetshanteraren för att identifiera och avbryta begäranden](/help/reporting-activity-manager/reporting-activity-overview.md) som förbrukar rapporttapacitet.</p> |
| [!UICONTROL This report is too complex. Please review best practices for building Analysis Workspace reports.] | Din rapporteringsbegäran är för stor och kan inte utföras. Medarbetare till det här felet är timeout på grund av att begäran är komplex. | Förenkla begäran genom att förkorta datumintervallet, förenkla filtervillkoren eller ta bort vissa kolumner eller rader i tabellen. Eller överväg att dela upp tabellen i separata begäranden. |
| [!UICONTROL The data view is currently exceeding its reporting capacity. Please simplify the request or try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss datavy. Medarbetare till det här felet är API-begäranden, schemalagda projekt och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för datavyn jämnare under dagen. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe har ett problem som måste lösas. | Skicka felkoden till kundtjänst. |
| [!UICONTROL Error 500: Failed to load page] | Problem med ditt lokala nätverk, som brandväggsinställningar [för företag](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html), bidrar till det här felet. Dessutom kan Adobe ha ett problem som måste lösas. | Försök logga in igen efter flera minuter. Om problemet kvarstår skickar du EIM-instans-ID-koden till Kundtjänst. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Tabellen innehåller för många frihandsceller (rad * kolumner). | Ta bort kolumner eller rader i tabellen eller dela upp tabellen i separata begäranden. |
