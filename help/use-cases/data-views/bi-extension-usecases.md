---
title: Användningsexempel för BI-tillägget i Customer Journey Analytics
description: Flera användningsfall som visar hur BI-tillägget används i olika BI-verktyg i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
exl-id: 07db28b8-b688-4a0c-8fb3-28a124342d25
source-git-commit: ae07aa8a275a37f88d7626bac2f59e21d4c40e5a
workflow-type: tm+mt
source-wordcount: '7932'
ht-degree: 0%

---

# Användningsexempel för BI-tillägg

I den här artikeln beskrivs hur du slutför ett antal användningsfall med tillägget Customer Journey Analytics BI. I varje användningsexempel förklaras Customer Journey Analytics-funktionen, följt av information om de BI-verktyg som stöds:

* **Power BI Desktop**. Den version som används är 2.137.1102.0 (64 bitar) (oktober 2024).
* **Skrivbord för surfplatta**. Den version som används är 2024.1.5 (20241.24.0705.0334), 64 bitar.

Följande användningsfall dokumenteras:

* **Anslut**
   * [Visa och koppla data](#connect-and-validate)
   * [Till FLATTEN eller inte](#to-flatten-or-not)

* **Rapportera och analysera**
   * [Daglig trend](#daily-trend)
   * [Trend varje timme](#hourly-trend)
   * [Månadstrender](#monthly-trend)
   * [Enkel dimension rankad](#single-dimension-ranked)
   * [Flera dimensioner rankade](#multiple-dimension-ranked)
   * [Räkna distinkta dimensionsvärden](#count-distinct-dimension-values)
   * [Använd datumintervallnamn för att filtrera](#use-date-range-names-to-filter)
   * [Använd filternamn för att filtrera](#use-filter-names-to-filter)
   * [Använd dimensionsvärden för att filtrera](#use-dimension-values-to-filter)
   * [Sortera](#sort)
   * [Gränser](#limits)

* **Förstå**

   * [Omformningar](#transformations)
   * [Visualiseringar](#visualizations)
   * [Caveats](#caveats)

I **connect**-användningsexemplet fokuseras på hur du ansluter BI-verktyg med Customer Journey Analytics BI-tillägget.

**rapport- och analysexemplen** instruerar dig hur du kan uppnå liknande Customer Journey Analytics-visualiseringar i de BI-verktyg som för närvarande stöds.

**Använd**-användningsexemplen innehåller mer information om:

* Transformeringar som inträffar när du använder BI-verktyg för att rapportera och analysera.
* Visualiseringslikheter och skillnader mellan Customer Journey Analytics och BI-verktyg.
* Omslag till alla BI-verktyg som du bör känna till.


## Anslut och validera

I det här användningsexemplet ställs anslutningen in från BI-verktyget till Customer Journey Analytics, tillgängliga datavyer listas och en datavy väljs som ska användas.

+++ Customer Journey Analytics

Instruktionerna avser en exempelmiljö med följande objekt:

* Datavy: **[!UICONTROL C&C - Data View]** ??.
* Dimensioner: **[!UICONTROL Product Name]** ?? och **[!UICONTROL Product Category]** ?..
* Mätvärden: **[!UICONTROL Purchase Revenue]** ?? och **[!UICONTROL Purchases]** ?..
* Filter: **[!UICONTROL Fishing Products]** ??.

![Grundinställningar för Customer Journey Analytics](assets/cja-base.png)

När du går igenom användningsexemplen ersätter du de här exempelobjekten med objekt som passar just din miljö.

+++

+++ BI-verktyg

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Få åtkomst till de nödvändiga autentiseringsuppgifterna och parametrarna från användargränssnittet för Experience Platform-frågetjänsten.

   1. Navigera till din Experience Platform-sandlåda.
   1. Välj ![Frågor](/help/assets/icons/DataSearch.svg) **[!UICONTROL Queries]** i den vänstra listen.
   1. Välj fliken **[!UICONTROL Credentials]** i gränssnittet **[!UICONTROL Queries]**.
   1. Välj `prod:cja` i listrutan **[!UICONTROL Database]**.

      ![Fråga efter autentiseringsuppgifter för tjänsten](assets/queryservice-credentials.png)

1. Starta Power BI Desktop.
   1. Välj **[!UICONTROL Get data from other sources]** i huvudgränssnittet.
   1. I dialogrutan **[!UICONTROL Get Data]**:
      ![PowerBI PostgreSQL-databas](assets/powerbi-postgresql.png)
      1. Sök efter och välj **[!UICONTROL PostgreSQL database]**.
      1. Välj **[!UICONTROL Connect]**.
   1. I dialogrutan **[!UICONTROL PostgreSQL database]**:
      ![Inställningar för PowerBI Desktop Server och Database](assets/powerbi-serverdatabase.png)
      1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in värdena **[!UICONTROL Host]** och **[!UICONTROL Port]** från panelen Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]**, avgränsade med `:` som värde för **[!UICONTROL Server]**. Till exempel: `examplecompany.platform-query.adobe.io:80`.
      1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in värdet **[!UICONTROL Database]** från panelen **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** i Experience Platform. Lägg till `?FLATTEN` i värdet som du klistrar in. Exempel: `prod:cja?FLATTEN`.
      1. Välj **[!UICONTROL DirectQuery]** som **[!UICONTROL Data connectivity mode]**.
      1. Välj **[!UICONTROL OK]**.
   1. I dialogrutan **[!UICONTROL PostgreSQL database]** - **[!UICONTROL Database]**:
      ![PowerBI Desktop-användare och lösenord](assets/powerbi-userpassword.png)
      1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera värdena **[!UICONTROL Username]** och **[!UICONTROL Password]** från Experience Platform-panelen **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** i fälten **[!UICONTROL User name]** och **[!UICONTROL Password]**. Om du använder en [icke-förfallande autentiseringsuppgift](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) ska du använda lösenordet för dina icke-förfallande autentiseringsuppgifter.
      1. Kontrollera att listrutan för **[!UICONTROL Select which level to apply these settings to]** är inställd på **[!UICONTROL Server]** som du har definierat tidigare.
      1. Välj **[!UICONTROL Connect]**.
   1. I dialogrutan **[!UICONTROL Navigator]** hämtas datavyer. Den här hämtningen kan ta en stund. När du har hämtat det här ser du följande i Power BI Desktop.
      ![Power BI Destkop Load Data](assets/powerbi-navigator-load.png)
      1. Välj **[!UICONTROL public.cc_data_view]** i listan i den vänstra panelen.
      1. Du har två alternativ:
         1. Välj **[!UICONTROL Load]** om du vill fortsätta och slutföra konfigurationen.
         1. Välj **[!UICONTROL Transform Data]**. En dialogruta visas där du kan välja att använda omformningar som en del av konfigurationen.
            ![Power BI Desktop Transform Data](assets/powerbi-transform-data.png)
            * Välj **[!UICONTROL Close & Apply]**.
   1. Efter en stund visas **[!UICONTROL public.cc_data_view]** i rutan **[!UICONTROL Data]**. Välj ![SparronRight](/help/assets/icons/ChevronRight.svg) om du vill visa mått och mått.
      ![Power BI-tjänstserverdata har lästs in](assets/powerbi-navigator-loaded.png)


>[!TAB Skrivbord för Tablet PC]

1. Få åtkomst till de nödvändiga autentiseringsuppgifterna och parametrarna från användargränssnittet för Experience Platform-frågetjänsten.

   1. Navigera till din Experience Platform-sandlåda.
   1. Välj ![Frågor](/help/assets/icons/DataSearch.svg) **[!UICONTROL Queries]** i den vänstra listen.
   1. Välj fliken **[!UICONTROL Credentials]** i gränssnittet **[!UICONTROL Queries]**.
   1. Välj `prod:cja` i listrutan **[!UICONTROL Database]**.

      ![Fråga efter autentiseringsuppgifter för tjänsten](assets/queryservice-credentials.png)

1. Starta Tableu.
   1. Välj **[!UICONTROL PostgreSQL]** från den vänstra listen under **[!UICONTROL To a Server]**. Om den inte är tillgänglig väljer du **[!UICONTROL More...]** och väljer **[!UICONTROL PostgreSQL]** i **[!UICONTROL Installed Connectors]**.
      ![Tableu-anslutningar](assets/tableau-connectors.png)
   1. I dialogrutan **[!UICONTROL PostgreSQL]** går du till fliken **[!UICONTROL General]**:
      ![Dialogrutan Logga in i tabell](assets/tableau-signin.png)
      1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in **[!UICONTROL Host]** från Experience Platform-panelen **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Server]**.
      1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in **[!UICONTROL Port]** från Experience Platform-panelen **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Port]**.
      1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in **[!UICONTROL Database]** från Experience Platform-panelen **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Database]**. Lägg till `%3FFLATTEN` i värdet som du klistrar in. Till exempel: `prod:cja%3FFLATTEN`.
      1. Välj **[!UICONTROL Username and Password]** i listrutan **[!UICONTROL Authentication]**.
      1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in **[!UICONTROL Username]** från Experience Platform-panelen **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Username]**.
      1. Använd ![Kopiera](/help/assets/icons/Copy.svg) om du vill kopiera och klistra in **[!UICONTROL Password]** från Experience Platform-panelen **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** till **[!UICONTROL Password]**. Om du använder en [icke-förfallande autentiseringsuppgift](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) ska du använda lösenordet för dina icke-förfallande autentiseringsuppgifter.
      1. Kontrollera att **[!UICONTROL Require SSL]** är markerad.
      1. Välj **[!UICONTROL Sign In]**.

      Du ser en **[!UICONTROL Progressing Request]**-dialogruta medan Skrivbord på Tablet PC verifierar anslutningen.
   1. I huvudfönstret visas på sidan **[!UICONTROL Data Source]** i den vänstra rutan:
      * Namnet på anslutningen, under **[!UICONTROL Connections]**.
      * Namnet på databasen, under **[!UICONTROL Database]**.
      * En lista med tabeller, under **[!UICONTROL Table]**.
        ![Tablet PC ansluten](assets/tableau-connected.png)
      1. Dra **[!UICONTROL cc_data_view]**-posten och släpp posten i huvudvyn som läser **[!UICONTROL Drag tables]** här.
   1. I huvudfönstret visas information om datavyn **[!UICONTROL cc_data_view]**.
      ![Tablet PC ansluten](assets/tableau-validation.png)

>[!ENDTABS]

+++

## Till FLATTEN eller inte

I det här fallet vill du veta om du måste använda ytterligare en `FLATTEN`-parameter för databasen när du ansluter till Customer Journey Analytics med BI-tillägget.

+++ Customer Journey Analytics

Customer Journey Analytics tillhandahåller information om hur du ansluter i gränssnittet Experience Platform.

1. Navigera till din Experience Platform-sandlåda.
1. Välj ![Frågor](/help/assets/icons/DataSearch.svg) **[!UICONTROL Queries]** i den vänstra listen.
1. Välj fliken **[!UICONTROL Credentials]** i gränssnittet **[!UICONTROL Queries]**.
1. Välj `prod:cja` i listrutan **[!UICONTROL Database]**.

![Fråga efter autentiseringsuppgifter för tjänsten](assets/queryservice-credentials.png)


+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för. I avsnittet BI-verktyg finns information om vilka explicita `FLATTEN`-parameteralternativ som krävs för en korrekt anslutning.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Power BI Desktop stöder följande scenarier för parametern `FLATTEN`.

| FLATTEN-parameter | Exempel | Stöds | Anmärkningar |
|---|---|:---:|---|
| Ingen | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CloseCircle](/help/assets/icons/CloseCircle.svg) | Power BI Desktop visar fel: **[!UICONTROL We couldn't authenticate with the credentials provided. Please try again.]** |

>[!TAB Skrivbord för Tablet PC]

Tableu Desktop stöder följande scenarier för parametern `FLATTEN`.

| FLATTEN-parameter | Exempel | Stöds | Anmärkningar |
|---|---|:---:|---|
| Ingen | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |

>[!ENDTABS]

+++


## Daglig trend

I det här fallet vill du visa en tabell och en enkel radvisualisering som visar en daglig trend för förekomster (händelser) från 1 januari 2023 till 31 januari 2023.

+++ Customer Journey Analytics

Ett exempel på **[!UICONTROL Daily Trend]**-panel för användningsfallet:

![Customer Journey Analytics, panelen Trend dagligen](assets/cja_daily_trend.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat en [lyckad anslutning och kan visa och använda datavyer](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterangeday]**.
   1. Välj **[!UICONTROL ∑ occurrences]**.

   En tabell visas med förekomsterna för den aktuella månaden. Förstora visualiseringen för bättre synlighet.

1. I rutan **[!UICONTROL Filters]**:

   1. Välj **[!UICONTROL daterangeday is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Advanced filtering]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023.` Du kan använda kalenderikonen för att välja och välja datum.
   1. Välj **[!UICONTROL Apply filter]**.

   Tabellen uppdateras med det använda **[!UICONTROL daterangeday]**-filtret.

1. I rutan **[!UICONTROL Visualizations]** väljer du **[!UICONTROL Line chart]**-visualisering.

   En linjediagramvisualisering ersätter tabellen och använder samma data som tabellen. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop Use Case 2 Date range filter](assets/uc2-pbi-daterange.png)

1. Visualisering av linjediagram:

   1. Välj ![Mer](/help/assets/icons/More.svg).
   1. Välj **[!UICONTROL Show as a table]** på snabbmenyn.

   Huvudvyn uppdateras för att visa både en radvisualisering och en tabell. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop Use Case 2 Final Daily Trend visualization](assets/uc2-pbi-final.png)

>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned för att växla från vyn **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och anger en punkt på `01/01/2023` - `01/02/2023`.

      ![Datorfilter för Tablet PC](assets/uc2-tableau-filter.png)

   1. Dra och släpp **[!UICONTROL Daterangeday]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten i fältet bredvid **[!UICONTROL Columns]**.
      * Välj **[!UICONTROL Day]** i listrutan **[!UICONTROL Daterangeday]** så att värdet uppdateras till **[!UICONTROL DAY(Daterangeday)]**.
   1. Dra och släpp **[!UICONTROL Occurrences]** från listan **[!UICONTROL Tables (*Måttnamn *)]**i rutan **[!UICONTROL Data]**och släpp posten i fältet bredvid **[!UICONTROL Rows]**.
      * Värdena konverteras automatiskt till **[!UICONTROL SUM(Occurrences)]**.
   1. Ändra **[!UICONTROL Standard]** till **[!UICONTROL Entire View]** i listrutan **[IUICONTROL-anpassning]** i verktygsfältet.

      Ditt skrivbord ska se ut så här nedan.

      ![Diagram för skrivbordsdator för Tableau](assets/uc2-tableau-graph.png)

1. Välj **[!UICONTROL Duplicate]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill skapa ett andra blad.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill byta namn på bladet till `Graph`.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1 (2)]** om du vill byta namn på bladet till `Data`.
1. Kontrollera att bladet **[!UICONTROL Data]** är markerat. I vyn **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL Show me]** längst upp till höger och välj **[!UICONTROL Text table]** (övre vänstra visualiseringen) för att ändra innehållet i datavyn till en tabell.
   1. Välj **[!UICONTROL Swap Rows and Columns]** i verktygsfältet.
   1. Ändra **[!UICONTROL Standard]** till **[!UICONTROL Entire View]** i listrutan **[IUICONTROL-anpassning]** i verktygsfältet.

      Ditt skrivbord ska se ut så här nedan.

      ![Skrivbordsdata för Tablet PC](assets/uc2-tableau-data.png)

1. Skapa en ny **[!UICONTROL Dashboard 1]**-vy genom att klicka på flikknappen **[!UICONTROL New Dashboard]** (längst ned). I vyn **[!UICONTROL Dashboard 1]**:
   1. Dra och släpp **[!UICONTROL Graph]**-bladet från **[!UICONTROL Sheets]**-hyllan till **[!UICONTROL Dashboard 1]**-vyn som läser *Drop sheets här*.
   1. Dra och släpp **[!UICONTROL Data]**-bladet från **[!UICONTROL Sheets]**-hyllan nedanför **[!UICONTROL Graph]**-bladet till **[!UICONTROL Dashboard 1]**-vyn.
   1. Markera bladet **[!UICONTROL Data]** i vyn och ändra **[!UICONTROL Entire View]** till **[!UICONTROL Fix Width]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Instrumentpanel för bordsdator ](assets/uc2-tableau-dashboard.png)

>[!ENDTABS]

+++


## Trend varje timme

I det här fallet vill du visa en tabell och en enkel radvisualisering som visar en timtrend för förekomster (händelser) för 1 januari 2023.

+++ Customer Journey Analytics

Ett exempel på **[!UICONTROL Hourly Trend]**-panel för användningsfallet:

![Customer Journey Analytics Trendvisualiseringar per timme](assets/cja_hourly_trend.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

![AlertRed](/help/assets/icons/AlertRed.svg) Power BI **förstår** inte hur datum- och tidsfält ska hanteras, så dimensioner som **[!UICONTROL daterangehour]** och **[!UICONTROL daterangeminute]** stöds inte.

>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och anger en punkt på `01/01/2023` - `02/01/2023`.

      ![Datorfilter för Tablet PC](assets/uc3-tableau-filter.png)

   1. Dra och släpp **[!UICONTROL Daterangehour]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten i fältet bredvid **[!UICONTROL Columns]**.
      * Välj **[!UICONTROL More]** > **[!UICONTROL Hours]** i listrutan **[!UICONTROL Daterangeday]** så att värdet uppdateras till **[!UICONTROL HOUR(Daterangeday)]**.
   1. Dra och släpp **[!UICONTROL Occurrences]** från listan **[!UICONTROL Tables (*Måttnamn *)]**i rutan **[!UICONTROL Data]**och släpp posten i fältet bredvid **[!UICONTROL Rows]**.
      * Värdena konverteras automatiskt till **[!UICONTROL SUM(Occurrences)]**.
   1. Ändra **[!UICONTROL Standard]** till **[!UICONTROL Entire View]** i listrutan **[IUICONTROL-anpassning]** i verktygsfältet.

      Ditt skrivbord ska se ut så här nedan.

      ![Diagram för skrivbordsdator för Tableau](assets/uc3-tableau-graph.png)

1. Välj **[!UICONTROL Duplicate]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill skapa ett andra blad.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill byta namn på bladet till `Graph`.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1 (2)]** om du vill byta namn på bladet till `Data`.
1. Kontrollera att bladet **[!UICONTROL Data]** är markerat. I vyn **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL Show me]** längst upp till höger och välj **[!UICONTROL Text table]** (övre vänstra visualiseringen) för att ändra innehållet i datavyn till en tabell.
   1. Dra **[!UICONTROL HOUR(Daterangeday)]** från **[!UICONTROL Columns]** till **[!UICONTROL Rows]**.
   1. Ändra **[!UICONTROL Standard]** till **[!UICONTROL Entire View]** i listrutan **[IUICONTROL-anpassning]** i verktygsfältet.

      Ditt skrivbord ska se ut så här nedan.

      ![Skrivbordsdata för Tablet PC](assets/uc3-tableau-data.png)

1. Skapa en ny **[!UICONTROL Dashboard 1]**-vy genom att klicka på tabbknappen **[!UICONTROL New Dashboard]** (längst ned). I vyn **[!UICONTROL Dashboard 1]**:
   1. Dra och släpp **[!UICONTROL Graph]**-bladet från **[!UICONTROL Sheets]**-hyllan till **[!UICONTROL Dashboard 1]**-vyn som läser *Drop sheets här*.
   1. Dra och släpp **[!UICONTROL Data]**-bladet från **[!UICONTROL Sheets]**-hyllan nedanför **[!UICONTROL Graph]**-bladet till **[!UICONTROL Dashboard 1]**-vyn.
   1. Markera bladet **[!UICONTROL Data]** i vyn och ändra **[!UICONTROL Entire View]** till **[!UICONTROL Fix Width]**.

      **[!UICONTROL Dashboard 1]**-vyn ska se ut så här nedan.

      ![Instrumentpanel för bordsdator ](assets/uc3-tableau-dashboard.png)


>[!ENDTABS]

+++


## Månadstrender

I det här fallet vill du visa en tabell och en enkel radvisualisering som visar en månatlig trend för händelser för 2023.

+++ Customer Journey Analytics

Ett exempel på **[!UICONTROL Monthly Trend]**-panel för användningsfallet:

![Customer Journey Analytics - månatlig trendvisualisering](assets/cja_monthly_trend.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterangemonth]**.
   1. Välj **[!UICONTROL ∑ occurrences]**.

   En tabell visas med förekomsterna för den aktuella månaden. Förstora visualiseringen för bättre synlighet.

1. I rutan **[!UICONTROL Filters]**:

   1. Välj **[!UICONTROL daterangemonth is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Advanced filtering]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `1/1/2024.` Du kan använda kalenderikonen för att välja och välja datum.
   1. Välj **[!UICONTROL Apply filter]**.

   Tabellen uppdateras med det använda **[!UICONTROL daterangemonth]**-filtret.

1. I rutan **[!UICONTROL Visualizations]**:

   1. Välj visualisering för **[!UICONTROL Line chart]**.

   En linjediagramvisualisering ersätter tabellen och använder samma data som tabellen. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop Use Case 2 Date range filter](assets/uc4-pbi-filter-daterange.png)

1. Visualisering av linjediagram:

   1. Välj ![Mer](/help/assets/icons/More.svg).
   1. Välj **[!UICONTROL Show as a table]** på snabbmenyn.

   Huvudvyn uppdateras för att visa både en radvisualisering och en tabell. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop Use Case 2 Final Daily Trend visualization](assets/uc4-pbi-filter-final.png)

>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och anger en punkt på `01/01/2023` - `01/01/2024`.

      ![Datorfilter för Tablet PC](assets/uc4-tableau-filter.png)

   1. Dra och släpp **[!UICONTROL Daterangeday]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten i fältet bredvid **[!UICONTROL Columns]**.
      * Välj **[!UICONTROL MONTH]** i listrutan **[!UICONTROL Daterangeday]** så att värdet uppdateras till **[!UICONTROL MONTH(Daterangeday)]**.
   1. Dra och släpp **[!UICONTROL Occurrences]** från listan **[!UICONTROL Tables (*Måttnamn *)]**i rutan **[!UICONTROL Data]**och släpp posten i fältet bredvid **[!UICONTROL Rows]**.
      * Värdena konverteras automatiskt till **[!UICONTROL SUM(Occurrences)]**.
   1. Ändra **[!UICONTROL Standard]** till **[!UICONTROL Entire View]** i listrutan **[IUICONTROL-anpassning]** i verktygsfältet.

      Ditt skrivbord ska se ut så här nedan.

      ![Diagram för skrivbordsdator för Tableau](assets/uc4-tableau-graph.png)

1. Välj **[!UICONTROL Duplicate]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill skapa ett andra blad.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill byta namn på bladet till `Graph`.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1 (2)]** om du vill byta namn på bladet till `Data`.
1. Kontrollera att bladet **[!UICONTROL Data]** är markerat. I datavyn:
   1. Välj **[!UICONTROL Show me]** längst upp till höger och välj **[!UICONTROL Text table]** (övre vänstra visualiseringen) för att ändra innehållet i datavyn till en tabell.
   1. Dra **[!UICONTROL MONTH(Daterangeday)]** från **[!UICONTROL Columns]** till **[!UICONTROL Rows]**.
   1. Ändra **[!UICONTROL Standard]** till **[!UICONTROL Entire View]** i listrutan **[IUICONTROL-anpassning]** i verktygsfältet.

      Ditt skrivbord ska se ut så här nedan.

      ![Skrivbordsdata för Tablet PC](assets/uc4-tableau-data.png)

1. Skapa en ny **[!UICONTROL Dashboard 1]**-vy genom att klicka på tabbknappen **[!UICONTROL New Dashboard]** (längst ned). I vyn **[!UICONTROL Dashboard 1]**:
   1. Dra och släpp **[!UICONTROL Graph]**-bladet från **[!UICONTROL Sheets]**-hyllan till **[!UICONTROL Dashboard 1]**-vyn som läser *Drop sheets här*.
   1. Dra och släpp **[!UICONTROL Data]**-bladet från **[!UICONTROL Sheets]**-hyllan nedanför **[!UICONTROL Graph]**-bladet till **[!UICONTROL Dashboard 1]**-vyn.
   1. Markera bladet **[!UICONTROL Data]** i vyn och ändra **[!UICONTROL Entire View]** till **[!UICONTROL Fix Width]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Instrumentpanel för bordsdator ](assets/uc4-tableau-dashboard.png)

>[!ENDTABS]

+++


## Enkel dimension rankad

I det här fallet vill du visa en tabell och en enkel fältvisualisering som visar köp- och inköpsintäkter för produktnamn under 2023.

+++ Customer Journey Analytics

Ett exempel på **[!UICONTROL Single Dimension Ranked]**-panel för användningsfallet:

![Customer Journey Analytics, endimensionell, rankad visualisering](assets/cja-single-dimension-ranked.png)
+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterange]**.
   1. Välj **[!UICONTROL product_name]**.
   1. Välj **[!UICONTROL ∑ purchase_revenue]**.
   1. Välj **[!UICONTROL ∑ purchases]**.

   En tom tabell visas endast med kolumnrubrikerna för det markerade elementet. Förstora visualiseringen för bättre synlighet.

1. I rutan **[!UICONTROL Filters]**:

   1. Välj **[!UICONTROL daterange is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Relative date]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is in the last]** `1` **[!UICONTROL calendar years]**.
   1. Välj **[!UICONTROL Apply filter]**.

   Tabellen uppdateras med det använda **[!UICONTROL daterange]**-filtret.

1. I rutan **[!UICONTROL Visualization]**:

   1. Använd ![CrossSize75](/help/assets/icons/CrossSize75.svg) för att ta bort **[!UICONTROL daterange]** från **[!UICONTROL Columns]**.
   1. Dra **[!UICONTROL Sum of purchases_revenue]** under **[!UICONTROL Sum of purchases]** i **[!UICONTROL Columns]**.

1. I tabellvisualiseringen:

   1. Välj **[!UICONTROL Sum of purchase_revenue]** om du vill sortera produktnamnen i fallande inköpsintäktsordning. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop Use Case 5 Table status ](assets/uc5-pbi-table.png)

1. I rutan **[!UICONTROL Filters]**:

   1. Välj **[!UICONTROL product_name is (All)]**.
   1. Ange **[!UICONTROL Filter type]** till **[!UICONTROL Top N]**.
   1. Definiera filtret för **[!UICONTROL Show items]** **[!UICONTROL Top]** `10` **[!UICONTROL By value]**.
   1. Dra och släpp **[!UICONTROL purchase_revenue]** i **[!UICONTROL By value]** **[!UICONTROL Add data fields here]**.
   1. Välj **[!UICONTROL Apply filter]**.

   Tabellen uppdateras med värden för inköpsintäkter synkroniserat med frihandstabellens visualisering i Analysis Workspace.

1. I rutan **[!UICONTROL Visualizations]**:

   1. Välj visualisering för **[!UICONTROL Line and stacked column chart]**.

   En visualisering av ett linjediagram och ett skiktat stapeldiagram ersätter tabellen med samma data som tabellen.

1. Dra och släpp **[!UICONTROL purchases]** på **[!UICONTROL Line y-axis]** i rutan **[!UICONTROL Visualizations]**.

   Linjediagrammet och det staplade stapeldiagrammet uppdateras. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI, användningsfall för datorer, versaler 5, diagram](assets/uc5-pbi-chart.png)

1. Visualisering av linjediagram och skiktade stapeldiagram:

   1. Välj ![Mer](/help/assets/icons/More.svg).
   1. Välj **[!UICONTROL Show as a table]** på snabbmenyn.

   Huvudvyn uppdateras för att visa både en radvisualisering och en tabell.

   ![Power BI Desktop Use Case 2 Final Daily Trend visualization](assets/uc5-pbi-final.png)

>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och anger en punkt på `01/01/2023` - `31/12/2024`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.

      ![Datorfilter för Tablet PC](assets/uc5-tableau-filter.png)

   1. Dra och släpp **[!UICONTROL Product Name]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten i fältet bredvid **[!UICONTROL Rows]**.
   1. Dra och släpp **[!UICONTROL Purchases]** från listan **[!UICONTROL Tables (*Måttnamn *)]**i rutan **[!UICONTROL Data]**och släpp posten i fältet bredvid **[!UICONTROL Rows]**.
      * Värdena konverteras automatiskt till **[!UICONTROL SUM(Purchases)]**.
   1. Dra och släpp **[!UICONTROL Purchase Revenue]** från listan **[!UICONTROL Tables (*Måttnamn *)]**i rutan **[!UICONTROL Data]**och släpp posten i fältet intill **[!UICONTROL Columns]**och vänster från **[!UICONTROL SUM(Purchases)]**.
      * Värdena konverteras automatiskt till **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Om du vill beställa båda diagrammen i fallande inköpsintäktsordning för du muspekaren över rubriken **[!UICONTROL Purchase Revenue]** och väljer sorteringsikonen.
   1. Om du vill begränsa antalet poster i diagrammen väljer du **[!UICONTROL SUM(Purchase Revenue)]** i **[!UICONTROL Rows]** och väljer **[!UICONTROL Filter]** i listrutan.
   1. I dialogrutan **[!UICONTROL Filter \[Purchase Revenue\]]** väljer du **[!UICONTROL Range of values]** och anger lämpliga värden. Till exempel: `1,000,000` - `2,000,000`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Om du vill konvertera de två stapeldiagrammen till ett dubbelkombinationsdiagram väljer du **[!UICONTROL SUM(Purchases)]** i **[!UICONTROL Rows]** och väljer **[!UICONTROL Dual Axis]** i listrutan. Stolpdiagrammen omformas till en punktdiagram.
   1. Så här ändrar du punktdiagram till ett stapeldiagram:
      1. Välj **[!UICONTROL SUM(Purchases)]** i området **[!UICONTROL Marks]** och välj **[!UICONTROL Line]** i listrutan.
      1. Välj **[!UICONTROL SUM(Purchase Revenue)]** i området **[!UICONTROL Marks]** och välj **[!UICONTROL Bar]** i listrutan.

   Ditt skrivbord ska se ut så här nedan.

   ![Diagram för skrivbordsdator för Tableau](assets/uc5-tableau-graph.png)

1. Välj **[!UICONTROL Duplicate]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill skapa ett andra blad.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill byta namn på bladet till `Data`.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1 (2)]** om du vill byta namn på bladet till `Graph`.
1. Kontrollera att bladet **[!UICONTROL Data]** är markerat.
   1. Välj **[!UICONTROL Show me]** längst upp till höger och välj **[!UICONTROL Text table]** (övre vänstra visualiseringen) för att ändra innehållet i de två diagrammen till en tabell.
   1. Om du vill beställa inköpsintäkt i fallande ordning för du över **[!UICONTROL Purchase Revenue]** i tabellen och väljer ![SortOrderDown](/help/assets/icons/SortOrderDown.svg).
   1. Välj **[!UICONTROL Entire View]** i listrutan **[!UICONTROL Fit]**.

   Ditt skrivbord ska se ut så här nedan.

   ![Skrivbordsdata för Tablet PC](assets/uc5-tableau-data.png)

1. Skapa en ny **[!UICONTROL Dashboard 1]**-vy genom att klicka på tabbknappen **[!UICONTROL New Dashboard]** (längst ned). I vyn **[!UICONTROL Dashboard 1]**:
   1. Dra och släpp **[!UICONTROL Graph]**-bladet från **[!UICONTROL Sheets]**-hyllan till **[!UICONTROL Dashboard 1]**-vyn som läser *Drop sheets här*.
   1. Dra och släpp **[!UICONTROL Data]**-bladet från **[!UICONTROL Sheets]**-hyllan nedanför **[!UICONTROL Graph]**-bladet till **[!UICONTROL Dashboard 1]**-vyn.
   1. Markera bladet **[!UICONTROL Data]** i vyn och ändra **[!UICONTROL Entire View]** till **[!UICONTROL Fix Width]**.

   **[!UICONTROL Dashboard 1]**-vyn ska se ut så här nedan.

   ![Instrumentpanel för bordsdator ](assets/uc5-tableau-dashboard.png)

>[!ENDTABS]

+++


## Flera dimensioner rankade

I det här fallet vill du visa en tabell som delar upp inköpsinkomster och inköp för produktnamn inom produktkategorier under 2023. Dessutom vill du använda visualiseringar för att illustrera både produktkategorifördelningen och bidragen till produktnamn inom varje produktkategori.

+++ Customer Journey Analytics

Ett exempel på **[!UICONTROL Multiple Dimension Ranked]**-panel för användningsfallet:

![Rankad panel för flera Dimensioner i Customer Journey Analytics](assets/cja-multiple-dimension-ranked.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
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
   1. Välj **[!UICONTROL ∑ purchase_revenue]**
   1. Välj **[!UICONTROL ∑ purchases]**

1. Om du vill ändra det lodräta stapeldiagrammet till en tabell kontrollerar du att tabellen är markerad och väljer **[!UICONTROL Matrix]** i rutan **[!UICONTROL Visualizations]**.
   * Dra **[!UICONTROL product_name]** från **[!UICONTROL Columns]** och släpp fältet under **[!UICONTROL product_categor]**y i **[!UICONTROL Rows]** i rutan **[!UICONTROL Visualization]**.

1. Om du vill begränsa antalet produkter som visas i tabellen väljer du **[!UICONTROL product_name is (All)]** i rutan **[!UICONTROL Filters]**.

   1. Välj **[!UICONTROL Advanced filtering]**.
   1. Välj **[!UICONTROL Filter type]** **[!UICONTROL Top N]** **[!UICONTROL Show items]** **[!UICONTROL Top]** `15` **[!UICONTROL By Value]**.
   1. Dra **[!UICONTROL purchases]** från rutan **[!UICONTROL Data]** till rutan **[!UICONTROL Add data fields here]**.
   1. Välj **[!UICONTROL Apply filter]**.

1. Om du vill förbättra läsbarheten väljer du **[!UICONTROL View]** på den översta menyn, väljer **[!UICONTROL Page View]** > **[!UICONTROL Actual size]** och ändrar storlek på tabellvisualiseringen.

1. Om du vill dela upp varje kategori i tabellen väljer du **[!UICONTROL +]** på produktkategorinivå. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop Multiple Dimensions Rankad matristabell](assets/uc6-powerbi-data.png)

1. Välj **[!UICONTROL Home]** på den översta menyn och välj **[!UICONTROL New visual]**. En ny visuell vy läggs till i rapporten.

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL product_category]**.
   1. Välj **[!UICONTROL product_name]**.
   1. Välj **[!UICONTROL purchase_revenue]**.

1. Om du vill ändra det visuella objektet markerar du stapeldiagrammet och väljer **[!UICONTROL Treemap]** i rutan **[!UICONTROL Visualizations]**.
1. Se till att **[!UICONTROL product_category]** visas under **[!UICONTROL Category]** och att **[!UICONTROL product_name]** visas under **[!UICONTROL Details]** i rutan **[!UICONTROL Visualizations]**.

   Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop Multiple Dimensions Rankad treemap](assets/uc6-powerbi-treemap.png)

1. Välj **[!UICONTROL Home]** på den översta menyn och välj **[!UICONTROL New visual]**. En ny visuell vy läggs till i rapporten.

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL product_category]**.
   1. Välj **[!UICONTROL purchase_revenue]**.
   1. Välj **[!UICONTROL purchase]**.

1. I rutan **[!UICONTROL Visualizations]**:
   1. Välj **[!UICONTROL Line and stacked column chart]** om du vill ändra visualiseringen.
   1. Dra **[!UICONTROL sum_of_purchases]** från **[!UICONTROL Column y-axis]** till **[!UICONTROL Line y-axis]**.

1. Blanda om de enskilda visualiseringarna i rapporten.

   Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop Multiple Dimensions Rankad sist](assets/uc6-powerbi-final.png)


>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Relative dates]**, väljer **[!UICONTROL Years]** och anger **[!UICONTROL Previous year]**. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Datorrankat filter för flera Dimensioner i Tableu ](assets/uc6-tableau-filter.png)

   1. Dra **[!UICONTROL Product Category]** och släpp intill **[!UICONTROL Columns]**.
   1. Dra **[!UICONTROL Purchase Revenue]** och släpp intill **[!UICONTROL Rows]**. Värdet ändras till **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Dra inköp och släpp bredvid **[!UICONTROL Rows]**. Värdet ändras till **[!UICONTROL SUM(Purchases)]**.
   1. Välj **[!UICONTROL SUM(Purchases)]** och välj **[!UICONTROL Dual Axis]** i listrutan.
   1. Välj **[!UICONTROL SUM(Purchases)]** i **[!UICONTROL Marks]** och välj **[!UICONTROL Line]** i listrutan.
   1. Välj **[!UICONTROL SUM(Purchase Revenue)]** i **[!UICONTROL Marks]** och välj **[!UICONTROL Bar]** i listrutan.
   1. Välj **[!UICONTROL Entire View]** på menyn **[!UICONTROL Fit]**.
   1. Markera rubriken **[!UICONTROL Purchase Revenue]** i diagrammet och kontrollera att inköpsinkomsterna är i stigande ordning.

      Ditt skrivbord ska se ut så här nedan.

      ![Datordefinierad kategori för flera Dimensioner i Tableu ](assets/uc6-tableau-category.png)

1. Byt namn på aktuellt **[!UICONTROL Sheet 1]**-blad till `Category`.
1. Välj **[!UICONTROL New Worksheet]** om du vill skapa ett nytt blad och ändra namnet till `Data`.

   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Relative dates]**, väljer **[!UICONTROL Years]** och anger **[!UICONTROL Previous year]**. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Purchase Revenue]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Dra **[!UICONTROL Purchase]** från **[!UICONTROL Data]**-rutan till **[!UICONTROL Columns]**, intill **[!UICONTROL Purchase Revenue]**. Värdet ändras till **[!UICONTROL SUM(Purchases)]**.
   1. Dra **[!UICONTROL Product Category]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Rows]**.
   1. Dra **[!UICONTROL Product Name]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Rows]**, bredvid **[!UICONTROL Product Category]**.
   1. Om du vill ändra de två vågräta staplarna till en tabell väljer du **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Om du vill begränsa antalet produkter väljer du **[!UICONTROL Purchases]** i **[!UICONTROL Measure Values]**. Välj **[!UICONTROL Filter]** i listrutan.
   1. I dialogrutan **[!UICONTROL Filter \[Purchases\]]** väljer du **[!UICONTROL At least]** och anger `7000`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL the]** Anpassa.

      Ditt skrivbord ska se ut så här nedan.

      ![Datorrankade data för flera Dimensioner på Tableu-skrivbordet](assets/uc6-tableau-data.png)

1. Välj **[!UICONTROL New worksheet]** om du vill skapa ett nytt blad och ändra namnet till **[!UICONTROL Treemap]**.
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filters Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Relative dates]**, väljer **[!UICONTROL Years]** och anger **[!UICONTROL Previous year]**. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Purchase Revenue]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Rows]**. Värdena ändras till **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Dra **[!UICONTROL Purchase]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Rows]**, bredvid **[!UICONTROL Purchase Revenue]**. Värdet ändras till **[!UICONTROL SUM(Purchases)]**.
   1. Dra **[!UICONTROL Product Category]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Columns]**.
   1. Dra **[!UICONTROL Product Name]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Columns]**.
   1. Om du vill ändra de två vertikala stapeldiagrammen till en treemap väljer du **[!UICONTROL Treemap]** från **[!UICONTROL Show Me]**.
   1. Om du vill begränsa antalet produkter väljer du **[!UICONTROL Purchases]** i **[!UICONTROL Measure Values]**. Välj **[!UICONTROL Filter]** i listrutan.
   1. I dialogrutan **[!UICONTROL Filter \[Purchases\]]** väljer du **[!UICONTROL At least]** och anger `7000`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Datorrankade data för flera Dimensioner på Tableu-skrivbordet](assets/uc6-tableau-treemap.png)

1. Skapa en ny **[!UICONTROL Dashboard 1]**-vy genom att klicka på tabbknappen **[!UICONTROL New Dashboard]** (längst ned). I vyn **[!UICONTROL Dashboard 1]**:
   1. Dra och släpp **[!UICONTROL Category]**-bladet från **[!UICONTROL Sheets]**-hyllan till **[!UICONTROL Dashboard 1]**-vyn som läser *Drop sheets här*.
   1. Dra och släpp **[!UICONTROL Treemap]**-bladet från **[!UICONTROL Sheets]**-hyllan nedanför **[!UICONTROL Category]**-bladet till **[!UICONTROL Dashboard 1]**-vyn.
   1. Dra och släpp **[!UICONTROL Data]**-bladet från **[!UICONTROL Sheets]**-hyllan nedanför **[!UICONTROL Treemap]**-bladet till **[!UICONTROL Dashboard 1]**-vyn.
   1. Ändra storlek på alla blad i vyn.

   **[!UICONTROL Dashboard 1]**-vyn ska se ut så här nedan.

   ![Instrumentpanel för bordsdator ](assets/uc6-tableau-final.png)

>[!ENDTABS]

+++


## Räkna distinkta dimensionsvärden

Du vill ha det tydliga antalet produktnamn som rapporterades i januari 2023.

+++ Customer Journey Analytics

Om du vill rapportera ett distinkt antal produktnamn anger du ett beräknat mått i Customer Journey Analytics, med **[!UICONTROL Title]** `Product Name (Count Distinct)` och **[!UICONTROL External Id]** `product_name_count_distinct`.

![Customer Journey Analytics produktnamn (Distincr Count) beräknat mått](assets/cja-calc-metric-distinct-count-product-names.png)

Du kan sedan använda det måttet i en **[!UICONTROL Count Distinct Dimension Values]**-panel för följande användningsfall:

![Värden för distinkt räkning för Customer Journey Analytics](assets/cja-count-distinct-dimension-values.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Om du vill vara säker på att datumintervallet gäller för alla visualiseringar drar och släpper du **[!UICONTROL daterangeday]** från rutan **[!UICONTROL Data]** till **[!UICONTROL Filters]** på den här sidan.
   1. Välj **[!UICONTROL daterangeday is (All)]** från **[!UICONTROL Filters on this page]**.
   1. Välj **[!UICONTROL Advanced filtering]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Välj **[!UICONTROL Apply filter]**.

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL datarangeday]**.
   1. Välj **[!UICONTROL ∑ cm_product_name_count_distinct]**, som är det beräknade måttet som definieras i Customer Journey Analytics.

1. Om du vill ändra det lodräta stapeldiagrammet till en tabell kontrollerar du att diagrammet är markerat och väljer **[!UICONTROL Table]** i rutan **[!UICONTROL Visualizations]**.

   Ditt Power BI Desktop ska se ut så här nedan.

   ![Distinkt tabell för antal Power BI Desktop Multiple Count](assets/uc7-powerbi-table.png)

1. Välj tabellvisualisering. Välj **[!UICONTROL Copy]** > **[!UICONTROL Copy visual]** på snabbmenyn.
1. Klistra in visualiseringen med **[!UICONTROL ctrl-v]**. Den exakta kopian av visualiseringen överlappar den ursprungliga. Flytta den åt höger i rapportområdet.
1. Om du vill ändra den kopierade visualiseringen från en tabell till ett kort väljer du **[!UICONTROL Card]** från **[!UICONTROL Visualizations]**.

   Ditt Power BI Desktop ska se ut så här nedan.

   ![Distinkt tabell för antal Power BI Desktop Multiple Count](assets/uc7-powerbi-final.png)

>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange]** från listan **[!UICONTROL Tables]** i rutan **[!UICONTROL Data]** och släpp posten på hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filter Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och sedan `01/01/2023` - `31/1/2023`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Cm Product Name Count Distinct]** till **[!UICONTROL Rows]**. Värdet ändras till **[!UICONTROL SUM(Cm Product Name Count Distinct)]**. Det här fältet är det beräknade måttet som du har definierat i Customer Journey Analytics.
   1. Dra **[!UICONTROL Daterangeday]** och släpp intill **[!UICONTROL Columns]**. Välj **[!UICONTROL Daterangeday]** och välj **[!UICONTROL Day]** i listrutan.
   1. Om du vill ändra radinvisualiseringen till en tabell väljer du **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Välj **[!UICONTROL Swap Rows and Columns]** i verktygsfältet.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Datorrankat filter för flera Dimensioner i Tableu ](assets/uc7-tableau-data.png)

1. Välj **[!UICONTROL Duplicate]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill skapa ett andra blad.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1]** om du vill byta namn på bladet till `Data`.
1. Välj **[!UICONTROL Rename]** på snabbmenyn på fliken **[!UICONTROL Sheet 1 (2)]** om du vill byta namn på bladet till `Card`.

1. Kontrollera att du har valt vyn **[!UICONTROL Card]**.
1. Välj **[!UICONTROL DAY(Daterangeday)]** och välj **[!UICONTROL Month]** i listrutan. Värdet ändras till **[!UICONTROL MONTH(Daterangeday)]**.
1. Välj **[!UICONTROL SUM(Cm Product Name Count Distinct)]** i **[!UICONTROL Marks]** och välj **[!UICONTROL Format]** i listrutan.
1. Om du vill ändra teckenstorleken väljer du **[!UICONTROL Font]** i **[!UICONTROL Default]** i rutan **[!UICONTROL Format SUM(CM Product Name Count Distinct)]** och väljer **[!UICONTROL 72]** som teckenstorlek.
1. Om du vill justera talet väljer du **[!UICONTROL Automatic]** bredvid **[!UICONTROL Alignment]** och anger **[!UICONTROL Horizontal]** till centrerad.
1. Om du vill använda heltal markerar du **[!UICONTROL 123.456]** bredvid **[!UICONTROL Numbers]** och väljer **[!UICONTROL Number (Custom)]**. Ange **[!UICONTROL Decimal places]** till `0`.

   Ditt skrivbord ska se ut så här nedan.

   ![Datorrankat filter för flera Dimensioner i Tableu ](assets/uc7-tableau-card.png)

1. Skapa en ny **[!UICONTROL Dashboard 1]**-vy genom att klicka på tabbknappen **[!UICONTROL New Dashboard]** (längst ned). I vyn **[!UICONTROL Dashboard 1]**:
   1. Dra och släpp **[!UICONTROL Card]**-bladet från **[!UICONTROL Sheets]**-hyllan till **[!UICONTROL Dashboard 1]**-vyn som läser *Drop sheets här*.
   1. Dra och släpp **[!UICONTROL Data]**-bladet från **[!UICONTROL Sheets]**-hyllan nedanför **[!UICONTROL Card]**-bladet till **[!UICONTROL Dashboard 1]**-vyn.

   **[!UICONTROL Dashboard 1]**-vyn ska se ut så här nedan.

   ![Instrumentpanel för bordsdator ](assets/uc7-tableau-final.png)

>[!ENDTABS]

+++



## Använd datumintervallnamn för att filtrera

Du vill använda ett datumintervall som du har definierat i Customer Journey Analytics för att filtrera och rapportera om händelser under det senaste året.

+++ Customer Journey Analytics

Om du vill rapportera med hjälp av ett datumintervall anger du ett datumintervall i Customer Journey Analytics, med **[!UICONTROL Title]** `Last Year 2023`.

![Customer Journey Analytics Använd datumintervallnamn som ska filtreras](assets/cja-daterange.png)

Du kan sedan använda det datumintervallet i en exempelpanel **[!UICONTROL Using Date Range Names To Filter]** för följande användningsfall:

![Värden för distinkt räkning för Customer Journey Analytics](assets/cja-using-date-range-filter-names-to-filter.png)

Observera hur datumintervallet som definieras i visualiseringen av frihandstabellen åsidosätter datumintervallet som tillämpas på panelen.

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterangemonth]**.
   1. Välj **[!UICONTROL daterangeName]**.
   1. Välj **[!UICONTROL ∑ occurrences]**.

   En visualisering visar **[!UICONTROL Error fetching data for this visual]**.

1. I rutan **[!UICONTROL Filters]**:

   1. Välj **[!UICONTROL daterangeName is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Basic filtering]** som **[!UICONTROL Filter type]**.
   1. Under fältet **[!UICONTROL Search]** väljer du **[!UICONTROL Last Year 2023]**, som är namnet på ditt datumintervall som definieras i Customer Journey Analytics.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort **[!UICONTROL daterangeName]** från **[!UICONTROL Columns]**.

   Tabellen uppdateras med det använda **[!UICONTROL daterangeName]**-filtret. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop använder datumintervallnamn för filter](assets/uc8-powerbi-final.png)

>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Daterange Name]** från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. Kontrollera att **[!UICONTROL Select from list]** är markerat i dialogrutan **[!UICONTROL Filter \[Daterange Name\]]** och välj **[!UICONTROL Last Year 2023]** i listan. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Daterangemonth]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Rows]**. Välj **[!UICONTROL Daterangemonth]** och välj **[!UICONTROL Month]**. Värdet ändras till **[!UICONTROL MONTH(Daterangemonth)]**.
   1. Dra **[!UICONTROL Occurrences]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Occurrences)]**.
   1. Välj **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Välj **[!UICONTROL Swap Rows and Columns]** i verktygsfältet.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Datorrankat filter för flera Dimensioner i Tableu ](assets/uc8-tableau-final.png)

>[!ENDTABS]

+++



## Använd filternamn för att filtrera

Du vill använda ett befintligt filter för produktkategorin Fiske som du har definierat i Customer Journey Analytics för att filtrera och rapportera produktnamn och förekomster (händelser) under januari 2023.

+++ Customer Journey Analytics

Inspect filtret som du vill använda i Customer Journey Analytics.

![Customer Journey Analytics Använd filternamn för filter](assets/cja-fishing-products.png)

Du kan sedan använda det filtret i en exempelpanel **[!UICONTROL Using Date Range Names To Filter]** för att använda skiftläget:

![Värden för distinkt räkning för Customer Journey Analytics](assets/cja-using-filter-names-to-filter.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterange]**.
   1. Välj **[!UICONTROL filterName]**.
   1. Välj **[!UICONTROL product_name]**.
   1. Välj **[!UICONTROL ∑ occurrences]**.

En visualisering visar **[!UICONTROL Error fetching data for this visual]**.

1. I rutan **[!UICONTROL Filters]**:

   1. Välj **[!UICONTROL filterName is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Basic filtering]** som **[!UICONTROL Filter type]**.
   1. Under fältet **[!UICONTROL Search]** väljer du **[!UICONTROL Fishing Products]**, som är namnet på det befintliga filter som definieras i Customer Journey Analytics.
   1. Välj **[!UICONTROL daterange is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Advanced filtering]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort **[!UICONTROL filterName]** från **[!UICONTROL Columns]**.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort **[!UICONTROL daterange]** från **[!UICONTROL Columns]**.

   Tabellen uppdateras med det använda **[!UICONTROL filterName]**-filtret. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop använder datumintervallnamn för filter](assets/uc9-powerbi-final.png)


>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Filter Name]** från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. Kontrollera att **[!UICONTROL Select from list]** är markerat i dialogrutan **[!UICONTROL Filter \[Filter Name\]]** och välj **[!UICONTROL Fishing Products]** i listan. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Daterange]**-posten från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filter Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och sedan `01/01/2023` - `01/02/2023`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Product Name]** från listan **[!UICONTROL Tables]** till **[!UICONTROL Rows]**.
   1. Dra **[!UICONTROL Occurrences]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Occurrences)]**.
   1. Välj **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Datorrankat filter för flera Dimensioner i Tableu ](assets/uc9-tableau-final.png)

>[!ENDTABS]

+++


## Använd dimensionsvärden för att filtrera

Du skapar ett nytt filter i Customer Journey Analytics som filtrerar på produkter i jaktproduktkategorin. Sedan vill du använda det nya filtret för att rapportera produktnamn och förekomster (händelser) för produkter i jaktkategorin under januari 2023.

+++ Customer Journey Analytics

Skapa ett nytt filter med **[!UICONTROL Title]** `Hunting Products` i Customer Journey Analytics.

![Customer Journey Analytics Använd Dimensioner för att filtrera](assets/cja-hunting-products.png)

Du kan sedan använda det filtret i en exempelpanel **[!UICONTROL Using Dimension Values To Filter]** för att använda skiftläget:

![Värden för distinkt räkning för Customer Journey Analytics](assets/cja-using-dimension-values-to-filter.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Välj **[!UICONTROL Home]** på menyn och välj sedan **[!UICONTROL Refresh]** i verktygsfältet. Du måste uppdatera anslutningen för att kunna plocka upp det nya filtret som du just definierade i Customer Journey Analytics.

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterange]**.
   1. Välj **[!UICONTROL filterName]**.
   1. Välj **[!UICONTROL product_name]**.
   1. Välj **[!UICONTROL ∑ occurrences]**.

En visualisering visar **[!UICONTROL Error fetching data for this visual]**.

1. I rutan **[!UICONTROL Filters]**:
   1. Välj **[!UICONTROL filterName is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Basic filtering]** som **[!UICONTROL Filter type]**.
   1. Under fältet **[!UICONTROL Search]** väljer du **[!UICONTROL Hunting Products]**, som är namnet på det befintliga filter som definieras i Customer Journey Analytics.
   1. Välj **[!UICONTROL daterange is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Advanced filtering]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort **[!UICONTROL filterName]** från **[!UICONTROL Columns]**.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort **[!UICONTROL daterange]** från **[!UICONTROL Columns]**.

   Tabellen uppdateras med det använda **[!UICONTROL filterName]**-filtret. Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop använder datumintervallnamn för filter](assets/uc10-powerbi-final.png)



>[!TAB Skrivbord för Tablet PC]

1. I vyn **[!UICONTROL Data Source]**, under **[!UICONTROL Data]**, på snabbmenyn på **[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**, väljer du **[!UICONTROL Refresh]**. Du måste uppdatera anslutningen för att kunna plocka upp det nya filtret som du just definierade i Customer Journey Analytics.
1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra posten **[!UICONTROL Filter Name]** från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. Kontrollera att **[!UICONTROL Select from list]** är markerat i dialogrutan **[!UICONTROL Filter \[Filter Name\]]** och välj **[!UICONTROL Hunting Products]** i listan. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Daterange]**-posten från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filter Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och sedan `01/01/2023` - `1/2/2023`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Product Name]** från listan **[!UICONTROL Tables]** till **[!UICONTROL Rows]**.
   1. Dra **[!UICONTROL Occurrences]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Occurrences)]**.
   1. Välj **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.

      Ditt skrivbord ska se ut så här nedan.

      ![Datorrankat filter för flera Dimensioner i Tableu ](assets/uc10-tableau-final.png)

>[!ENDTABS]

+++



## Sortera

Du vill rapportera om inköpsinkomster och inköp för produktnamn under januari 2023, sorterade i fallande inköpsintäktsorder.

+++ Customer Journey Analytics

Ett exempel på **[!UICONTROL Sort]**-panel för användningsfallet:

![Panelen Sortera Customer Journey Analytics](assets/cja-sort.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterange]**.
   1. Välj **[!UICONTROL product_namr]**.
   1. Välj **[!UICONTROL ∑ purchase_revenue]**.
   1. Välj **[!UICONTROL ∑ purchases]**.

1. I rutan **[!UICONTROL Filters]**:
   1. Välj **[!UICONTROL daterange is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Advanced filtering]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.

1. I rutan Visualiseringar:
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort daterange från kolumner.
   1. Dra **[!UICONTROL Sum of purchase_revenue]** längst ned på **[!UICONTROL Column]** objekt.

1. I rapporten väljer du **[!UICONTROL Sum of purchase_revenue]** för att sortera tabellen i fallande ordning efter inköpsintäkt.

   Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop använder datumintervallnamn för filter](assets/uc11-powerbi-final.png)

Frågan som körs av Power BI Desktop med BI-tillägget innehåller inte någon `sort`-sats. Avsaknaden av en `sort`-sats tyder på att sorteringen körs på klientsidan.

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra **[!UICONTROL Daterange]**-posten från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filter Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Range of dates]** och sedan `01/01/2023` - `1/2/2023`. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Product Name]** från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Rows]**.
   1. Dra **[!UICONTROL Purchases]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Purchases)]**.
   1. Dra **[!UICONTROL Purchase Revenue]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Columns]**, intill **[!UICONTROL SUM(Purchases)]**. Värdet ändras till **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Välj **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.
   1. Markera kolumnrubriken **[!UICONTROL Purchase Revenue]** och sortera tabellen i den här kolumnen i fallande ordning.

      Ditt skrivbord ska se ut så här nedan.

      ![Skrivbordssortering för surfplatta](assets/uc11-tableau-final.png)

Frågan som körs av Tableau Desktop med BI-tillägget innehåller inte någon `sort`-sats. Avsaknaden av den här `sort`-satsen tyder på att sorteringen körs på klientsidan.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!ENDTABS]

+++

## Gränser

Du vill rapportera om de fem vanligaste förekomsterna av produktnamn under 2023.

+++ Customer Journey Analytics

Ett exempel på **[!UICONTROL Limit]**-panel för användningsfallet:

![Panelen Gräns för Customer Journey Analytics](assets/cja-limit.png)

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. I rutan **[!UICONTROL Data]**:
   1. Välj **[!UICONTROL daterange]**.
   1. Välj **[!UICONTROL product_name]**.
   1. Välj **[!UICONTROL ∑ occurrences]**.

1. I rutan **[!UICONTROL Filters]**:
   1. Välj **[!UICONTROL daterange is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Relative date]** som **[!UICONTROL Filter type]**.
   1. Definiera filtret för **[!UICONTROL Show items when the value]** **[!UICONTROL is in the last]** `1` **[!UICONTROL calendar years]**.
   1. Välj **[!UICONTROL Apply filter]**.
   1. Välj **[!UICONTROL product_name is (All)]** från **[!UICONTROL Filters on this visual]**.
   1. Välj **[!UICONTROL Top N]** som **[!UICONTROL Filter type]**.
   1. Välj **[!UICONTROL Show Items]** **[!UICONTROL Top]** `5` **[!UICONTROL By value]**.
   1. Dra och släpp **[!UICONTROL ∑ occurrences]** från rutan **[!UICONTROL Data]** och släpp den på **[!UICONTROL Add data fields here]**.
   1. Välj **[!UICONTROL Apply filter]**.

1. I visualiseringsfönstret:
   * Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort daterange från kolumner.

   Ditt Power BI Desktop ska se ut så här nedan.

   ![Power BI Desktop använder datumintervallnamn för filter](assets/uc12-powerbi-final.png)

Frågan som körs av Power BI Desktop med BI-tillägget innehåller en `limit`-sats, men inte den som förväntades. Gränsen för de 5 högsta förekomsterna tillämpas av Power BI Desktop med uttryckliga produktnamnsresultat.

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Skrivbord för Tablet PC]

1. Välj fliken **[!UICONTROL Sheet 1]** längst ned om du vill växla från **[!UICONTROL Data source]**. I vyn **[!UICONTROL Sheet 1]**:
   1. Dra **[!UICONTROL Daterange]**-posten från listan **[!UICONTROL Tables]** i hyllan **[!UICONTROL Filters]**.
   1. I dialogrutan **[!UICONTROL Filter Field \[Daterange\]]** väljer du **[!UICONTROL Range of Dates]** och sedan **[!UICONTROL Next >]**.
   1. I dialogrutan **[!UICONTROL Filter \[Daterange]]** väljer du **[!UICONTROL Relative dates]**, väljer **[!UICONTROL Years]** och väljer **[!UICONTROL Previous years]**. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.
   1. Dra **[!UICONTROL Product Name]** från listan **[!UICONTROL Tables]** till **[!UICONTROL Rows]**.
   1. Dra **[!UICONTROL Occurrences]**-posten från listan **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Columns]**. Värdet ändras till **[!UICONTROL SUM(Occurrences)]**.
   1. Välj **[!UICONTROL Text Table]** från **[!UICONTROL Show Me]**.
   1. Välj **[!UICONTROL Fit Width]** i listrutan **[!UICONTROL Fit]**.
   1. Välj **[!UICONTROL Product Name]** i **[!UICONTROL Rows]**. Välj **[!UICONTROL Filter]** i listrutan.
      1. Välj fliken **[!UICONTROL Top]** i dialogrutan **[!UICONTROL Filter \[Product Name\]]**.
      1. Välj **[!UICONTROL By field:]** **[!UICONTROL Top]** `5` **[!UICONTROL by Occurrences]** **[!UICONTROL Sum]**.
      1. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.

         ![AlertRed](/help/assets/icons/AlertRed.svg) Tabellen försvinner. Att välja de fem främsta produktnamnen efter förekomster fungerar **inte** korrekt med det här filtret.
      1. Välj **[!UICONTROL Product Name]** i **[!UICONTROL Filter]**-hyllan och välj **[!UICONTROL Remove]** i listrutan. Tabellen visas igen.
   1. Välj **[!UICONTROL SUM(Occurrences)]** i **[!UICONTROL Marks]**-hyllan. Välj **[!UICONTROL Filter]** i listrutan.
      1. Välj **[!UICONTROL At least]** i dialogrutan **[!UICONTROL Filter \[Occurrences\]]**.
      1. Ange `47.799` som värde. Detta värde garanterar att endast de fem översta objekten visas i tabellen. Välj **[!UICONTROL Apply]** och **[!UICONTROL OK]**.

         Ditt skrivbord ska se ut så här nedan.

         ![Skrivbordsbegränsningar för Tableu](assets/uc12-tableau-final.png)

Som framgår ovan misslyckas den här frågan som körs av Tableau Desktop när du definierar ett Top 5 instances-filter på produktnamn.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

Frågan som körs av Tableau Desktop, när ett av de fem vanligaste filtren definieras för förekomster, visas nedan. Gränsen visas inte i frågan och används på klientsidan.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!ENDTABS]

+++

## Omformningar

Du vill förstå omformningarna av Customer Journey Analytics-objekt som dimensioner, mått, filter, beräknade mått och datumintervall med de olika BI-verktygen.

+++ Customer Journey Analytics

I Customer Journey Analytics definierar du i en [datavy](/help/data-views/data-views.md), som och hur komponenter i dina datauppsättningar visas som [dimensions](/help/components/dimensions/overview.md) och [metrics](/help/components/apply-create-metrics.md). Definitionen av mått och mått visas för BI-verktygen med BI-tillägget.
Du använder komponenter som [Filter](/help/components/filters/filters-overview.md), [Beräknade mätvärden](/help/components/calc-metrics/calc-metr-overview.md) och [Datumintervall](/help/components/date-ranges/overview.md) som en del av dina Workspace-projekt. Dessa komponenter visas också för BI-verktygen med BI-tillägget.

+++

+++ BI-verktyg

>[!PREREQUISITES]
>
>Kontrollera att du har verifierat [en lyckad anslutning, kan visa datavyer och använda en datavy](#connect-and-validate) för BI-verktyget som du vill testa det här användningsfallet för.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Objekten Customer Journey Analytics är tillgängliga i rutan **[!UICONTROL Data]** och hämtas från tabellen som du har markerat i Power BI Desktop. Exempel: **[!UICONTROL public.cc_data_view]**. Tabellens namn är detsamma som det externa ID som du har definierat för datavyn i Customer Journey Analytics. Datavy med till exempel **[!UICONTROL Title]** `C&C - Data View` och **[!UICONTROL External ID]** `cc_data_view`.

**Dimensioner**
Dimensioner från Customer Journey Analytics identifieras av [!UICONTROL Component ID] . [!UICONTROL Component ID] definieras i datavyn i Customer Journey Analytics. Dimensionen **[!UICONTROL Product Name]** i Customer Journey Analytics har till exempel [!UICONTROL Component ID] **[!UICONTROL product_name]** som är namnet på dimensionen i Power BI Desktop.
Datumintervalldimensioner från Customer Journey Analytics, som **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** och mer, är tillgängliga som **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]** med flera.

**Mätvärden**
Mätvärden från Customer Journey Analytics identifieras av [!UICONTROL Component ID] . [!UICONTROL Component ID] definieras i datavyn i Customer Journey Analytics. Måttet **[!UICONTROL Purchase Revenue]** i Customer Journey Analytics har till exempel [!UICONTROL Component ID] **[!UICONTROL purchase_revenue]** som är namnet på måttet i Power BI Desktop. En **[!UICONTROL ∑]** indikerar mått. När du använder ett mätvärde i en visualisering får måttet det nya namnet **[!UICONTROL Sum of *metric *]**.

**Filter**
Filter som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL filterName]** . När du använder ett **[!UICONTROL filterName]**-fält i Power BI Desktop kan du ange vilket filter som ska användas.

**Beräknade mått**
Beräknade mått som du definierar i Customer Journey Analytics identifieras av den [!UICONTROL External ID] du har definierat för det beräknade måttet. Det beräknade måttet **[!UICONTROL Product Name (Count Distinct)]** har till exempel [!UICONTROL External ID] **[!UICONTROL product_name_count_distinct]** och visas som **[!UICONTROL cm_product_name_count_distinc]**t i Power BI Desktop.

**Datumintervall**
Datumintervall som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL daterangeName]** . När du använder ett **[!UICONTROL daterangeName]**-fält kan du ange vilket datumintervall som ska användas.

**Anpassade omformningar**
Power BI Desktop tillhandahåller anpassade omformningsfunktioner med hjälp av [DAX (Data Analysis Expressions)](https://learn.microsoft.com/en-us/dax/dax-overview). Du vill till exempel köra ett fall där en dimension rangordnas med produktnamn i gemener.

1. Välj fältvisualisering i rapportvyn.
1. Välj product_name i datapanelen.
1. Välj Ny kolumn i verktygsfältet.
1. I formelredigeraren definierar du en ny kolumn med namnet `product_name_lower`, som `product_name_lower = LOWER('public.cc_data_view[product_name])`.
   ![Power BI Desktop Transformation to Lower](assets/uc14-powerbi-transformation.png)
1. Se till att du väljer den nya kolumnen product_name_lower i rutan Data i stället för kolumnen product_name.
1. Välj Rapportera som tabell från ![Mer](/help/assets/icons/More.svg) i tabellvisualiseringen.

   Ditt Power BI Desktop ska se ut så här nedan.
   ![Power BI Desktop Transformation Final](assets/uc14-powerbi-final.png)

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

Objekten Customer Journey Analytics är tillgängliga i sidofältet **[!UICONTROL Data]** när du arbetar i ett blad. Och hämtas från tabellen som du har valt som en del av sidan **[!UICONTROL Data source]** i Tableau. Exempel: **[!UICONTROL cc_data_view]**. Tabellens namn är detsamma som det externa ID som du har definierat för datavyn i Customer Journey Analytics. Datavy med till exempel **[!UICONTROL Title]** `C&C - Data View` och **[!UICONTROL External ID]** `cc_data_view`.

**Dimensioner**
Dimensioner från Customer Journey Analytics identifieras av [!UICONTROL Component name] . [!UICONTROL Component name] definieras i datavyn i Customer Journey Analytics. Dimensionen **[!UICONTROL Product Name]** i Customer Journey Analytics har till exempel [!UICONTROL Component name] **[!UICONTROL Product Name]** som är namnet på dimensionen i Tableau. Alla dimensioner identifieras av **[!UICONTROL Abc]**.
Datumintervalldimensioner från Customer Journey Analytics, som **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** och mer, är tillgängliga som **[!UICONTROL Daterangeday]**, **[!UICONTROL Daterangeweek]**, **[!UICONTROL Daterangemonth]** med flera. När du använder en datumintervalldimension måste du välja en lämplig definition av datum och tid som ska användas på den datumintervalldimensionen i listrutan. Exempel: **[!UICONTROL Year]**, **[!UICONTROL Quarter]**, **[!UICONTROL Month]**, **[!UICONTROL Day]**.

**Mätvärden**
Mätvärden från Customer Journey Analytics identifieras av [!UICONTROL Component Name] . [!UICONTROL Component Name] definieras i datavyn i Customer Journey Analytics. Måttet **[!UICONTROL Purchase Revenue]** i Customer Journey Analytics har till exempel [!UICONTROL Component Name] **[!UICONTROL Purchase Revenue]** som är namnet på måttet i Tableau. Alla mått identifieras av **[!UICONTROL #]**. När du använder ett mätvärde i en visualisering får måttet det nya namnet **[!UICONTROL Sum(*metric *)]**.

**Filter**
Filter som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL Filter Name]** . När du använder ett **[!UICONTROL Filter Name]**-fält i Tableau kan du ange vilket filter som ska användas.

**Beräknade mått**
Beräknade mått som du definierar i Customer Journey Analytics identifieras av den [!UICONTROL Title] du har definierat för det beräknade måttet. Det beräknade måttet **[!UICONTROL Product Name (Count Distinct)]** har till exempel [!UICONTROL Title] **[!UICONTROL Product Name (Count Distinct)]** och visas som **[!UICONTROL Cm Product Name Count Distinct]** i Tableau.

**Datumintervall**
Datumintervall som du definierar i Customer Journey Analytics är tillgängliga som en del av fältet **[!UICONTROL Daterange Name]** . När du använder ett **[!UICONTROL Daterange Name]**-fält kan du ange vilket datumintervall som ska användas.

**Anpassade omformningar**
Tableu Desktop har anpassade omformningsfunktioner som använder [Beräknade fält](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm). Du vill till exempel köra ett fall där en dimension rangordnas med produktnamn i gemener.

1. Välj **[!UICONTROL Analysis]** > **[!UICONTROL Create Calculated Field]** på huvudmenyn.
   1. Definiera **[!UICONTROL Lowercase Product Name]** med funktionen `LOWER([Product Name])`.
      ![Beräknat fält i tabell](assets/uc14-tableau-calculated-field.png)
   1. Välj **[!UICONTROL OK]**.
1. Markera bladet **[!UICONTROL Data]**.
   1. Dra **[!UICONTROL Lowercase Product Name]** från **[!UICONTROL Tables]** och släpp posten i fältet intill **[!UICONTROL Rows]**.
   1. Ta bort **[!UICONTROL Product Name]** från **[!UICONTROL Rows]**.
1. Välj vyn **[!UICONTROL Dashboard 1]**.

Ditt skrivbord ska se ut så här nedan.

![Skrivbord för Tablet PC efter omvandling](assets/uc14-tableau-final.png)

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

>[!ENDTABS]

+++



## Visualiseringar

I det här fallet vill jag förstå hur de visualiseringar som finns i Customer Journey Analytics kan skapas på liknande sätt med de tillgängliga visualiseringarna i BI-verktygen.

+++ Customer Journey Analytics

Customer Journey Analytics har ett antal visualiseringar. Se [Visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) för en introduktion och en översikt över alla möjliga visualiseringar.

+++

+++ BI-verktyg

>[!BEGINTABS]

>[!TAB Power BI Desktop]

### Jämförelse

För de flesta visualiseringar i Customer Journey Analytics erbjuder Power BI Desktop likvärdiga upplevelser. Se tabellen nedan.

| Ikon | Customer Journey Analytics visualisering | Power BI Desktop-visualisering |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Område](/help/analysis-workspace/visualizations/area.md) | [Ytdiagram, staplat ytdiagram och 100 % ytdiagram](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#area-charts-basic-layered-and-stacked) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Bar](/help/analysis-workspace/visualizations/bar.md) | [Grupperat kolumndiagram](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Stapel staplad](/help/analysis-workspace/visualizations/bar.md) | [Staplat stapeldiagram och staplat 100 % stapeldiagram](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [Punkt](/help/analysis-workspace/visualizations/bullet-graph.md) |  |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Kohortabell](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Kombination](/help/assets/icons/ComboChart.svg) | [Kombination](/help/analysis-workspace/visualizations/combo-charts.md) | [Stapeldiagram, stapeldiagram, linjediagram och grupperade stapeldiagram](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#combo-charts) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Ringdiagram](/help/analysis-workspace/visualizations/donut.md) | [Diagram ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#doughnut-charts) |
| ![ConversionTratt](/help/assets/icons/ConversionFunnel.svg) | [Utfall](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [Tratt](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#funnel-charts). |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [Flöde](/help/analysis-workspace/visualizations/c-flow/flow.md) | Dispositionsträd? |
| ![VisaTabell](/help/assets/icons/ViewTable.svg)</p> | [Frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tabell](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#tables) och [Matris](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#matrix) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [Histogram](/help/analysis-workspace/visualizations/histogram.md) |  |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Vågrätt fält](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Grupperat stapeldiagram](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarHorizontalStached](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Vågrätt fält staplat](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Staplat stapeldiagram och staplat liggande stapeldiagram till 100 %](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Förgrening3](/help/assets/icons/Branch3.svg) | [Researbetsyta](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | [Delningsträd](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#decomposition-tree) |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [Sammanfattning av nyckelmått](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Linjediagram](/help/analysis-workspace/visualizations/line.md) | [Linjediagram](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#line-charts) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Spridning](/help/analysis-workspace/visualizations/scatterplot.md) | [Punktdiagram](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#scatter) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [Avsnittshuvud](/help/analysis-workspace/visualizations/section-header.md) | [Textruta](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md) | [Kort](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![123](/help/assets/icons/123.svg)</p> | [Sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md) | [Kort](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![Text](/help/assets/icons/Text.svg) | [Text](/help/analysis-workspace/visualizations/text.md) | [Textruta](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Treemap-diagram](/help/analysis-workspace/visualizations/treemap.md)<p> | [Treemap-diagram](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#treemaps) |
| ![Typ](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


### Detaljgranska

Power BI stöder [detaljerat läge](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) för att utforska detaljinformation om vissa visualiseringar. I exemplet nedan analyserar du inköpsinkomster för produktkategorier. På snabbmenyn för ett fält som representerar en produktkategori kan du välja **[!UICONTROL Drill down]**.

![Power BI-borrning nedåt](assets/uc15-powerbi-drilldown.png)

Detaljnivån uppdaterar visualiseringen med inköpsintäkterna för produkter i den valda produktkategorin.

![Power BI-fördjupning](assets/uc15-powerbi-drillup.png)

Detaljnivån resulterar i följande SQL-fråga som använder en `WHERE`-sats:

```sql
select "_"."product_category" as "c25",
    "_"."product_name" as "c26",
    "_"."a0" as "a0"
from 
(
    select "_"."product_category",
        "_"."product_name",
        "_"."a0"
    from 
    (
        select "_"."product_category",
            "_"."product_name",
            "_"."a0"
        from 
        (
            select "rows"."product_category" as "product_category",
                "rows"."product_name" as "product_name",
                sum("rows"."purchase_revenue") as "a0"
            from 
            (
                select "_"."product_category",
                    "_"."product_name",
                    "_"."purchase_revenue"
                from "public"."cc_data_view" "_"
                where ("_"."daterange" >= date '2023-01-01' and "_"."product_category" = 'Fishing') and "_"."daterange" < date '2024-01-01'
            ) "rows"
            group by "product_category",
                "product_name"
        ) "_"
        where not "_"."a0" is null
    ) "_"
) "_"
order by "_"."product_category",
        "_"."product_name"
limit 1001
```

>[!TAB Skrivbord för Tablet PC]

### Jämförelse

För de flesta visualiseringar i Customer Journey Analytics erbjuder Tableau likvärdiga upplevelser. Se tabellen nedan.

| Ikon | Customer Journey Analytics visualisering | Power BI Desktop-visualisering |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Område](/help/analysis-workspace/visualizations/area.md) | [Ytdiagram](https://help.tableau.com/current/pro/desktop/en-us/qs_area_charts.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Bar](/help/analysis-workspace/visualizations/bar.md) | [Stolpdiagram](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Stapel staplad](/help/analysis-workspace/visualizations/bar.md) |  |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [Punkt](/help/analysis-workspace/visualizations/bullet-graph.md) | [Punktdiagram](https://help.tableau.com/current/pro/desktop/en-us/qs_bullet_graphs.htm) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Kohortabell](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Kombination](/help/assets/icons/ComboChart.svg) | [Kombination](/help/analysis-workspace/visualizations/combo-charts.md) | [Kombinationsdiagram](https://help.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Ringdiagram](/help/analysis-workspace/visualizations/donut.md) | |
| ![ConversionTratt](/help/assets/icons/ConversionFunnel.svg) | [Utfall](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [Flöde](/help/analysis-workspace/visualizations/c-flow/flow.md) |  |
| ![VisaTabell](/help/assets/icons/ViewTable.svg)</p> | [Frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Texttabell](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [Histogram](/help/analysis-workspace/visualizations/histogram.md) | [Histogram](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm) |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Vågrätt fält](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Stolpdiagram](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarHorizontalStached](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Vågrätt fält staplat](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Stolpdiagram](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![Förgrening3](/help/assets/icons/Branch3.svg) | [Researbetsyta](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [Sammanfattning av nyckelmått](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Linjediagram](/help/analysis-workspace/visualizations/line.md) | [Linjediagram](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Spridning](/help/analysis-workspace/visualizations/scatterplot.md) | [Spridningspunkt](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [Avsnittshuvud](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![123](/help/assets/icons/123.svg)</p> | [Sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![Text](/help/assets/icons/Text.svg) | [Text](/help/analysis-workspace/visualizations/text.md) | |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Treemap-diagram](/help/analysis-workspace/visualizations/treemap.md)<p> | [Treemap-diagram](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_treemap.htm) |
| ![Typ](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


### Detaljgranska

Tableau stöder [detaljerat läge](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) via [hierarkier](https://help.tableau.com/current/pro/desktop/en-us/qs_hierarchies.htm). I exemplet nedan skapar du en hierarki när du markerar fältet Produktnamn i Tabeller och drar det över produktkategorin. Sedan kan du välja **[!UICONTROL + Drill down]** på snabbmenyn för ett fält som representerar en produktkategori.

![Detaljnivå för flikar](assets/uc15-tableau-drilldown.png)

Detaljnivån uppdaterar visualiseringen med inköpsintäkterna för produkter i den valda produktkategorin.

![Tabbladet - detaljnivå upp](assets/uc15-tableau-drillup.png)

Detaljnivån resulterar i följande SQL-fråga som använder en GROUP BY-sats:

```sql
SELECT CAST("cc_data_view"."product_category" AS TEXT) AS "product_category",
  CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1,
  2
```

Frågan begränsar **inte** resultaten till den valda produktkategorin. Endast visualiseringen visar den valda produktkategorin.

![Tabbladet - detaljnivå upp](assets/uc15-tableau-drillup2.png)

Du kan också skapa en detaljerad kontrollpanel där ett visuellt värde är resultatet av markeringen i ett annat visuellt läge. I exemplet nedan används visualiseringen **[!UICONTROL Product Categories]** som ett filter för att uppdatera tabellen **[!UICONTROL Product Names]**. Det här visualiseringsfiltret är bara för klienten och leder inte till någon ytterligare SQL-fråga.

![Visualiseringsfilter för Tablet PC](assets/uc15-tableau-visualizationfilter.png)


>[!ENDTABS]

+++


## Caveats

Var och en av de BI-verktyg som stöds har några kavattningar i arbetet med tillägget Customer Journey Analytics BI.

+++ BI-verktyg

>[!BEGINTABS]

>[!TAB Power BI Desktop]

* Power BI Desktop Avancerad filtrering av datumintervall är exklusiv.  För slutdatumet måste du välja ett som ligger efter den dag du vill rapportera på. Till exempel **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL and before]** `1/2/2023`.
* Power BI Desktop har standardvärdet **[!UICONTROL Import]** när du skapar en anslutning. Kontrollera att du använder **[!UICONTROL Direct Query]**.
* Power BI Desktop visar dataomvandlingar via Power Query.  Power Query fungerar i första hand med Import-typanslutningar, så många omformningar som du använder, som datum- eller strängfunktioner, genererar ett fel som säger att du måste växla till en Import-typanslutning.  Om du behöver omforma data vid frågetillfället bör du använda härledda dimensioner och mätvärden så att Power BI inte behöver göra själva omformningarna.
* Power BI Desktop förstår inte hur typkolumner för datum och tid ska hanteras. Därför stöds inte måtten **[!UICONTROL daterange*X *]**som **[!UICONTROL daterangehour]**och **[!UICONTROL daterangeminute]**.
* Power BI Desktop försöker som standard skapa flera anslutningar med hjälp av fler sessioner i frågetjänsten.  Du bör gå till Power BI-inställningarna för ditt projekt och inaktivera parallella frågor.
* Power BI Desktop utför all sortering och begränsning på klientsidan och har också olika semantik för toppfiltrering av *X* som innehåller bundna värden så att du inte kan skapa exakt samma sortering och begränsning som du kan göra i Analysis Workspace.
* I tidigare versioner av Power BI Desktop, oktober 2024-versionen bryts PostgreSQL-datakällor. Se till att du använder den version som omnämns i den här artikeln.

>[!TAB Skrivbord för Tablet PC]

* Datumfiltreringen för Tableu är exklusiv. För slutdatumet måste du välja ett som ligger efter den dag du vill rapportera på.
* Som standard när du lägger till ett datum- eller datum-/tidsmått som **[!UICONTROL Daterangemonth]** på raderna i ett blad, kapslas fältet i en **[!UICONTROL YEAR()]** -funktion.  För att få det du vill ha måste du markera dimensionen och välja den datumfunktion som du vill använda i listrutan.  Ändra till exempel **[!UICONTROL Year]** till **[!UICONTROL Month]** när du försöker använda **[!UICONTROL Daterangemonth]**.
* Det är inte uppenbart att resultaten begränsas till de övre *X* i skrivbordet i Tableu. Du kan begränsa resultaten explicit eller använda ett beräkningsfält och funktionen **[!UICONTROL INDEX()]**.  Om du lägger till ett översta *X*-filter i en dimension genereras komplex SQL med hjälp av en inre koppling som inte stöds.

>[!ENDTABS]

+++
