---
title: Använd datumintervallnamn för filter
description: Använd datumintervallnamn för att filtrera användningsfall för BI-tillägg i olika BI-verktyg i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 1%

---

# Använd datumintervallnamn för att filtrera

I det här fallet vill du använda ett datumintervall som du har definierat i Customer Journey Analytics för att filtrera och rapportera om händelser (händelser) under det senaste året.

+++ Customer Journey Analytics

Om du vill rapportera med hjälp av ett datumintervall anger du ett datumintervall i Customer Journey Analytics, med **[!UICONTROL Title]** `Last Year 2023`.

![Customer Journey Analytics Använd datumintervallnamn för att filtrera](../assets/cja-daterange.png)

Du kan sedan använda det datumintervallet i en exempelpanel **[!UICONTROL Using Date Range Names To Filter]** för följande användningsfall:

![Customer Journey Analytics Distinct Count-värden](../assets/cja-using-date-range-filter-names-to-filter.png)

Observera hur datumintervallet som definieras i visualiseringen av frihandstabellen åsidosätter datumintervallet som tillämpas på panelen.

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](connect-and-validate.md) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterangemonth]**.
   1. Välj **[!UICONTROL daterangeName]**.
   1. Välj **[!UICONTROL sum occurrences]**.

   En visualisering visar **[!UICONTROL Error fetching data for this visual]**.

1. I rutan **[!UICONTROL Filters]**:

   1. Välj **[!UICONTROL daterangeName is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Basic filtering]** som **[!UICONTROL Filter type]**.
   1. Under fältet **[!UICONTROL Search]** väljer du **[!UICONTROL Last Year 2023]**, som är namnet på ditt datumintervall som definieras i Customer Journey Analytics.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort **[!UICONTROL daterangeName]** från **[!UICONTROL Columns]**.

   Tabellen uppdateras med det använda **[!UICONTROL daterangeName]**-filtret. Ditt Power BI-skrivbord ska se ut så här nedan.

   ![Power BI Desktop använder datumintervallnamn för att filtrera](../assets/uc8-powerbi-final.png)

>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange Name]** från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. Kontrollera att **[!UICONTROL Filter \[Daterange Name\]]** är markerat i dialogrutan **[!UICONTROL Select from list]** och välj **[!UICONTROL Last Year 2023]** i listan. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Daterangemonth]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Rows]**. Välj **[!UICONTROL Daterangemonth]** och välj **[!UICONTROL Month]**. Värdet ändras till **[!UICONTROL MONTH(Daterangemonth)]**.
   1. Dra **[!UICONTROL Occurrences]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Occurrences)]**.
   1. Välj **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Välj **[!UICONTROL Swap Rows and Columns]** i verktygsfältet.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc8-tableau-final.png)

>[!TAB Sökare]

1. Kontrollera att du har en ren konfiguration i gränssnittet **[!UICONTROL Explore]** för Looker. Om inte väljer du ![Inställning](/help/assets/icons/Setting.svg) **[!UICONTROL Remove fields and filters]**.
1. Välj **[!UICONTROL + Filter]** under **[!UICONTROL Filters]**.
1. I dialogrutan **[!UICONTROL Add Filter]**:
   1. Välj **[!UICONTROL ‣ Cc Data View]**
   1. Välj **[!UICONTROL ‣ Daterange Name]** i listan med fält.
1. Ange filtret **[!UICONTROL Cc Data View Daterange Name]** som **[!UICONTROL is]** och välj **[!UICONTROL Last Year 2023]** i listan med värden.
1. Från avsnittet **[!UICONTROL ‣ Cc Data View]** i den vänstra listen:
   1. Välj **[!UICONTROL Daterange Month]** och sedan **[!UICONTROL Month]**.
   1. Välj **[!UICONTROL Count]** under **[!UICONTROL MEASURES]** i den vänstra listen (längst ned).
1. Välj **[!UICONTROL Run]**.
1. Välj **[!UICONTROL ‣ Visualization]**.

En visualisering och en tabell som liknar den visas nedan.

![Distinkt antal sökare](../assets/uc8-looker-result.png)


>[!TAB Jupyter-anteckningsbok]

1. Ange följande satser i en ny cell.

   ```python
   data = %sql SELECT daterangeName FROM cc_data_view;
   style = {'description_width': 'initial'}
   daterange_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Date Range Name:',
      style=style
   )
   display(daterange_name)
   ```

1. Kör cellen. Du bör se utdata som liknar skärmbilden nedan.

   ![Jupyter-anteckningsboksresultat](../assets/uc8-jupyter-input.png)

1. Välj **[!UICONTROL Fishing Products]** i listrutan.

1. Ange följande satser i en ny cell.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterangeName = '{daterange_name.value}' \
               GROUP BY 1 \
               ORDER BY Month ASC
   df = data.DataFrame()
   df = df.groupby('Month', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Month', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Kör cellen. Du bör se utdata som liknar skärmbilden nedan.

   ![Jupyter-anteckningsboksresultat](../assets/uc8-jupyter-results.png)


>[!TAB RStudio]

1. Ange följande programsatser mellan ` ` ``{r} ` och ` `` ` ` i ett nytt segment. Se till att du använder rätt namn för datumintervall. Exempel: `Last Year 2023`.

   ```R
   ## Monthly Events for Last Year
   df <- dv %>%
      filter(daterangeName == "Last Year 2023") %>%
      group_by(daterangemonth) %>%
      count() %>%
      arrange(daterangemonth, .by_group = FALSE)
   ggplot(df, aes(x = daterangemonth, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Kör segmentet. Du bör se utdata som liknar skärmbilden nedan.

   ![Resultat av Gällande ljud](../assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++

