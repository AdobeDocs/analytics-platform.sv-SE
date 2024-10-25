---
title: Användningsexempel för BI-tillägget i Customer Journey Analytics
description: Flera användningsfall som visar hur BI-tillägget används i olika BI-verktyg i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
source-git-commit: b111a75041743e14a71d0df56b04c85ed4bae7b8
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 0%

---

# Användningsexempel för BI-tillägg

Den här artikeln innehåller ett antal användningsexempel som visar hur du använder BI-tilläggets funktioner i olika BI-verktyg.

Följande användningsfall dokumenteras:

1. [Anslut och visa datavyer](#connect-and-list-data-views).
1. [Daglig trend](#daily-trend).
1. [Trend per timme](#hourly-trend).
1. [Månadstrend](#monthly-trend).
1. [En dimension rankad](#single-dimension-ranked).
1. [Flera dimensioner rankade](#multiple-dimension-ranked).
1. [Räkna distinkta dimensionsvärden](#count-distinct-dimension-values).
1. [Använd datumintervallnamn för att filtrera](#use-date-range-names-to-filter).
1. [Använd filternamn för att filtrera](#use-filter-names-to-filter).
1. [Använd dimensionsvärden för att filtrera](#use-dimension-values-to-filter).
1. [Sortera](#sort).
1. [Gränser](#limits).
1. [Till FÖRENKLING eller inte](#to-flatten-or-not).
1. [Dimension- och måttomformningar](#dimension-and-metric-transformations).
1. [Visualiseringar och interaktioner](#visualizations-and-interactions).

För varje användningsfall finns instruktioner tillgängliga för följande BI-verktyg i avsnittet **Detaljer**:

* Power BI Desktop (version 2.136.1478.0, 64 bitar (september 2024))
* Tableau Desktop (version 2022.3.5 (2023.23.0310) 64-bitar)

Instruktionerna refererar till en exempeldatavy som heter **[!UICONTROL public.ares_sql_validation]**, två exempeldimensioner (**[!UICONTROL Product Name]** och **[!UICONTROL Product Category]**) och två exempelmått (**[!UICONTROL Purchases]** och **[!UICONTROL Purchase Revenue]**). När du går igenom instruktionerna kan du ändra de här exempelobjekten för din specifika miljö där det passar.


## Visa och koppla data

I det här användningsexemplet konfigureras anslutningen från BI-verktyget till Customer Journey Analytics och en lista över tillgängliga datavyer för att testa anslutningen.

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Få åtkomst till de nödvändiga autentiseringsuppgifterna och parametrarna från användargränssnittet för Experience Platform-frågetjänsten.

   1. Navigera till din Experience Platform-sandlåda.
   1. Välj ![Frågor](/help/assets/icons/DataSearch.svg) **[!UICONTROL Queries]** i den vänstra listen.
   1. Välj fliken **[!UICONTROL Credentials]** i gränssnittet **[!UICONTROL Queries]**.
   1. Välj `prod:cja` i listrutan **[!UICONTROL Database]**.

      ![Fråga efter autentiseringsuppgifter för tjänsten](assets/queryservice-credentials.png)

1. Öppna Power BI Desktop.
1. Välj **[!UICONTROL Get data from other sources]** i huvudgränssnittet.
1. I dialogrutan **[!UICONTROL Get Data]**:
   ![PowerBI PostgreSQL-databas](assets/powerbi-postgresql.png)
   1. Sök efter och välj **[!UICONTROL PostgreSQL database]**.
   1. Välj **[!UICONTROL Connect]**.
1. I dialogrutan **[!UICONTROL PostgreSQL database]**:
   ![Inställningar för PowerBI Desktop Server och Database](assets/powerbi-serverdatabase.png)
   1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in värdena **[!UICONTROL Host]** och **[!UICONTROL Port]** från Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]**, avgränsade med `:` som värde för **[!UICONTROL Server]**. Till exempel: `examplecompany.platform-query.adobe.io:80`.
   1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in värdet **[!UICONTROL Database]** från Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]**. Lägg till `?FLATTEN` i värdet som du klistrar in. Exempel: `prod:cja?FLATTEN`.
   1. Välj **[!UICONTROL DirectQuery]** som [!UICONTROL Data connectivity mode].
   1. Välj **[!UICONTROL OK]**.
1. I dialogrutan **[!UICONTROL PostgreSQL database]** - **[!UICONTROL Database]**:
   ![PowerBI Desktop-användare och lösenord](assets/powerbi-userpassword.png)
   1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera värdena **[!UICONTROL Username]** och **[!UICONTROL Password]** från Experience Platform-panelen **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** i fälten **[!UICONTROL User name]** och **[!UICONTROL Password]**. Om du använder en [icke-förfallande autentiseringsuppgift](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) ska du använda lösenordet för dina icke-förfallande autentiseringsuppgifter.
   1. Kontrollera att listrutan för **[!UICONTROL Select which level to apply these settings to]** är inställd på **[!UICONTROL Server]** som du har definierat tidigare.
   1. Välj **[!UICONTROL Connect]**.
1. I dialogrutan **[!UICONTROL Navigator]** hämtas datavyer. Den här hämtningen kan ta en stund. När den har hämtats:
   ![Inläsningsdata för Power BI-målservern](assets/powerbi-navigator-load.png)
   1. Välj **[!UICONTROL public.ares_sql_validation]** i listan i den vänstra panelen.
   1. Välj **[!UICONTROL Load]**.
1. Efter en stund visas tillgängliga mått och mått i rutan **[!UICONTROL Data]**.
   ![Power BI-tjänstserverdata har lästs in](assets/powerbi-navigator-loaded.png)


>[!TAB Tablet PC]

1. Få åtkomst till de nödvändiga autentiseringsuppgifterna och parametrarna från användargränssnittet för Experience Platform-frågetjänsten.

   1. Navigera till din Experience Platform-sandlåda.
   1. Välj ![Frågor](/help/assets/icons/DataSearch.svg) **[!UICONTROL Queries]** i den vänstra listen.
   1. Välj fliken **[!UICONTROL Credentials]** i gränssnittet **[!UICONTROL Queries]**.
   1. Välj `prod:cja` i listrutan **[!UICONTROL Database]**.

      ![Fråga efter autentiseringsuppgifter för tjänsten](assets/queryservice-credentials.png)

1. Öppna Tableu.
1. Välj **[!UICONTROL PostgreSQL]** från den vänstra listen under **[!UICONTROL To a Server]**. Om den inte är tillgänglig väljer du **[!UICONTROL More...]** och väljer **[!UICONTROL PostgreSQL]** i **[!UICONTROL Installed Connectors]**.
   ![Tableu-anslutningar](assets/tableau-connectors.png)
1. I dialogrutan **[!UICONTROL PostgreSQL]** går du till fliken **[!UICONTROL General]**:
   ![Dialogrutan Logga in i tabell](assets/tableau-signin.png)
   1. Använd ![Kopiera](/help/assets/icons/Copy.svg) för att kopiera och klistra in **[!UICONTROL Host]** från Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Server]**.
   1. Använd ![Kopiera](/help/assets/icons/Copy.svg) för att kopiera och klistra in **[!UICONTROL Port]** från Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Port]**.
   1. Använd ![Kopiera](/help/assets/icons/Copy.svg) för att kopiera och klistra in **[!UICONTROL Database]** från Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Database]**. Lägg till `%3FFLATTEN` i värdet som du klistrar in. Till exempel: `prod:cja%3FFLATTEN`.
   1. Välj **[!UICONTROL Username and Password]** i listrutan **[!UICONTROL Authentication]**.
   1. Använd ![Kopiera](/help/assets/icons/Copy.svg) för att kopiera och klistra in **[!UICONTROL Username]** från Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Username]**.
   1. Använd ![Kopiera](/help/assets/icons/Copy.svg) för att kopiera och klistra in **[!UICONTROL Password]** från Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Password]**. Om du använder en [icke-förfallande autentiseringsuppgift](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) ska du använda lösenordet för dina icke-förfallande autentiseringsuppgifter.
   1. Kontrollera att **[!UICONTROL Require SSL]** är markerad.
   1. Välj **[!UICONTROL Sign In]**.

   Du ser en **[!UICONTROL Progressing Request]**-dialogruta medan Skrivbord på Tablet PC verifierar anslutningen.
1. I huvudfönstret ser du följande i vyn Data Source i den vänstra rutan:
   * Namnet på anslutningen, under **[!UICONTROL Connections]**.
   * Namnet på databasen, under **[!UICONTROL Database]**.
   * En lista med tabeller, under **[!UICONTROL Table]**.
     ![Tablet PC ansluten](assets/tableau-connected.png)
   1. Dra **[!UICONTROL ares_sql_validation]**-posten och släpp posten i huvudvyn som läser **[!UICONTROL Drag tables]** här.
1. Huvudfönstret visar nu information om datavyn **[!UICONTROL ares_sql_validation]**.
   ![Tablet PC ansluten](assets/tableau-validation.png)

>[!ENDTABS]

+++


## Daglig trend

I det här fallet vill du visa en tabell och en enkel radvisualisering som visar en daglig trend för förekomster från 1 januari 2023 till 31 januari 2023.

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj dimensionen **[!UICONTROL daterangeday]**.
   1. Välj måttet **[!UICONTROL occurrences]**.

   En tabell visas med förekomsterna för den aktuella månaden. Förstora tabellvisualiseringen för bättre synlighet.

1. I rutan **[!UICONTROL Filters]**:

   1. Välj **[!UICONTROL daterangeday is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Advanced filtering]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `1/2/2023.` Du kan använda kalenderikonen för att välja och välja datum.
   1. Välj **[!UICONTROL Apply filter]**.

   Tabellen uppdateras med det använda **[!UICONTROL daterangeday]**-filtret.

1. I rutan **[!UICONTROL Visualizations]**:

   1. Välj visualisering för **[!UICONTROL Line chart]**.

   En linjediagramvisualisering ersätter tabellen och använder samma data som tabellen.

   ![Power BI Desktop Use Case 2 Date range filter](assets/uc2-pbi-filter-daterange.png)

1. Visualisering av linjediagram:

   1. Välj ![Mer](/help/assets/icons/More.svg).
   1. Välj **[!UICONTROL Show as a table]** på snabbmenyn.

   Huvudvyn uppdateras för att visa både en radvisualisering och en tabell.

   ![Power BI Desktop Use Case 2 Final Daily Trend visualization](assets/uc2-pbi-filter-final.png)

>[!TAB Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och anger en punkt på `01/01/2023` - `01/02/2023`.

      ![Datorfilter för Tablet PC](assets/uc2-tableau-filter.png)

   1. Dra och släpp **[!UICONTROL Daterangeday]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten i fältet bredvid **[!UICONTROL Columns]**.
      * Välj **[!UICONTROL Day]** i listrutan **[!UICONTROL Daterangeday]** så att värdet uppdateras till **[!UICONTROL DAY(Daterangeday)]**.
   1. Dra och släpp **[!UICONTROL Occurrences]** från listan **[!UICONTROL Tables (*Måttnamn *)]**i rutan **[!UICONTROL Data]**och släpp posten i fältet bredvid **[!UICONTROL Rows]**.
      * Värdena konverteras automatiskt till **[!UICONTROL SUM(Occurrences)]**.
   1. Ändra **[!UICONTROL Standard]** till **[!UICONTROL Entire View]** på den nedrullningsbara menyn i verktygsfältet.

      Vyn Blad 1 ska se ut så här nedan.

      ![Diagram för skrivbordsdator för Tableau](assets/uc2-tableau-graph.png)

1. Välj **[!UICONTROL Duplicate]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill skapa ett andra blad.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill byta namn på bladet till `Graph`.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1 (2)]** om du vill byta namn på bladet till `Data`.
1. Kontrollera att bladet **[!UICONTROL Data]** är markerat. I datavyn:
   1. Välj **[!UICONTROL Show me]** längst upp till höger och välj **[!UICONTROL Text table]** (övre vänstra visualiseringen) för att ändra innehållet i datavyn till en tabell.
   1. Dra **[!UICONTROL DAY(Daterangeday)]** från **[!UICONTROL Columns]** till **[!UICONTROL Rows]**.
   1. Ändra **[!UICONTROL Standard]** till **[!UICONTROL Entire View]** på den nedrullningsbara menyn i verktygsfältet.

      **[!UICONTROL Day]**-vyn ska se ut så här nedan.

      ![Skrivbordsdata för Tablet PC](assets/uc2-tableau-data.png)

1. Välj fliken **[!UICONTROL Dashboard]** om du vill skapa en ny **[!UICONTROL Dashboard 1]**-vy. I vyn **[!UICONTROL Dashboard 1]**:
   1. Dra och släpp **[!UICONTROL Graph]**-bladet från **[!UICONTROL Sheets]**-hyllan till **[!UICONTROL Dashboard 1]**-vyn som läser *Drop sheets här*.
   1. Dra och släpp **[!UICONTROL Data]**-bladet från **[!UICONTROL Sheets]**-hyllan nedanför **[!UICONTROL Graph]**-bladet till **[!UICONTROL Dashboard 1]**-vyn.
   1. Markera bladet **[!UICONTROL Data]** i vyn och ändra **[!UICONTROL Entire View]** till **[!UICONTROL Fix Width]**.

      **[!UICONTROL Dashboard 1]**-vyn ska se ut så här nedan.

      ![Instrumentpanel för bordsdator ](assets/uc2-tableau-dashboard.png)


>[!ENDTABS]

+++


## Trend varje timme

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++


## Månadstrender

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++


## Enkel dimension rankad

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++


## Flera dimensioner rankade

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++


## Räkna distinkta dimensionsvärden

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++



## Använd datumintervallnamn för att filtrera

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++



## Använd filternamn för att filtrera

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++



## Använd dimensionsvärden för att filtrera

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++



## Sortera

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++



## Gränser

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++



## Till FLATTEN eller inte

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++



## Dimension- och metriska omformningar

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++



## Visualiseringar och interaktioner

Synpunkter på användningsfall

+++ Information

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Steg

>[!TAB Tablet PC]

Steg

>[!ENDTABS]

+++


