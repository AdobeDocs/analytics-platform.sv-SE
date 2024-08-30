---
title: Customer Journey Analytics BI-tillägg
description: Lär dig hur du kan använda Power BI eller Tableau för att komma åt datavyer med tillägget Customer Journey Analytics BI.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 81bde9f61f208fd01b3ba1c3df57609104109800
workflow-type: tm+mt
source-wordcount: '2901'
ht-degree: 0%

---

# Customer Journey Analytics BI-tillägg

{{select-package}}

[!DNL Customer Journey Analytics BI extension] aktiverar SQL-åtkomst till de [datavyer](./data-views.md) som du har definierat i Customer Journey Analytics. Dina datatekniker och analytiker kanske känner bättre till Power BI, Tableu eller andra verktyg för affärsintelligens och visualisering (kallas även BI-verktyg). De kan nu skapa rapporter och kontrollpaneler baserat på samma datavyer som Customer Journey Analytics-användare använder när de skapar sina Analysis Workspace-projekt.

Adobe Experience Platform [frågetjänst](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) är SQL-gränssnittet till data som är tillgängliga i datasjön i Experience Platform. När [!DNL Customer Journey Analytics BI extension] är aktiverat utökas funktionaliteten för [!DNL Query Service] så att du kan se dina datavyer i Customer Journey Analytics som tabeller eller vyer i en [!DNL Query Service] -session. Det innebär att de verktyg för affärsintelligens som använder [!DNL Query Service] som PostgresSQL-gränssnitt sömlöst drar nytta av den här utökade funktionen.

De viktigaste fördelarna är:

* Du behöver inte återskapa en motsvarande representation av datavyer från Customer Journey Analytics i BI-verktyget. <br/>Se [Datavyer](data-views.md) för mer information om funktionaliteten hos datavyer för att förstå vad som måste återskapas.
* Större konsekvens i rapportering och analys mellan BI-verktyg och Customer Journey Analytics.
* Kombinera data från Customer Journey Analytics med andra datakällor som redan finns i BI-verktyg.

## Förutsättningar

Om du vill använda den här funktionen måste du ha:

<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

* Tillgång till Experience Platform och Customer Journey Analytics.
* Beviljad produktadministratörsåtkomst till Customer Journey Analytics så att du kan visa, redigera, uppdatera eller ta bort anslutningar och datavyer.
* Beviljad åtkomst till de datavyer som du vill komma åt.
* Beviljade åtkomst till CJA BI-tillägget.
* Använd förfallodatum för autentiseringsuppgifter som inte förfaller för att ansluta BI-verktyg till [!DNL Customer Journey Analytics BI extension]. Guiden [Autentiseringsuppgifter](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) innehåller mer information om hur du anger förfallodatum för autentiseringsuppgifter eller ej förfallande autentiseringsuppgifter.

Mer information finns i [Åtkomstkontroll för kundresa](../technotes/access-control.md), särskilt [Tilläggsbehörigheter för produktadministratör](../technotes/access-control.md#product-admin-additional-permissions) och [Customer Journey Analytics i Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Användning

Om du vill använda funktionen [!DNL Customer Journey Analytics BI extension] kan du antingen använda SQL direkt eller använda dra och släpp-funktionen som är tillgänglig i det specifika BI-verktyget.

### SQL

Du kan använda funktionerna direkt i SQL-satser med antingen Frågeredigeraren eller en vanlig PostgresSQL-klient (CLI).

+++ Frågeredigerare

I Adobe Experience Platform:

1. Välj **[!UICONTROL ** Frågor **]** från **[!UICONTROL ** DATAHANTERING **]** i den vänstra listen.

1. Välj ![Skapa fråga](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Skapa fråga **]**.

1. Välj `cja` **[!UICONTROL ** Databas **]**.

1. Om du vill köra frågan skriver du SQL-satsen och väljer knappen ![Spela upp](assets/Smock_Play_18_N.svg) (eller trycker på `[SHIFT]` + `[ENTER]`).

+++


+++ PostgresSQL CLI

1. Söka efter och kopiera dina PostgresSQL-autentiseringsuppgifter i Adobe Experience Platform:

   1. Välj **[!UICONTROL ** Frågor **]** i den vänstra listen (under **[!UICONTROL ** DATAHANTERING **]**).

   1. Välj **[!UICONTROL ** Autentiseringsuppgifter **]** i det övre fältet.

   1. Välj `cja` **[!UICONTROL ** Databas **]**.

   1. Om du vill kopiera kommandosträngen använder du ![Kopiera](assets/Smock_Copy_18_N.svg) i avsnittet **[!UICONTROL ** PSQL-kommando **]**.

1. Öppna ett kommando eller ett terminalfönster.

1. Om du vill logga in och börja köra dina frågor klistrar du in kommandosträngen i terminalen.

+++

Mer information finns i [Användargränssnittsguiden för frågeredigeraren](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide).


### BI-verktyg

För närvarande stöds och testas [!DNL Customer Journey Analytics BI extension] endast för Power BI och Tableau. Andra BI-verktyg som använder PSQL-gränssnittet kan också fungera, men stöds ännu inte officiellt.

+++ Power BI

1. Här hittar du information om dina PostgresSQL-autentiseringsuppgifter i Adobe Experience Platform:

   1. Välj **[!UICONTROL ** Frågor **]** i den vänstra listen (under **[!UICONTROL ** DATAHANTERING **]**).

   1. Välj **[!UICONTROL ** Autentiseringsuppgifter **]** i det övre fältet.

   1. Välj `cja` **[!UICONTROL ** Databas **]**.

   1. Använd ![Kopiera](assets/Smock_Copy_18_N.svg) om du vill kopiera var och en av Postgres-autentiseringsparametrarna ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] med flera) vid behov i Power BI.

1. I Power BI:

   1. I huvudfönstret väljer du **[!UICONTROL ** Hämta data **]** i det övre verktygsfältet.

   1. Välj **[!UICONTROL More...]** i den vänstra listen.

   1. På skärmen **Hämta data** söker du efter `PostgresSQL` och väljer **[!UICONTROL ** PostgresSQL-databasen **]** i listan.

   1. I dialogrutan **[!UICONTROL ** PostProgressSQL-databas **]**:

      1. Klistra in parametern **[!UICONTROL ** Host **]** från Experience Platform Queries [!UICONTROL Credentials] i textfältet **[!UICONTROL ** Server **]**.

      1. Klistra in parametern **[!UICONTROL ** Database **]** från Experience Platform Queries [!UICONTROL Credentials] i textfältet **[!UICONTROL ** Database **]** .

         Lägg till `?FLATTEN` i parametern **[!UICONTROL ** Database **]**, så den blir som `prod:cja?FLATTEN` till exempel. Mer information finns i [Förenkla kapslade datastrukturer för användning med BI-verktyg från tredje part](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Välj **[!UICONTROL DirectQuery]** när du uppmanas till **[!UICONTROL Data Connectivity]**-läge.

      1. Du uppmanas att ange **[!UICONTROL Username]** och **[!UICONTROL Password]**. Använd motsvarande parametrar från Experience Platform Queries [!UICONTROL Credentials].


   1. När inloggningen är klar visas datavytabellerna i Customer Journey Analytics i Power BI:er **[!UICONTROL ** Navigator **]**.

   1. Markera de datavytabeller som du vill använda och välj **[!UICONTROL ** Läs in **]**.

   Alla dimensioner och mätvärden som är kopplade till en eller flera markerade tabeller visas i den högra rutan, redo att användas i dina visualiseringar.

   Mer information finns i [Ansluta Power BI till frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi).

+++

+++Tableau

1. Här hittar du information om dina PostgresSQL-autentiseringsuppgifter i Adobe Experience Platform:

   1. Välj **[!UICONTROL ** Frågor **]** i den vänstra listen (under **[!UICONTROL ** DATAHANTERING **]**).

   1. Välj **[!UICONTROL ** Autentiseringsuppgifter **]** i det övre fältet.

   1. Välj ` cja` **[!UICONTROL ** Databas **]**.

   1. Använd ![Kopiera](assets/Smock_Copy_18_N.svg) om du vill kopiera var och en av Postgres-autentiseringsparametrarna ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] med flera) vid behov i Tablet.

1. I tabell:

   1. Välj **[!UICONTROL ** Mer **]** från **[!UICONTROL ** Till en server **]** i den vänstra listen.

   1. Välj **[!UICONTROL ** PostgresSQL **]** i listan.

   1. I dialogrutan [!UICONTROL PostgresSQL]:

      1. Klistra in parametern **[!UICONTROL ** Host **]** från Experience Platform Queries [!UICONTROL Credentials] i textfältet **[!UICONTROL ** Server **]**.

      1. Klistra in parametern **[!UICONTROL ** Port **]** från Experience Platform Queries [!UICONTROL Credentials] i textfältet **[!UICONTROL ** Port **]**.

      1. Klistra in parametern **[!UICONTROL ** Database **]** från Experience Platform Queries [!UICONTROL Credentials] i textfältet **[!UICONTROL ** Database **]** .

         Lägg till `%3FFLATTEN` i parametern **[!UICONTROL ** Database **]**, så den blir som `prod:cja%3FFLATTEN` till exempel. Mer information finns i [Förenkla kapslade datastrukturer för användning med BI-verktyg från tredje part](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Välj **[!UICONTROL ** Användarnamn och lösenord **]** i listan **[!UICONTROL ** Autentisering **]**.

      1. Klistra in parametern **[!UICONTROL ** Användarnamn **]** från Experience Platform Queries [!UICONTROL Credentials] i textfältet **[!UICONTROL ** Användarnamn **]**.

      1. Klistra in parametern **[!UICONTROL ** Password **]** från Experience Platform Queries [!UICONTROL Credentials] i textfältet **[!UICONTROL ** Password **]** .

      1. Välj **[!UICONTROL ** Logga in **]**.

   1. Datavyer i Customer Journey Analytics visas som tabeller i listan **[!UICONTROL ** Tabell **]**.

   1. Dra de tabeller som du vill använda på arbetsytan.

   Nu kan du arbeta med data från datavytabellerna för att skapa rapporter och visualiseringar.

   Mer information finns i [Ansluta tabell till frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau).

+++

Se [Ansluta klienter till frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview) för en översikt och mer information om de olika verktygen som finns.

## Funktionalitet

Som standard har datavyerna ett tabellsäkert namn som genereras utifrån det egna namnet. Datavyn [!UICONTROL My Web Data View] har till exempel vynamnet `my_web_data_view`. Du kan definiera ett föredraget namn som ska användas i BI-verktyget för datavyn. Mer information finns i [Datavy settings](create-dataview.md#settings).

Om du vill använda ID:n för datavyn som tabellnamn kan du lägga till den valfria inställningen `CJA_USE_IDS` i databasnamnet när du ansluter. `prod:cja?CJA_USE_IDS` visar till exempel dina datavyer med namn som `dv_ABC123`.

### Datastyrning

De datastyrningsrelaterade inställningarna i Customer Journey Analytics ärvs från Adobe Experience Platform. Integrationen mellan Customer Journey Analytics och Adobe Experience Platform datastyrning möjliggör märkning av känsliga uppgifter från Customer Journey Analytics och tillämpning av integritetspolicyer.

Sekretessetiketter och integritetspolicyer som har skapats för datauppsättningar som används av Experience Platform kan visas i arbetsflödet för datavyer i Customer Journey Analytics. Data som efterfrågas med [!DNL Customer Journey Analytics BI extension] visar därför lämpliga varningar eller fel när de inte följer definierade sekretessetiketter och principer.

#### Standardvärden och begränsningar

Följande ytterligare standardvärden och begränsningar gäller av datastyrningsskäl.

* BI-tillägget kräver en radgräns för frågeresultaten. Standardvärdet är 50, men du kan åsidosätta detta i SQL med `LIMIT n`, där `n` är 1 - 50000.
* BI-tillägget kräver ett datumintervall för att begränsa de rader som används för beräkningar. Standardvärdet är de sista 30 dagarna, men du kan åsidosätta detta i SQL `WHERE`-satsen med hjälp av de särskilda [`timestamp`](#timestamp)- eller [`daterange`](#date-range)-kolumnerna.
* BI-tillägget kräver aggregerade frågor. Du kan inte använda SQL som `SELECT * FROM ...` för att hämta de underliggande raderna i Raw-format. På en hög nivå bör dina sammanställda frågor använda:
   * Välj summor med `SUM` och/eller `COUNT`.<br/> Till exempel `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Välj mått uppdelade efter dimension. <br/>Exempel: `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Välj distinkta mätvärden.<br/>Exempel: `SELECT DISTINCT dimension1 FROM ...`

     Mer information finns i [SQL](#supported-sql) som stöds.

### Visa datavyer

I standard-PostgreSQL CLI kan du visa dina vyer med `\dv`

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### Kapslade kontra separerade

Som standard använder schemat för datavyer kapslade strukturer, precis som de ursprungliga XDM-schemana. Integrationen stöder även alternativet `FLATTEN`. Du kan använda det här alternativet för att tvinga schemat för datavyer (och andra tabeller i sessionen) att förenklas. Förenkling gör det enklare att använda i BI-verktyg som inte stöder strukturerade scheman. Mer information finns i [Arbeta med kapslade datastrukturer i frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

### SQL som stöds

Mer information om vilken typ av SQL som stöds finns i [SQL-referens för frågetjänst](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview).

Se tabellen nedan för exempel på den SQL du kan använda.

+++ Exempel

| Mönster | Exempel |
|---|---|
| Schemaidentifiering | <pre>VÄLJ * FRÅN DV1 DÄR 1=0</pre> |
| Rankad eller uppdelad | <pre>VÄLJ dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>VÄLJ dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/> filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>VÄLJ dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39; AND<br/> AND (dim2 = &#39;A&#39; ELLER dim3 IN (&#39;X&#39;, &#39;Y&#39;&#39;, &#39;Z&#39;)<br/>GRUPP BY dim1</pre> |
| `HAVING`-sats | <pre>VÄLJ dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;202-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Distinkta, övre <br/>dimensionsvärden | <pre>VÄLJ DISTINCT dim1 FROM dv1</pre><pre>VÄLJ dim1 SOM dv1<br/>FRÅN dv1<br/>WHERE \`timestamp\` MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>VÄLJ dim1 SOM dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMLIMIN IT 15</pre> |
| Måttsummor | <pre>VÄLJ SUM(metric1) SOM m1<br/>FRÅN dv1<br/>WHERE \`timestamp\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;</pre> |
| Flerdimensions<br/>uppdelningar<br/>och toppdistinktioner | <pre>VÄLJ dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>VÄLJ dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>VÄLJ DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Delmarkera:<br/>Filtrera ytterligare<br/>resultat | <pre>VÄLJ dim1, m1<br/>FROM (<br/> SELECT dim1, SUM(metric1) AS m1<br/> FROM dv1<br/> WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br> GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Delmarkera:<br/>Frågar över<br/>datavyer | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/> SELECT dim1 AS key, SUM(metric1) AS m1<br/> FROM dv1<br/> WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;{3 <br/> GROUP BY dim1<br/><br/> UNION<br/><br/> SELECT dim2 AS key, SUM(m1) AS m1<br/> FROM dv2<br/> WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/> GROUP BY dim2 <br/>GRUPPERA EFTER nyckel<br/>BESTÄLL EFTER summa</pre> |
| Delmarkera: <br/>Källa i lager, <br/>filtrering, <br/> och aggregering | Lager med delmarkeringar:<br><pre>MARKERA rows.dim1, SUM(rows.m1) SOM total<br/>FROM (<br/> SELECT \_.dim1,\_.m1<br/> FROM (<br/>)    VÄLJ \* FRÅN DV1<br/>    DÄR \`tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/> ) \_<br/> DÄR \_.dim1 i (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rader<br/>GRUPP BY 1<br/>BESTÄLL EFTER</pre><br/>Lager med CTE WITH:<br/><pre>MED rader SOM (<br/>) MED \_ AS (<br/>)    SELECT * FROM data_ares <br/>    DÄR \`tidsstämpel\` MELLAN &#39;2021-01-01&#39; OCH &#39;2021-02-01&#39;<br/> )<br/> MARKERA \_.item, \_.units FROM \_<br/> DÄR \_.item INTE ÄR NULL<br/>)<br/>MARKERA rader.item, SUTENT M(rows.units) AS units<br/>FROM rows WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Väljer var <br/>måtten kommer före<br/> eller blandas med <br/>måtten | <pre>VÄLJ SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;202-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Mått

Du kan välja någon av de tillgängliga dimensionerna som standard eller definierad i datavyn. Du väljer en dimension med dess ID.

### Mätvärden

De mätvärden som är tillgängliga är:

* någon av de mätvärden som är tillgängliga som standard,
* Definieras i datavyn.
* Beräknade mått som är kompatibla med datavyn som användaren har åtkomst till.

Du väljer ett mått med dess ID som omsluts av ett `SUM(metric)`-uttryck på samma sätt som du gör med andra SQL-källor.

Du kan använda

* `SELECT COUNT(*)` eller `COUNT(1)` om du vill hämta förekomstmått.
* `SELECT COUNT(DISTINCT dimension)` eller `SELECT APPROX_COUNT_DISTINCT(dimension)` om du vill räkna de ungefärliga distinkta värdena för en dimension. Se information i [Räkna distinkta värden](#counting-distinct-values).
* [Infogade beräkningar](#inline-calculations) om du vill kombinera mätvärden i farten och/eller göra matematik på dem.

#### Räkna distinkta värden

På grund av den underliggande karaktären hos hur Customer Journey Analytics fungerar är den enda dimensionen du kan få ett exakt distinkt antal för dimensionen `adobe_personid`. Följande SQL-satser `SELECT COUNT(DISTINCT adobe_personid)` eller `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` returnerar värdet för standardpersonmåttet, vilket är antalet distinkta personer. För andra dimensioner returneras ett ungefärligt distinkt antal.

#### Villkorliga mått

Du kan bädda in en `IF`- eller `CASE`-sats i funktionerna `SUM` eller `COUNT` för att lägga till ytterligare filtrering som är specifik för ett markerat mätresultat. Att lägga till dessa satser liknar att tillämpa ett filter på en måttkolumn i en Workspace-rapporttabell.

Exempel:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Infogade beräkningar

Du kan använda ytterligare matematik för måttuttryck i `SELECT`. Denna matematik kan användas i stället för att definiera matematiken i ett beräknat mått. I följande tabell visas vilka typer av uttryck som stöds.

| Operatör eller funktion | Information |
|---|---|
| `+`, `-`, `*`, `/` och `%` | Lägg till, subtrahera, multiplicera, dela och modulera/rest |
| `-X` eller `+X` | Ändra tecknet eller ett mått där X är måttuttrycket |
| `PI()` | π konstant |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` och `TANH` | Unära matematiska funktioner |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binära matematiska funktioner |

{style="table-layout:auto"}

### Specialkolumner

#### Tidsstämpel

Specialkolumnen `timestamp` används för att ange datumintervall för frågan. Ett datumintervall kan definieras med ett `BETWEEN`-uttryck eller ett par av `timestamp` `>`, `>=`, `<`, `<=` kontroller `AND` tillsammans.
`timestamp` är valfritt och om inget fullständigt intervall anges används standardvärden:

* Om bara ett minimum anges (`timestamp > X` eller ` timestamp >= X`) är intervallet från X till nu.
* Om bara ett max anges (`timestamp < X` eller `timestamp <= X`) är intervallet från X minus 30 dagar till X.
* Om inget anges är intervallet från och med nu minus 30 dagar.

Tidsstämpelintervallet konverteras till ett globalt datumintervallfilter i RankedRequest.
Tidsstämpelfältet kan också användas i datum/tid-funktioner för att analysera eller korta av händelsens tidsstämpel.

#### Datumintervall

Specialkolumnen `daterange` fungerar på ungefär samma sätt som `timestamp`, men filtreringen är begränsad till fullständiga dagar. `daterange` är också valfritt och har samma standardvärden som `timestamp`.
Fältet `daterange` kan också användas i datum/tid-funktioner för att analysera eller korta av händelsedatumet.

Specialkolumnen `daterangeName` kan användas för att filtrera frågan med ett namngivet datumintervall som `Last Quarter`.

>[!NOTE]
>
>Power BI stöder inte `daterange`-mått som är mindre än en dag (timme, 30 minuter, 5 minuter osv.).
>

#### Filter-ID

Specialkolumnen `filterId` är valfri och används för att tillämpa ett externt definierat filter på frågan. Att använda ett externt definierat filter på en fråga liknar att dra ett filter på en panel i Workspace. Flera filter-ID:n kan användas av `AND`.

Tillsammans med `filterId` kan du använda `filterName` för att använda ett filternamn i stället för ID.

### Where-sats

Satsen `WHERE` hanteras i tre steg:

1. Hitta datumintervallet från specialfälten `timestamp`, `daterange` eller `daterangeName`.

1. Sök efter externt definierade `filterId` eller `filterName` som ska inkluderas i filtreringen.

1. Omvandla de återstående uttrycken till ad hoc-filter.

Hanteringen görs genom att tolka den första nivån på `AND` i `WHERE` -satsen. Varje `AND`-ed-uttryck på den översta nivån måste matcha något av ovanstående. Allt som är större än den första nivån i `AND` eller, om `WHERE`-satsen använder `OR` på den översta nivån, hanteras som ett ad hoc-filter.

### Sorteringsordning

Som standard sorteras resultatet i frågan efter det första valda måttet i fallande ordning. Du kan skriva över standardsorteringsordningen genom att ange `ORDER BY ... ASC` eller `ORDER BY ... DESC`. Om du använder `ORDER BY` måste du ange `ORDER BY` för det första valda måttet.

Du kan också vända ordningen genom att använda `-` (minus) framför måttet. Båda programsatserna nedan resulterar i samma ordning:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Allmänt funktionsstöd

| Funktion | Exempel | Information |
|---|---|---|
| [Avgjutning](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` eller <br/> `` `timestamp`::string `` | Typdatatypsbyte stöds inte för närvarande, men inget fel genereras. Funktionen `CAST` ignoreras. |
| [Tidsstämpel](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Tolka en tidssträng som en tidsstämpel som ska användas i en `WHERE`-sats. |
| [Till tidsstämpel](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Tolka en tidssträng som en tidsstämpel som ska användas i en `WHERE`-sats och ange eventuellt ett format för den tidssträngen. |
| [Datum](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Tolka en datumsträng som en tidsstämpel som ska användas i en `WHERE`-sats. |
| [Till datum](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Tolka en datumsträng som en tidsstämpel som ska användas i en `WHERE`-sats och ange eventuellt ett format för den datumsträngen. |

{style="table-layout:auto"}

### Funktionsstöd för Dimension

Dessa funktioner kan användas för dimensioner i `SELECT`, `WHERE` eller i villkorsstyrda mått.

**Strängfunktioner**

| Funktion | Exempel | Information |
|---|---|---|
| [Nedre](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |

{style="table-layout:auto"}

**Funktioner för datum och tid**

| Funktion | Exempel | Information |
|---|---|---|
| [År](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [Månad](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [Dag](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [Veckodag](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet eftersom du behöver talet, inte det egna namnet. |
| [Dag på året](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [Vecka](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [Kvartal](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [Timme](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet eftersom du behöver talet, inte det egna namnet. |
| [Minut](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [Extrahera](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet för vissa delar av den här funktionen eftersom du behöver talet och inte det egna namnet.<br/>Delar som stöds är:<br>- Nyckelord: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Strängar: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` eller  `'MINUTE'`. |
| [Datum (del)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet för vissa delar av den här funktionen eftersom du behöver talet och inte det egna namnet.<br/>Följande strängdelar stöds: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, eller `'MINUTE'`. |
| [Datum (trunkerat)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet.<br/>Stränggranulariteter som stöds är: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` eller `'MINUTE'`. |

{style="table-layout:auto"}
