---
description: Lär dig använda datumjämförelse i Analysis Workspace, där du kan skapa en vanlig datumjämförelse för alla kolumner som innehåller ett datumintervall.
title: Datumjämförelse
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
source-git-commit: 5a9cb206076755d5b34a8ec9108ca88a9468bfe3
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Datumjämförelse

Med datumjämförelsen i Analysis Workspace kan du ta vilken kolumn som helst som innehåller ett datumintervall och skapa en gemensam datumjämförelse, till exempel: år-över-år, kvartal-över-kvartal, månad-över-månad och så vidare.

## Jämför tidsperioder

Analysen kräver ett sammanhang, och ofta tillhandahålls detta sammanhang av en tidigare tidsperiod. Frågan *Hur mycket bättre eller sämre gör du nu jämfört med den här gången förra året?* är grundläggande för att förstå din verksamhet. Datumjämförelse innehåller automatiskt en *differenskolumn*, som visar den procentuella ändringen jämfört med en angiven tidsperiod.

1. Skapa en [frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) med alla mått och mått som du vill jämföra under en tidsperiod.
1. Ställ in tidsperioden på panelen eller kolumnen för att bestämma tidsramen för jämförelsen och om det är en rullande eller fast tidsjämförelse.

   Om du vill skapa en jämförelse av rullande tid anger du panelens eller kolumnens datumintervall till ett rullande datumintervall (till exempel **[!UICONTROL Last 7 days]**, **[!UICONTROL Last 30 days]**).

   Om du vill skapa en tidsjämförelse ställer du in ett anpassat datumintervall för panelen eller kolumnen.

1. Öppna snabbmenyn för en tabellrad och välj **[!UICONTROL Compare time periods]**.

   ![Tabellrad med Jämför tidsperioder markerad](assets/compare-time.png)

   >[!NOTE]
   >
   >Det här snabbmenyalternativet är inaktiverat för måttrader, datumintervallrader och tidsdimensioneringsrader.

1. Beroende på hur du har angett tabellens datumintervall kan du göra följande jämförelser:

   | Alternativ | Beskrivning |
   |---|---|
   | **[!UICONTROL Prior *x *veckor/månader/kvartal/år till detta datumintervall]** | Jämför med det valda datumintervallet omedelbart före det här datumintervallet. |
   | **[!UICONTROL These x weeks / months / quarters / years last year to this date range]** | Jämför med samma datumintervall för ett år sedan. |
   | **[!UICONTROL Custom date range to this date range]** | Här kan du definiera ett anpassat datumintervall. |

   >[!NOTE]
   >
   >När du väljer ett anpassat antal dagar, till exempel 7 oktober-20 oktober (ett 14-dagarsintervall), får du bara två alternativ: **[!UICONTROL Prior 14 days before this date range]** och **[!UICONTROL Custom date range to this date range]**.

1. Jämförelsen ser ut så här:

   ![Frihandsregister som visar en jämförelse av datumintervall och procentuell ändring.](assets/compare-time-result.png)

   Rader i kolumnen Procent av ändring visas som röda för negativa värden och gröna för positiva värden.

## Lägg till en tidsperiodkolumn för jämförelse

Nu kan du lägga till en tidsperiod för varje kolumn i en tabell, så att du kan lägga till en annan tidsperiod än den som du har angett för kalendern.

1. Högerklicka på en kolumn i tabellen och välj **[!UICONTROL Add time period column]**.

   ![](assets/add-time-period-column.png)

1. Beroende på hur du har angett tabellens datumintervall kan du göra följande jämförelser:

   | Alternativ | Beskrivning |
   |---|---|
   | **[!UICONTROL Prior *x *veckor/månader/kvartal/år till detta datumintervall]** | Lägg till en kolumn med veckan/månaden/osv. omedelbart före detta datumintervall. |
   | **[!UICONTROL These *x *veckor/månader/kvartal/år förra året till detta datumintervall]** | Lägg till samma datumintervall för ett år sedan. |
   | **[!UICONTROL Custom date range to this date range]** | Gör att du kan skapa ett anpassat datumintervall. |

   >[!NOTE]
   >
   >När du väljer ett anpassat antal dagar, till exempel 7 oktober-20 oktober (ett 14-dagarsintervall), får du bara två alternativ: **[!UICONTROL Prior 14 days before this date range]** och **[!UICONTROL Custom date range to this date range]**.

1. Tidsperioden infogas ovanpå kolumnen som du valde:

   ![Frihandstabell med förekomster för den aktuella kalenderperioden och föregående kalendermånad.](assets/add-time-period-column2.png)

1. Du kan lägga till så många tidskolumner du vill och blanda och matcha olika datumintervall:

1. Dessutom kan du sortera efter varje kolumn, vilket ändrar ordningen på dagar beroende på vilken kolumn du sorterar efter.

## Justera kolumndatum så att de startar på samma rad

Du kan justera datumen från varje kolumn så att alla börjar på samma rad.

Du kan till exempel göra en jämförelse dag för dag för den sista veckan (som slutar den 5 oktober 2024) och den föregående veckan. Som standard börjar den vänstra kolumnen med 22 september och den högra kolumnen med 29 september.

![Inte justerade datum](assets/not-align-dates.png)

Du kan aktivera **[!UICONTROL Align dates from each column to all start on the same row]** i [Inställningar](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) för visualisering av frihandstabellen för att justera kolumndatum så att de startar på samma rad.

![](assets/align-dates.png)

Tänk på följande när du använder det här alternativet:

* Den här inställningen är aktiverad som standard för alla nya projekt.

* Den här inställningen gäller för hela tabellen. Om du till exempel ändrar den här inställningen för en uppdelning i tabellen, används inställningen på hela tabellen.

