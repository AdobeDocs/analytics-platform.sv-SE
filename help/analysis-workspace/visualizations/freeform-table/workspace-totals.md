---
description: Läs om hur totalsummor i frihandstabeller i Analysis Workspace beräknas.
title: Summor
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 1%

---

# Summor {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Summa"
>abstract="Summan stöds inte för tabeller eller uppdelningar med statiska rader."


I frihandstabeller visas en summeringsrad på varje uppdelningsnivå och kan visa två summor:

![Friformstabell som visar totalsumman och tabellsumman.](assets/total-row.png)

* **[!UICONTROL Table total]** ➊ - Denna summa är vanligtvis lika med eller en delmängd av [!UICONTROL Grand total]. Summan återspeglar alla tabellsegment som används i friformstabellen, inklusive alternativet [!UICONTROL Include None].
* **[!UICONTROL Grand total]** (**[!UICONTROL out of]** *number*) ➋ - Den här summan representerar alla händelser som har samlats in. När ett segment används antingen på panelnivå eller i friformstabellen justeras det totala värdet så att alla händelser som matchar segmentvillkoren återspeglas.




## Visa summor

Under ![Inställning](/help/assets/icons/Setting.svg) **[!UICONTROL Column settings]** finns det alternativ för **[!UICONTROL Show totals]** och **[!UICONTROL Show grand total]**. Om de här inställningarna inte är markerade tas summorna bort från tabellen, vilket kan vara önskvärt om det inte går att använda summorna.


[Statiska radsummor](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) fungerar annorlunda och styrs med ![Inställning](/help/assets/icons/Setting.svg) **[!UICONTROL Row Settings]**.

| Alternativ | Beskrivning |
|---|---|
| **[!UICONTROL Show sum of current rows as the total]** | Visa en summa av raderna i tabellen på klientsidan. Den här summan tar **inte** bort dubbletter av mått som sessioner eller personer. |
| **[!UICONTROL Show grand total]** | Visa en serversidessumma. Den totala mängden avduplicerade mått som sessioner eller personer. |

Se [Dynamiska och statiska dimensionsobjekt i frihandstabeller](column-row-settings/manual-vs-dynamic-rows.md).


## Frågor och svar

| Frågor | Svar |
|---|---|
| Vilka *totalt* är procentsatserna för gråa kolumner baserade på? | Det här *totala*-värdet beror på inställningen **[!UICONTROL Percentages]** under **[!UICONTROL Row Settings]**:<ul><li>Beräkna procentandelar per kolumn - Den här inställningen är standard. Procentsatserna baseras på tabellsumman.</li><li>Beräkna procentandelar per rad - Procentsatserna baseras på totalsumman.</li></ul> |
| Hur påverkar inställningen för **[!UICONTROL Include "No value"]** summorna? | Om inställningen **[!UICONTROL Include "No value"]** inte är markerad tas raden **[!UICONTROL No value]** bort från tabellen, tabellsumman, och fortsätter till alla beräknade mått som använder [*Total*-mätningstyper](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| När anpassade tabellsegment används i en frihandstabell, gör jag alla mina beräknade värden och villkorsstyrda formateringskonton för segmentet? | Inte just nu. **[!UICONTROL Include "No value"]** är ett konto, men anpassade tabellsegment påverkar inte följande:<ul><li>Kolumnens maximala/minsta intervall som villkorsstyrd formatering använder ser ut över alla data.</li><li>Beräknade mätvärden som utnyttjar **[!UICONTROL Grand total]** mätningstyper.</li><li>Beräknade mätvärden med funktioner som beräknas över rader i en friformstabell: Kolumnsumma, Kolumnmax, Kolumnmin, Antal, Medel, Percentile, Kvarnvärde, Radantal, Standardavvikelse, Varians, Ackumulativt, Ackumulativt genomsnitt, Regressionsvarianter, T-poäng, T-test, Z-poäng och Z-test.</li></ul> |
| I Beräknade mått, vad återspeglar den **[!UICONTROL Grand total]**-metriska typen? | **[!UICONTROL Grand total]** fortsätter att referera till **[!UICONTROL Grand total]** och speglar inte segment som används i en tabell eller **[!UICONTROL Table total]**. |
| Vilken summa visas när data kopieras och klistras in från en frihandstabell eller hämtas via CSV? | Den totala raden återspeglar endast **[!UICONTROL Table total]** och respekterar inställningen för kolumnen **[!UICONTROL Show totals]**. |
