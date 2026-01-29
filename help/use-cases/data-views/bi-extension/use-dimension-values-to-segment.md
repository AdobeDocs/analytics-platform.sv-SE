---
title: Använd Dimension-värden för att segmentera
description: Använd dimensionsvärden för att segmentera användningsexempel för BI-tillägg i olika BI-verktyg i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 1%

---

# Använd dimensionsvärden för att segmentera

Du använder det dynamiska **[!UICONTROL Hunting]**-värdet för **[!UICONTROL Product Category]** för att segmentera produkter från jaktkategorin. För de BI-verktyg som inte har stöd för dynamisk hämtning av produktkategorivärden skapar du ett nytt segment i Customer Journey Analytics som segmenterar produkter i jaktproduktkategorin.
Sedan vill du använda det nya segmentet för att rapportera produktnamn och förekomster (händelser) för produkter i jaktkategorin under januari 2023.

+++ Customer Journey Analytics

Skapa ett nytt segment med **[!UICONTROL Title]** `Hunting Products` i Customer Journey Analytics.

![Customer Journey Analytics använder Dimension-värden för att segmentera](../assets/cja-hunting-products.png)

Du kan sedan använda det segmentet i en exempelpanel **[!UICONTROL Using Dimension Values To Filter]** för följande användningsområden:

![Customer Journey Analytics Distinct Count-värden](../assets/cja-using-dimension-values-to-filter.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](connect-and-validate.md) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Välj **[!UICONTROL Home]** på menyn och välj sedan **[!UICONTROL Refresh]** i verktygsfältet. Du måste uppdatera anslutningen för att kunna plocka upp det nya filtret som du just definierade i Customer Journey Analytics.

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterange]**.
   1. Välj **[!UICONTROL product_category]**.
   1. Välj **[!UICONTROL product_name]**.
   1. Välj **[!UICONTROL sum occurrences]**.

En visualisering visar **[!UICONTROL Error fetching data for this visual]**.

1. I rutan **[!UICONTROL Filters]**:
   1. Välj **[!UICONTROL filterName is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Basic filtering]** som **[!UICONTROL Filter type]**.
   1. Välj **[!UICONTROL daterange is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Advanced filtering]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Välj **[!UICONTROL Basic filter]** som **[!UICONTROL Filter type]** för **[!UICONTROL product_category]** och välj **[!UICONTROL Hunting]** i listan över möjliga värden.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort **[!UICONTROL filterName]** från **[!UICONTROL Columns]**.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort **[!UICONTROL daterange]** från **[!UICONTROL Columns]**.

   Tabellen uppdateras med det använda **[!UICONTROL product_category]**-filtret. Ditt Power BI-skrivbord ska se ut så här nedan.

   ![Power BI Desktop använder datumintervallnamn för att filtrera](../assets/uc10-powerbi-final.png)



>[!TAB Skrivbord för Tablet PC]

![AlertRed](/help/assets/icons/AlertRed.svg) Skrivbordsdatorn Tableau stöder inte hämtning av den dynamiska listan över produktkategorier från Customer Journey Analytics. I det här användningsexemplet används det nyligen skapade filtret för **[!UICONTROL Hunting Products]** och filternamnskriterierna används.

1. I vyn **[!UICONTROL Data Source]**, under **[!UICONTROL Data]**, på snabbmenyn på **[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**, väljer du **[!UICONTROL Refresh]**. Du måste uppdatera anslutningen för att kunna plocka upp det nya filtret som du just definierade i Customer Journey Analytics.
1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Filter Name]** från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. Kontrollera att **[!UICONTROL Filter \[Filter Name\]]** är markerat i dialogrutan **[!UICONTROL Select from list]** och välj **[!UICONTROL Hunting Products]** i listan. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Daterange]**-posten från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filter Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange\]]** väljer du **[!UICONTROL Range of dates]** och sedan `01/01/2023` - `1/2/2023`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Product Name]** från listan **[!UICONTROL Tables]** till **[!UICONTROL Rows]**.
   1. Dra **[!UICONTROL Occurrences]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Occurrences)]**.
   1. Välj **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc10-tableau-final.png)

>[!TAB Sökare]

1. I 1. Uppdatera anslutningen i **[!UICONTROL Explore]**-gränssnittet för Looker. Välj ![Inställning](/help/assets/icons/Setting.svg) **[!UICONTROL Clear cache and refresh]**.
1. Kontrollera att du har en ren konfiguration i gränssnittet **[!UICONTROL Explore]** för Looker. Om inte väljer du ![Inställning](/help/assets/icons/Setting.svg) **[!UICONTROL Remove fields and filters]**.
1. Välj **[!UICONTROL + Filter]** under **[!UICONTROL Filters]**.
1. I dialogrutan **[!UICONTROL Add Filter]**:
   1. Välj **[!UICONTROL ‣ Cc Data View]**
   1. Välj **[!UICONTROL ‣ Daterange Date]** och sedan **[!UICONTROL Daterange Date]** i listan med fält.
      ![Looker-filter](../assets/uc2-looker-filter.png)
1. Ange filtret **[!UICONTROL Cc Data View Daterange Date]** som **[!UICONTROL is in range]** **[!UICONTROL 2023/01/01]** **[!UICONTROL until (before)]** **[!UICONTROL 2023/02/01]**.
1. Välj **[!UICONTROL + Filter]** under **[!UICONTROL Filters]** om du vill lägga till ytterligare ett filter.
1. I dialogrutan **[!UICONTROL Add Filter]**:
   1. Välj **[!UICONTROL ‣ Cc Data View]**
   1. Välj **[!UICONTROL ‣ Product Category]** i listan med fält.
1. Kontrollera **[!UICONTROL is]** som markering för filtret.

![AlertRed](/help/assets/icons/AlertRed.svg)-uppslag visar inte listan över möjliga värden för **[!UICONTROL Product Category]**.

![Distinkt antal sökare](../assets/uc10-looker-result.png)


>[!TAB Jupyter-anteckningsbok]

1. Ange följande satser i en ny cell.

   ```python
   data = %sql SELECT DISTINCT product_category FROM cc_data_view WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01';
   style = {'description_width': 'initial'}
   category_filter = widgets.Dropdown(
      options=[d for d, in data],
      description='Product Category:',
      style=style
   )
   display(category_filter)
   ```

1. Kör cellen. Du bör se utdata som liknar skärmbilden nedan.

   ![Jupyter-anteckningsboksresultat](../assets/uc10-jupyter-input.png)

1. Välj **[!UICONTROL Hunting]** i listrutan.

1. Ange följande satser i en ny cell.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               AND product_category = '{category_filter.value}' \
               GROUP BY 1 \
               ORDER BY Events DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Kör cellen. Du bör se utdata som liknar skärmbilden nedan.

   ![Jupyter-anteckningsboksresultat](../assets/uc10-jupyter-results.png)


>[!TAB RStudio]

1. Ange följande programsatser mellan ` ```{r} ` och ` ``` ` i ett nytt segment. Se till att du använder en lämplig kategori. Till exempel `Hunting`.

   ```R
   ## Dimension 1 Filtered by Dimension 2 value
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & product_category == "Hunting") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. Kör segmentet. Du bör se utdata som liknar skärmbilden nedan.

   ![Resultat av Gällande ljud](../assets/uc10-rstudio-results.png)

>[!ENDTABS]

+++

