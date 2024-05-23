---
title: Customer Journey Analytics BI-tillägg
description: Lär dig hur du kan använda frågetjänsten, Power BIET, Tableau eller andra BI- och SQL-verktyg för att få åtkomst till datavyer med tillägget Customer Journey Analytics BI.
solution: Customer Journey Analytics
feature: SQL Connector
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 5ed1622d4e9f1bcc25931cbf3d3cbd6796d0ac15
workflow-type: tm+mt
source-wordcount: '2743'
ht-degree: 0%

---

# Customer Journey Analytics BI-tillägg

{{select-package}}

The [!DNL Customer Journey Analytics BI extension] aktiverar SQL-åtkomst till [datavyer](./data-views.md) som du har definierat i Customer Journey Analytics. Dina datatekniker och analytiker kanske känner bättre till Power BI, Tableu eller andra verktyg för affärsintelligens och visualisering (kallas även BI-verktyg). De kan nu skapa rapporter och kontrollpaneler baserat på samma datavyer som Customer Journey Analytics-användare använder när de skapar sina Analysis Workspace-projekt.

Adobe Experience Platform [Frågetjänst](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) är SQL-gränssnittet till data som är tillgängliga i datasjön i Experience Platform. Med [!DNL Customer Journey Analytics BI extension] aktiverad, funktionaliteten hos [!DNL Query Service] utökas så att du kan se datavyer i Customer Journey Analytics som tabeller eller vyer i en [!DNL Query Service] session. Detta resulterar i att verktyg för affärsinformation som använder [!DNL Query Service] som PostgresSQL-gränssnittet har en smidig fördel av den utökade funktionaliteten.

De viktigaste fördelarna är:

* Du behöver inte återskapa en motsvarande representation av datavyer från Customer Journey Analytics i BI-verktyget. <br/>Se [Datavyer](data-views.md) för mer information om funktionaliteten hos datavyer för att förstå vad som måste återskapas.
* Större konsekvens i rapportering och analys mellan BI-verktyg och Customer Journey Analytics.
* Kombinera data från Customer Journey Analytics med andra datakällor som redan finns i BI-verktyg.

## Förutsättningar

Om du vill använda den här funktionen måste du:

<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

* Konfigurera funktionaliteten för relevanta produktprofiler, användargrupper och/eller enskilda användare. Åtkomstkraven är:
   * Adobe Experience Platform Query Service
   * Arbetsyteprojekt i Customer Journey Analytics
   * Önskade CJA-datavyer som kan användas
   * Åtkomst till BI-tillägget i datavyverktygen

* Använd förfallodatum för ej förfallande autentiseringsuppgifter för att ansluta BI-verktyg till [!DNL Customer Journey Analytics BI extension]. The [Handbok för autentiseringsuppgifter](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) innehåller mer information om hur du anger förfallodatum för inloggningsuppgifter eller ej utgångsdatum.

Se [Åtkomstkontroll](../technotes/access-control.md) i administrationsdelen för Customer Journey Analytics för ytterligare information.


## Användning

Använd [!DNL Customer Journey Analytics BI extension] kan du antingen använda SQL direkt eller använda dra och släpp-funktionen som finns i det specifika BI-verktyget.

### SQL

Du kan använda funktionerna direkt i SQL-satser med antingen Frågeredigeraren eller en vanlig PostgresSQL-klient (CLI).

+++ Frågeredigerare

I Adobe Experience Platform:

1. Välj **[!UICONTROL ** Frågor **]** från **[!UICONTROL ** DATAHANTERING **]** till vänster.

1. Välj ![Skapa fråga](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Skapa fråga **]**.

1. Välj `cja` **[!UICONTROL ** Databas **]**.

1. Om du vill köra frågan skriver du SQL-satsen och väljer ![Spela upp](assets/Smock_Play_18_N.svg) eller tryck på `[SHIFT]` + `[ENTER]`).

+++


+++ PostgresSQL CLI

1. Söka efter och kopiera dina PostgresSQL-autentiseringsuppgifter i Adobe Experience Platform:

   1. Välj **[!UICONTROL ** Frågor **]** från vänster räl (under **[!UICONTROL ** DATAHANTERING **]**).

   1. Välj **[!UICONTROL ** Referenser **]** i det övre fältet.

   1. Välj `cja` **[!UICONTROL ** Databas **]**.

   1. Om du vill kopiera kommandosträngen använder du ![Kopiera](assets/Smock_Copy_18_N.svg) i **[!UICONTROL ** PSQL, kommando **]** -avsnitt.

1. Öppna ett kommando eller ett terminalfönster.

1. Om du vill logga in och börja köra dina frågor klistrar du in kommandosträngen i terminalen.

+++

Se [Användargränssnittshandbok för frågeredigeraren](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) för mer information.


### BI-verktyg

För närvarande är [!DNL Customer Journey Analytics BI extension] stöds och testas endast för Power BI och Tableau. Andra BI-verktyg som använder PSQL-gränssnittet kan också fungera, men stöds ännu inte officiellt.

+++ Power BI

1. Här hittar du information om dina PostgresSQL-autentiseringsuppgifter i Adobe Experience Platform:

   1. Välj **[!UICONTROL ** Frågor **]** från vänster räl (under **[!UICONTROL ** DATAHANTERING **]**).

   1. Välj **[!UICONTROL ** Referenser **]** i det övre fältet.

   1. Välj `cja` **[!UICONTROL ** Databas **]**.

   1. Använd ![Kopiera](assets/Smock_Copy_18_N.svg) för att kopiera alla Postgres-autentiseringsparametrar ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username]och andra) vid behov inom Power BI.

1. I Power BI:

   1. I huvudfönstret väljer du **[!UICONTROL ** Hämta data **]** i det övre verktygsfältet.

   1. Välj **[!UICONTROL More...]** till vänster.

   1. I **Hämta data** skärm, sök efter `PostgresSQL` och väljer **[!UICONTROL ** PostgresSQL-databas **]** från listan.

   1. I **[!UICONTROL ** PostSQL-databas **]** dialog:

      1. Klistra in **[!UICONTROL ** Värd **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Server **]** textfält.

      1. Klistra in **[!UICONTROL ** Databas **]** parameter från Experience Platform Queries [!UICONTROL Credentials] in **[!UICONTROL ** Databas **]** textfält.

         Lägg till `?FLATTEN` till **[!UICONTROL ** Databas **]** parameter, så den ser ut som `prod:cja?FLATTEN` till exempel. Se [Förenkla kapslade datastrukturer för användning med BI-verktyg från tredje part](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) för mer information.

      1. När du uppmanas till detta **[!UICONTROL Data Connectivity]** läge, välja **[!UICONTROL DirectQuery]**.

      1. Du uppmanas att ange **[!UICONTROL Username]** och **[!UICONTROL Password]**. Använd likvärdiga parametrar från Experience Platform-frågor [!UICONTROL Credentials].


   1. När inloggningen är klar visas datavytabellerna i Customer Journey Analytics i Power BIETS **[!UICONTROL **&#x200B;Överblick **]**.

   1. Markera de datavytabeller som du vill använda och markera **[!UICONTROL ** Läs in **]**.

   Alla dimensioner och mätvärden som är kopplade till en eller flera markerade tabeller visas i den högra rutan, redo att användas i dina visualiseringar.

   Se [Anslut Power BI till frågetjänst](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) för mer information.

+++

+++Tableau

1. Här hittar du information om dina PostgresSQL-autentiseringsuppgifter i Adobe Experience Platform:

   1. Välj **[!UICONTROL ** Frågor **]** från vänster räl (under **[!UICONTROL ** DATAHANTERING **]**).

   1. Välj **[!UICONTROL ** Referenser **]** i det övre fältet.

   1. Välj ` cja` **[!UICONTROL ** Databas **]**.

   1. Använd ![Kopiera](assets/Smock_Copy_18_N.svg) för att kopiera alla Postgres-autentiseringsparametrar ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], och andra) när det behövs i Tablet.

1. I tabell:

   1. Välj **[!UICONTROL ** Mer **]** från **[!UICONTROL ** Till en server **]** till vänster.

   1. Välj **[!UICONTROL ** PostgresSQL **]** från listan.

   1. I [!UICONTROL PostgresSQL] dialog:

      1. Klistra in **[!UICONTROL ** Värd **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Server **]** textfält.

      1. Klistra in **[!UICONTROL ** Port **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Port **]** textfält.

      1. Klistra in **[!UICONTROL ** Databas **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Databas **]** textfält.

         Lägg till `%3FFLATTEN` till **[!UICONTROL ** Databas **]** parameter, så den ser ut som `prod:cja%3FFLATTEN` till exempel. Se [Förenkla kapslade datastrukturer för användning med BI-verktyg från tredje part](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) för mer information.

      1. Välj **[!UICONTROL ** Användarnamn och lösenord **]** från **[!UICONTROL ** Autentisering **]** lista.

      1. Klistra in **[!UICONTROL ** Användarnamn **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Användarnamn **]** textfält.

      1. Klistra in **[!UICONTROL ** Lösenord **]** parameter från Experience Platform Queries [!UICONTROL Credentials] till **[!UICONTROL ** Lösenord **]** textfält.

      1. Välj **[!UICONTROL ** Logga in **]**.

   1. datavyer i Customer Journey Analytics visas som tabeller i **[!UICONTROL ** Tabell **]** lista.

   1. Dra de tabeller som du vill använda på arbetsytan.

   Nu kan du arbeta med data från datavytabellerna för att skapa rapporter och visualiseringar.

   Se [Koppla tabell till frågetjänst](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau) för mer information.

+++

Se [Anslut klienter till frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview) om du vill ha en översikt över och mer information om de olika verktygen.

## Funktionalitet

Som standard har datavyerna ett tabellsäkert namn som genereras utifrån det egna namnet. Datavy med namnet [!UICONTROL My Web Data View] har vynamnet `my_web_data_view`. Du kan definiera ett föredraget namn som ska användas i BI-verktyget för datavyn. Se [Inställningar för datavy](create-dataview.md#settings) för mer information.

Om du vill använda ID:n för datavyn som tabellnamn kan du lägga till de valfria `CJA_USE_IDS` ange till ditt databasnamn vid anslutning. Till exempel: `prod:cja?CJA_USE_IDS` visar datavyer med namn som `dv_ABC123`.

### Datastyrning

De datastyrningsrelaterade inställningarna i Customer Journey Analytics ärvs från Adobe Experience Platform. Integrationen mellan Customer Journey Analytics och Adobe Experience Platform datastyrning möjliggör märkning av känsliga uppgifter från Customer Journey Analytics och tillämpning av integritetspolicyer.

Sekretessetiketter och integritetspolicyer som har skapats för datauppsättningar som används av Experience Platform kan visas i arbetsflödet för datavyer i Customer Journey Analytics. Det innebär att data efterfrågas med [!DNL Customer Journey Analytics BI extension] visa lämpliga varningar eller fel när de inte följer de definierade sekretessetiketterna och principerna.

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

Som standard använder schemat för datavyer kapslade strukturer, precis som de ursprungliga XDM-schemana. Integreringen har även stöd för `FLATTEN` alternativ. Du kan använda det här alternativet för att tvinga schemat för datavyer (och andra tabeller i sessionen) att förenklas. Förenkling gör det enklare att använda i BI-verktyg som inte stöder strukturerade scheman. Se [Arbeta med kapslade datastrukturer i frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) för mer information.

### SQL som stöds

Se [SQL-referens för frågetjänst](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview) för fullständig referens om vilken typ av SQL som stöds.

Se tabellen nedan för exempel på den SQL du kan använda.

+++ Exempel

| Mönster | Exempel |
|---|---|
| Schemaidentifiering | <pre>VÄLJ * FRÅN DV1 DÄR 1=0</pre> |
| Rankad/uppdelning | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA EFTER NEDRE1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39; OCH<br/>  filterId = &#39;12345&#39;<br/>GRUPPERA EFTER NEDRE1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39; OCH<br/>  AND (dim2 = &#39;A&#39; ELLER dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GRUPPERA EFTER NEDRE1</pre> |
| `HAVING` sats | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA EFTER NEDRE1<br/>MED m1 > 100</pre> |
| Distinkt, övre <br/>dimensionsvärden | <pre>VÄLJ DISTINCT dim1 FROM dv1</pre><pre>VÄLJ dim1 AS dv1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA EFTER NEDRE1</pre><pre>VÄLJ dim1 AS dv1<br/>FRÅN DV1<br/>DÄR \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\&#39; &lt; &#39;2022-01-02&#39;<br/>GRUPPERA EFTER NEDRE1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Måttsummor | <pre>VÄLJ SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;</pre> |
| Flera dimensioner<br/>uppdelning<br/>och förstklassiga | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA MED 1, 2<br/>BESTÄLL AV 1, 2</pre><pre>VÄLJ DISTINCT dim1, dim2<br/>FRÅN DV1</pre> |
| Delmarkera:<br/>Filtrera ytterligare<br/>resultat | <pre>SELECT dim1, m1<br/>FRÅN (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FRÅN DV1<br/>  DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;</br>  GRUPPERA EFTER NEDRE1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Delmarkera:<br/>Fråga tvärs över<br/>datavyer | <pre>SELECT key, SUM(m1) AS total<br/>FRÅN (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FRÅN DV1<br/>  DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>  GRUPPERA EFTER NEDRE1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FRÅN DV2<br/>  DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>  GRUPPERA EFTER NEDRE2<br/>GROUP BY-tangenten<br/>BESTÄLL EFTER Summa</pre> |
| Delmarkera: <br/>Källa i lager, <br/>filtrering, <br/>och aggregering | Lager med delmarkeringar:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FRÅN (<br/>  SELECT \_.dim1,\_.m1<br/>  FRÅN (<br/>    VÄLJ \* FRÅN DV1<br/>    DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 i (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rader<br/>GRUPPERA MED 1<br/>BESTÄLL EFTER Summa</pre><br/>Lager med CTE WITH:<br/><pre>MED rader AS (<br/>  MED \_ AS (<br/>    SELECT * FROM data_ares<br/>    DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2021-01-01&#39; OCH &#39;2021-02-01&#39;<br/>  )<br/>  VÄLJ \_.item, \_.units FROM \_<br/>  DÄR \_.item INTE ÄR NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FRÅN rader DÄR rader.objekt i (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Markerar var<br/>mätvärden kommer före<br/> eller är blandade med<br/>dimensionerna | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FRÅN DV1<br/>DÄR \&quot;tidsstämpel\&quot; MELLAN &#39;2022-01-01&#39; OCH &#39;2022-01-02&#39;<br/>GRUPPERA MED 2</pre> |

{style="table-layout:auto"}

+++

### Mått

Du kan välja någon av de tillgängliga dimensionerna som standard eller definierad i datavyn. Du väljer en dimension med dess ID.

### Mätvärden

De mätvärden som är tillgängliga är:

* någon av de mätvärden som är tillgängliga som standard,
* Definieras i datavyn.
* Beräknade mått som är kompatibla med datavyn som användaren har åtkomst till.

Du väljer ett mått med dess ID som omsluts av en `SUM(metric)` -uttryck på samma sätt som du gör med andra SQL-källor.

Du kan använda

* `SELECT COUNT(*)` eller `COUNT(1)` för att få förekomstmåtten.
* `SELECT COUNT(DISTINCT dimension)` eller `SELECT APPROX_COUNT_DISTINCT(dimension)` för att räkna de ungefärliga distinkta värdena för en dimension. Mer information finns i [Räkna distinkta värden](#counting-distinct-values).
* [Infogade beräkningar](#inline-calculations) för att kombinera mätvärden i farten och/eller göra matematik på dem.

#### Räkna distinkta värden

På grund av det underliggande sättet som Customer Journey Analytics fungerar på är den enda dimension som du kan få ett exakt distinkt antal för `adobe_personid` dimension. Följande SQL-satser `SELECT COUNT(DISTINCT adobe_personid)` eller `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` returnerar värdet för standardpersonmåttet, vilket är antalet distinkta personer. För andra dimensioner returneras ett ungefärligt distinkt antal.

#### Villkorliga mått

Du kan bädda in en `IF` eller `CASE` -satsen i `SUM` eller `COUNT` funktioner för att lägga till ytterligare filtrering som är specifik för ett markerat mätvärde. Att lägga till dessa satser påminner om att tillämpa ett filter på en måttkolumn i en arbetsyterapporttabell.

Exempel:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Infogade beräkningar

Du kan använda ytterligare matematik för metriska uttryck i `SELECT` i stället för att matematiken ska definieras i ett beräknat mått. I följande tabell visas vilka typer av uttryck som stöds.

| Operatör eller funktion | Information |
|---|---|
| `+`, `-`, `*`, `/`och `%` | Lägg till, subtrahera, multiplicera, dela och modulera/rest |
| `-X` eller `+X` | Ändra tecknet eller ett mått där X är måttuttrycket |
| `PI()` | π konstant |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`och `TANH` | Unära matematiska funktioner |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binära matematiska funktioner |

{style="table-layout:auto"}

### Specialkolumner

#### Tidsstämpel

The `timestamp` specialkolumn används för att ange datumintervall för frågan. Ett datumintervall kan definieras med en `BETWEEN` uttryck eller par med `timestamp` `>`, `>=`, `<`, `<=` kontroller `AND`tillsammans.
The `timestamp` är valfritt och om inget fullständigt intervall anges används standardvärdena:

* Om bara ett minimum anges (`timestamp > X` eller ` timestamp >= X`) är intervallet från X till nu.
* Om bara ett maxvärde anges (`timestamp < X` eller `timestamp <= X`) är intervallet från X minus 30 dagar till X.
* Om inget anges är intervallet från och med nu minus 30 dagar.

Tidsstämpelintervallet konverteras till ett globalt datumintervallfilter i RankedRequest.
Tidsstämpelfältet kan också användas i datum/tid-funktioner för att analysera eller korta av händelsens tidsstämpel.

#### Datumintervall

The `daterange` specialspalt fungerar ungefär som  `timestamp`filtreringen är dock begränsad till hela dagar. The `daterange` är också valfritt och har samma intervallstandard som `timestamp`.
The `daterange` -fältet kan också användas i datum/tid-funktioner för att analysera eller korta av händelsedatumet.

The `daterangeName` specialkolumner kan användas för att filtrera frågan med ett namngivet datumintervall som `Last Quarter`.

>[!NOTE]
>
>PowerBI stöder inte `daterange` mätvärden som är mindre än en dag (timme, 30 minuter, 5 minuter osv.).


#### Filter-ID

The `filterId` specialkolumnen är valfri och används för att tillämpa ett externt definierat filter på frågan. Att använda ett externt definierat filter på en fråga liknar att dra ett filter på en panel i Arbetsytan. Flera filter-ID:n kan anges av `AND`-Jag tar dem.

Tillsammans med `filterId`kan du använda `filterName` om du vill använda ett filtrets namn i stället för ID.

### Where-sats

The `WHERE` -satsen hanteras i tre steg:

1. Sök efter datumintervallet på menyn `timestamp`, `daterange`, eller `daterangeName` specialfält.

1. Sök efter externt definierade `filterId`s eller `filterName`s som ska tas med i filtreringen.

1. Omvandla de återstående uttrycken till ad hoc-filter.

Hanteringen görs genom att den första nivån i `AND`s i `WHERE` -sats. Varje översta nivå `AND`-ed-uttrycket måste matcha något av ovanstående. Allt som är djupare än den första nivån `AND`s, eller, om `WHERE` -sats använder `OR`s på den översta nivån hanteras som ett ad hoc-filter.

### Sorteringsordning

Som standard sorteras resultatet i frågan efter det första valda måttet i fallande ordning. Du kan skriva över standardsorteringsordningen genom att ange `ORDER BY ... ASC` eller `ORDER BY ... DESC`. Om du `ORDER BY`måste du ange `ORDER BY` på det första valda måttet.

Du kan också vända ordningen med `-` (minus) framför måttet. Båda programsatserna nedan resulterar i samma ordning:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Allmänt funktionsstöd

| Funktion | Exempel | Information |
|---|---|---|
| [Kast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` eller <br/> `` `timestamp`::string `` | Typdatatypsbyte stöds inte för närvarande, men inget fel genereras. The `CAST` funktionen ignoreras. |
| [Tidsstämpel](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Tolka en tidssträng som en tidsstämpel för användning i en `WHERE` -sats. |
| [Till tidsstämpel](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Tolka en tidssträng som en tidsstämpel för användning i en `WHERE` -sats, om du vill ange ett format för den tidssträngen. |
| [Datum](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Tolka en datumsträng som en tidsstämpel som ska användas i en `WHERE` -sats. |
| [Till-datum](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Tolka en datumsträng som en tidsstämpel som ska användas i en `WHERE` -sats, om du vill ange ett format för den datumsträngen. |

{style="table-layout:auto"}

### Funktionsstöd för Dimension

De här funktionerna kan användas på dimensioner i `SELECT`, `WHERE` eller i villkorsstyrda värden.

**Strängfunktioner**

| Funktion | Exempel | Information |
|---|---|---|
| [Lägre](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. |

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
| [Extract](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet för vissa delar av den här funktionen eftersom du behöver talet och inte det egna namnet.<br/>Följande delar stöds:<br>- Nyckelord: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Strängar:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, eller `'MINUTE'`. |
| [Datum (del)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet. Använd artikel-ID i stället för värdet för vissa delar av den här funktionen eftersom du behöver talet och inte det egna namnet.<br/>Följande strängdelar stöds: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, eller `'MINUTE'`. |
| [Datum (trunkerat)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generera en dynamisk dimensionsidentitet för det skickade fältet.<br/>Stränggranulariteter som stöds är: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, eller `'MINUTE'`. |

{style="table-layout:auto"}
