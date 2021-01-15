---
description: Med synkronisering av visualiseringar kan du styra vilken datatabell eller datakälla som motsvarar en visualisering.
keywords: Analysis Workspace;Synchronize visualization with data source
title: Hantera datakällor
translation-type: tm+mt
source-git-commit: 3dc9d0d0a1f65a4205120895c35aa508f080c25d
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 4%

---


# Hantera datakällor

Med synkronisering av visualiseringar kan du styra vilken datatabell eller datakälla som motsvarar en visualisering.

**Tips:** Du kan se vilka visualiseringar som är relaterade till färgen på punkten bredvid titeln. Matchande färger innebär att visualiseringar baseras på samma datakälla.

Genom att hantera en datakälla kan du visa datakällan eller låsa markeringen. Dessa inställningar avgör hur visualiseringen ändras (eller inte ändras) när nya data kommer in.

1. [Skapa ett ](/help/analysis-workspace/home.md) projekt med en datatabell och en  [visualisering](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. Markera cellerna (datakällan) som du vill koppla till visualiseringen i datatabellen.
1. I visualiseringen klickar du på punkten bredvid titeln för att visa dialogrutan **[!UICONTROL Data Source]**. Välj **[!UICONTROL Show Data Source]** eller **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synkronisering av en visualisering till en tabellcell skapar en ny (dold) tabell och färgkodar den synkroniserade visualiseringen med den tabellen.

| Element | Beskrivning |
|--- |--- |
| [!UICONTROL Linked Visualizations] | Om det finns visualiseringar kopplade till en frihands- eller kohorttabell öppnas den övre vänstra punkten för att visa de anslutna visualiseringarna och har kryssrutan &quot;visa&quot; för att visa/dölja tabellen.  När du hovrar markeras den länkade visualiseringen och du klickar på den. |
| [!UICONTROL Show Data Source] | Gör att du kan visa (genom att aktivera kryssrutan) eller dölja (genom att inaktivera) den datatabell som motsvarar visualiseringen. |
| [!UICONTROL Lock Selection] | Aktivera den här inställningen för att låsa visualiseringen till de data som är markerade i motsvarande datatabell. När det är aktiverat väljer du mellan:  <ul><li>**Markerade positioner**: Välj det här alternativet om du vill att visualiseringen ska förbli låst på de positioner som är markerade i motsvarande datatabell. Dessa positioner kommer även fortsättningsvis att visualiseras, även om de specifika objekten i dessa positioner ändras. Välj till exempel det här alternativet om du alltid vill visa de fem främsta kampanjnamnen i den här visualiseringen, oavsett vilka kampanjnamn som visas i de fem främsta.</li> <li>**Markerade objekt**: Välj det här alternativet om du vill att visualiseringen ska förbli låst för de specifika objekt som är markerade i motsvarande datatabell. Dessa objekt kommer även fortsättningsvis att visualiseras, även om de ändrar sin rankning bland objekt i tabellen. Välj till exempel det här alternativet om du alltid vill visa samma fem specifika kampanjnamn i den här visualiseringen, oavsett var kampanjnamnen rangordnas.</li></ul> |

Arkitekturen skiljer sig från den tidigare på så sätt att Analysis Workspace inte längre skapar en dold tabell som lagrar den låsta markeringen åt dig. Datakällan pekar nu på tabellen som du skapade visualiseringen från.

**Exempel:**

* Du kan skapa en sammanfattningsvisualisering och låsa den till en cell i tabellen som du skapade den från. När du aktiverar Visa datakälla visas exakt var informationen kommer från i tabellen. Källdata blir nedtonade:

   ![](assets/data-source2.png)>
* Du kan lägga till många visualiseringar och hämta dem från olika celler i samma tabell, vilket visas här. Tabellen är densamma som i exemplet ovan, men källcellen (och måttet) är annorlunda:

   ![](assets/data-source3.png)>
* Du kan se om det finns några visualiseringar kopplade till en frihand- eller kohorttabell genom att klicka på den övre vänstra punkten (Inställningar för datakälla). Vid hovring markeras den länkade visualiseringen och om du klickar på den kommer du till den.

   ![](assets/linked-visualizations.png)>
