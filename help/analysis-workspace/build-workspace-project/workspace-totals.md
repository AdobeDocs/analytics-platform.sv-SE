---
description: Hur arbetsytans totaler beräknas.
title: Arbetsytesummor
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 1%

---


# Arbetsytesummor

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

I Freeform-tabeller visas en total rad på varje uppdelningsnivå och kan visa två summor:

* **[!UICONTROL Grand Total]** (Grå &#39;out of&#39;-nummer) - denna summa representerar alla träffar som har samlats in, ibland kallade &#39;report suite total&#39;. När ett segment används antingen på panelnivå eller i frihandstabellen justeras det totala segmentet så att det återspeglar alla träffar som matchar segmentkriterierna.
* **[!UICONTROL Table Total]** (svart tal) - denna summa är vanligtvis lika med eller en delmängd av [!UICONTROL Grand Total]. Den visar alla tabellfilter som används i frihandstabellen, inklusive [!UICONTROL Include None] alternativ.

![](assets/total-row.png)

## Visa total inställning

Under **[!UICONTROL Column Settings]** finns det alternativ för **[!UICONTROL Show Totals]** och **[!UICONTROL Show Grand Total]**. Om de här inställningarna är avmarkerade tas summorna bort från tabellen. Detta kan vara önskvärt i fall där totalsummor inte är meningsfulla, t.ex. i vissa [Beräknade metriska scenarier](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html).

![](assets/column-settings-total.png)

## Totalt antal statiska rader

[Statisk rad](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) summor beter sig annorlunda och kontrolleras under **[!UICONTROL Row Settings]**.

* **[!UICONTROL Show sum of current rows as the total]** - detta visar en summa av raderna i tabellen på klientsidan, vilket innebär att summan av **inte** Avduplicerade mått som besök eller besökare.
* **[!UICONTROL Show Grand Total]** - Detta visar en summa på serversidan, vilket innebär att summan kommer att dubblera mått som besök eller besökare.

![](assets/static-rows.png)

## Frågor och svar

| Frågor | Svar |
|---|---|
| Vilket &quot;totalt&quot; är de grå kolumnprocenten baserat på? | Detta beror på **[!UICONTROL Percentages]** ange markering under **[!UICONTROL Row Settings]**:<ul><li>Beräkna procentandelar per kolumn - Detta är standardinställningen. Procenttalen baseras på totalsumman för tabellen.</li><li>Beräkna procentandelar per rad - Procentsatser baseras på totalsumman.</li></ul> |
| Hur **[!UICONTROL Include Unspecified (None)]** Vill du ställa in effektsummor? | Om **[!UICONTROL Include Unspecified (None)]** inställningen är avmarkerad, raden Ingen/ospecificerad tas bort från tabellen, Tabellsumma, och fortsätter till alla beräknade mått som använder [Totala metatyper](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| När anpassade tabellfilter tillämpas på en frihandstabell, gör då alla mina beräknade mått och villkorliga formateringskonto för filtret? | Inte för tillfället. **[!UICONTROL Include Unspecified (None)]** kommer att beaktas, men anpassade tabellfilter påverkar inte följande:<ul><li>Kolumnens max/min-intervall som villkorsstyrd formatering använder ser ut över alla data.</li><li>Beräknade mått som ger hävstångseffekt **[!UICONTROL Grand Total]** metriska typer.</li><li>Beräknade mått med funktioner som beräknas över rader i en friformstabell - d.v.s. kolumnsumma, kolumnmax, kolumnmin, antal, medel, medel, medel, medel, percentile, kvartiltal, radantal, standardavvikelse, varians, ackumulerat, ackumulerat medelvärde, regressionsvarianter, T-poäng, T-test, Z-poäng, Z-test.</li></ul> |
| Vad gör **[!UICONTROL Grand Total]** spegla metertyp? | **[!UICONTROL Grand Total]** fortsätter att hänvisa till **[!UICONTROL Grand Total]** och inte återspeglar filter som används i en tabell eller i **[!UICONTROL Table Total]**. |
| Hur mycket visas när data kopieras och klistras in från ett frihandsregister eller laddas ned via CSV? | Den totala raden återspeglar **[!UICONTROL Table Total]** endast och respekterar kolumnen **[!UICONTROL Show Totals]** inställning. |

