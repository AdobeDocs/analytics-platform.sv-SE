---
description: Lär dig hantera schemalagda projekt.
title: Schemalagda projekt
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 0%

---

# Schemalagda projekt

Schemalagda Analysis Workspace-projekt kan hanteras i Customer Journey Analytics med **[!UICONTROL Components]** > **[!UICONTROL Scheduled projects]**.

I **[!UICONTROL Scheduled Projects]** kan du redigera och ta bort återkommande projektscheman.  I [schemalagda projektlistan](#scheduled-project-list) visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser.

![Gränssnitt för schemalagda projekt](assets/scheduled-projects.png)

## Schemalagd projektlista

Listan ➊ med schemalagda projekt visar kolumner för:

| Kolumn | Beskrivning |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | När ett eller flera schemalagda projekt har valts visas ett blått åtgärdsfält längst ned i gränssnittet för schemalagda projekt. Mer information finns i [Åtgärder](#actions). |
| ![Stjärna](/help/assets/icons/Star.svg) | Välj om du vill gynna ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) i ett schemalagt projekt. |
| **[!UICONTROL Schedule ID]** | Ett ID som huvudsakligen används för felsökning. |
| **[!UICONTROL Name]** | Projektets namn.<br/>Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg) om du vill visa mer information om det schemalagda projektet.<br/>Välj ![Mer](/help/assets/icons/More.svg) om du vill öppna en snabbmeny. På den här menyn kan du:<ul><li>![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** ett schemalagt projekt.</li><li>![Etiketter](/help/assets/icons/Labels.svg) **[!UICONTROL Tag]** ett planerat projekt.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** ett schemalagt projekt.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]**: Exportera ett planerat projekt till en CSV-fil.</li></ul> |
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

Sök efter ett schemalagt projekt med ![Sök](/help/assets/icons/Search.svg). Du kan också se om några filter har tillämpats från filterpanelen. Om du vill ta bort ett filter väljer du ![CrossSize75](/help/assets/icons/CrossSize75.svg) för ett filter. Om du vill ta bort alla filter väljer du **[!UICONTROL Clear all]**.

Om du vill redigera ett schemalagt projekt markerar du titeln på det schemalagda projektet. Använd dialogrutan **[!UICONTROL Edit scheduled project]** för att uppdatera schemainformationen. Mer information finns i [Skicka filer till andra](../analysis-workspace/export/t-schedule-report.md).

![Redigera schemalagt projekt](assets/edit-scheduled-project.png)

Välj **[!UICONTROL Update]** om du vill uppdatera schemat.




## Åtgärder

Följande är vanliga åtgärder i hanteraren för schemalagda projekt. Du kan välja åtgärder från snabbmenyn eller från det blå åtgärdsfältet när du väljer ett eller flera schemalagda projekt.

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![Stäng](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selected]** | Välj det här alternativet om du vill avmarkera dina valda schemalagda projekt. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de valda schemalagda projekten för projektet. Projekten tas inte bort.  <p>Mer information om hur du tar bort ett projekt finns i [Projektöversikt](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> |
| ![Etiketter](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Tagga de valda schemalagda projekten. I **[!UICONTROL Tag Scheduled projects]** markerar du taggar och väljer **[!UICONTROL Save]** att spara. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** | Godkänn de valda schemalagda projekten. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera de markerade schemalagda projekten till en fil med namnet `Export Scheduled Projects List.csv`. |


## Filter

Du kan filtrera listan [Schemalagda projekt](#scheduled-project-list) med filterpanelen ➌. Om du vill visa eller dölja filterpanelen använder du ![Filter](/help/assets/icons/Filter.svg).

Filterpanelen består av följande avsnitt.

### Taggar

| Taggar | Beskrivning |
|---|---|
| ![Taggar](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | I avsnittet **[!UICONTROL Tags]** kan du filtrera efter taggar. <ul><li>Du använder ![Sök](/help/assets/icons/Search.svg) **[!UICONTROL Search Tags]** för att söka efter taggar som du vill använda för att filtrera.</li><li>Du kan markera flera taggar. Vilka märkord som är tillgängliga beror på vilka markeringar du har gjort i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>7︎⃣: Antalet schemalagda projekt som är associerade med den specifika taggen.</li></ul></li></ul> |


### Ägare

| Ägare | Beskrivning |
|---|---|
| ![Ägare](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | I avsnittet **[!UICONTROL Owner]** kan du filtrera efter ägare. <ul><li>Du använder ![Sök](/help/assets/icons/Search.svg) *Sökägare* för att söka efter ägare som du vill använda för att filtrera.</li><li>Du kan välja mer än en ägare. Vilka ägare som är tillgängliga beror på vad som har gjorts i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>4︎⃣: Antalet schemalagda projekt som är associerade med den specifika ägaren.</li></ul></li></ul> |


### Andra filter

| Andra filter | Beskrivning |
|---|---|
| ![Andra filter](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | I avsnittet **[!UICONTROL Other filters]** kan du filtrera på andra fördefinierade filter.<ul><li>Du kan välja ett eller flera av följande alternativ:<ul><li> **[!UICONTROL Expired]**: Filtrera på inaktuella schemalagda projekt.</li><li>**[!UICONTROL Failed]**: Filtrera på schemalagda projekt som schemat har misslyckats för.</li></ul>Vad du kan välja beror på din roll och dina behörigheter.</li><li>Du kan markera mer än ett annat filter. Vilka andra filter som är tillgängliga beror på vilka markeringar du har gjort i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>4︎⃣: Antalet schemalagda projekt som är associerade med det specifika andra filtret.</li></ul></li></ul> |
