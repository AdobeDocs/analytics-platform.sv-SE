---
description: Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen.
title: Radinställningar
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 6%

---


# Radinställningar

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen.

Du kan också använda [högerklicksåtgärder i en tabell](/help/analysis-workspace/visualizations/freeform-table.md) för att hantera markerade rader.

Om du vill komma åt tabellradsinställningarna klickar du på inställningsikonen bredvid en dimension, ett segment, ett mått, en tidsperiod eller en uppdelning i var och en av dessa:

![](assets/row-settings.png)

| Radinställning | Beskrivning |
|--- |--- |
| Datumjämförelser | Justera datum från varje kolumn så att alla börjar på samma rad.   När du väljer att justera datumen, till exempel i en månadsjämförelse mellan oktober och september 2016, börjar den vänstra kolumnen med 1 oktober och den högra kolumnen börjar med 1 september.<br>Inaktiverad som standard. |
| Procenttal | Beräkna procentandelar per rad Tvingar fram friformstabellen för att beräkna cellprocenten över raden i stället för nedåt i kolumnen. Detta är särskilt användbart för att hantera procentsatser.<br>Aktiveras som standard när du använder ikonen Visualisera. |
| Kolumnsummor | De här inställningarna visas bara med [statiska rader](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (när du har markerat en begränsad uppsättning med objekt), inte med dynamiska rader (d.v.s. när du släpper i en dimension som visar alla objekt).<ul><li>**[!UICONTROL Show sum of current rows as the total]** - här visas en summa av raderna i tabellen på klientsidan, vilket innebär att summan **inte** kan deduplicera mått som besök eller besökare.</li><li>**[!UICONTROL Show Grand Total]** - detta visar en summa på serversidan, vilket innebär att summan kommer att ta bort dubbletter av statistik som besök eller besökare.</li></ul> |
| Uppdelningar | **[!UICONTROL Breakdown by position]**: Du kan utföra uppdelningar baserat på en fast plats i en frihandstabell. Du kan till exempel ange att de sju översta raderna alltid ska brytas ned.<br>(Tidigare var listan med värden i neddelningen &quot;låst&quot;. Detta ledde till en situation där du, om du t.ex. bröt ned Datum för sida, fick en lista över de 50 översta sidorna för det valda datumintervallet. Om du sparade den rapporten och sedan körde den igen en månad senare hade de 50 översta sidorna förmodligen ändrats. Analysis Workspace använder dock resultaten från den ursprungliga uppdelningen och returnerar samma sidor, men med den aktuella månaden som datumintervall.)<br>Så här utför du uppdelningar baserade på en fast plats: 1. Dela upp några av raderna i tabellen. 2. Klicka på ikonen Inställningar (kugghjulet) bredvid tabellraden som du vill ha i fast position. 3. Markera kryssrutan bredvid Uppdelning efter position. 4. Ändra sorteringsordningen eller datumintervallet och lägg märke till att uppdelningarna nu är knutna till radpositionen, inte till de hårdkodade raderna.<br>Inaktiverad som standard. |