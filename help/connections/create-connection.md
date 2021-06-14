---
title: Skapa en anslutning
description: Beskriver hur du skapar en anslutning till en plattformsdatauppsättning i Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
source-git-commit: 16533219915421ed3ff642250bb707bf5ef13ed7
workflow-type: tm+mt
source-wordcount: '2001'
ht-degree: 2%

---

# Skapa en anslutning

Med en anslutning kan du integrera datauppsättningar från [!DNL Adobe Experience Platform] i [!UICONTROL Workspace]. För att kunna rapportera [!DNL Experience Platform]-datauppsättningar måste du först upprätta en anslutning mellan datauppsättningar i [!DNL Experience Platform] och [!UICONTROL Workspace].

Klicka [här](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connecting-customer-journey-analytics-to-data-sources-in-platform.html?lang=en) om du vill se en videoöversikt.

## Behörigheter krävs

Om du vill skapa en Customer Journey Analytics-anslutning (CJA) behöver du följande behörigheter i [Adobe Admin Console](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html):

Adobe Experience Platform:
* Datamodellering: Visa scheman, hantera scheman
* Datahantering: Visa datauppsättningar, hantera datauppsättningar
* Dataintag: Hantera källor

Customer Journey Analytics
* Produktadministratörsåtkomst

>[!IMPORTANT]
>
>Du kan kombinera flera [!DNL Experience Platform]-datauppsättningar till en enda anslutning.

## Välj sandlåda och datauppsättningar

1. Gå till [https://analytics.adobe.com](https://analytics.adobe.com).

1. Klicka på fliken **[!UICONTROL Connections]**.

1. Klicka på **[!UICONTROL Create new connection]** överst till höger.

   ![Skapa anslutning](assets/create-connection0.png)

1. Välj en sandlåda i Experience Platform som innehåller den eller de datauppsättningar som du vill skapa en anslutning till.

   Adobe Experience Platform tillhandahåller [sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) som partitionerar en enda plattformsinstans till separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Du kan tänka dig sandlådor som&quot;dataisoleringar&quot; som innehåller datauppsättningar. Sandlådor används för att styra åtkomst till datauppsättningar.  När du har valt sandlådan visas alla datauppsättningar i den sandlådan som du kan hämta från den vänstra listen.

   >[!IMPORTANT]
   >
   >Du kan inte komma åt data över sandlådor, d.v.s. du kan bara kombinera datauppsättningar som finns i samma sandlåda.

1. Markera en eller flera datauppsättningar som du vill hämta till [!UICONTROL Customer Journey Analytics] och klicka på **[!UICONTROL Add]**.

   (Om du har många datauppsättningar att välja bland kan du söka efter de rätta med hjälp av sökfältet **[!UICONTROL Search datasets]** ovanför listan med datauppsättningar.)

   CJA baseras på datauppsättningar från Experience Platform. Även om du kan använda en schemafälttyp som stöds i Platform stöds inte alla fälttyper i CJA. Du kan lägga till datauppsättningar i CJA med andra schemafälttyper än strängar eller numeriska värden, men CJA kan inte visa dessa data. Dessutom är endast strängar tillåtna i uppslagsuppsättningar just nu.
Om du letar efter ett fält att lägga till i en datavy efter att du har lagt till datauppsättningen i en anslutning, är standardtaggen [!UICONTROL Contains data] tillgänglig för alla fält i datauppsättningarna. Den här taggen gör datavyer mer hanterbara eftersom den bara innehåller schemafält som har data i datauppsättningarna.

## Konfigurera datauppsättning

Till höger kan du nu konfigurera de datauppsättningar som du har lagt till.

![Konfigurera datauppsättning](assets/create-connection.png)

1. **[!UICONTROL Dataset type]**: För varje datauppsättning som du har lagt till i den här anslutningen anges datauppsättningstypen  [!UICONTROL Customer Journey Analytics] automatiskt baserat på de data som kommer in.

   Det finns tre olika datamängdstyper: [!UICONTROL Event] data, [!UICONTROL Profile] data och [!UICONTROL Lookup] data.

   | Typ av datauppsättning | Beskrivning | Tidsstämpel | Schema | Person-ID |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsinformation osv.). Detta kan till exempel vara typiska klickströmsdata, med ett kund-ID eller ett cookie-ID och en tidsstämpel. Med händelsedata får du flexibilitet vad gäller vilket ID som används som person-ID. | Är automatiskt inställt på standardtidsstämpelfältet från händelsebaserade scheman i [!UICONTROL Experience Platform]. | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet&quot;Time Series&quot;. Exempel är &quot;XDM Experience Event&quot; eller &quot;XDM Decision Event&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datamängdsschema som definieras i Experience Platform kan ha en egen uppsättning av en eller flera identiteter som är definierade och associerade med ett identitetsnamnutrymme. Alla dessa kan användas som person-ID. Exempel är cookie-ID, Stitched ID, User ID, Tracking Code osv. |
   | [!UICONTROL Lookup] | Dessa data används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. Se [det här användningsexemplet](/help/use-cases/b2b.md) för ett exempel. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet &quot;Record&quot;, förutom klassen &quot;XDM Individual Profile&quot;. | Ej tillämpligt |
   | [!UICONTROL Profile] | Data som tillämpas på besökare, användare eller kunder i [!UICONTROL Event]-data. Du kan till exempel överföra CRM-data om dina kunder. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på klassen &quot;XDM Individual Profile&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i [!DNL Experience Platform] har en egen uppsättning med ett eller flera definierade person-ID, som cookie-ID, Stitched ID, User ID, Tracking Code, osv.<br>![Person ](assets/person-id.png)**IDNote**: Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du verkligen vill sammanfoga datauppsättningar måste du använda samma person-ID. |

1. **[!UICONTROL Dataset ID]**: Detta ID genereras automatiskt.

1. **[!UICONTROL Time stamp]**: Endast för händelsedatamängder anges den här inställningen automatiskt till standardfältet för tidsstämpling från händelsebaserade scheman i  [!UICONTROL Experience Platform].

1. **[!UICONTROL Schema]**: Det här är den  [](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html) schemaläggning som datauppsättningen skapades på i Adobe Experience Platform.

1. **[!UICONTROL Person ID]**: Välj ett person-ID i listrutan med tillgängliga identiteter. Dessa identiteter definierades i datauppsättningsschemat i Experience Platform. Nedan finns information om hur du använder identitetskartan som ett person-ID.

   >[!IMPORTANT]
   >
   >Om det inte finns några person-ID:n att välja mellan, innebär det att ett eller flera person-ID:n inte har definierats i schemat. Visa [den här videon](https://youtu.be/G_ttmGl_LRU) om hur du definierar en identitet i Experience Platform.

1. Klicka på **[!UICONTROL Next]** för att gå till dialogrutan [!UICONTROL Enable Connection].

### Använd identitetskarta som person-ID

Customer Journey Analytics har nu stöd för möjligheten att använda identitetskartan för sitt person-ID. Identitetskarta är en kartdatastruktur som gör att någon kan överföra nyckel -> värdepar. Nycklarna är ID-namnutrymmen och värdet är den struktur som innehåller identitetsvärdet. Identitetskartan finns för varje överförd rad/händelse och fylls i för varje rad i enlighet med detta.

Identitetskartan är tillgänglig för alla datauppsättningar som använder ett schema baserat på klassen [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html). När du väljer en sådan datauppsättning som ska inkluderas i en CJA-anslutning kan du välja att antingen välja ett fält som primärt ID eller identitetskartan:

![](assets/idmap1.png)

Om du väljer Identitetskarta får du ytterligare två konfigurationsalternativ:

| Alternativ | Beskrivning |
|---|---|
| [!UICONTROL Use Primary ID Namespace] | Detta instruerar CJA, per rad, att hitta identiteten i identitetskartan som är markerad med ett primär=true-attribut och använda det som ID för den raden. Detta innebär att det här är den primärnyckel som ska användas i Experience Platform för partitionering. Det är också den primära kandidaten för CJA:s besökar-ID (beroende på hur datauppsättningen konfigureras i en CJA-anslutning). |
| [!UICONTROL Namespace] | (Det här alternativet är bara tillgängligt om du inte använder namnutrymmet för primärt ID.) Identitetsnamnutrymmen är en komponent i [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) som fungerar som indikatorer för det sammanhang som en identitet relateras till. Om du anger ett namnutrymme söker CJA efter den här namnutrymmesnyckeln i varje rads identitetskarta och använder identiteten under namnutrymmet som ID för den raden. Observera att eftersom CJA inte kan göra en fullständig datauppsättningssökning av alla rader för att avgöra vilka namnutrymmen som faktiskt finns, visas alla möjliga namnutrymmen i listrutan. Du måste veta vilka namnutrymmen som anges i data; detta kan inte identifieras automatiskt. |

### Kantärenden för identitetskarta

I den här tabellen visas de två konfigurationsalternativen när det finns kantfall och hur de hanteras:

| Alternativ | Det finns inga ID:n i identitetskartan | Inga ID har markerats som primära | Flera ID:n är markerade som primära | Ett ID är markerat som primärt | Ogiltigt namnutrymme med ett ID markerat som primärt |
|---|---|---|---|---|---|
| **Använd namnutrymme för primärt ID markerat** | Raden tas bort av CJA. | Raden tas bort av CJA eftersom inget primärt ID har angetts. | Alla ID:n som markerats som primära, under alla namnutrymmen, extraheras till en lista. De sorteras sedan alfabetiskt, med den här nya sorteringen används det första namnutrymmet med dess första ID som person-ID. | Det enda ID som är markerat som primärt används som person-ID. | Även om namnutrymmet kan vara ogiltigt (inte finns i AEP) kommer CJA att använda det primära ID:t under namnutrymmet som Person-ID. |
| **Namnområdet Specifik identitetskarta har valts** | Raden tas bort av CJA. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. (Endast ett giltigt namnutrymme kan väljas när anslutningen skapas, så det är inte möjligt att använda ett ogiltigt namnutrymme/ID som person-ID) |

## Aktivera anslutning

![Aktivera anslutning](assets/create-connection2.png)

1. Om du vill aktivera en anslutning definierar du de här inställningarna för hela anslutningen, dvs. alla datauppsättningar i anslutningen:

   | Alternativ | Beskrivning |
   | --- | --- |
   | [!UICONTROL Name Connection] | Ge anslutningen ett beskrivande namn. Anslutningen kan inte sparas utan ett namn. |
   | [!UICONTROL Description] | Lägg till mer information för att skilja den här anslutningen från andra. |
   | [!UICONTROL Datasets] | De datauppsättningar som ingår i den här anslutningen. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Välj det här alternativet om du vill upprätta en pågående anslutning så att alla nya databatchar som läggs till i datauppsättningarna i den här anslutningen automatiskt flödar till [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | När du väljer det här alternativet och sparar anslutningen importeras eller fylls alla befintliga (historiska) data från [!DNL Experience Platform] för alla datauppsättningar i den här anslutningen i bakgrunden. I framtiden kommer även alla befintliga historiska data för nya datauppsättningar som läggs till i den här sparade anslutningen att importeras automatiskt. Se även [Bakåtfyll historiska data](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#backfill-historical-data) nedan.<br>**Observera att den här inställningen inte kan ändras när anslutningen har sparats.** |
   | [!UICONTROL Average number of daily events] | Du måste ange det genomsnittliga antalet händelser per dag som ska importeras (nya data **och** data för bakgrundsfyllning) för alla datauppsättningar i anslutningen. Välj ett alternativ i listrutan. Detta gör att Adobe kan tilldela tillräckligt med utrymme för dessa data.<br>Om du inte känner till det genomsnittliga antalet dagliga händelser som ditt företag kommer att importera kan du göra en enkel SQL-fråga i  [Adobe Experience Platform Query ](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) Services för att ta reda på det.<br>Se &quot;Beräkna det genomsnittliga antalet dagliga händelser&quot; nedan. |

1. Klicka på **[!UICONTROL Save and create data view]**. Mer information finns i [skapa en datavy](/help/data-views/create-dataview.md).

### Bakgrundsfyllningshistorikdata

**[!UICONTROL Import all existing data]** gör att du kan fylla i historiska data baklänges. Tänk på detta:

* Vi har tagit bort begränsningen för bakåtfyllnad (import av historiska data). Tidigare kunde ni fylla upp maximalt 2,5 miljarder rader på egen hand och på annat sätt kräva konstruktionsarbete. Nu kan ni fylla i data på egen hand utan begränsningar.
* Vi prioriterar nya data som läggs till i en datauppsättning i anslutningen, så att dessa nya data har den lägsta latensen.
* Eventuella bakåtfyllnadsdata (historiska) importeras i en långsammare takt. Fördröjningen påverkas av hur mycket historisk information du har, i kombination med **[!UICONTROL Average number of daily events]**-inställningen du valde. Om du till exempel har mer än en miljard rader data per dag, plus tre års historiska data, kan det ta flera veckor att importera dem. Å andra sidan, om du har mindre än en miljon rader per dag och en vecka med historiska data, tar det mindre än en timme.
* Påfyllning gäller för hela anslutningen, inte för varje enskild datauppsättning.
* Med [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/ingest-data-from-adobe-analytics.html) importeras upp till 13 månaders data, oavsett storlek.

### Beräkna det genomsnittliga antalet dagliga händelser

Denna beräkning måste göras för varje datauppsättning i anslutningen.

1. Gå till [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) och skapa en ny fråga.

1. Frågan skulle se ut så här:<br>`Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;`

* I det här exemplet är &quot;analytics_demo_data&quot; namnet på datauppsättningen.
* Utför `Show Tables`-frågan för att visa alla datauppsättningar som finns i AEP.
