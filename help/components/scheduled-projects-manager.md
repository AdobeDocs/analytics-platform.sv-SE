---
description: Det finns två sätt att använda mätvärden i Analysis Workspace.
title: Mätvärden
feature: Components
source-git-commit: 6f3ae14e4d34de17ed64ae30cee4611e4d6f3226
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---

# Schemalagda projekt

Schemalagda Analysis Workspace-projekt kan hanteras under **[!UICONTROL Analytics]> [!UICONTROL Components] >[!UICONTROL Scheduled Projects]**.

I Hanteraren för schemalagda projekt kan du redigera och ta bort återkommande projektscheman. Sök efter ett schema i sökfältet eller med filteralternativen i den vänstra listen. Du kan filtrera efter tagg, godkända scheman, ägare med mera.

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
| **[!UICONTROL View failed schedules]** | Navigera till den vänstra listen > Andra filter > Misslyckade för att se misslyckade scheman. |
| **[!UICONTROL View expired schedules]** | Navigera till den vänstra listen > Andra filter > Förfallen om du vill visa scheman som har upphört att gälla. Klicka på schemats titel för att ställa in ett nytt leveransschema. |
| **[!UICONTROL View schedule ID]** | Navigera till kolumnalternativen längst upp till höger och lägg till kolumnen Schedule-ID i tabellen. Det schemalagda ID:t är ofta användbart vid felsökning. |

I Hanteraren för schemalagda projekt visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser.