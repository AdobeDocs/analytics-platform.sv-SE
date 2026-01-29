---
title: Omformningar
description: Omvandlingar använder sig av exempel för BI-tillägget i olika BI-verktyg i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1473'
ht-degree: 0%

---

# Omformningar


Du vill förstå omformningarna av Customer Journey Analytics-objekt som dimensioner, mått, filter, beräknade värden och datumintervall med de olika BI-verktygen.

+++ Customer Journey Analytics

I Customer Journey Analytics definierar du i en [datavy](/help/data-views/data-views.md), som och hur komponenter i dina datauppsättningar visas som [dimensions](/help/components/dimensions/overview.md) och [metrics](/help/components/apply-create-metrics.md). Definitionen av mått och mått visas för BI-verktygen med BI-tillägget.
Du använder komponenter som [Filter](/help/components/segments/seg-overview.md), [Beräknade mätvärden](/help/components/calc-metrics/calc-metr-overview.md) och [Datumintervall](/help/components/date-ranges/overview.md) som en del av dina Workspace-projekt. Dessa komponenter visas också för BI-verktygen med BI-tillägget.

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](connect-and-validate.md) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Customer Journey Analytics-objekten är tillgängliga i rutan **[!UICONTROL Data]** och hämtas från tabellen som du har valt i Power BI Desktop. Exempel: **[!UICONTROL public.cc_data_view]**. Tabellnamnet är detsamma som det externa ID som du har definierat för datavyn i Customer Journey Analytics. Datavy med till exempel **[!UICONTROL Title]** `C&C - Data View` och **[!UICONTROL External ID]** `cc_data_view`.

**Dimensioner**
Dimensioner från Customer Journey Analytics identifieras av [!UICONTROL Component ID] . [!UICONTROL Component ID] definieras i datavyn för Customer Journey Analytics. Dimensionen **[!UICONTROL Product Name]** i Customer Journey Analytics har till exempel [!UICONTROL Component ID] **[!UICONTROL product_name]** som är namnet på dimensionen i Power BI Desktop.
Datumintervallsdimensioner från Customer Journey Analytics, som **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** och mer, är tillgängliga som **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]** med flera.

**Mätvärden**
Mätvärden från Customer Journey Analytics identifieras av [!UICONTROL Component ID] . [!UICONTROL Component ID] definieras i datavyn för Customer Journey Analytics. Måttet **[!UICONTROL Purchase Revenue]** i Customer Journey Analytics har till exempel [!UICONTROL Component ID] **[!UICONTROL purchase_revenue]** som är namnet på måttet i Power BI Desktop. En **[!UICONTROL ∑]** indikerar mått. När du använder ett mätvärde i en visualisering får måttet det nya namnet **[!UICONTROL Sum of *metric *]**.

**Filter**
Filter som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL filterName]** . När du använder ett **[!UICONTROL filterName]**-fält i Power BI Desktop kan du ange vilket filter som ska användas.

**Beräknade mått**
Beräknade mätvärden som du definierar i Customer Journey Analytics identifieras av den [!UICONTROL External ID] som du har definierat för det beräknade mätvärdet. Det beräknade måttet **[!UICONTROL Product Name (Count Distinct)]** har till exempel [!UICONTROL External ID] **[!UICONTROL product_name_count_distinct]** och visas som **[!UICONTROL cm_product_name_count_distinc]**t i Power BI Desktop.

**Datumintervall**
Datumintervall som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL daterangeName]** . När du använder ett **[!UICONTROL daterangeName]**-fält kan du ange vilket datumintervall som ska användas.

**Anpassade omformningar**
Power BI Desktop har anpassade omvandlingsfunktioner med [DAX (Data Analysis Expressions)](https://learn.microsoft.com/en-us/dax/dax-overview). Du vill till exempel köra [Single dimension rankad](#single-dimension-ranked) med produktnamn i gemener.

1. Välj fältvisualisering i rapportvyn.
1. Välj **[!UICONTROL product_name]** i datapanelen.
1. Välj **[!UICONTROL New column]** i verktygsfältet.
1. I formelredigeraren definierar du en ny kolumn med namnet `product_name_lower`, som `product_name_lower = LOWER('public.cc_data_view[product_name])`.
   ![Power BI Desktop Transformation to Lower](../assets/uc14-powerbi-transformation.png)
1. Se till att du väljer den nya kolumnen **[!UICONTROL product_name_lower]** i rutan **[!UICONTROL Data]** i stället för kolumnen **[!UICONTROL product_name]**.
1. Välj **[!UICONTROL Report as Table]** från ![Mer](/help/assets/icons/More.svg) i tabellvisualiseringen.

   Ditt Power BI-skrivbord ska se ut så här nedan.
   ![Power BI Desktop Transformation Final](../assets/uc14-powerbi-final.png)

Den anpassade omvandlingen resulterar i en uppdatering av SQL-frågor. Se hur funktionen `lower` används i SQL-exemplet nedan:

```sql
select "_"."product_name_lower",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name_lower" as "product_name_lower",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterange" as "daterange",
            "_"."product_name" as "product_name",
            "_"."purchase_revenue" as "purchase_revenue",
            "_"."purchases" as "purchases",
            lower("_"."product_name") as "product_name_lower"
        from 
        (
            select "_"."daterange",
                "_"."product_name",
                "_"."purchase_revenue",
                "_"."purchases"
            from 
            (
                select "daterange",
                    "product_name",
                    "purchase_revenue",
                    "purchases"
                from "public"."cc_data_view" "$Table"
            ) "_"
            where ("_"."daterange" < date '2024-01-01' and "_"."daterange" >= date '2023-01-01') and ("_"."product_name" in ('4G Cellular Trail Camera', '4K Wildlife Trail Camera', 'Wireless Trail Camera', '8-Person Cabin Tent', '20MP No-Glow Trail Camera', 'HD Wildlife Camera', '4-Season Mountaineering Tent', 'Trail Camera', '16MP Trail Camera with Solar Panel', '10-Person Family Tent'))
        ) "_"
    ) "rows"
    group by "product_name_lower"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```

>[!TAB Skrivbord för Tablet PC]

Customer Journey Analytics-objekten är tillgängliga i sidlisten **[!UICONTROL Data]** när du arbetar i ett blad. Och hämtas från tabellen som du har valt som en del av sidan **[!UICONTROL Data source]** i Tableau. Exempel: **[!UICONTROL cc_data_view]**. Tabellnamnet är detsamma som det externa ID som du har definierat för datavyn i Customer Journey Analytics. Datavy med till exempel **[!UICONTROL Title]** `C&C - Data View` och **[!UICONTROL External ID]** `cc_data_view`.

**Dimensioner**
Dimensioner från Customer Journey Analytics identifieras av [!UICONTROL Component name] . [!UICONTROL Component name] definieras i datavyn för Customer Journey Analytics. Dimensionen **[!UICONTROL Product Name]** i Customer Journey Analytics har till exempel en [!UICONTROL Component name] **[!UICONTROL Product Name]** som är namnet på dimensionen i Tableau. Alla dimensioner identifieras av **[!UICONTROL Abc]**.
Datumintervallsdimensioner från Customer Journey Analytics, som **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** och mer, är tillgängliga som **[!UICONTROL Daterangeday]**, **[!UICONTROL Daterangeweek]**, **[!UICONTROL Daterangemonth]** med flera. När du använder en datumintervalldimension måste du välja en lämplig definition av datum och tid som ska användas för datumintervalldimensionen i den nedrullningsbara menyn. Exempel: **[!UICONTROL Year]**, **[!UICONTROL Quarter]**, **[!UICONTROL Month]**, **[!UICONTROL Day]**.

**Mätvärden**
Mätvärden från Customer Journey Analytics identifieras av [!UICONTROL Component Name] . [!UICONTROL Component Name] definieras i datavyn för Customer Journey Analytics. Måttet **[!UICONTROL Purchase Revenue]** i Customer Journey Analytics har till exempel [!UICONTROL Component Name] **[!UICONTROL Purchase Revenue]** som är namnet på måttet i Tableau. Alla mått identifieras av **[!UICONTROL #]**. När du använder ett mätvärde i en visualisering får måttet det nya namnet **[!UICONTROL Sum(*metric *)]**.

**Filter**
Filter som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL Filter Name]** . När du använder ett **[!UICONTROL Filter Name]**-fält i Tableau kan du ange vilket filter som ska användas.

**Beräknade mått**
Beräknade mätvärden som du definierar i Customer Journey Analytics identifieras av den [!UICONTROL Title] som du har definierat för det beräknade mätvärdet. Det beräknade måttet **[!UICONTROL Product Name (Count Distinct)]** har till exempel [!UICONTROL Title] **[!UICONTROL Product Name (Count Distinct)]** och visas som **[!UICONTROL Cm Product Name Count Distinct]** i Tableau.

**Datumintervall**
Datumintervall som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL Daterange Name]** . När du använder ett **[!UICONTROL Daterange Name]**-fält kan du ange vilket datumintervall som ska användas.

**Anpassade omformningar**
Tableu Desktop har anpassade omformningsfunktioner som använder [Beräknade fält](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm). Du vill till exempel köra [Single dimension rankad](#single-dimension-ranked) med produktnamn i gemener.

1. Välj **[!UICONTROL Analysis]** > **[!UICONTROL Create Calculated Field]** på huvudmenyn.
   1. Definiera **[!UICONTROL Lowercase Product Name]** med funktionen `LOWER([Product Name])`.
      ![Beräknat fält i tabell](../assets/uc14-tableau-calculated-field.png)
   1. Välj **[!UICONTROL OK]**.
1. Markera bladet **[!UICONTROL Data]**.
   1. Dra **[!UICONTROL Lowercase Product Name]** från **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Rows]**.
   1. Ta bort **[!UICONTROL Product Name]** från **[!UICONTROL Rows]**.
1. Välj vyn **[!UICONTROL Dashboard 1]**.

Ditt skrivbord ska se ut så här nedan.

![Skrivbord för Tablet PC efter omvandling](../assets/uc14-tableau-final.png)

Den anpassade omvandlingen resulterar i en uppdatering av SQL-frågor. Se hur funktionen `LOWER` används i SQL-exemplet nedan:

```sql
SELECT LOWER(CAST(CAST("cc_data_view"."product_name" AS TEXT) AS TEXT)) AS "Calculation_1562467608097775616",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-12-31')))
GROUP BY 1
HAVING ((SUM("cc_data_view"."purchase_revenue") >= 999999.99999998999) AND (SUM("cc_data_view"."purchase_revenue") <= 2000000.00000002))
```

>[!TAB Sökare]

Customer Journey Analytics-objekten är tillgängliga i gränssnittet **[!UICONTROL Explore]**. Och hämtas som en del av konfigurationen av anslutningen, projektet och modellen i Looker. Exempel: **[!UICONTROL cc_data_view]**. Vyns namn är detsamma som det externa ID som du har definierat för datavyn i Customer Journey Analytics. Datavy med till exempel **[!UICONTROL Title]** `C&C - Data View` och **[!UICONTROL External ID]** `cc_data_view`.

**Dimensioner**
Dimensioner från Customer Journey Analytics visas som **[!UICONTROL DIMENSION]** i den **[!UICONTROL Cc Data View]** vänstra listen. Dimensionen definieras i datavyn för Customer Journey Analytics. Dimensionen **[!UICONTROL Product Name]** i Customer Journey Analytics har till exempel en **[!UICONTROL DIMENSION]** **[!UICONTROL Product Name]** som är namnet på dimensionen i Looker.
Datumintervallsdimensioner från Customer Journey Analytics, som **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** och mer, är tillgängliga som **[!UICONTROL Daterangeday Date]**, **[!UICONTROL Daterangeweek Date]**, **[!UICONTROL Daterangemonth Date]** med flera.  När du använder en datumintervalldimension måste du välja en lämplig definition av datum och tid. Exempel: **[!UICONTROL Year]**, **[!UICONTROL Quarter]**, **[!UICONTROL Month]**, **[!UICONTROL Date]**.

**Mätvärden**
Mätvärden från Customer Journey Analytics listas som **[!UICONTROL DIMENSION]** i den **[!UICONTROL Cc Data View]** vänstra listen. Måttet **[!UICONTROL Purchase Revenue]** i Customer Journey Analytics har till exempel **[!UICONTROL DIMENSION]** **[!UICONTROL Purchase Revenue]**. Om du vill använda som mätvärde skapar du ett anpassat måttfält så som visas i exemplen ovan, eller använder kortkommandot för en dimension. Välj till exempel **[!UICONTROL ⋮]**, **[!UICONTROL Aggregate]** och sedan **[!UICONTROL Sum]**.

**Filter**
Filter som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL Filter Name]** . När du använder ett **[!UICONTROL Filter Name]**-fält i Looker kan du ange vilket filter som ska användas.

**Beräknade mått**
Beräknade mätvärden som du definierar i Customer Journey Analytics identifieras av den [!UICONTROL Title] som du har definierat för det beräknade mätvärdet. Det beräknade måttet **[!UICONTROL Product Name (Count Distinct)]** har till exempel [!UICONTROL Title] **[!UICONTROL Product Name (Count Distinct)]** och visas som **[!UICONTROL Cm Product Name Count Distinct]** i Looker.

**Datumintervall**
Datumintervall som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL Daterange Name]** . När du använder ett **[!UICONTROL Daterange Name]**-fält kan du ange vilket datumintervall som ska användas.

**Anpassade omformningar**
Looker tillhandahåller anpassade omformningsfunktioner med hjälp av anpassade fältbyggare, vilket visas ovan. Du vill till exempel köra [Single dimension rankad](#single-dimension-ranked) med produktnamn i gemener.

1. Från avsnittet **[!UICONTROL ‣ Custom Fields]** i den vänstra listen:
   1. Välj **[!UICONTROL Custom Dimension]** i listrutan **[!UICONTROL + Add]**.
   1. Ange `lower(${cc_data_view.product_name})` i textområdet **[!UICONTROL Expression]**. Du får hjälp med rätt syntax när du börjar skriva `Product Name`.
      ![Exempel på sökomformning](../assets/uc14-looker-transformation.png)
   1. Ange `product name` som **[!UICONTROL Name]**.
   1. Välj **[!UICONTROL Save]**.

Du bör se en liknande tabell som nedan.

![Sökomformningsresultat](../assets/uc14-looker-result.png)


Den anpassade omvandlingen resulterar i en uppdatering av SQL-frågor. Se hur funktionen `LOWER` används i SQL-exemplet nedan:

```sql
SELECT
    LOWER((cc_data_view."product_name")) AS "product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchase_revenue",
    COALESCE(SUM(CAST(( cc_data_view."purchases"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchases"
FROM public.cc_data_view  AS cc_data_view
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-01')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```

>[!TAB Jupyter-anteckningsbok]

Customer Journey Analytics-objekten (mått, mått, filter, beräknade mått och datumintervall) är tillgängliga som en del av de inbäddade SQL-frågor som du skapar. Se tidigare exempel.

**Anpassade omformningar**

1. Ange följande satser i en ny cell.

   ```python
   data = %sql SELECT LOWER(product_category) AS `Product Category`, COUNT(*) AS EVENTS \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. Kör cellen. Du bör se utdata som liknar skärmbilden nedan.

   ![Jupyter-anteckningsboksresultat](../assets/uc13-jupyter-results.png)

Frågan körs av BI-tillägget enligt definitionen i Jupyter-anteckningsbok.

>[!TAB RStudio]

Customer Journey Analytics-komponenterna (mått, mått, filter, beräknade värden och datumintervall) är tillgängliga som liknande namngivna objekt på R-språket. Se komponenterna med komponenten Se tidigare exempel.

**Anpassade omformningar**

1. Ange följande programsatser mellan ` ```{r} ` och ` ``` ` i ett nytt segment.

   ```R
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange <= "2024-01-01") %>%
      mutate(d2=lower(product_category)) %>%
      group_by(d2) %>%
      count() %>%
      arrange(d2, .by_group = FALSE)
   print(df)
   ```

1. Kör segmentet. Du bör se utdata som liknar skärmbilden nedan.

   ![Resultat av Gällande ljud](../assets/uc13-rstudio-results.png)

Frågan som genereras av RStudio med BI-tillägget inkluderar `lower`, vilket betyder att den anpassade omvandlingen körs av RStudio och BI-tillägget.

```sql
SELECT "d2", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*, lower("product_category") AS "d2"
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" <= '2024-01-01')
) AS "q01"
GROUP BY "d2"
ORDER BY "d2"
LIMIT 1000
```

>[!ENDTABS]

+++

