---
title: Skapa ett schema för Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 22d3e7b8-4a4d-48a8-a98d-5172a9876286
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1514'
ht-degree: 0%

---

# Skapa och konfigurera en anslutning som ska användas med Customer Journey Analytics {#upgrade-create-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-connection"
>title="Skapa en anslutning i Customer Journey Analytics"
>abstract="Med en anslutning kan ni översätta data från Adobe Experience Platform till ett format som är optimerat för Customer Journey Analytics rapportering. Det är enkelt att skapa en anslutning i Customer Journey Analytics, vilket tar bara några minuter."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/connections/create-connection.md -->

Följande information förklarar hur du skapar och konfigurerar en anslutning samt hur du lägger till Experience Platform-datauppsättningar i den anslutning du skapar. Mer information om hur du skapar och konfigurerar en anslutning finns i [Skapa eller redigera en anslutning](/help/connections/create-connection.md).

## Skapa och konfigurera anslutningen {#create-connection}

1. I Customer Journey Analytics väljer du **[!UICONTROL Connections]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.
1. Välj **[!UICONTROL Create new connection]**.

   ![Namnlösa anslutningsinställningar](assets/create-conn1.png)

1. Konfigurera anslutningsinställningarna.

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Connection name]** | Ange ett unikt namn för anslutningen. |
   | **[!UICONTROL Connection description]** | Beskriv syftet med den här anslutningen. |
   | **[!UICONTROL Sandbox]** | Välj en sandlåda i Experience Platform som innehåller den eller de datauppsättningar som du vill skapa en anslutning till.<p>Adobe Experience Platform tillhandahåller [sandlådor](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) som partitionerar en enda plattformsinstans till separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Du kan tänka dig sandlådor som&quot;dataisoleringar&quot; som innehåller datauppsättningar. Sandlådor används för att styra åtkomst till datauppsättningar.<p>När du har valt sandlådan visas alla datauppsättningar i den sandlådan som du kan hämta från den vänstra listen. |
   | **[!UICONTROL Enable rolling data window]** | Om den här kryssrutan är markerad kan du definiera Customer Journey Analytics datalagring som ett rullande fönster på anslutningsnivå i månader (1 månad, 3 månader, 6 månader och så vidare).<p>Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för rullande datafönster för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar. Om din anslutning innehåller en profil- eller uppslagsdatauppsättning (förutom en eller flera händelsedatamängder), behålls dessa data för samma tidsperiod.<p> Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader.<p>Om du låter standardinställningen (inte markerad) stå över kvarhållningsperioden för data i Adobe Experience Platform. Om ni har 25 månaders data i Experience Platform får Customer Journey Analytics 25 månaders data genom förifyllning. Om du raderade 10 av dessa månader i Platform behåller Customer Journey Analytics de återstående 15 månaderna. |
   | **[!UICONTROL Add datasets]** (se nedan) | Lägg till datauppsättningar om det inte finns några datauppsättningar i datauppsättningslistan. |
   | **[!UICONTROL Dataset name]** | Markera en eller flera datauppsättningar som du vill hämta till Customer Journey Analytics och välj **[!UICONTROL Add]**.<p>(Om du har många datauppsättningar att välja bland kan du söka efter rätt datauppsättningar med sökfältet Sök efter datauppsättningar ovanför listan med datauppsättningar.) |
   | **[!UICONTROL Last updated]** | Endast för händelsedatamängder anges den här inställningen automatiskt till standardfältet för tidsstämpling från händelsebaserade scheman i Experience Platform. &quot;Ej tillämpligt&quot; innebär att den här datauppsättningen inte innehåller några data. |
   | **[!UICONTROL Number of records]** | Det totala antalet poster under den föregående månaden för datauppsättningen i Experience Platform. |
   | **[!UICONTROL Schema]** | Det [schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition) som baserar sig på vilken datauppsättningen skapades i Adobe Experience Platform. |
   | **[!UICONTROL Dataset type]** | För varje datauppsättning som du har lagt till i den här anslutningen anger Customer Journey Analytics automatiskt datauppsättningstypen baserat på de data som kommer in. Det finns tre olika datamängdstyper: Händelsedata, Profildata och Uppslagsdata. Se tabellen nedan för en förklaring av datamängdstyperna. |
   | **[!UICONTROL Granularity]** | Detaljrikedomen för data i datauppsättningen. Gäller endast för sammanfattningsdatauppsättningar. |
   | **[!UICONTROL Data source type]** | Datamängdens datakälltyp. Gäller inte för sammanfattningsdatauppsättningar. |
   | **[!UICONTROL Person ID]** | Välj ett person-ID i listrutan med tillgängliga identiteter. Dessa identiteter definierades i datauppsättningsschemat i Experience Platform. Nedan finns information om hur du använder identitetskartan som ett person-ID.<p>VIKTIGT: Om det inte finns några person-ID att välja mellan, innebär det att ett eller flera person-ID inte har definierats i schemat. Visa [den här videon](https://www.youtube.com/watch?v=G_ttmGl_LRU) om hur du definierar en identitet i Experience Platform. |
   | **[!UICONTROL Key]** | Endast för uppslagsdatauppsättningar (till exempel _id). |
   | **[!UICONTROL Matching Key]** | Endast för uppslagsdatauppsättningar (till exempel _id). |
   | **[!UICONTROL Import new data]** | Inställd på På eller Av. |
   | **[!UICONTROL Backfill data]** | Du kan begära att data i en datauppsättning fylls i på nytt. Du kan till exempel begära att de senaste 7 dagarnas data ska fyllas i igen. Konfigurera datauppsättningen korrekt och testa anslutningen. Om allt ser bra ut kan du enkelt fylla i alla återstående data.<p>Dessutom kan du aktivera import av nya data per datauppsättning. |
   | **[!UICONTROL Backfill status]** | Den här statusen anger om några data för bakgrundsfyllning bearbetas. |

   {style="table-layout:auto"}

## Lägga till och konfigurera datauppsättningar {#add-dataset}

Du kan lägga till en Experience Platform-datauppsättning när du skapar en anslutning.

1. Välj **[!UICONTROL Add datasets]** i dialogrutan Anslutningsinställningar.

1. I steget [!UICONTROL Select datasets] visas en lista med Experience Platform-datauppsättningar.

   ![Välj datauppsättningar](assets/select-datasets.png)

   För varje datauppsättning visas följande i listan:

   | Kolumn | Beskrivning |
   |---|---|
   | Datauppsättning | Datauppsättningens namn. Markera namnet som du vill dirigera till datauppsättningen i Experience Platform. Välj ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) om du vill visa ett popup-fönster med mer information om datauppsättningen. Du kan välja **[!UICONTROL Edit in Platform]** om du vill redigera datauppsättningen direkt i Experience Platform. |
   | Datauppsättningstyp | Datatypen: Händelse, profil, sökning eller sammanfattning. |
   | Antal poster | Det totala antalet poster under den föregående månaden för datauppsättningen i Experience Platform. |
   | Schema | Schemat för datauppsättningen. Markera namnet som du vill dirigera till schemat i Experience Platform. |
   | Senaste batch | Status för den senaste batchen som importerats till Experience Platform. Mer information finns i [Gruppstatus](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/batch/troubleshooting#batch-states). |
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
   | **[!UICONTROL Timestamp]** | Endast för händelse- och sammanfattningsdatauppsättningar anges den här inställningen automatiskt till standardfältet för tidsstämpling från händelsebaserade scheman i Experience Platform. |
   | **[!UICONTROL Key]** | Endast tillgängligt för uppslagsdatauppsättningar. Nyckeln som ska användas för en uppslagsdatauppsättning. |
   | **[!UICONTROL Matching key]** | Endast tillgängligt för uppslagsdatauppsättningar. Den matchande nyckeln som ska användas i en av händelsedatamängderna. Om den här listan är tom har du förmodligen inte lagt till eller konfigurerat någon händelsedatamängd. |
   | **[!UICONTROL Timezone]** | Endast tillgängligt för sammanfattningsdata. Välj lämplig tidszon för tidsseriens sammanfattningsdata. |
   | **[!UICONTROL Data source type]** | Välj en typ av datakälla. <br/>Typer av datakällor omfattar: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>Det här fältet används för att undersöka vilka typer av datakällor som används. |
   | **[!UICONTROL Import new data]** | Aktivera det här alternativet om du vill upprätta en pågående anslutning. Med en pågående anslutning blir nya databatchar som läggs till i datauppsättningarna automatiskt tillgängliga i Workspace. |
   | **[!UICONTROL Dataset backfill]** | Aktivera **[!UICONTROL Backfill all existing data]** för att se till att alla befintliga data är efterfyllda.<br/><br/>Välj **[!UICONTROL Request backfill]** om du vill fylla i historiska data baklänges för en viss period. Du kan definiera upp till 10 backfill-perioder för datauppsättningar.<ol><li>Definiera perioden genom att ange start- och slutdata eller välja datum med ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Välj **[!UICONTROL Queue backfill]** om du vill lägga till en bakgrundsfyllning i listan eller **[!UICONTROL Cancel]** om du vill avbryta.</li></ol>För varje post väljer du ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) om du vill redigera punkten eller ![Ta bort](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) om du vill ta bort posten.<br/><br/>På bakåtfyllningar:<ul><li>Du kan fylla i varje datauppsättning separat.</li><li>Du prioriterar nya data som läggs till i en datauppsättning i anslutningen, så att dessa nya data har den lägsta fördröjningen.</li><li>Eventuella bakåtfyllnadsdata (historiska) importeras i en långsammare takt. Mängden historiska data påverkar latensen.</li><li>Analysens källanslutning importerar upp till 13 månaders data (oavsett storlek) för produktionssandlådor. Bakåtfyllnaden i icke-produktionssandlådor är begränsad till tre månader.</li></ul> |
   | **[!UICONTROL Transform dataset]** | För specifika B2B-sökdatauppsättningar kan du aktivera omvandling av en datauppsättning för korrekta B2B-personbaserade rapportscenarier. |
   | **[!UICONTROL Backfill status]** | Möjliga statusindikatorer är:<ul><li>Lyckades</li><li>X-bearbetning av bakgrundsfyllning(ar)</li><li>Av</li></ul> |
   | **[!UICONTROL Dataset ID]** | Detta ID genereras automatiskt. |
   | **[!UICONTROL Description]** | Beskrivningen som den här datauppsättningen fick när den skapades. |
   | **[!UICONTROL Dataset size]** | Datauppsättningens storlek. |
   | **[!UICONTROL Schema]** | Det schema som datamängden skapades utifrån i Adobe Experience Platform. |
   | **[!UICONTROL Dataset]** | Datauppsättningens namn. |
   | **[!UICONTROL Preview: *datauppsättningsnamn *]** | Förhandsgranskar datauppsättningen med kolumnerna date, my ID och Identifier. |
   | **[!UICONTROL Remove]** | Du kan ta bort eller ta bort datauppsättningen och ändra person-ID utan att ta bort hela anslutningen. Att ta bort eller ta bort minskar kostnaderna för datainmatning och den krångliga processen att återskapa hela anslutningen och tillhörande datavyer. |

   {style="table-layout:auto"}

{{upgrade-final-step}}
