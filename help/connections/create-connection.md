---
title: Skapa en anslutning
description: Beskriver hur du skapar en anslutning till en plattformsdatauppsättning i Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 36fc82cf2c075550ced98193fe50115af12974de
workflow-type: tm+mt
source-wordcount: '2008'
ht-degree: 2%

---

# Skapa en anslutning

Ett nytt anslutningsarbetsflöde startades nyligen i Customer Journey Analytics (CJA). Här är en översikt över de nya funktionerna:

* Du kan aktivera ett rullande datalagringsfönster när du skapar anslutningen.
* Du kan lägga till och ta bort datauppsättningar från en anslutning. (Om du tar bort en datauppsättning tas den bort från anslutningen och påverkar associerade datavyer och underliggande Analysis Workspace-projekt.)
* Du kan aktivera och begära data för bakåtfyllnad per datauppsättning.
* Du kan redigera datauppsättningar, t.ex. för att begära en annan bakgrundsfyllning.
* Du kan importera befintliga data per datauppsättning.

## Skapa och konfigurera anslutningen {#create-connection}

1. I CJA klickar du på **[!UICONTROL Connections]** -fliken.
1. Klicka på **[!UICONTROL Create new connection]**.

   ![Anslutningsinställningar](assets/create-conn1.png)

1. Konfigurera anslutningsinställningarna.

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Connection name]** | Ange ett unikt namn för anslutningen. |
   | **[!UICONTROL Connection description]** | Beskriv syftet med den här anslutningen. |
   | **[!UICONTROL Sandbox]** | Välj en sandlåda i Experience Platform som innehåller den eller de datauppsättningar som du vill skapa en anslutning till.<p>Adobe Experience Platform tillhandahåller [sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) som partitionerar en enda plattformsinstans i separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Du kan tänka dig sandlådor som&quot;dataisoleringar&quot; som innehåller datauppsättningar. Sandlådor används för att styra åtkomst till datauppsättningar.<p>När du har valt sandlådan visas alla datauppsättningar i den sandlådan som du kan hämta från den vänstra listen. |
   | **[!UICONTROL Enable rolling data window]** | Med den här inställningen kan du definiera CJA-datalagring som ett rullande fönster på anslutningsnivå i månader (1 månad, 3 månader, 6 månader osv.).<p>Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för rullande datafönster för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar. Om din anslutning innehåller en profil- eller uppslagsdatauppsättning (förutom en eller flera händelsedatamängder) kommer dessa data att lagras under samma tidsperiod.<p> Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader. |
   | **[!UICONTROL Add datasets]** (se nedan) | Lägg till datauppsättningar om det inte finns några datauppsättningar i datauppsättningslistan. |
   | **[!UICONTROL Dataset name]** | Markera en eller flera datauppsättningar som du vill hämta till Customer Journey Analytics och klicka på **[!UICONTROL Add]**.<p>(Om du har många datauppsättningar att välja bland kan du söka efter rätt datauppsättningar med sökfältet Sök efter datauppsättningar ovanför listan med datauppsättningar.) |
   | **[!UICONTROL Last updated]** | Endast för händelsedatamängder anges den här inställningen automatiskt till standardfältet för tidsstämpling från händelsebaserade scheman i Experience Platform. &quot;Ej tillämpligt&quot; innebär att den här datauppsättningen inte innehåller några data. |
   | **[!UICONTROL Schema]** | Det här är [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en) baserat på vilket datauppsättningen skapades i Adobe Experience Platform. |
   | **[!UICONTROL Dataset type]** | För varje datauppsättning som du har lagt till i den här anslutningen anger Customer Journey Analytics automatiskt datauppsättningstypen baserat på de data som kommer in. Det finns tre olika datamängdstyper: Händelsedata, profildata och sökdata. Se tabellen nedan för en förklaring av datamängdstyperna. |
   | **[!UICONTROL Person ID]** | Välj ett person-ID i listrutan med tillgängliga identiteter. Dessa identiteter definierades i datauppsättningsschemat i Experience Platform. Nedan finns information om hur du använder identitetskartan som ett person-ID.<p>VIKTIGT! Om det inte finns några person-ID:n att välja mellan, innebär det att ett eller flera person-ID:n inte har definierats i schemat. Visa [den här videon](https://www.youtube.com/watch?v=G_ttmGl_LRU) om hur du definierar en identitet i Experience Platform. |
   | **[!UICONTROL Key]** | Endast för uppslagsdatauppsättningar (till exempel _id). |
   | **[!UICONTROL Matching Key]** | Endast för uppslagsdatauppsättningar (till exempel _id). |
   | **[!UICONTROL Import new data]** | Ange till På eller Av. |
   | **[!UICONTROL Backfill data]** |  |
   | **[!UICONTROL Backfill status]** | Anger om några data för bakgrundsfyllning bearbetas. |

   {style=&quot;table-layout:auto&quot;}

## Lägga till och konfigurera datauppsättningar {#add-dataset}

Med det nya arbetsflödet kan du lägga till en datauppsättning i Experience Platform när du skapar en anslutning.

1. I dialogrutan Anslutningsinställningar klickar du på **[!UICONTROL Add datasets]**.
1. Markera en eller flera datauppsättningar och klicka på **[!UICONTROL Next]**.

   Observera att minst en händelsedatamängd måste ingå i anslutningen.
1. Konfigurera datauppsättningarna en i taget.

   ![Konfigurera datauppsättningar](assets/add-dataset.png)

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Välj ett person-ID i listrutan med tillgängliga identiteter. Dessa identiteter definierades i datauppsättningsschemat i Experience Platform. Nedan finns information om hur du använder identitetskartan som ett person-ID.<p>Om det inte finns några person-ID:n att välja mellan, innebär det att ett eller flera person-ID:n inte har definierats i schemat. Se den här videon om hur du definierar en identitet i Experience Platform. |
   | **[!UICONTROL Timestamp]** | Endast för händelsedatamängder anges den här inställningen automatiskt till standardfältet för tidsstämpling från händelsebaserade scheman i Experience Platform. |
   | **[!UICONTROL Import new data]** | Välj det här alternativet om du vill upprätta en pågående anslutning så att alla nya databatchar som läggs till i datauppsättningarna i den här anslutningen automatiskt flödar till arbetsytan. Kan anges till På eller Av. |
   | **[!UICONTROL Dataset backfill]** | Klicka **[!UICONTROL Request backfill]** för att fylla historikdata baklänges.<ul><li>Du kan fylla i varje datauppsättning separat.</li><li>Vi prioriterar nya data som läggs till i en datauppsättning i anslutningen, så att dessa nya data har den lägsta latensen.</li><li>Eventuella bakåtfyllnadsdata (historiska) importeras i en långsammare takt. Latensen påverkas av hur mycket historisk information du har.</li><li>Adobe Analytics Source Connector importerar upp till 13 månaders data, oavsett storlek.</li></ul> |
   | **[!UICONTROL Backfill status]** | Möjliga statusindikatorer är:<ul><li>Lyckades</li><li>X-bearbetning av bakgrundsfyllning(ar)</li><li>Av</li></ul> |
   | **[!UICONTROL Dataset ID]** | Detta ID genereras automatiskt. |
   | **[!UICONTROL Description]** | Beskrivningen som den här datauppsättningen fick när den skapades. |
   | **[!UICONTROL Dataset size]** | Datauppsättningens storlek. |
   | **[!UICONTROL Schema]** | Detta är schemat som baserar sig på vilket datauppsättningen skapades i Adobe Experience Platform. |
   | **[!UICONTROL Dataset]** | Datauppsättningens namn. |
   | **[!UICONTROL Preview]**: `<dataset name>` | Förhandsgranskar datauppsättningen med kolumnerna date, my ID och Identifier. |
   | **[!UICONTROL Remove]** | Ta bort den här datauppsättningen från anslutningen. |

   {style=&quot;table-layout:auto&quot;}

## Förhandsgranska anslutning {#preview}

Om du vill förhandsgranska anslutningen som du har skapat klickar du på **[!UICONTROL Connection preview]** i dialogrutan Anslutningsinställningar.

![Förhandsgranska anslutning](assets/create-conn4.png)

Den här förhandsgranskningen innehåller ett antal kolumner som visar anslutningskonfigurationen. Vilka kolumntyper som visas beror på dina enskilda datauppsättningar.

## Datamängdstyper {#dataset-types}

För varje datauppsättning som du har lagt till i den här anslutningen [!UICONTROL Customer Journey Analytics] anger automatiskt datamängdstypen baserat på de data som kommer in.

>[!IMPORTANT]
>
>Du måste lägga till minst en händelsedatamängd som en del av en anslutning.

Det finns tre olika datamängdstyper: [!UICONTROL Event] data, [!UICONTROL Profile] data, och [!UICONTROL Lookup] data.

| Typ av datauppsättning | Beskrivning | Tidsstämpel | Schema | Person-ID |
|---|---|---|---|---|
| **[!UICONTROL Event]** | Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsinformation osv.). Detta kan till exempel vara typiska klickströmsdata, med ett kund-ID eller ett cookie-ID och en tidsstämpel. Med händelsedata får du flexibilitet vad gäller vilket ID som används som person-ID. | ställs automatiskt in på standardfältet för tidsstämpling från händelsebaserade scheman i [!UICONTROL Experience Platform]. | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet&quot;Time Series&quot;. Exempel är &quot;XDM Experience Event&quot; eller &quot;XDM Decision Event&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datamängdsschema som definieras i Experience Platform kan ha en egen uppsättning av en eller flera identiteter som är definierade och associerade med ett identitetsnamnutrymme. Alla dessa kan användas som person-ID. Exempel är cookie-ID, Stitched ID, User ID, Tracking Code osv. |
| **[!UICONTROL Lookup]** | Dessa data används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. Se [det här användningsfallet](/help/use-cases/b2b.md) till exempel. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet &quot;Record&quot;, förutom klassen &quot;XDM Individual Profile&quot;. | Ej tillämpligt |
| **[!UICONTROL Profile]** | Data som tillämpas på era besökare, användare eller kunder i [!UICONTROL Event] data. Du kan till exempel överföra CRM-data om dina kunder. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på klassen &quot;XDM Individual Profile&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i [!DNL Experience Platform] har en egen uppsättning av ett eller flera definierade person-ID, t.ex. cookie-ID, Stitched ID, User ID, Tracking Code osv.<br>![Person-ID ](assets/person-id.png)**Anteckning**: Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du verkligen vill sammanfoga datauppsättningar måste du använda samma person-ID. |

{style=&quot;table-layout:auto&quot;}

## Använd identitetskarta som person-ID {#id-map}

Customer Journey Analytics har nu stöd för möjligheten att använda identitetskartan för sitt person-ID. Identitetskarta är en kartdatastruktur som gör att någon kan överföra nyckel -> värdepar. Nycklarna är ID-namnutrymmen och värdet är den struktur som innehåller identitetsvärdet. Identitetskartan finns för varje överförd rad/händelse och fylls i för varje rad i enlighet med detta.

Identitetskartan är tillgänglig för alla datauppsättningar som använder ett schema baserat på [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) klassen. När du väljer en sådan datauppsättning som ska inkluderas i en CJA-anslutning kan du välja att antingen välja ett fält som primärt ID eller identitetskartan:

![](assets/idmap1.png)

Om du väljer Identitetskarta får du ytterligare två konfigurationsalternativ:

| Alternativ | Beskrivning |
|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | Detta instruerar CJA, per rad, att hitta identiteten i identitetskartan som är markerad med ett primär=true-attribut och använda det som ID för den raden. Detta innebär att det här är den primärnyckel som ska användas i Experience Platform för partitionering. Det är också den primära kandidaten för CJA:s besökar-ID (beroende på hur datauppsättningen konfigureras i en CJA-anslutning). |
| **[!UICONTROL Namespace]** | (Det här alternativet är bara tillgängligt om du inte använder namnutrymmet för primärt ID.) Identitetsnamnutrymmen är en komponent i [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) som fungerar som indikatorer för det sammanhang som en identitet hör till. Om du anger ett namnutrymme söker CJA efter den här namnutrymmesnyckeln i varje rads identitetskarta och använder identiteten under namnutrymmet som ID för den raden. Observera att eftersom CJA inte kan göra en fullständig datauppsättningssökning av alla rader för att avgöra vilka namnutrymmen som faktiskt finns, visas alla möjliga namnutrymmen i listrutan. Du måste veta vilka namnutrymmen som anges i data; detta kan inte identifieras automatiskt. |

{style=&quot;table-layout:auto&quot;}

### Kantärenden för identitetskarta {#id-map-edge}

I den här tabellen visas de två konfigurationsalternativen när det finns kantfall och hur de hanteras:

| Alternativ | Det finns inga ID:n i identitetskartan | Inga ID har markerats som primära | Flera ID:n är markerade som primära | Ett ID är markerat som primärt | Ogiltigt namnutrymme med ett ID markerat som primärt |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace]checked** | Raden tas bort av CJA. | Raden tas bort av CJA eftersom inget primärt ID har angetts. | Alla ID:n som markerats som primära, under alla namnutrymmen, extraheras till en lista. De sorteras sedan alfabetiskt, med den här nya sorteringen används det första namnutrymmet med dess första ID som person-ID. | Det enda ID som är markerat som primärt används som person-ID. | Även om namnutrymmet kan vara ogiltigt (inte finns i AEP) kommer CJA att använda det primära ID:t under namnutrymmet som Person-ID. |
| **[!UICONTROL Specific Identity Map namespace]markerad** | Raden tas bort av CJA. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. (Endast ett giltigt namnutrymme kan väljas när anslutningen skapas, så det är inte möjligt att använda ett ogiltigt namnutrymme/ID som person-ID) |

{style=&quot;table-layout:auto&quot;}

## Beräkna det genomsnittliga antalet dagliga händelser

Denna beräkning måste göras för varje datauppsättning i anslutningen.

1. Gå till [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv) och skapa en ny fråga.

   Frågan skulle se ut så här:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   I det här exemplet är &quot;analytics_demo_data&quot; namnet på datauppsättningen.

1. Utför `Show Tables` -fråga för att visa alla datauppsättningar som finns i AEP.
