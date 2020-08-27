---
description: Med kolumninställningar kan du konfigurera kolumnformatering, av vilka vissa kan vara villkorliga.
title: Kolumninställningar
uuid: 151d66da-04f7-4d0f-985c-4fdd92bc1308
translation-type: tm+mt
source-git-commit: d49e07d14d1b202d9cc12f42d60083c052a1c364
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 23%

---


# [!UICONTROL Column Settings]

[!UICONTROL Column Settings] I kan du konfigurera kolumnformatering, varav vissa kan vara villkorliga.

## Redigera [!UICONTROL Column Settings] {#column-settings}

Åtkomst [!UICONTROL Column Settings], dra en Freeform-tabell till projektet och klicka sedan på redskapsikonen i kolumnrubriken.

![](assets/column_settings.png)

Du kan redigera inställningar **för flera kolumner samtidigt**. Markera bara flera kolumner och klicka på inställningsikonen för någon av dessa kolumner. Alla ändringar du gör gäller för alla kolumner där celler är markerade.

| Element | Beskrivning |
| --- | --- |
| Nummer | Anger om en cell visar/döljer det numeriska värdet för måttet. Om måttet till exempel är Sidvyer är det numeriska värdet antalet sidvyer för radobjektet. |
| Procent | Anger om en cell visar/döljer procentvärdet för måttet. Om måttet t.ex. är Sidvyer är procentvärdet antalet sidvyer för radobjektet delat med den totala sidvyn för kolumnen.  Anmärkning: Vi kan visa procenttal som är större än 100 procent, för att vara mer exakta. Vi flyttar också det övre gränsvärdet till 1 000 procent för att se till att kolumnerna kan växa i för stora bredder. |
| Anomalies | Anger om avvikelseidentifiering körs på värdena i den här kolumnen. |
| Figursätt rubriktext | Gör att du kan figursätta rubriktexten i Freeform-tabeller för att göra rubrikerna mer läsbara och tabellerna mer delbara. Detta är användbart för .pdf-återgivning och för mått med långa namn. Aktiverad som standard. |
| Tolka noll som inget värde | För celler med värdet 0 anger du om en 0-cell eller en tom cell ska visas. Detta är användbart när du tittar på data för varje dag i en månad, och några dagar har inte inträffat än.  I stället för att visa 0:s för framtida datum kan tomma celler visas i stället. Även den här inställningen respekteras (dvs. de visar inte en linje eller stapel med 0 värden när den här inställningen är markerad). |
| Bakgrund | Anger om en cell visar/döljer all cellformatering, inklusive stapeldiagram och villkorlig formatering. |
| Stapeldiagram | Visar ett vågrätt stolpdiagram som representerar cellens värde i förhållande till totalvärdet för kolumnen. |
| Villkorsstyrd formatering | Se avsnittet nedan. |
| Förhandsgranskning av tabellcell | Visar en förhandsvisning av hur varje cell visas med de aktuella formateringsalternativen. |

## Villkorsstyrd formatering {#conditional-formatting}

Med villkorlig formatering används formatering för övre, mellersta och nedre gränser som du kan definiera. Tillämpning av villkorsstyrd formatering (färger osv.) i Freeform-tabeller aktiveras också automatiskt vid indelningar, såvida inte &quot;Anpassade&quot; gränser väljs.

![](assets/conditional-formatting.png)

| Element | Beskrivning |
| --- | --- |
| Villkorsstyrd formatering | Använder följande färger på celler baserat på datavärden: <ul><li>Grön: höga värden</li><li>Gul: mittpunktsvärden</li><li>Röd: låga värden</li></ul> <br> Om du ersätter ett mått i tabellen återställs gränserna för villkorsstyrd formatering. Om du ersätter ett mätvärde räknas gränserna för den kolumnen om (där ett mätvärde finns på X-axeln och ett mått på Y-axeln). |
| Använd procentgränser | Ändra gränsintervallet så att det baseras på procentvärden i stället för absoluta värden. Det här fungerar för mått som endast är procentuellt baserade (t.ex. studsfrekvens) samt för mått som har en siffra och en procentsats (t.ex. Sidvyer). |
| Automatiskt genererad | Beräkna automatiskt övre/mellersta/nedre gränser baserat på data. Den övre gränsen är det största värdet i den här kolumnen. Den undre gränsen är det lägsta och mittpunkten är medelvärdet av de övre och nedre gränserna. |
| Anpassad | Tilldela manuellt övre/mellersta/nedre gränser. Då får du den flexibilitet du behöver för att avgöra när ett kolumnvärde blir bra, medelbra eller dåligt. |

## Använd en attributmodell som inte är standard {#attribution}

Stöd för Analysis Workspace [tilldelning](../../attribution/overview.md) för nästan alla metriska egenskaper.

1. Klicka på ikonen Inställningar (växel) i kolumnen Frihandstabell.

   ![Kryssruta för attribut](assets/attribution-checkbox.png)

1. Under **[!UICONTROL Data Settings]**, kontrollera **[!UICONTROL Use non-default attribution model]**. Mer information om olika tilldelningsmodeller finns i [Attributmodeller](../../attribution/models.md).

   ![Välj attributmodell](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Hantera datakällor](/help/analysis-workspace/visualizations/t-sync-visualization.md)

