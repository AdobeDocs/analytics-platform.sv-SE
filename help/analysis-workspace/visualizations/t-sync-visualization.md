---
description: Med synkronisering av visualiseringar kan du styra vilken datatabell eller datakälla som motsvarar en visualisering.
keywords: Analysis Workspace;Synkronisera visualisering med datakälla
title: Hantera datakällor
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: 8f9c03607130bdeaf6cb7a32d8dd465712a47ea5
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Hantera datakällor {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Lås markering"
>abstract="Aktivera den här inställningen för att låsa visualiseringen till de valda positionerna eller de valda objekten i datakällan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Visa tabell"
>abstract="Om du väljer **[!UICONTROL Show table]** genereras en ny datakälla för den aktuella visualiseringen, som är skild från den ursprungliga datakällan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Visa tabell"
>abstract="Välj **[!UICONTROL Show table]** om du vill generera en ny datakälla för den aktuella visualiseringen, som är skild från den ursprungliga datakällan."

<!-- markdownlint-enable MD034 -->



Med synkronisering av visualiseringar kan du styra vilken datatabell eller datakälla som motsvarar en visualisering.

>[!TIP]
>
>Du kan se vilka visualiseringar som är relaterade till färgen ![StatusOrange](/help/assets/icons/StatusOrange.svg) bredvid titeln för visualiseringar. Matchande färger innebär att visualiseringar baseras på samma datakälla.
>

Du kan visa eller dölja datakällan. Du kan även låsa markeringen till markerade positioner eller markerade objekt. Dessa inställningar avgör hur visualiseringen ändras (eller inte ändras) när nya data kommer in.

![Dialogrutan Data Source med alternativen som beskrivs i nästa avsnitt.](assets/lock-selection.png)


| Alternativ | Beskrivning |
|--- |--- |
| **[!UICONTROL Data source]** | Välj den datakälla som visualiseringen baseras på i listrutan. |
| **[!UICONTROL Linked visualizations]** | Visar alla länkade visualiseringar. Gäller datakällan (friformstabell). |
| **[!UICONTROL Show data source]** | Gör att du kan visa eller dölja den datakälla (frihandstabell) som motsvarar visualiseringen. |
| **[!UICONTROL Lock Selection]** | Välj det här alternativet om du vill låsa visualiseringen ![LockClosed](/help/assets/icons/LockClosed.svg) till de data som är markerade i motsvarande datatabell. När den är aktiverad väljer du mellan:  <ul><li>**Markerade positioner**: Visualiseringen är låst för de **positioner** som är markerade i motsvarande datatabell. Dessa positioner fortsätter att visualiseras, även om de specifika objekten i de här positionerna ändras (till exempel på grund av sortering eller filtrering). Välj till exempel det här alternativet om du alltid vill visa de fem främsta kampanjnamnen som anges i datakällan i den här visualiseringen. Oavsett vilka kampanjnamn som visas.</li> <li>**Markerade objekt**: Visualiseringen är låst för de specifika **objekt** som är markerade i motsvarande datatabell. Dessa objekt fortsätter att visualiseras, även om de ändrar sin rankning bland objekt i tabellen. Välj till exempel det här alternativet om du alltid vill visa samma fem specifika kampanjnamn som finns i datakällan i den här visualiseringen. Oavsett hur kampanjnamnen rankas.</li></ul>Om visualiseringen är låst till data som inte längre är synliga i den anslutna datatabellen, kan du generera en ny tabell. Välj **[!UICONTROL Show table]** om du vill generera en ny datakälla för den aktuella visualiseringen, som är skild från den ursprungliga datakällan. |
