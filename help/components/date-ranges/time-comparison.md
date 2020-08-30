---
description: Med datumjämförelse i Analysis Workspace kan du ta vilken kolumn som helst som innehåller ett datumintervall och skapa en vanlig datumjämförelse, t.ex. år över år, kvartal över kvartal, månad över månad osv.
title: Datumjämförelse
uuid: ef18f9d9-b6ad-4859-b7c9-9750ca0df519
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 6%

---


# Datumjämförelse

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Med datumjämförelse i Analysis Workspace kan du ta vilken kolumn som helst som innehåller ett datumintervall och skapa en vanlig datumjämförelse, till exempel: Överår, kvartal, månad över månad osv.

## Jämför tidsperioder

Analysen kräver sammanhang, och ofta tillhandahålls detta sammanhang av en tidigare tidsperiod. Till exempel frågan &quot;Hur mycket bättre/sämre gör vi än vid denna tidpunkt förra året?&quot; är grundläggande för att förstå din verksamhet. Datumjämförelse innehåller automatiskt en &quot;differens&quot;-kolumn som visar procentförändringen jämfört med en angiven tidsperiod.

1. Skapa en Freeform-tabell med alla mått och mått som du vill jämföra över en tidsperiod.
1. Högerklicka på en tabellrad och välj **[!UICONTROL Compare Time Periods]**.

   ![](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >Det här högerklicksalternativet är inaktiverat för metriska rader, datumintervallrader och tidsdimensionsrader.

1. Beroende på hur du har ställt in tabellens datumintervall har du följande alternativ för jämförelse:

   | Alternativ | Beskrivning |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Jämför med vecka/månad/osv. omedelbart före detta datumintervall. |
   | **[!UICONTROL This week/month/quarter/year last year]** | Jämför med samma datumintervall för ett år sedan. |
   | **[!UICONTROL Select range]** | Gör att du kan välja ett anpassat datumintervall. |

   >[!NOTE]
   >
   >När du väljer ett anpassat antal dagar, till exempel den 7 oktober - den 20 oktober (ett 14-dagarsintervall), får du endast två alternativ: **[!UICONTROL Prior 14 days before this date range]** och **[!UICONTROL Select range]**.

1. Den resulterande jämförelsen ser ut så här:

   ![](assets/compare-time-result.png)

   Raderna i kolumnen Procent ändring visas med rött för negativa värden och grönt för positiva värden.

1. (Valfritt) Som i alla andra arbetsyteprojekt kan du skapa visualiseringar baserade på dessa tidsjämförelser. Här visas t.ex. ett stapeldiagram:

   ![](assets/compare-time-barchart.png)

   Observera att om du vill visa procentändringen i stapeldiagrammet måste du ha [!UICONTROL Percentages] ange incheckad [!UICONTROL Visualization Settings].

## Lägg till en tidsperiodkolumn för jämförelse

Nu kan du lägga till en tidsperiod i varje kolumn i en tabell, så att du kan lägga till en annan tidsperiod än den som du har angett för kalendern. Det är ett annat sätt att jämföra datum.

1. Högerklicka på en kolumn i tabellen och välj **[!UICONTROL Add Time Period Column]** ![](assets/add-time-period-column.png)

1. Beroende på hur du har ställt in tabellens datumintervall har du följande alternativ för jämförelse:

   | Alternativ | Beskrivning |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Lägger till en kolumn med veckan/månaden/osv. omedelbart före detta datumintervall. |
   | **[!UICONTROL This week/month/quarter/year last year]** | Lägger till samma datumintervall för ett år sedan. |
   | **[!UICONTROL Select range]** | Gör att du kan välja ett anpassat datumintervall. |

   >[!NOTE]
   >
   >När du väljer ett anpassat antal dagar, till exempel den 7 oktober - den 20 oktober (ett 14-dagarsintervall), får du endast två alternativ: **[!UICONTROL Prior 14 days before this date range]** och **[!UICONTROL Select range]**.

1. Tidsperioden infogas ovanpå den markerade kolumnen:

   ![](assets/add-time-period-column2.png)

1. Du kan lägga till så många tidskolumner som du vill, samt blanda och matcha olika datumintervall:

   ![](assets/add-time-period-column4.png)

1. Dessutom kan du sortera efter varje kolumn, vilket ändrar ordningen på dagar beroende på vilken kolumn du sorterar på.

## Justera kolumndatum så att de börjar på samma rad {#section_5085E200082048CB899C3F355062A733}

Med en ny inställning för alla tabeller kan du **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**. &quot;Gäller för hela tabellen&quot; innebär att om du t.ex. gör en uppdelning i tabellen och om du ändrar den här inställningen för uppdelningen, ändras inställningen för hela tabellen.

![](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>Den här inställningen är **handikappad** (omarkerat) för alla befintliga projekt och **aktiverad** (Markerat) för alla nya projekt.

Exempel: När du väljer att justera datumen, om du gör en månatlig jämförelse över månad mellan oktober och september 2016, börjar den vänstra kolumnen med oktober 1 och den högra kolumnen börjar med september 1:

![](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->

