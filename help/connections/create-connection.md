---
title: Skapa eller redigera en anslutning
description: Beskriver hur du skapar eller redigerar en anslutning till en datauppsättning för Experience Platform i Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 8fe3fb966f559aa12f3203e02a1766436e45a24a
workflow-type: tm+mt
source-wordcount: '3029'
ht-degree: 1%

---

# Skapa eller redigera en anslutning

Arbetsflödet för att skapa och redigera anslutningar gör att alla konfigurationsinställningar för datauppsättningar och anslutningar hamnar mitt på skärmen med ett hjälparbetsflöde. Den ger detaljerad information om val, konfiguration och granskning av datauppsättningar. Och gör att du kan ange viktig information som datamängdstyp, storlek, schema, datauppsättnings-ID, batchstatus, bakåtfyllnadsstatus, person-ID och mycket annat, för att minska risken för fel anslutningskonfiguration. Här är en översikt över funktionerna:

* Du kan aktivera ett rullande datalagringsfönster när du skapar anslutningen.
* Du kan lägga till och ta bort datauppsättningar från en anslutning. (Om du tar bort en datauppsättning tas den bort från anslutningen och påverkar associerade datavyer och underliggande Analysis Workspace-projekt.)
* Du kan aktivera och begära data för bakåtfyllnad per datauppsättning.
* Du kan redigera datauppsättningar, t.ex. för att begära en annan bakgrundsfyllning.
* Du kan importera befintliga data per datauppsättning.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## Förutsättningar

Det maximala antalet datauppsättningar som du kan lägga till i en anslutning är 100. Blandningen beror på vilket Customer Journey Analytics-paket ditt företag har köpt.

Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

| **Välj**-paket | Paketet **Foundation** |
| --- | --- |
| Valfri kombination av händelse-/profil-/uppslagsdatauppsättningar, vilket ger upp till 100 | En händelsedatamängd per anslutning |
|  | Upp till 99 profil- eller uppslagsdatauppsättningar per anslutning |

{style="table-layout:auto"}

## Skapa och konfigurera anslutningen {#create-connection}

1. I Customer Journey Analytics väljer du fliken **[!UICONTROL Connections]**.
1. Välj **[!UICONTROL Create new connection]**.

   ![Namnlösa anslutningsinställningar](assets/create-conn1.png)

1. Konfigurera anslutningsinställningarna.

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Connection name]** | Ange ett unikt namn för anslutningen. |
   | **[!UICONTROL Connection description]** | Beskriv syftet med den här anslutningen. |
   | **[!UICONTROL Sandbox]** | Välj en sandlåda i Experience Platform som innehåller den eller de datauppsättningar som du vill skapa en anslutning till.<p>Adobe Experience Platform tillhandahåller [sandlådor](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) som partitionerar en enda plattformsinstans till separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Du kan tänka dig sandlådor som&quot;dataisoleringar&quot; som innehåller datauppsättningar. Sandlådor används för att styra åtkomst till datauppsättningar.<p>När du har valt sandlådan visas alla datauppsättningar i den sandlådan som du kan hämta från den vänstra listen. |
   | **[!UICONTROL Enable rolling data window]** | Om den här kryssrutan är markerad kan du definiera datalagring i Customer Journey Analytics som ett rullande fönster på anslutningsnivå i månader (1 månad, 3 månader, 6 månader och så vidare).<p>Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för rullande datafönster för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar. Om din anslutning innehåller en profil- eller uppslagsdatauppsättning (förutom en eller flera händelsedatamängder), behålls dessa data för samma tidsperiod.<p> Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader.<p>Om du låter standardvärdet vara (omarkerat) ersätts kvarhållningsperioden av Adobe Experience Platform datalagringsinställning. Om du har 25 månaders data i Experience Platform får Customer Journey Analytics 25 månaders data genom backfill. Om du raderade 10 av dessa månader i Platform behåller Customer Journey Analytics de återstående 15 månaderna. |
   | **[!UICONTROL Add datasets]** (se nedan) | Lägg till datauppsättningar om det inte finns några datauppsättningar i datauppsättningslistan. |
   | **[!UICONTROL Dataset name]** | Markera en eller flera datauppsättningar som du vill hämta till Customer Journey Analytics och välj **[!UICONTROL Add]**.<p>(Om du har många datauppsättningar att välja bland kan du söka efter rätt datauppsättningar med sökfältet Sök efter datauppsättningar ovanför listan med datauppsättningar.) |
   | **[!UICONTROL Last updated]** | Endast för händelsedatamängder anges den här inställningen automatiskt till standardfältet för tidsstämpling från händelsebaserade scheman i Experience Platform. &quot;Ej tillämpligt&quot; innebär att den här datauppsättningen inte innehåller några data. |
   | **[!UICONTROL Schema]** | Det [schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition) som baserar sig på vilken datauppsättningen skapades i Adobe Experience Platform. |
   | **[!UICONTROL Dataset type]** | För varje datauppsättning som du har lagt till i den här anslutningen anger Customer Journey Analytics automatiskt datauppsättningstypen baserat på de data som kommer in. Det finns tre olika datamängdstyper: Händelsedata, Profildata och Uppslagsdata. Se tabellen nedan för en förklaring av datamängdstyperna. |
   | **[!UICONTROL Person ID]** | Välj ett person-ID i listrutan med tillgängliga identiteter. Dessa identiteter definierades i datauppsättningsschemat i Experience Platform. Nedan finns information om hur du använder identitetskartan som ett person-ID.<p>VIKTIGT: Om det inte finns några person-ID att välja mellan, innebär det att ett eller flera person-ID inte har definierats i schemat. Visa [den här videon](https://www.youtube.com/watch?v=G_ttmGl_LRU) om hur du definierar en identitet i Experience Platform. |
   | **[!UICONTROL Key]** | Endast för uppslagsdatauppsättningar (till exempel _id). |
   | **[!UICONTROL Matching Key]** | Endast för uppslagsdatauppsättningar (till exempel _id). |
   | **[!UICONTROL Import new data]** | Inställd på På eller Av. |
   | **[!UICONTROL Backfill data]** | Du kan begära att få fylla i data i en datauppsättning baklänges baserat på tidsstämplar för händelsen. Du kan till exempel begära att de senaste 7 dagarnas data ska fyllas i igen. Konfigurera rätt person-ID och testa anslutningen. Om allt ser bra ut kan du enkelt fylla i alla återstående data.<p>Dessutom kan du aktivera import av nya data per datauppsättning. |
   | **[!UICONTROL Backfill status]** | Den här statusen anger om några data för bakgrundsfyllning bearbetas. |

   {style="table-layout:auto"}

## Lägga till och konfigurera datauppsättningar {#add-dataset}

Med det nya arbetsflödet kan du lägga till en datauppsättning i Experience Platform när du skapar en anslutning.

1. Välj **[!UICONTROL Add datasets]** i dialogrutan Anslutningsinställningar.

1. I [!UICONTROL Select datasets]-steget visas en lista med datauppsättningar i Experience Platform.

   ![Välj datauppsättningar](assets/select-datasets.png)

   För varje datauppsättning visas följande i listan:

   | Kolumn | Beskrivning |
   |---|---|
   | Datauppsättning | Datauppsättningens namn. Markera namnet som du vill dirigera till datauppsättningen i Experience Platform. Välj ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) om du vill visa ett popup-fönster med mer information om datauppsättningen. På popup-menyn kan du välja **[!UICONTROL Edit in Platform]** om du vill redigera datauppsättningen direkt i Experience Platform. |
   | Datauppsättningstyp | Datatypen: Händelse, profil eller Sök. |
   | Antal poster | Det totala antalet poster under föregående månad för datauppsättningen i Experience Platform. |
   | Schema | Det schema som datauppsättningen baseras på. Markera namnet som du vill dirigera till schemat i Experience Platform. |
   | Senaste batch | Status för den senaste batchen som importerats i Experience Platform. Mer information finns i [Gruppstatus](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/batch/troubleshooting#batch-states). |
   | Datauppsättnings-ID | Datauppsättningens ID. |
   | Senast uppdaterad | Den senaste uppdaterade tidsstämpeln för datauppsättningen. |


1. Markera en eller flera datauppsättningar och välj **[!UICONTROL Next]**. Minst en händelsedatamängd måste ingå i anslutningen.
   * Om du vill ändra vilka kolumner som visas för listan med datauppsättningar väljer du ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) och markerar de kolumner som ska visas i dialogrutan [!UICONTROL Customize table].
   * Om du vill söka efter en viss datauppsättning använder du sökfältet ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Om du vill växla mellan att visa eller dölja de markerade datauppsättningarna väljer du ![Markera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg) **[!UICONTROL Hide selected]** eller **[!UICONTROL Show selected]**.
   * Om du vill ta bort en datauppsättning från listan med valda datauppsättningar använder du ![Close](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Om du vill ta bort alla markerade datauppsättningar väljer du **[!UICONTROL Clear all]**.




1. Konfigurera datauppsättningarna en i taget.

   ![Konfigurera datauppsättningar](assets/add-dataset.png)

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Endast tillgängligt för händelse- och profildatauppsättningar. Välj ett person-ID i listrutan med tillgängliga identiteter. Dessa identiteter definierades i datauppsättningsschemat i Experience Platform. Nedan finns information om hur du använder identitetskartan som ett person-ID.<p>Om det inte finns några person-ID:n att välja mellan, innebär det att ett eller flera person-ID:n inte har definierats i schemat. Mer information finns i [Definiera identitetsfält i användargränssnittet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity). <p>Värdet för det valda person-ID:t anses vara skiftlägeskänsligt. `abc123` och `ABC123` är till exempel två olika värden. |
   | **[!UICONTROL Timestamp]** | Endast för händelsedatamängder anges den här inställningen automatiskt till standardfältet för tidsstämpling från händelsebaserade scheman i Experience Platform. |
   | **[!UICONTROL Key]** | Endast tillgängligt för uppslagsdatauppsättningar. Nyckeln som ska användas för en uppslagsdatauppsättning. |
   | **[!UICONTROL Matching key]** | Endast tillgängligt för uppslagsdatauppsättningar. Den matchande nyckeln som ska användas i en av händelsedatamängderna. Om den här listan är tom har du förmodligen inte lagt till eller konfigurerat någon händelsedatamängd. |
   | **[!UICONTROL Data source type]** | Välj en typ av datakälla. <br/>Typer av datakällor omfattar: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>Det här fältet används för att undersöka vilka typer av datakällor som används. |
   | **[!UICONTROL Import new data]** | Välj det här alternativet om du vill upprätta en pågående anslutning så att alla nya databatchar som läggs till i datauppsättningarna i den här anslutningen automatiskt flödar till Workspace. Kan anges till [!UICONTROL On] eller [!UICONTROL Off]. |
   | **[!UICONTROL Dataset backfill]** | Aktivera **[!UICONTROL Backfill all existing data]** för att se till att alla befintliga data är efterfyllda.<br/><br/>Välj **[!UICONTROL Request backfill]** om du vill fylla i historiska data baklänges för en viss period. Du kan definiera upp till 10 backfill-perioder för datauppsättningar.<ol><li>Definiera perioden genom att ange start- och slutdata eller välja datum med ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Välj **[!UICONTROL Queue backfill]** om du vill lägga till en bakgrundsfyllning i listan eller **[!UICONTROL Cancel]** om du vill avbryta.</li></ol>För varje post väljer du ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) om du vill redigera punkten eller ![Ta bort](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) om du vill ta bort posten.<br/><br/>På bakåtfyllningar:<ul><li>Du kan fylla i varje datauppsättning separat.</li><li>Du prioriterar nya data som läggs till i en datauppsättning i anslutningen, så att dessa nya data har den lägsta fördröjningen.</li><li>Eventuella bakåtfyllnadsdata (historiska) importeras i en långsammare takt. Latensen påverkas av hur mycket historisk information du har.</li><li>Analysens källanslutning importerar upp till 13 månaders data (oavsett storlek) för produktionssandlådor. Bakåtfyllnaden i icke-produktionssandlådor är begränsad till tre månader.</li></ul> |
   | **[!UICONTROL Transform dataset]** | För specifika B2B-sökdatauppsättningar kan du aktivera omvandling av en datauppsättning för korrekta B2B-personbaserade rapportscenarier. Mer information finns i [Omforma datauppsättningar för B2B-sökningar](transform-datasets-b2b-lookups.md). |
   | **[!UICONTROL Backfill status]** | Möjliga statusindikatorer är:<ul><li>Lyckades</li><li>X-bearbetning av bakgrundsfyllning(ar)</li><li>Av</li></ul> |
   | **[!UICONTROL Dataset ID]** | Detta ID genereras automatiskt. |
   | **[!UICONTROL Description]** | Beskrivningen som den här datauppsättningen fick när den skapades. |
   | **[!UICONTROL Dataset size]** | Datauppsättningens storlek. |
   | **[!UICONTROL Schema]** | Det schema som datamängden skapades utifrån i Adobe Experience Platform. |
   | **[!UICONTROL Dataset]** | Datauppsättningens namn. |
   | **[!UICONTROL Preview: *datauppsättningsnamn *]** | Förhandsgranskar datauppsättningen med kolumnerna date, my ID och Identifier. |
   | **[!UICONTROL Remove]** | Du kan ta bort eller ta bort datauppsättningen och ändra person-ID utan att ta bort hela anslutningen. Att ta bort eller ta bort minskar kostnaderna för datainmatning och den krångliga processen att återskapa hela anslutningen och tillhörande datavyer. |

   {style="table-layout:auto"}

## Förhandsgranska anslutning {#preview}

Om du vill förhandsgranska anslutningen som du har skapat väljer du **[!UICONTROL Connection preview]** i dialogrutan Anslutningsinställningar.

![Förhandsgranskning av anslutning](assets/create-conn4.png)

Den här förhandsgranskningen innehåller några kolumner med en lista över anslutningskonfigurationen. Vilka kolumntyper som visas beror på dina enskilda datauppsättningar.

## Datamängdstyper {#dataset-types}

För varje datauppsättning som du lägger till i den här anslutningen anger [!UICONTROL Customer Journey Analytics] automatiskt datamängdstypen baserat på de data som kommer in.

>[!IMPORTANT]
>
>Lägg till minst en händelsedatamängd som en del av en anslutning.

Det finns tre olika datamängdstyper: [!UICONTROL Event] data, [!UICONTROL Profile] data och [!UICONTROL Lookup] data.

| Typ av datauppsättning | Beskrivning | Tidsstämpel | Schema | Person-ID |
|---|---|---|---|---|
| **[!UICONTROL Event]** | Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsvisningsdata osv.). Dessa data kan till exempel vara typiska klickströmsdata, med ett kund-ID eller ett cookie-ID och en tidsstämpel. Med händelsedata får du flexibilitet vad gäller vilket ID som används som person-ID. | Ange automatiskt till standardtidsstämpelfältet från händelsebaserade scheman i [!UICONTROL Experience Platform]. | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet&quot;Time Series&quot;. Exempel är &quot;XDM Experience Event&quot; eller &quot;XDM Decision Event&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datamängdsschema som definieras i Experience Platform kan ha en egen uppsättning av en eller flera identiteter som är definierade och associerade med ett identitetsnamnutrymme. Alla dessa identiteter kan användas som person-ID. Exempel är cookie-ID, Stitched ID, User ID, Tracking Code och så vidare. |
| **[!UICONTROL Lookup]** | Nu kan du lägga till datauppsättningar som uppslag med fält i alla datamängdstyper: Profil-, uppslags- och händelsedatamängder (den senare stöds alltid). Den här extrafunktionen utökar CJA:s förmåga att stödja komplexa datamodeller, inklusive B2B CDP. Dessa data används för att söka efter värden eller nycklar som finns i dina Event-, Profile- eller Lookup-data. Du kan lägga till upp till två söknivåer. (Observera att [Härledda fält](/help/data-views/derived-fields/derived-fields.md) inte kan användas som matchande nycklar för uppslag i anslutningar.) Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. Ett exempel finns i [användningsfall för B2B](/help/use-cases/b2b/b2b.md). | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet &quot;Record&quot;, förutom klassen &quot;XDM Individual Profile&quot;. | Ej tillämpligt |
| **[!UICONTROL Profile]** | Data som tillämpas på dina personer, användare eller kunder i [!UICONTROL Event]-data. Du kan till exempel överföra CRM-data om dina kunder. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på klassen &quot;XDM Individual Profile&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i [!DNL Experience Platform] har en egen uppsättning med ett eller flera definierade person-ID, till exempel cookie-ID, Stitched ID, User ID, Tracking Code o.s.v.<br>![Person-ID ](assets/person-id.png)**Obs!** Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, visas detta i rapporten. Om du vill sammanfoga datauppsättningar måste du använda samma person-ID. |

{style="table-layout:auto"}

## Använd numeriska fält som söknycklar och sökvärden {#numeric}

Den här sökfunktionen är användbar om du vill lägga till ett numeriskt fält, t.ex. en kostnad eller marginal, i ett strängbaserat nyckelfält. Det tillåter att numeriska värden ingår i uppslag, antingen som nycklar eller som värden. I sökschemat kan du ha numeriska värden kopplade till exempelvis produktnamn, COGS, kampanjmarknadsföringskostnader eller marginaler. Här är ett exempel på sökschema i Adobe Experience Platform:

![Sökschema](assets/schema.png)

Ni har nu stöd för att lägga in dessa värden som mått i Customer Journey Analytics-rapporter. När du konfigurerar anslutningen och hämtar in uppslagsdatauppsättningar kan du redigera datauppsättningarna och välja [!UICONTROL Key] och [!UICONTROL Matching Key]:

![Redigera-datamängd](assets/lookup-dataset.png)

När du ställer in en datavy baserad på den här anslutningen lägger du till numeriska värden som komponenter i datavyn. Alla projekt som baseras på den här datavyn kan sedan rapportera dessa numeriska värden.

## Använd identitetskarta som person-ID {#id-map}

Customer Journey Analytics stöder möjligheten att använda identitetskartan för sitt person-ID. Identitetskarta är en kartdatastruktur som gör att du kan överföra nyckelvärden -> värdepar. Nycklarna är ID-namnutrymmen och värdet är den struktur som innehåller identitetsvärdet. Identitetskartan finns för varje överförd rad/händelse och fylls i för varje rad i enlighet med detta.

Identitetskartan är tillgänglig för alla datauppsättningar som använder ett schema baserat på [ExperienceEvent XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home) -klassen. När du väljer en sådan datauppsättning som ska inkluderas i en Customer Journey Analytics-anslutning kan du välja att antingen välja ett fält som primärt ID eller identitetskartan:

![](assets/idmap1.png)

Om du väljer Identitetskarta får du ytterligare två konfigurationsalternativ:

| Alternativ | Beskrivning |
|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | Det här alternativet instruerar Customer Journey Analytics, per rad, att hitta identiteten i identitetskartan som är markerad med ett `primary=true`-attribut och använda den identiteten som ID för den raden. Den här identiteten är den primärnyckel som används i Experience Platform för partitionering. Och den här identiteten är också den primära kandidaten för användning som Customer Journey Analytics person-ID (beroende på hur datauppsättningen konfigureras i en Customer Journey Analytics-anslutning). |
| **[!UICONTROL Namespace]** | (Det här alternativet är bara tillgängligt om du inte använder namnutrymmet för primärt ID.) Identitetsnamnutrymmen är en komponent i [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces) som fungerar som indikatorer för det sammanhang som en identitet relateras till. Om du anger ett namnutrymme söker Customer Journey Analytics igenom varje rads identitetskarta efter namnutrymmesnyckeln och använder identiteten under namnutrymmet som ID för den raden. Eftersom Customer Journey Analytics inte kan göra en fullständig datauppsättningssökning av alla rader för att avgöra vilka namnutrymmen som finns, visas alla möjliga namnutrymmen i listrutan. Ha koll på vilka namnutrymmen som anges i data. Dessa namnutrymmen identifieras inte automatiskt. |

{style="table-layout:auto"}

### Kantärenden för identitetskarta {#id-map-edge}

I den här tabellen visas de två konfigurationsalternativen när det finns kantfall och hur de hanteras:

| Alternativ | Det finns inga ID:n i identitetskartan | Flera ID:n, ingen markerade som primär | Flera ID:n är markerade som primära | Ett ID, markerat som primärt eller inte | Ogiltigt namnutrymme med ett ID markerat som primärt |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace]checked** | Customer Journey Analytics släpper raden. | Customer Journey Analytics släpper raden eftersom inget primärt ID har angetts. | Alla ID:n som markerats som primära, under alla namnutrymmen, extraheras till en lista. De sorteras sedan i bokstavsordning. Med den nya sorteringen används det första namnutrymmet med dess första ID som person-ID. | Det enskilda ID:t används som person-ID. | Även om namnutrymmet kan vara ogiltigt (inte finns i Adobe Experience Platform) använder Customer Journey Analytics det primära ID:t under det namnutrymmet som Person-ID. |
| **[!UICONTROL Specific Identity Map namespace]markerade** | Customer Journey Analytics släpper raden. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. (Endast ett giltigt namnutrymme kan väljas när anslutningen skapas, så det är inte möjligt att använda ett ogiltigt namnutrymme/ID som person-ID) |

{style="table-layout:auto"}

## Beräkna det genomsnittliga antalet dagliga händelser {#average-number}

Beräkningen görs för varje datauppsättning i anslutningen.

1. Gå till [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) och skapa en fråga.

   Frågan skulle se ut så här:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   I det här exemplet är &quot;analytics_demo_data&quot; namnet på datauppsättningen.

2. Om du vill visa alla datauppsättningar som finns i Adobe Experience Platform ska du utföra frågan `Show Tables`.


## Algoritmisk rensning av stora uppslagsdatauppsättningar

När du skapar en anslutning kan du lägga till stora datauppsättningar för uppslagsändamål. En datauppsättning som representerar en produktkatalog så att beskrivande produktinformation kan slås upp när rapporter och visualiseringar skapas. En sådan stor datauppsättning för sökning kan överskrida det maximala antalet 10 miljoner unika sökningar som för närvarande implementeras som ett skyddsutkast, vilket resulterar i att ytterligare data hoppas över.

Du kan begära en algoritmisk rensning av en stor uppslagsdatauppsättning. Den här algoritmiska rensningen sparar bara data i uppslagsdatauppsättningen som matchar nycklarna i händelsedatauppsättningen. På så sätt behöver du inte läsa in hela datauppsättningen för orensad sökning. Gamla eller mindre ofta använda objekt tas bort, vilket kan påverka rapporter något men ger avsevärda fördelar. Algoritmen tittar tillbaka 90 dagar och uppdateras varje vecka.

Kontakta supportteamet på Adobe för mer information och för att aktivera den här funktionen.
