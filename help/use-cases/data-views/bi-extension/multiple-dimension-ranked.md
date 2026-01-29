---
title: Flera Dimension-rankade
description: Användningsexempel med flera dimensioner rankade för BI-tillägget i olika BI-verktyg i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1117'
ht-degree: 2%

---

# Flera dimensioner rankade


I det här fallet vill du visa en tabell som delar upp inköpsinkomster och inköp för produktnamn inom produktkategorier under 2023. Dessutom vill du använda visualiseringar för att illustrera både produktkategorifördelningen och bidragen till produktnamn inom varje produktkategori.

+++ Customer Journey Analytics

Ett exempel på **[!UICONTROL Multiple Dimension Ranked]**-panel för användningsfallet:

![Customer Journey Analytics Multiple Dimension Ranked panel](../assets/cja-multiple-dimension-ranked.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](connect-and-validate.md) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Om du vill vara säker på att datumintervallet gäller för alla visualiseringar drar och släpper du **[!UICONTROL daterangeday]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Filters on this page]**.
   1. Välj **[!UICONTROL daterangeday is (All)]** från **[!UICONTROL Filters on this page]**.
   1. Välj **[!UICONTROL Relative date]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is in the last]** `1` **[!UICONTROL calendar years]**.
   1. Välj **[!UICONTROL Apply filter]**.

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL datarangeday]**.
   1. Välj **[!UICONTROL product_category]**.
   1. Välj **[!UICONTROL product_name]**.
   1. Välj **[!UICONTROL sum purchase_revenue]**
   1. Välj **[!UICONTROL sum purchases]**

1. Om du vill ändra det lodräta stapeldiagrammet till en tabell kontrollerar du att tabellen är markerad och väljer **[!UICONTROL Matrix]** i rutan **[!UICONTROL Visualizations]**.
   * Dra **[!UICONTROL product_name]** från **[!UICONTROL Columns]** och släpp fältet under **[!UICONTROL product_categor]**y i **[!UICONTROL Rows]** i rutan **[!UICONTROL Visualization]**.

1. Om du vill begränsa antalet produkter som visas i tabellen väljer du **[!UICONTROL product_name is (All)]** i rutan **[!UICONTROL Filters]**.

   1. Välj **[!UICONTROL Advanced filtering]**.
   1. Välj **[!UICONTROL Filter type]** **[!UICONTROL Top N]** **[!UICONTROL Show items]** **[!UICONTROL Top]** `15` **[!UICONTROL By Value]**.
   1. Dra **[!UICONTROL purchases]** från rutan **[!UICONTROL Data]** till rutan **[!UICONTROL Add data fields here]**.
   1. Välj **[!UICONTROL Apply filter]**.

1. Om du vill förbättra läsbarheten väljer du **[!UICONTROL View]** på den översta menyn, väljer **[!UICONTROL Page View]** > **[!UICONTROL Actual size]** och ändrar storlek på tabellvisualiseringen.

1. Om du vill dela upp varje kategori i tabellen väljer du **[!UICONTROL +]** på produktkategorinivå. Ditt Power BI-skrivbord ska se ut så här nedan.

   ![Power BI-matristabell med flera dimensioner för stationära datorer ](../assets/uc6-powerbi-data.png)

1. Välj **[!UICONTROL Home]** på den översta menyn och välj **[!UICONTROL New visual]**. En ny visuell vy läggs till i rapporten.

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL product_category]**.
   1. Välj **[!UICONTROL product_name]**.
   1. Välj **[!UICONTROL purchase_revenue]**.

1. Om du vill ändra det visuella objektet markerar du stapeldiagrammet och väljer **[!UICONTROL Treemap]** i rutan **[!UICONTROL Visualizations]**.
1. Se till att **[!UICONTROL product_category]** visas under **[!UICONTROL Category]** och att **[!UICONTROL product_name]** visas under **[!UICONTROL Details]** i rutan **[!UICONTROL Visualizations]**.

   Ditt Power BI-skrivbord ska se ut så här nedan.

   ![Power BI Multiple Dimensions, rankat treemap](../assets/uc6-powerbi-treemap.png)

1. Välj **[!UICONTROL Home]** på den översta menyn och välj **[!UICONTROL New visual]**. En ny visuell vy läggs till i rapporten.

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL product_category]**.
   1. Välj **[!UICONTROL purchase_revenue]**.
   1. Välj **[!UICONTROL purchase]**.

1. I rutan **[!UICONTROL Visualizations]**:
   1. Välj **[!UICONTROL Line and stacked column chart]** om du vill ändra visualiseringen.
   1. Dra **[!UICONTROL sum_of_purchases]** från **[!UICONTROL Column y-axis]** till **[!UICONTROL Line y-axis]**.

1. Blanda om de enskilda visualiseringarna i rapporten.

   Ditt Power BI-skrivbord ska se ut så här nedan.

   ![Flera dimensioner för Power BI Desktop Rankad sist](../assets/uc6-powerbi-final.png)


>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange\]]** väljer du **[!UICONTROL Relative dates]**, väljer **[!UICONTROL Years]** och anger **[!UICONTROL Previous year]**. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc6-tableau-filter.png)

   1. Dra **[!UICONTROL Product Category]** och släpp intill **[!UICONTROL Columns]**.
   1. Dra **[!UICONTROL Purchase Revenue]** och släpp intill **[!UICONTROL Rows]**. Värdet ändras till **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Dra inköp och släpp bredvid **[!UICONTROL Rows]**. Värdet ändras till **[!UICONTROL SUM(Purchases)]**.
   1. Välj **[!UICONTROL SUM(Purchases)]** och välj **[!UICONTROL Dual Axis]** i listrutan.
   1. Välj **[!UICONTROL SUM(Purchases)]** i **[!UICONTROL Marks]** och välj **[!UICONTROL Line]** i listrutan.
   1. Välj **[!UICONTROL SUM(Purchase Revenue)]** i **[!UICONTROL Marks]** och välj **[!UICONTROL Bar]** i listrutan.
   1. Välj **[!UICONTROL Entire View]** på menyn **[!UICONTROL Fit]**.
   1. Markera rubriken **[!UICONTROL Purchase Revenue]** i diagrammet och kontrollera att inköpsinkomsterna är i stigande ordning.

      Ditt skrivbord ska se ut så här nedan.

      ![Flera dimensioner rankade för Tableu Desktop ](../assets/uc6-tableau-category.png)

1. Byt namn på aktuellt **[!UICONTROL Sheet 1]**-blad till `Category`.
1. Välj **[!UICONTROL New Worksheet]** om du vill skapa ett nytt blad och ändra namnet till `Data`.

   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange\]]** väljer du **[!UICONTROL Relative dates]**, väljer **[!UICONTROL Years]** och anger **[!UICONTROL Previous year]**. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Purchase Revenue]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Dra **[!UICONTROL Purchase]** från **[!UICONTROL Data]**-rutan till **[!UICONTROL Columns]**, intill **[!UICONTROL Purchase Revenue]**. Värdet ändras till **[!UICONTROL SUM(Purchases)]**.
   1. Dra **[!UICONTROL Product Category]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Rows]**.
   1. Dra **[!UICONTROL Product Name]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Rows]**, bredvid **[!UICONTROL Product Category]**.
   1. Om du vill ändra de två vågräta staplarna till en tabell väljer du **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Om du vill begränsa antalet produkter väljer du **[!UICONTROL Purchases]** i **[!UICONTROL Measure Values]**. Välj **[!UICONTROL Filter]** i listrutan.
   1. I dialogrutan **[!UICONTROL Filter \[Purchases\]]** väljer du **[!UICONTROL At least]** och anger `7000`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL the]** Anpassa.

      Ditt skrivbord ska se ut så här nedan.

      ![Skrivbordsdator med flera Dimension-rankade data](../assets/uc6-tableau-data.png)

1. Välj **[!UICONTROL New worksheet]** om du vill skapa ett nytt blad och ändra namnet till **[!UICONTROL Treemap]**.
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange\]]** väljer du **[!UICONTROL Relative dates]**, väljer **[!UICONTROL Years]** och anger **[!UICONTROL Previous year]**. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Purchase Revenue]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Rows]**. Värdena ändras till **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Dra **[!UICONTROL Purchase]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Rows]**, bredvid **[!UICONTROL Purchase Revenue]**. Värdet ändras till **[!UICONTROL SUM(Purchases)]**.
   1. Dra **[!UICONTROL Product Category]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Columns]**.
   1. Dra **[!UICONTROL Product Name]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Columns]**.
   1. Om du vill ändra de två vertikala stapeldiagrammen till en treemap väljer du **[!UICONTROL Treemap]** från **[!UICONTROL Show Me]**.
   1. Om du vill begränsa antalet produkter väljer du **[!UICONTROL Purchases]** i **[!UICONTROL Measure Values]**. Välj **[!UICONTROL Filter]** i listrutan.
   1. I dialogrutan **[!UICONTROL Filter \[Purchases\]]** väljer du **[!UICONTROL At least]** och anger `7000`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Skrivbordsdator med flera Dimension-rankade data](../assets/uc6-tableau-treemap.png)

1. Skapa en ny **[!UICONTROL New Dashboard]**-vy genom att klicka på tabbknappen **[!UICONTROL Dashboard 1]** (längst ned). I vyn **[!UICONTROL Dashboard 1]**:
   1. Dra och släpp **[!UICONTROL Category]**-bladet från **[!UICONTROL Sheets]**-hyllan till **[!UICONTROL Dashboard 1]**-vyn som läser *Drop sheets här*.
   1. Dra och släpp **[!UICONTROL Treemap]**-bladet från **[!UICONTROL Sheets]**-hyllan under **[!UICONTROL Category]**-bladet i vyn **[!UICONTROL Dashboard 1]**.
   1. Dra och släpp **[!UICONTROL Data]**-bladet från **[!UICONTROL Sheets]**-hyllan under **[!UICONTROL Treemap]**-bladet i vyn **[!UICONTROL Dashboard 1]**.
   1. Ändra storlek på alla blad i vyn.

   **[!UICONTROL Dashboard 1]**-vyn ska se ut så här nedan.

   ![Instrumentpanel för bordsdator ](../assets/uc6-tableau-final.png)


>[!TAB Sökare]

1. Kontrollera att du har en ren konfiguration i gränssnittet **[!UICONTROL Explore]** för Looker. Om inte väljer du ![Inställning](/help/assets/icons/Setting.svg) **[!UICONTROL Remove fields and filters]**.
1. Välj **[!UICONTROL + Filter]** under **[!UICONTROL Filters]**.
1. I dialogrutan **[!UICONTROL Add Filter]**:
   1. Välj **[!UICONTROL ‣ Cc Data View]**
   1. Välj **[!UICONTROL ‣ Daterange Date]** och sedan **[!UICONTROL Daterange Date]** i listan med fält.
      ![Looker-filter](../assets/uc2-looker-filter.png)
1. Ange filtret **[!UICONTROL Cc Data View Daterange Date]** som **[!UICONTROL is in range]** **[!UICONTROL 2023/01/01]** **[!UICONTROL until (before)]** **[!UICONTROL 2024/01/01]**.
1. Från avsnittet **[!UICONTROL ‣ Cc Data View]** i den vänstra listen:
   1. Välj **[!UICONTROL Product Category]**.
   1. Välj **[!UICONTROL Product Name]**.
1. Från avsnittet **[!UICONTROL ‣ Custom Fields]** i den vänstra listen:
   1. Välj **[!UICONTROL Custom Measure]** i listrutan **[!UICONTROL + Add]**.
   1. I dialogrutan **[!UICONTROL Create custom measure]**:
      1. Välj **[!UICONTROL Purchase Revenue]** i listrutan **[!UICONTROL Field to measure]**.
      1. Välj **[!UICONTROL Sum]** i listrutan **[!UICONTROL Measure type]**.
      1. Ange ett anpassat fältnamn för **[!UICONTROL Name]**. Till exempel: `Sum of Purchase Revenue`.
      1. Klicka på fliken **[!UICONTROL Field details]**.  
      1. Välj **[!UICONTROL Decimals]** i listrutan **[!UICONTROL Format]** och kontrollera att `0` anges i **[!UICONTROL Decimals]**.
         ![Sök efter anpassat måttfält](../assets/uc5-looker-customfield.png)
      1. Välj **[!UICONTROL Save]**.
   1. Välj **[!UICONTROL Custom Measure]** en gång till på den nedrullningsbara menyn **[!UICONTROL + Add]**. I dialogrutan **[!UICONTROL Create custom]**:
      1. Välj **[!UICONTROL Purchases]** i listrutan **[!UICONTROL Field to measure]**.
      1. Välj **[!UICONTROL Sum]** i listrutan **[!UICONTROL Measure type]**.
      1. Ange ett anpassat fältnamn för **[!UICONTROL Name]**. Till exempel: `Sum of Purchases`.
      1. Klicka på fliken **[!UICONTROL Field details]**.  
      1. Välj **[!UICONTROL Decimals]** i listrutan **[!UICONTROL Format]** och kontrollera att `0` anges i **[!UICONTROL Decimals]**.
      1. Välj **[!UICONTROL Save]**.
   1. Båda fälten läggs automatiskt till i datavyn.
1. Välj **[!UICONTROL Filters]** i avsnittet **[!UICONTROL + Filter]**. I dialogrutan **[!UICONTROL Add Filter]**. Välj **[!UICONTROL ‣ Custom Fields]** och sedan **[!UICONTROL Purchase Revenue]**.
1. Välj **[!UICONTROL is >]** och ange `800000` för att begränsa resultaten.
1. Välj **[!UICONTROL Run]**.
1. Välj **[!UICONTROL ‣ Visualization]** om du vill visa radinvisualiseringen.
1. Välj **[!UICONTROL Edit]** i **[!UICONTROL Visualization]** för att uppdatera visualiseringen. I popup-dialogrutan:
   1. Klicka på fliken **[!UICONTROL Plot]**.  
   1. Rulla ned och välj **[!UICONTROL Edit Chart Config]**.
   1. Ändra JSON i **[!UICONTROL Chart Config (Override)]** som i skärmbilden nedan och välj sedan **[!UICONTROL Preview]**.

      ![Looker-serialiseringskonfiguration](../assets/uc6-looker-visualization.png)

   1. Välj **[!UICONTROL Apply]**.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) bredvid **[!UICONTROL Edit]** för att dölja popup-dialogrutan

En visualisering och en tabell som liknar den visas nedan.

![Sökresultat, daglig trend](../assets/uc6-looker-result.png)


>[!TAB Jupyter-anteckningsbok]

1. Ange följande satser i en ny cell.

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_category AS `Product Category`, product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1, 2 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby(['Product Category', 'Product Name'], as_index=False).sum()
   plt.figure(figsize=(8, 8))
   sns.scatterplot(x='Product Category', y='Product Name', size='Purchase Revenue', sizes=(10, 200), hue='Purchases', palette='husl', data=df)
   plt.show()
   display(data)
   ```

1. Kör cellen. Du bör se utdata som liknar skärmbilden nedan.

   ![Jupyter-anteckningsboksresultat](../assets/uc6-jupyter-results.png)


>[!TAB RStudio]

1. Ange följande programsatser mellan ` ```{r} ` och ` ``` ` i ett nytt segment.

   ```R
   ## Multiple dimensions ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_category, product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. Kör segmentet. Du bör se utdata som liknar skärmbilden nedan.

   ![Resultat av Gällande ljud](../assets/uc6-rstudio-results.png)


>[!ENDTABS]

+++
