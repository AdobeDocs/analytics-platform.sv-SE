---
description: Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen.
title: Radinställningar
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 0%

---

# Radinställningar


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rad- och kolumninställningar i en frihandstabell](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen. Om du vill komma åt tabellradsinställningar väljer du ![Inställning](/help/assets/icons/Setting.svg) **[!UICONTROL Settings]** bredvid en dimension, ett segment, ett mått, en tidsperiod eller en uppdelning inom vart och ett av dessa objekt.

![Frihandstabell som markerar inställningsikonen för mått](assets/row-settings.png)

| Inställning | Beskrivning |
| --- | --- |
| **[!UICONTROL Breakdown by position]** | Som standard är den här inställningen inaktiverad och uppdelningar är fasta på statiska radobjekt. Tänk dig att du har delat upp de tre viktigaste sidobjekten (startsida, sökresultat, utcheckning) efter marknadsföringskanal. Sedan lämnar du projektet och återvänder två veckor senare. När du öppnar projektet igen har de tre översta sidorna ändrats, och nu är startsidan, sökresultaten och utcheckningen de 4-6 översta sidorna istället. Som standard visas dina Marketing Channel-indelningar fortfarande under Hemsida, Sökresultat och Utcheckning, även om de nu finns på raderna 4-6. <br> Däremot delas **Uppdelning efter position** alltid upp i de tre översta objekten, oavsett vad de är. När du öppnar ditt projekt på nytt är Marketing Channel-uppdelningarna kopplade till de tre översta sidorna i tabellen. Och inte till startsidan, sökresultat och utcheckning, som nu finns på raderna 4-6. |
| **[!UICONTROL Percentages]** | **Beräkna procentsatser efter kolumn** (standard): de procentandelar som visas i celler beräknas baserat på kolumnsumman. <br>**Beräkna procentsatser efter rad**: procentsatserna i celler beräknas över raden, till skillnad från nedåt i kolumnen, med totalsumman som nämnare. Den här beräkningen är användbar för att hantera procentsatser. |
| **[!UICONTROL Column totals]** | De här inställningarna är bara tillgängliga för [statiska rader](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Visa som summan av de aktuella raderna** visar en summa av raderna på klientsidan i tabellen, vilket innebär att summan *inte* avduplicerar mått som besök eller personer. <br> **Visa totalsumman** visar en serversidessumma, vilket innebär summan av avduplicerade mått. |

## Ändra radantal

Så här ändrar du antalet rader som visas:

1. Klicka på siffran bredvid **[!UICONTROL Rows]** överst i tabellens första kolumn.

   ![Friformstabell som visar listrutan för antalet rader som visas. 400 rader är markerade.](assets/change-row-count.gif)

1. I listrutan väljer du det antal rader som du vill att tabellen ska visa.


## Snabbmeny

Följande snabbmenyalternativ är tillgängliga när du väljer dimensionshuvudet.

| Alternativ | Beskrivning |
| --- | --- |
| **[!UICONTROL Copy selection to clipboard]** | Kopiera markeringen från visualiseringen till Urklipp. |
| **[!UICONTROL Download items as CSV (*dimensionsnamn *)]** | Ladda omedelbart ned dimensionsobjekten (högst 50 000) av visualiseringen till din lokala enhet. Högst 50 000 dimensionsartiklar för den valda dimensionen. |
| **[!UICONTROL Download selection as CSV]** | Ladda omedelbart ned dimensionsobjekten för visualiseringen till din lokala enhet. |
| **[!UICONTROL Create hyperlink for all dimension items]** | Skapa hyperlänkar för alla dimensionsobjekt. Se [Hyperlänkar för mått i en frihandstabell](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Edit hyperlink for all dimension items]** | Redigera hyperlänkar för alla dimensionsobjekt. Se [Hyperlänkar för mått i en frihandstabell](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remove hyperlink for all dimension items]** | Ta bort hyperlänkar för alla dimensionsobjekt. Se [Hyperlänkar för mått i en frihandstabell](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Delete]** | Tar bort dimensionen från registret. |
| **[!UICONTROL Visualize]** | Visualisera dimensionen med någon av de tillgängliga visualiseringarna. |
| **[!UICONTROL Display only selected rows]** | Visa endast de markerade objekten i visualiseringen. |
| **[!UICONTROL Create annotation from selection]** | Öppna **[!UICONTROL Annotation details]** för att lägga till en anteckning. |


Följande alternativ på snabbmenyn är tillgängliga när du markerar ett eller flera dimensionsobjekt (första kolumnen) eller en eller flera enskilda celler i friformstabellen.

| Alternativ | Beskrivning |
| --- | --- |
| **[!UICONTROL Create hyperlink]** | Skapa en hyperlänk för objektet. Se [Hyperlänkar för mått i en frihandstabell](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Edit hyperlink]** | Redigera en hyperlänk för objektet. Se [Hyperlänkar för mått i en frihandstabell](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remove hyperlink]** | Ta bort en hyperlänk för objektet. Se [Hyperlänkar för mått i en frihandstabell](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Breakdown]** | Dela upp dimensionsobjektet. Välj i listan med **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]**, **[!UICONTROL Segments]** eller **[!UICONTROL Date ranges]**. Alternativ sökning efter en komponent med *Sök*. |
| **[!UICONTROL Delete selected]** | Ta bort markerade rader (objekt). |
| **[!UICONTROL Trend selection]** | Skapa en anpassad linjediagramvisualisering för markeringen. |
| **[!UICONTROL Display only selected rows]** | Visa endast de markerade raderna i visualiseringen. |
| **[!UICONTROL Display all rows]** | Visa alla rader i visualiseringen. |
| **[!UICONTROL Create segment from selection]** | Öppna **[!UICONTROL Segment builder]** för att skapa ett segment från markeringen. |
| **[!UICONTROL Create audience from selection]** | Öppna dialogrutan **[!UICONTROL Create audience]** om du vill skapa en målgrupp utifrån urvalet. |

Följande alternativ på snabbmenyn är tillgängliga när du väljer en kolumnrubrik för mätvärden.

| Alternativ | Beskrivning |
|---|---|
| **[!UICONTROL Create metric from selection]** | Skapa ett nytt mått från det valda måttet. Mått kan vara Medel, Media, Kolumn max, Kolumn min, Kolumnsumma. Du kan också välja Öppna i verktyget för beräknade mått om du vill skapa ett beräknat mått. |
| **[!UICONTROL Add time period column]** | Lägg till en tidsperiodkolumn. Du erbjuds flera alternativ där kalenderintervallet på panelen avgör *datumintervallet*: <li>**[!UICONTROL Prior *datumintervall *till det här datumintervallet]**</li><li>**[!UICONTROL These *datumintervall *till det här datumintervallet]**.</li><li>**[!UICONTROL Custom date range to this date range]**. Öppnar **[!UICONTROL Date range builder]** för att ange datumintervall.</li>Mer information finns i [Datumjämförelse](/help/components/date-ranges/time-comparison.md). |
| **[!UICONTROL Compare time periods]** | Lägger till jämförelsetidsperiodens kolumner. Endast tillgängligt när dimensionen inte är baserad på tid. Du erbjuds flera alternativ som avgör *datumintervallet*: <li>**[!UICONTROL Prior *datumintervall *till det här datumintervallet]**</li><li>**[!UICONTROL Custom date range to this date range]**. Öppnar **[!UICONTROL Date range builder]** för att ange datumintervall.</li>Mer information finns i [Datumjämförelse](/help/components/date-ranges/time-comparison.md). |
| **[!UICONTROL Modify attribution models]** | Ändra kolumnens attribueringsmodell. |
| **[!UICONTROL Compare attribution model]** | Ange en ny distributionsmodell och jämför den med attribueringsmodellen för den valda kolumnen. En ny kolumn läggs till med den nya attributmodellens mått. En ändringskolumn i procent läggs också till för jämförelse. |
| **[!UICONTROL Reset column widths]** | Återställ kolumnbredderna till standardbredden. |
| **[!UICONTROL Create annotation from selection]** | Öppna **[!UICONTROL Annotation details]** för att lägga till en anteckning. |
| **[!UICONTROL Create segment from selection]** | Öppna **[!UICONTROL Segment builder]** för att skapa ett segment från markeringen. |
| **[!UICONTROL Create audience from selection]** | Öppna dialogrutan **[!UICONTROL Create audience]** om du vill skapa en målgrupp utifrån urvalet. |

## Ändra radhöjd

Du kan ange vydensiteten för ett projekt till **[!UICONTROL Compact]**, **[!UICONTROL Comfortable]** och **[!UICONTROL Expanded]**. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/view-density).