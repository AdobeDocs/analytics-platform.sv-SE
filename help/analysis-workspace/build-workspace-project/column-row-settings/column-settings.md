---
description: Med kolumninställningar kan du konfigurera kolumnformatering, som vissa kan vara villkorliga.
title: Kolumninställningar
uuid: 151d66da-04f7-4d0f-985c-4fdd92bc1308
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 25%

---


# Kolumninställningar

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Med kolumninställningar kan du konfigurera kolumnformatering, som vissa kan vara villkorliga.

## Kolumninställningar {#section_C5A9C13553BF4BFDAD7FACE0139AECA3}

Du öppnar [!UICONTROL Column Settings]genom att dra en friformstabell till projektet och sedan klicka på kugghjulsikonen i kolumnrubriken.

![](assets/column_settings.png)

Du kan redigera inställningar **för flera kolumner samtidigt**. Markera bara flera kolumner och klicka på inställningsikonen för någon av dessa kolumner. Alla ändringar du gör gäller för alla kolumner där celler är markerade.

| Element | Beskrivning |
|--- |--- |
| Nummer | Avgör om en cell visar/döljer det numeriska värdet för måttet. Om måttet till exempel är Sidvyer är det numeriska värdet antalet sidvyer för radobjektet. |
| Procent | Avgör om en cell visar/döljer procentvärdet för måttet. Om måttet till exempel är Sidvyer är procentvärdet antalet sidvyer för radobjektet delat med de totala sidvyerna för kolumnen.  Obs!  Vi kan visa procenttal större än 100 % för att vara mer korrekta. Vi flyttar också det övre gränsvärdet till 1 000 % för att säkerställa att kolumnerna kan växa i för stora bredder. |
| Anomalier | Avgör om avvikelseidentifiering körs på värdena i den här kolumnen. |
| Radbryt rubriktext | Gör att du kan radbryta rubriktexten i frihandstabeller så att rubrikerna blir mer läsbara och tabellerna mer delbara. Detta är användbart för .pdf-återgivning och för mått med långa namn. Aktiverat som standard. |
| Tolka noll som inget värde | För celler med värdet 0 anger om en 0-cell eller en tom cell ska visas. Det här är användbart när du tittar på data för varje dag i en månad, och vissa dagar har inte inträffat än.  I stället för att visa 0 för framtida datum kan tomma celler visas i stället. Diagram följer även den här inställningen (d.v.s. de visar inte en linje eller en stapel med 0 värden när den här inställningen är markerad). |
| Bakgrund | Anger om en cell visar/döljer all cellformatering, inklusive stapeldiagrammet och villkorsstyrd formatering. |
| Stolpdiagram | Visar ett vågrätt stolpdiagram som representerar cellens värde i förhållande till totalvärdet för kolumnen. |
| Villkorsstyrd formatering | Se avsnittet nedan. |
| Förhandsgranskning av tabellcell | Visar en förhandsvisning av hur varje cell visas med de valda formateringsalternativen. |


## Conditional formatting {#section_3DD847151DA14914888A70FC4FD7BDFB}

Villkorsstyrd formatering tillämpar formatering på övre, mellersta och nedre gränser som du kan definiera. Om du använder villkorsstyrd formatering (färger o.s.v.) i frihandstabeller aktiveras även automatiskt vid uppdelning, såvida inte &quot;Anpassade&quot; gränser har valts.

![](assets/conditional-formatting.png)

| Element | Beskrivning |
|--- |--- |
| Villkorsstyrd formatering | Använder följande färger på celler baserat på datavärden: <ul><li>Grön: höga värden</li><li>Gul: mittpunktsvärden</li><li>Röd: låga värden</li></ul><br>Om du ersätter ett mått i tabellen återställs gränserna för villkorsstyrd formatering. Om du ersätter ett mätvärde räknas gränserna för den kolumnen om (där ett mätvärde finns på X-axeln och ett mått på Y-axeln). |
| Använd procentgränser | Används för att använda övre, mellersta och nedre gränser baserat på procentvärden för varje mätvärde. Detta fungerar för mätvärden som endast är procentbaserade (som Studsfrekvens) samt för mätvärden som har ett antal och ett procenttal (som sidvyer). |
| Automatiskt genererad | Genererar automatiskt gränser för villkorsstyrd formatering. Den övre gränsen är det största värdet i den här kolumnen. Den undre gränsen är det lägsta och mittpunkten är medelvärdet av de övre och nedre gränserna. |
| Anpassad | Du kan tilldela värden för fälten Övre, Mittpunkt och Nedre manuellt för villkorlig formatering. Då får du den flexibilitet du behöver för att avgöra när ett kolumnvärde blir bra, medelbra eller dåligt. |
| Förhandsgranskning av tabellcell | Visar en förhandsvisning av hur varje cell visas med de valda formateringsalternativen. |

## Använd en attribueringsmodell som inte är standard

Analysis Workspace stöder [attribuering](../../attribution/overview.md) för nästan alla mätvärden.

1. Klicka på ikonen Inställningar (kugghjulet) i en kolumn i frihandstabellen.

   ![Kryssrutan Attribut](assets/attribution-checkbox.png)

2. Under **[!UICONTROL Data Settings]**, kolla **[!UICONTROL Use non-default attribution model]**. Mer information om olika attribueringsmodeller finns i [Attributmodeller](../../attribution/models.md).

   ![Välj attribueringsmodell](assets/attribution-select.png)


>[!MORELIKETHIS]
>
>* [Hantera datakällor](/help/analysis-workspace/visualizations/t-sync-visualization.md)

