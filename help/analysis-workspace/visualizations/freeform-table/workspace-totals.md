---
description: Hur summor för arbetsytan beräknas.
title: Summor för arbetsyta
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 1%

---

# Summor för arbetsyta

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

I frihandstabeller visas en summeringsrad på varje uppdelningsnivå och kan visa två summor:

* **[!UICONTROL Grand Total]** (antal grå &#39;utanför&#39;) - det här totala antalet representerar alla träffar som har samlats in. När ett filter används på panelnivå eller i friformstabellen justeras det totala värdet så att alla träffar som matchar segmentvillkoren visas.
* **[!UICONTROL Table Total]** (svart tal) - den här summan är vanligtvis lika med eller en delmängd av  [!UICONTROL Grand Total]. Alla tabellfilter som används i friformstabellen, inklusive alternativet [!UICONTROL Include None], visas.

![](assets/total-row.png)

## Visa total inställning

Under **[!UICONTROL Column Settings]** finns det alternativ för **[!UICONTROL Show Totals]** och **[!UICONTROL Show Grand Total]**. Om de här inställningarna inte är markerade tas summorna bort från tabellen. Detta kan vara önskvärt om summorna inte är rimliga, t.ex. i vissa [beräknade måttscenarier](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html).

![](assets/column-settings-total.png)

## Inställningar för totalt antal statiska rader

[Statiska ](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) radsummor fungerar annorlunda och styrs under  **[!UICONTROL Row Settings]**.

* **[!UICONTROL Show sum of current rows as the total]** - här visas en summering av raderna i tabellen på klientsidan, vilket innebär att summan inte kommer att  **** dubblera mätvärden som besök eller besökare.
* **[!UICONTROL Show Grand Total]** - detta visar en summa på serversidan, vilket innebär att summan kommer att ta bort dubbletter av statistik som besök eller besökare.

![](assets/static-rows.png)

## Frågor och svar

| Frågor | Svar |
|---|---|
| Vilken summa är procentsatserna för gråa kolumner baserade på? | Detta beror på **[!UICONTROL Percentages]**-inställningsvalet under **[!UICONTROL Row Settings]**:<ul><li>Beräkna procentandelar per kolumn - Det här är standardinställningen. Procentsatserna baseras på tabellsumman.</li><li>Beräkna procentandelar per rad - Procentsatserna baseras på totalsumman.</li></ul> |
| Hur påverkar inställningen **[!UICONTROL Include Unspecified (None)]** summorna? | Om inställningen **[!UICONTROL Include Unspecified (None)]** inte är markerad tas raden Inget/Ospecificerad bort från tabellen, Tabellsumma, och utförs på alla beräknade mått som använder [&#39;Total&#39; metric-typer](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| När anpassade tabellfilter tillämpas på en frihandstabell, gör jag då alla mina beräknade värden och villkorsstyrda formateringskonton för filtret? | Inte just nu. **[!UICONTROL Include Unspecified (None)]** tas med i beräkningen, men anpassade tabellfilter påverkar inte följande:<ul><li>Kolumnens max/min-intervall som villkorsstyrd formatering använder ser ut över alla data.</li><li>Beräknade mätvärden som utnyttjar **[!UICONTROL Grand Total]** mätningstyper.</li><li>Beräknade mätvärden med funktioner som beräknas över rader i en friformstabell, t.ex. kolumnsumma, kolumnmax, kolumnmin, antal, medel, medel, medel, percentil, kvartil, radantal, standardavvikelse, varians, ackumulerat, kumulativt genomsnitt, regressionsvarianter, T-poäng, T-test, Z-poäng, Z-test, Z-test.</li></ul> |
| I Beräknade mått, vad återspeglar måtttypen **[!UICONTROL Grand Total]**? | **[!UICONTROL Grand Total]** fortsätter att referera till  **[!UICONTROL Grand Total]** och reflekterar inte filter som används i en tabell eller i  **[!UICONTROL Table Total]**. |
| Vilken summa visas när data kopieras och klistras in från en frihandstabell eller hämtas via CSV? | Den totala raden återspeglar endast **[!UICONTROL Table Total]** och respekterar inställningen för kolumnen **[!UICONTROL Show Totals]**. |
