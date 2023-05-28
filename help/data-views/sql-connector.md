---
title: SQL Connector
description: Lär dig hur du kan använda frågetjänsten, Power BIET och/eller Tableau för att komma åt datavyer med SQL Connector.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '2867'
ht-degree: 0%

---

# SQL Connector

{{release-limited-testing}}

The [!DNL Customer Journey Analytics (CJA) SQL Connector] aktiverar SQL-åtkomst till [datavyer](./data-views.md) som du har definierat i CJA. Dina datatekniker och analytiker kanske känner bättre till Power BI, Tableu eller andra verktyg för affärsintelligens och visualisering (kallas även BI-verktyg). De kan nu skapa rapporter och kontrollpaneler baserat på samma datavyer som CJA-användare använder när de skapar sina Analysis Workspace-projekt.

Adobe Experience Platform [Frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en) är SQL-gränssnittet till data som är tillgängliga i datasjön i Experience Platform. Med [!DNL CJA SQL Connector] aktiverad, funktionaliteten hos [!DNL Query Service] byggs ut för att visa dina CJA-datavyer som tabeller eller vyer i en [!DNL Query Service] session. Detta resulterar i att verktyg för affärsinformation som använder [!DNL Query Service] som PostgresSQL-gränssnittet har en smidig fördel av den utökade funktionaliteten.

De viktigaste fördelarna är:

- Du behöver inte återskapa en motsvarande representation av CJA-datavyer i BI-verktyget. <br/>Se [Datavy](data-views.md) om du vill ha mer information om funktionerna i datavyer för att förstå vad som måste återskapas.<br/>

- Större konsekvens i rapportering och analys mellan BI-verktyg och CJA.

- Kombinera CJA-data med andra datakällor som redan finns i BI-verktyg.

## Förutsättningar

Om du vill använda den här funktionen måste du

- Aktivera [!UICONTROL CJA SQL Connector] i Experience Platform.

- Konfigurera funktionerna för relevanta produktprofiler, användargrupper och/eller enskilda användare.<br/>
Användarna måste ha tillgång till:
   - Experience Platform Query Service,
   - CJA Workspace-projekt och
   - CJA-datavyer som de vill använda.

- Använd förfallodatum för ej förfallande autentiseringsuppgifter för att ansluta BI-verktyg till CJA SQL Connector. Thr [Handbok för autentiseringsuppgifter](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) innehåller mer information om hur du anger förfallodatum för inloggningsuppgifter eller ej utgångsdatum.

Se [Åtkomstkontroll](../admin/cja-access-control.md) i CJA-administrationsavsnittet om du vill ha mer information.


## Användning

Så här använder du [!DNL CJA SQL Connector] kan du antingen använda SQL direkt eller använda dra och släpp-funktionen som finns i det specifika BI-verktyget.

### SQL

Du kan använda funktionerna direkt i SQL-satser med antingen Frågeredigeraren eller en vanlig PostgresSQL-klient (CLI).

+++ Frågeredigeraren

I användargränssnittet i Experience Platform:

1. Välj **[!UICONTROL ** Frågor **]** från **[!UICONTROL ** DATAHANTERING **]** till vänster.

2. Välj ![Skapa fråga](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Skapa fråga **]**.

3. Om du vill köra frågan skriver du SQL-satsen och väljer ![Spela upp](assets/Smock_Play_18_N.svg) eller tryck på SKIFT + RETUR.

+++


+++ PostgresSQL CLI

1. I användargränssnittet för Experience Platform ska du slå upp och kopiera dina PostgresSQL-autentiseringsuppgifter:

   1. Välj **[!UICONTROL ** Frågor **]** från vänster räl (under **[!UICONTROL ** DATAHANTERING **]**).

   2. Välj **[!UICONTROL ** Autentiseringsuppgifter **]** i det övre fältet.

   3. Om du vill kopiera anslutningssträngen använder du ![Kopiera](assets/Smock_Copy_18_N.svg) i **[!UICONTROL ** PSQL, kommando **]** -avsnitt.

2. Öppna PostgresSQL CLI.

3. Om du vill logga in och börja köra dina frågor klistrar du in anslutningssträngen i PostgresSQL CLI.

+++

Se [Användargränssnittshandbok för frågeredigeraren](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) för mer information.


### BI-verktyg

För närvarande stöds CJA SQL Connector för Power BI och Tableau.

+++ Power BI

1. I Adobe Experience Platform UI kan du söka efter information om dina PostgresSQL-autentiseringsuppgifter.

   1. Välj **[!UICONTROL ** Frågor **]** från vänster räl (under **[!UICONTROL ** DATAHANTERING **]**).

   2. Välj **[!UICONTROL ** Autentiseringsuppgifter **]** i det övre fältet.

   3. Använd ![Kopiera](assets/Smock_Copy_18_N.svg) för att kopiera alla Postgres-autentiseringsparametrar ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username]och andra) vid behov inom Power BI.

2. I Power BI:

   1. I huvudfönstret väljer du **[!UICONTROL ** Hämta data **]** i det övre verktygsfältet.

   2. Välj **[!UICONTROL ** Mer ...**]** till vänster.

   3. I **Hämta data** skärm, sök efter `PostgresSQL` och väljer **[!UICONTROL ** PostgresSQL-databas **]** från listan.

   4. I **[!UICONTROL ** PostSQL-databas **]** dialog:

      1. Klistra in **[!UICONTROL ** Värd **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Server **]** textfält.

      2. Klistra in **[!UICONTROL ** Databas **]** parameter från Experience Platform Queries [!UICONTROL Credentials] in **[!UICONTROL ** Databas **]** textfält.

         Lägg till `?FLATTEN` till **[!UICONTROL ** Databas **]** parameter, så den ser ut som `prod:all?FLATTEN` till exempel. Se [Förenkla kapslade datastrukturer för användning med BI-verktyg från tredje part](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) för mer information.

      3. När du uppmanas till detta **[!UICONTROL ** Dataanslutning **]** läge, välja **[!UICONTROL ** DirectQuery **]** för att säkerställa att datastrukturerna förenklas på rätt sätt.

      4. Du uppmanas att **[!UICONTROL ** Användarnamn **]** och **[!UICONTROL ** Lösenord **]**. Använd likvärdiga parametrar från Experience Platform-frågor [!UICONTROL Credentials].
   5. När inloggningen är klar visas CJA-datavytabellerna i Power BIETS **[!UICONTROL **&#x200B;Överblick **]**. Datavy-tabeller identifieras med `dv_` i deras namn.


   6. Markera de datavytabeller som du vill använda och markera **[!UICONTROL ** Läs in **]**.

   Alla dimensioner och mätvärden som är kopplade till en eller flera markerade tabeller visas i den högra rutan, redo att användas i dina visualiseringar.

   Se [Anslut Power BI till frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) för mer information.

+++

+++Tableau

1. I användargränssnittet för Experience Platform ska du leta upp information om dina PostgresSQL-autentiseringsuppgifter.

   1. Välj **[!UICONTROL ** Frågor **]** från vänster räl (under **[!UICONTROL ** DATAHANTERING **]**).

   2. Välj **[!UICONTROL ** Autentiseringsuppgifter **]** i det övre fältet.

   3. Använd ![Kopiera](assets/Smock_Copy_18_N.svg) för att kopiera alla Postgres-autentiseringsparametrar ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], och andra) när det behövs i Tablet.

2. I tabell:

   1. Välj **[!UICONTROL ** Mer **]** från **[!UICONTROL ** Till en server **]** till vänster.

   2. Välj **[!UICONTROL ** PostgresSQL **]** från listan.

   3. I [!UICONTROL PostgresSQL] dialog:

      1. Klistra in **[!UICONTROL ** Värd **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Server **]** textfält.

      2. Klistra in **[!UICONTROL ** Port **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Port **]** textfält.

      3. Klistra in **[!UICONTROL ** Databas **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Databas **]** textfält.

         Lägg till `%3FFLATTEN` till **[!UICONTROL ** Databas **]** parameter, så den ser ut som `prod:all%3FFLATTEN` till exempel. Se [Förenkla kapslade datastrukturer för användning med BI-verktyg från tredje part](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) för mer information.

      4. Välj **[!UICONTROL ** Användarnamn och lösenord **]** från **[!UICONTROL ** Autentisering **]** lista.

      5. Klistra in **[!UICONTROL ** Användarnamn **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Användarnamn **]** textfält.

      6. Klistra in **[!UICONTROL ** Lösenord **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Lösenord **]** textfält.

      7. Välj **[!UICONTROL ** Logga in **]**.
   4. CJA-datavyer visas som tabeller i **[!UICONTROL ** Tabell **]** lista. Datavy tables with `dv_`.

   5. Dra de tabeller som du vill använda på arbetsytan.

   Nu kan du arbeta med data från datavytabellerna för att skapa rapporter och visualiseringar.

   Se [Anslut tabell till frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) för mer information.

+++

Se [Anslut klienter till frågetjänsten](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) om du vill ha en översikt över och mer information om de olika verktygen.

## Funktionalitet

Som standard har datavyerna ett tabellsäkert namn som genereras utifrån det egna namnet. Datavy med namnet [!UICONTROL My Web Data] har vynamnet `dv_my_web_data`.

Om du vill använda ID:n för datavyn som tabellnamn kan du lägga till de valfria `CJA_USE_IDS` ange till ditt databasnamn vid anslutning. Till exempel: `prod:all?CJA_USE_IDS` visar datavyer med namn som `dv_ABC123`.

### Datastyrning

De datastyrningsrelaterade inställningarna i Customer Journey Analytics ärvs från Adobe Experience Platform. Integrationen mellan CJA och Adobe Experience Platform Data Governance möjliggör märkning av känsliga CJA-data och tillämpning av sekretesspolicyer.

Sekretessetiketter och integritetspolicyer som har skapats för datauppsättningar som används av Experience Platform kan visas i arbetsflödet för CJA-datavyer. Data som efterfrågas med CJA SQL Connector visar därför lämpliga varningar eller fel när de inte följer de definierade sekretessetiketterna och principerna.

### Listdatavyer

I standard-PostgreSQL CLI kan du visa dina vyer med `\dv`

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### Kapslade kontra separerade

Som standard använder schemat för datavyer kapslade strukturer, precis som de ursprungliga XDM-schemana. Integreringen har även stöd för `FLATTEN` alternativ. Du kan använda det här alternativet för att tvinga schemat för datavyer (och andra tabeller i sessionen) att förenklas. Förenkling gör det enklare att använda i BI-verktyg som inte stöder strukturerade scheman. Se [Arbeta med kapslade datastrukturer i frågetjänsten](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) för mer information.

### SQL som stöds

Se [SQL-referens för frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) för fullständig referens om vilken typ av SQL som stöds.

Se tabellen Mönster nedan för en översikt över mönster och exempel.

+++Mönster

| Mönster | Exempel |
|---|---|
| Schemaidentifiering | <pre>VÄLJ * FRÅN DV1 DÄR 1=0</pre> |
| Rankad/uppdelning | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA EFTER NEDRE1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39; OCH<br/>  filterId = &#39;12345&#39;<br/>GRUPPERA EFTER NEDRE1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39; OCH<br/>  AND (dim2 = &#39;A&#39; ELLER dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GRUPPERA EFTER NEDRE1</pre> |
| HAVING-satsen | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA EFTER NEDRE1<br/>MED m1 > 100</pre> |
| Distinkt, övre <br/>dimensionsvärden | <pre>VÄLJ DISTINCT dim1 FROM dv1</pre><pre>VÄLJ dim1 AS dv1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA EFTER NEDRE1</pre><pre>VÄLJ dim1 AS dv1<br/>FRÅN DV1<br/>DÄR \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GRUPPERA EFTER NEDRE1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Måttsummor | <pre>VÄLJ SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;</pre> |
| Flera dimensioner<br/>uppdelningar<br/>och förstklassiga | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA MED 1, 2<br/>BESTÄLL AV 1, 2</pre><pre>VÄLJ DISTINCT dim1, dim2<br/>FRÅN DV1</pre> |
| Markera en del:<br/>Ytterligare resultat<br/>filtrering | <pre>SELECT dim1, m1<br/>FRÅN (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FRÅN DV1<br/>  DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;</br>  GRUPPERA EFTER NEDRE1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Markera en del:<br/>Förena med<br/>datamängden är inte i<br/>CJA | <pre>SELECT b.key, a.dim1, a.m1<br/>FRÅN (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FRÅN DV1<br/>  DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>  GRUPPERA EFTER NEDRE1<br/>) a<br/>LEFT JOIN-sökningar b ON a.dim1 = b.key</pre> |
| Markera en del:<br/>Fråga tvärs över<br/>datavyer | <pre>SELECT key, SUM(m1) AS total<br/>FRÅN (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FRÅN DV1<br/>  DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>  GRUPPERA EFTER NEDRE1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FRÅN DV2<br/>  DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>  GRUPPERA EFTER NEDRE2<br/>GROUP BY-tangenten<br/>BESTÄLL EFTER Summa</pre> |
| Markera en del: <br/>Källa i lager, <br/>filtrering, <br/>och aggregering | Lager med delmarkeringar:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FRÅN (<br/>  SELECT \_.dim1,\_.m1<br/>  FRÅN (<br/>    VÄLJ \* FRÅN DV1<br/>    DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 i (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rader<br/>GRUPPERA MED 1<br/>BESTÄLL EFTER Summa</pre><br/>Lager med CTE WITH:<br/><pre>MED rader AS (<br/>  MED \_ AS (<br/>    SELECT * FROM data_ares<br/>    DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2021-01-01&#39; OCH &#39;2021-02-01&#39;<br/>  )<br/>  VÄLJ _.item, _.units FROM _<br/>  DÄR _.item INTE ÄR NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FRÅN rader DÄR rader.objekt i (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Markerar var<br/>mätvärden kommer före<br/> eller är blandade med<br/>dimensionerna | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA MED 2</pre> |

{style="table-layout:auto"}

+++

### Mått

Du kan välja någon av de tillgängliga dimensionerna som standard eller definierad i datavyn. Du väljer en dimension med dess ID.

### Mätvärden

De mätvärden som är tillgängliga är:

- någon av de mätvärden som är tillgängliga som standard,

- definieras i datavyn,

- beräknade mätvärden som är kompatibla med den datavy som användaren har tillgång till.

Du väljer ett mått med dess ID som omsluts av en `SUM(metric)` -uttryck på samma sätt som du gör med andra SQL-källor.

Du kan använda:

- `SELECT COUNT(*)` eller `COUNT(1)` för att få förekomstmåtten.

- `SELECT COUNT(DISTINCT dimension)` eller `SELECT APPROX_COUNT_DISTINCT(dimension)` för att räkna de ungefärliga distinkta värdena för en dimension. Mer information finns i [Räkningsdistinktioner](#counting-distincts).

- [Textbundna beräkningar](#inline-calculations) för att kombinera mätvärden i farten och/eller göra matematik på dem.

#### Räkningsdistinktioner

På grund av den underliggande karaktären hos hur CJA fungerar är den enda dimension som du kan få ett exakt distinkt antal för `adobe_personid` dimension. Följande SQL-satser `SELECT COUNT(DISTINCT adobe_personid)` eller `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` returnerar värdet för standardpersonmåttet, vilket är antalet distinkta personer. För andra dimensioner returneras ett ungefärligt distinkt antal.

#### Villkorliga mått

Du kan bädda in en `IF` eller `CASE` -satsen i `SUM` eller `COUNT` funktioner för att lägga till ytterligare filtrering som är specifik för ett markerat mätvärde. Att lägga till dessa satser påminner om att tillämpa ett filter på en måttkolumn i en arbetsyterapporttabell.

Exempel:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Textbundna beräkningar

Du kan använda ytterligare metriska uttryck i `SELECT` i stället för att matematiken ska definieras i ett beräknat mått. I följande tabell visas vilka typer av uttryck som stöds.

| Operatör eller funktion | Detaljer |
|---|---|
| `+`, `-`, `*`, `/`och `%` | Lägg till, subtrahera, multiplicera, dela och modulera/rest |
| `-X` eller `+X` | Ändra tecknet eller ett mått där X är måttuttrycket |
| `PI()` | π konstant |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`och `TANH` | Unära matematiska funktioner |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binära matematiska funktioner |

{style="table-layout:auto"}

### Specialkolumner

**Tidsstämpel**

The `timestamp` specialkolumn används för att ange datumintervall för frågan. Ett datumintervall kan definieras med en `BETWEEN` uttryck eller par `timestamp` `>`, `>=`, `<`, `<=` kontroller `AND`tillsammans.
The `timestamp` är valfritt och om inget fullständigt intervall anges används standardvärdena:

- Om bara ett minimum anges (`timestamp > X` eller ` timestamp >= X`) är intervallet från X till nu.

- Om bara ett maxvärde anges (`timestamp < X` eller `timestamp <= X`) är intervallet mellan X-30 dagar och X.

- Om inget anges är intervallet från och med nu 30 dagar.

Tidsstämpelintervallet konverteras till ett globalt filter för datumintervall i RankedRequest.
Tidsstämpelfältet kan också användas i Date-Time-funktioner för att analysera och korta av händelsens tidsstämpel.

**Datumintervall**

The `daterange` specialspalt fungerar ungefär som  `timestamp`filtreringen är dock begränsad till hela dagar. The `daterange` är också valfritt och har samma intervallstandard som `timestamp`.
The `daterange` -fältet kan också användas i Datum-Tid-funktioner för att tolka, korta av händelsedatumet.

**filterId**

The `filterId` specialkolumnen är valfri och används för att tillämpa ett externt definierat filter på frågan. Att använda ett externt definierat filter på en fråga liknar att dra ett filter på en panel i Arbetsytan. Flera filter-ID:n kan anges av `AND`-Jag tar dem.

### WHERE-sats

WHERE-satsen hanteras i tre steg:

1. Sök efter datumintervallet från `timestamp` specialfält.

2. Sök efter externt definierade `filterId`s som ska tas med i filtreringen.

3. Omvandla de återstående uttrycken till ad hoc-filter.

Hanteringen görs genom att den första nivån i `AND`i `WHERE` -sats. Varje översta nivå `AND`ed-uttrycket måste matcha något av ovanstående. Allt som är djupare än den första nivån i `AND`s, eller om `WHERE` -sats använder `OR`s på den översta nivån hanteras som ett ad hoc-filter.

### BESTÄLL AV

Som standard sorteras resultatet i frågan efter det första valda måttet i fallande ordning. Du kan skriva över standardsorteringsordningen genom att ange `ORDER BY ... ASC` eller `ORDER BY ... DESC`. Om du använder `ORDER BY`måste du ange `ORDER BY` på det första valda måttet.

Du kan också vända ordningen med `-` (minus) framför måttet. Båda programsatserna nedan resulterar i samma ordning:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Allmänt funktionsstöd

|  -funktion | Exempel | Detaljer |
|---|---|---|
| [CAST (kolumntyp AS)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` eller <br/> `` `timestamp`::string `` | Typdatatypsbyte stöds inte för närvarande, men inget fel genereras. The `CAST` funktionen ignoreras. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Tolka en tidssträng som en tidsstämpel för användning i en `WHERE` -sats. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Tolka en tidssträng som en tidsstämpel för användning i en `WHERE` -sats, om du vill ange ett format för den tidssträngen. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Tolka en datumsträng som en tidsstämpel för användning i en `WHERE` -sats. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Tolka en datumsträng som en tidsstämpel för användning i en `WHERE` -sats, om du vill ange ett format för den datumsträngen. |

{style="table-layout:auto"}

### Funktionsstöd för Dimension

De här funktionerna kan användas på dimensioner i `SELECT`, `WHERE` eller i villkorsstyrda värden.

**Strängfunktioner**

|  -funktion | Exempel | Detaljer |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |

{style="table-layout:auto"}

**Funktioner för datum och tid**

|  -funktion | Exempel | Detaljer |
|---|---|---|
| [ÅR (datum eller tid)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [MÅNAD(datum eller tid)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [DAY(datum eller datum-tid)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [DAYOFWEEK(datum eller tid)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet eftersom du behöver talet, inte det egna namnet. |
| [DAYOFYEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [VECKA (datum eller tid)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [KVARTAL(datum eller datum-tid)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [TIMME (datum eller tid)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet eftersom du behöver talet, inte det egna namnet. |
| [MINUTE(date eller date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |
| [EXTRACT(del FRÅN datum eller tid)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet för vissa delar av den här funktionen eftersom du behöver talet och inte det egna namnet.<br/>Följande delar stöds:<br>- Nyckelord: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Strängar:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, eller `'MINUTE'`. |
| [DATE_PART(part, date eller date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet för vissa delar av den här funktionen eftersom du behöver talet och inte det egna namnet.<br/>Strängdelar som stöds är: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, eller `'MINUTE'`. |
| [DATE_TRUNC(granularitet, datum eller tid)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet.<br/>Stränggranulariteter som stöds är: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, eller `'MINUTE'`. |

{style="table-layout:auto"}

