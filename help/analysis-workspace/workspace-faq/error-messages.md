---
description: Läs mer om fel och felsökning för Analysis Workspace.
title: Fel och felsökning
feature: Workspace Basics
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 11%

---

# Fel och felsökning

Det kan uppstå fel vid interaktion med Analysis Workspace som kan påverka dess funktioner eller prestanda. Nedan visas de vanligaste feltyperna, varför de inträffar och optimeringar som kan göras.

## Felmeddelanden

Några vanliga felmeddelanden du kan se när du använder Analysis Workspace:

| Felmeddelande | Varför inträffar felet? | Optimering |
| --- | --- | --- |
| [!UICONTROL The data view is experiencing unusually heavy reporting. Please try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss datavy. Medarbetare till det här felet är API-begäranden, schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för datavyn jämnare under dagen.<p>Administratörer kan använda [Rapporteringsaktivitetshanteraren för att identifiera och avbryta begäranden](/help/reporting-activity-manager/reporting-activity-overview.md) som förbrukar rapporttapacitet.</p> |
| [!UICONTROL This report is too complex. Please review best practices for building Analysis Workspace reports.] | Din rapporteringsbegäran är för stor och kan inte utföras. Medarbetare till det här felet är timeout på grund av att begäran är komplex. | Förenkla er begäran. Du kan t.ex. korta ned datumintervallet, förenkla segmentvillkoren eller ta bort vissa kolumner eller rader i tabellen. Du kan också dela upp tabellen i separata begäranden. |
| [!UICONTROL The data view is currently exceeding its reporting capacity. Please simplify the request or try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss datavy. Medarbetare till det här felet är API-begäranden, schemalagda projekt och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för datavyn jämnare under dagen. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe har ett problem som behöver lösas. | Skicka felkoden till kundtjänst. |
| [!UICONTROL Error 500: Failed to load page] | Problem med ditt lokala nätverk, som brandväggsinställningar [för företag](/help/technotes/ip-addresses.md), bidrar till det här felet. Dessutom kan Adobe ha problem som behöver åtgärdas. | Försök logga in igen efter flera minuter. Om problemet kvarstår skickar du EIM-instans-ID-koden till Kundtjänst. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Tabellen innehåller för många frihandsceller (rad * kolumner). | Ta bort kolumner eller rader i tabellen eller dela upp tabellen i separata begäranden. |


## Felsökning

När du använder Analysis Workspace kan du använda informationen nedan för att felsöka några vanliga problem.

| Problem | Felsöka |
|---|---|
| När jag drar ett mätresultat över står det *Ogiltiga data*. | Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av mått och mätvärden som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Istället placerar du mätvärdena sida vid sida. |
| När jag drar ett mätresultat över ser jag inga verkliga data - bara nollor. | Om du har skapat en rapport om arbetsytan men det inte finns några data kan du kontrollera några saker:<ul><li>Om du tillämpade ett segment i rapporten kanske segmentvillkoren inte matchar några data. Prova med att ta bort segmentet eller justera segmentdefinitionen.</li><li>Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.</li><li>Navigera till webbplatsen och använd [Felsökning](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) för att verifiera att data samlas in.</li></ul> |
