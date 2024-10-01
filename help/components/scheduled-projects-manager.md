---
description: Det finns två sätt att använda mätvärden i Analysis Workspace.
title: Mätvärden
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Schemalagda projekt

Schemalagda Analysis Workspace-projekt kan hanteras i Customer Journey Analytics med **[!UICONTROL Components]** > **[!UICONTROL Scheduled projects]**.

I **[!UICONTROL  Scheduled Projects]** kan du redigera och ta bort återkommande projektscheman. Sök efter ett schema med ![Sök](/help/assets/icons/Search.svg) i sökfältet. Du kan också använda filteralternativen ![Filter](/help/assets/icons/Filter.svg) på den vänstra panelen. Du kan filtrera efter **[!UICONTROL Tag]**, **[!UICONTROL Owners]** och **[!UICONTROL Other filters]**.

I listan Schemalagda projekt visas kolumner för:

| Fält | Beskrivning |
| --- | --- |
| ![Stjärna](/help/assets/icons/Star.svg) | Om du väljer ![Stjärna](/help/assets/icons/Star.svg) blir det här schemat en favorit. |
| **[!UICONTROL Schedule ID]** | Ett ID som huvudsakligen används för felsökning. |
| [!UICONTROL Name] | Projektets namn.<br/>Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg) om du vill visa mer information om det schemalagda projektet.<br/>Välj ![Mer](/help/assets/icons/More.svg) om du vill öppna en snabbmeny. På den här menyn kan du:<ul><li>![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** ett schemalagt projekt.</li><li>![Etiketter](/help/assets/icons/Labels.svg) **[!UICONTROL Tag]** ett planerat projekt.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** ett schemalagt projekt.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]**: Exportera ett planerat projekt till en CSV-fil.</li></ul> |
| **[!UICONTROL Owner]** | Personen som skapade och äger projektet. |
| **[!UICONTROL Tags]** | (valfritt) Taggning är ett bra sätt att ordna projekt. Alla användare kan skapa taggar och använda en eller flera taggar i ett projekt. Men du kan bara se taggar för de projekt som du äger eller som har delats med dig. |
| **[!UICONTROL Delivered to]** | Mottagarna av det här schemalagda projektet. |
| **[!UICONTROL Expiration date]** | Du kan ange ett förfallodatum till upp till ett år, oavsett hur ofta schemat används. |
| **[!UICONTROL Frequency]** | Hur ofta du vill att schemaprojektet ska skickas till en eller flera mottagare. |
| **[!UICONTROL Execution Time]** | Vid vilken tidpunkt på dagen det här schemalagda projektet skickas. |
| **[!UICONTROL Number of Queries]** | Antalet frågor mot det här projektet. |
| **[!UICONTROL Longest Date Range]** | Det längsta datumintervallet som har definierats för det schemalagda projektet. Det här värdet kan vara relevant för att undersöka prestandaproblem. Mer information finns i [Rapportera aktivitetshanteraren](/help/reporting-activity-manager/reporting-activity-overview.md). |
| **[!UICONTROL Number of queries]** | Antalet frågor som har körts för det schemalagda projektet. Det här värdet kan vara relevant för att undersöka prestandaproblem. Mer information finns i [Rapportera aktivitetshanteraren](/help/reporting-activity-manager/reporting-activity-overview.md). |

Du kan använda ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att konfigurera vilka kolumner som ska visas.

Schemalagda projekt visar de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser.



## Åtgärder

Följande är vanliga åtgärder i hanteraren för schemalagda projekt. Du kan välja åtgärder på snabbmenyn eller från det blå åtgärdsfältet när du markerar mer än ett schemalagt projekt.

| Åtgärd | Beskrivning |
|---|---|
| **[!UICONTROL Approve]** | Godkänn det planerade projektet. |
| **[!UICONTROL Edit]** | Klicka på schemats rubrik för att uppdatera dess leveransinställningar. |
| **[!UICONTROL Delete]** | Ta bort det valda schemat för projektet. Själva projektet tas inte bort. |
| **[!UICONTROL Tag]** | Tagga det schemalagda projektet så att det blir lättare att hitta projekten. |

Med ![Filter](/help/assets/icons/Filter.svg)-filtret kan du även utföra följande åtgärder:

| Åtgärd | Beskrivning |
|---|---|
| **[!UICONTROL View failed schedules]** | Navigera till **[!UICONTROL Other filters]** och välj **[!UICONTROL Failed]** för att se om det finns några misslyckade scheman. |
| **[!UICONTROL View expired schedules]** | Navigera till **[!UICONTROL Other filters]** och välj **[!UICONTROL Expired]** för att se scheman som har upphört att gälla. Klicka på schemats rubrik för att ställa in ett nytt leveransschema. |

