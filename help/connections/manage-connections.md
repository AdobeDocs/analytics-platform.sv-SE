---
title: Hantera anslutningar i Customer Journey Analytics
description: Beskriver hur du hanterar anslutningar till datauppsättningar i Experience Platform i Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: bafe2bfdd62065b58ebe5ea6f54a892e0177bbce
workflow-type: tm+mt
source-wordcount: '3049'
ht-degree: 0%

---

# Hantera anslutningar

När du har [skapat eller redigerat en eller flera anslutningar](/help/connections/create-connection.md) kan du hantera dem i **[!UICONTROL Connections]**. Med anslutningar kan du:

* Visa alla dina anslutningar i korthet, inklusive ägaren, sandlådan och när anslutningarna skapades och ändrades.
* Redigera en anslutning.
* Ta bort en anslutning.
* Skapa en datavy från en anslutning.
* Visa alla datauppsättningar i en anslutning.
* Kontrollera status för anslutningsens datauppsättningar och status för överföringsprocessen. Till exempel när är dina data tillgängliga så att du kan börja med rapporter och analyser i Analysis Workspace.
* Identifiera eventuella dataavvikelser på grund av felaktig konfiguration. Saknar du några rader? Om så är fallet, vilka rader saknas och varför? Har du felkonfigurerat anslutningar och orsakat saknade data i Customer Journey Analytics?
* Få insikter om hur inkapslade och rapportbara rader används i alla era anslutningar.

[!UICONTROL Connections] har två gränssnitt: [[!UICONTROL List]](#list) och [[!UICONTROL Usage]](#usage).


## Lista

Gränssnittet [!UICONTROL List] är standardgränssnittet för anslutningar. Om det inte är markerat väljer du fliken **[!UICONTROL List]** för att komma åt gränssnittet.

![listvy](assets/list-view.png)

Gränssnittet [!UICONTROL List] visar en tabell med alla tillgängliga anslutningar. Du kan snabbt söka efter en anslutning med sökrutan ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

Följande kolumner eller ikoner är tillgängliga i tabellen.

| Kolumn eller ikon | Beskrivning |
| --- | --- |
| [!UICONTROL Name] | Anslutningens egna namn. Om du vill visa information om anslutningen markerar du namnet på den hyperlänkade anslutningen. Se [Anslutningsinformation](#connection-details). |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Om du vill visa information om [!UICONTROL Datasets included], [!UICONTROL Sandbox], [!UICONTROL Owner] och mer väljer du ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) bredvid anslutningsnamnet.<p>Ett popup-fönster visar information. <p><img src="./assets/conn-info.png" alt="Visa anslutningsinformation" width="400"/> |
| ![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Om du vill [skapa en datavy](#create-a-data-view) för anslutningen väljer du ![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Den här ikonen visas bara när ingen datavy redan är kopplad till anslutningen. |
| ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) för att: <p>![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Redigera](#edit-a-connection) en anslutning.<p>![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Ta bort](#delete-a-connection) en anslutning.<p>![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Skapa ny datavy](#create-a-data-view). Om du vill skapa ytterligare datavyer för anslutningen. |
| [!UICONTROL Datasets] | En eller flera länkar till de datauppsättningar som är en del av anslutningen. Du kan välja datauppsättningens hyperlänk för att visa datauppsättningen i anslutningen. Om fler datauppsättningar ingår i den valda anslutningen väljer du **[!UICONTROL +*x *more]**för att visa en **[!UICONTROL Datasets included]**-panel. I den här panelen visas länkar till alla datauppsättningar och ett alternativ för att söka efter en specifik datauppsättning som är en del av anslutningen.<p><img src="./assets/datasets-included.png" alt="Inkluderade datatillgångar" width="400"/><p>Om du väljer ett datauppsättningsnamn öppnas datauppsättningen i användargränssnittet för Experience Platform på en ny flik. |
| [!UICONTROL Sandbox] | Sandlådan [Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) som den här anslutningen ritar sina datauppsättningar från. Den här sandlådan valdes när du först skapade anslutningen. Den kan inte ändras. |
| [!UICONTROL Owner] | Den person som skapade anslutningen. |
| [!UICONTROL Import new data] | Status för import av nya data för datauppsättningar: <p>![Status grön](assets/status-green.svg))    **[!UICONTROL _x _On]**för datauppsättningar som konfigurerats för att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för datauppsättningar som inte har konfigurerats för import av nya data. |
| [!UICONTROL Date created] | Tidsstämpeln när anslutningen skapades. |
| [!UICONTROL Last modified] | Tidsstämpeln när anslutningen senast uppdaterades. |
| [!UICONTROL Backfill data] | Status för data som fylls i bakåt över datauppsättningar.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills across datasets,<p>![Statusorange](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**för antal bearbetning av efterfyllningar i datauppsättningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antalet slutförda efterfyllningar för datauppsättningar, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om det inte finns några bakåtfyllningar definierade för datauppsättningarna i anslutningen. |

Om du vill konfigurera vilka kolumner som ska visas väljer du ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), som visar dialogrutan **Anpassa tabell** där du kan aktivera och inaktivera kolumner i tabellen.

### Redigera en anslutning

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet
1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** på snabbmenyn.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** i det blå fältet.

När du redigerar en anslutning kan du:

* Starta och sluta importera nya data.
* Byt namn på en anslutning.
* Uppdatera datauppsättningen/datauppsättningarna.
* Ta bort datauppsättningar från anslutningarna.

Mer information finns i [Skapa eller redigera en anslutning](create-connection.md).


### Ta bort en anslutning {#connections-delete}

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
1. Välj ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]**.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** i det blå fältet.

När du tar bort en anslutning visar en **[!UICONTROL Delete connection]**-panel vilka datavyer som tas bort och vilka arbetsyteprojekt som påverkas.

![Ta bort anslutning](assets/delete-connection.png)

Välj **[!UICONTROL Continue]** om du vill ta bort anslutningen.

Mer information om hur du tar bort en anslutning finns i [Ta bort konsekvenser](/help/technotes/deletion.md).


### Skapa en datavy för en anslutning

* Om ingen datavy är associerad med anslutningen:

   1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) bredvid anslutningsnamnet.

* Om en eller flera datavyer redan har skapats för anslutningen:

   1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
   1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]**.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** i det blå knappfältet.

Mer information finns i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).

### Anslutningsinformation {#connection-detail}

Om du vill gå till informationen för en anslutning väljer du ett anslutningsnamn i anslutningstabellen.

![Alla datauppsättningsfönster med widgetar och inställningar](assets/conn-details.png)

Gränssnittet Anslutningsinformation ger en detaljerad vy över anslutningsstatus. Ni kan:

* Kontrollera status för anslutningsens datauppsättningar och för överföringsprocessen.
* Identifiera konfigurationsproblem som kan orsaka överhoppade eller borttagna poster.
* Se när data är tillgängliga för rapportering.

| Användargränssnitt | Beskrivning |
| --- | --- |
| ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Edit Connection] | Om du vill redigera information om en anslutning väljer du ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]**. Mer information finns i [Skapa eller redigera en anslutning](create-connection.md). |
| Datauppsättningsväljare | Gör att du kan välja en eller alla datauppsättningar i anslutningen. Du kan inte markera datauppsättningar i flera steg. Standardvärdet är [!UICONTROL All datasets]. |
| Datumintervallväljare | Redigera startdatum, slutdatum eller välj ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) för att öppna dataområdesväljaren. Välj ett datumintervall i datumintervallväljaren genom att använda någon av de fördefinierade perioderna (till exempel **[!UICONTROL Last 6 months]**) eller använd kalendern för att välja start- och slutdatum. Välj **[!UICONTROL Apply]** om du vill använda det nya dataintervallet. |
| [!UICONTROL Records of event data available] | Det totala antalet händelsedatamängdsrader som är tillgängliga för rapportering, **för hela anslutningen**. Antalet är oberoende av eventuella kalenderinställningar. Antalet ändras om du väljer en datauppsättning från datauppsättningsväljaren eller genom att markera en datauppsättning i tabellen. När data har lagts till finns det en fördröjning på 1-2 timmar för att få data att visas vid rapportering. |
| [!UICONTROL Metrics] | Sammanfatta de poster för händelse, sökning, profil och sammanfattning av datauppsättningar som har lagts till, hoppats över och tagits bort samt antalet grupper som har lagts till. Dessa mått baseras på **den datamängd och det datumintervall som du har valt**.<p>Välj **[!UICONTROL Check detail]** om du vill visa popup-fönstret **[!UICONTROL Check skipped detail]**. I popup-fönstret visas antalet poster som hoppats över och orsaken till alla händelsedatamängder eller valda datauppsättningar.<p><img src="./assets/skipped-records.png" width="500"/><p>Välj popup-fönstret ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) med mer information. Av vissa orsaker som hoppats över, som [!UICONTROL Empty visitor ID], visar popup-fönstret exempel-PSQL för EQS (Experience Platform för frågetjänst) som du kan använda i [ frågetjänst ](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) för att fråga efter de överhoppade posterna i datauppsättningen. Välj ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copy sample PSQL for EQS]** om du vill kopiera SQL:en. |
| [!UICONTROL Records added] | Anger hur många rader som har lagts till under den valda tidsperioden, **för den datamängd och det datumintervall som du har valt**. Uppdaterades var 10:e minut. |
| [!UICONTROL Records skipped] | Anger hur många rader som hoppades över under den valda tidsperioden, **för den datamängd och det datumintervall som du har valt**. Orsaker till att hoppa över poster är: saknade tidsstämplar, person-ID saknas eller är ogiltigt osv. Uppdaterades var 10:e minut. <p>Ogiltiga person-ID:n (till exempel `undefined` eller `00000000`, eller en kombination av siffror och bokstäver i en [!UICONTROL Person ID] som visas i en händelse mer än 1 miljon gånger i en viss månad) är ID:n som inte kan tilldelas någon specifik användare eller person. Dessa rader kan inte infogas i systemet och resulterar i felbenägen inmatning och rapportering. Du kan åtgärda ogiltiga person-ID:n på tre sätt:<ul><li>Använd [Stitching](/help/stitching/overview.md) för att fylla i användar-ID:n som inte definierats eller är helt noll med giltiga användar-ID:n.</li><li>Töm användar-ID:t som sedan tas bort vid förtäring (helst med ett ogiltigt eller helt nollfritt användar-ID).</li><li>Korrigera ogiltiga användar-ID:n i systemet innan data hämtas.</li></ul> |
| [!UICONTROL Records] har tagits bort | Anger hur många rader som har tagits bort under den valda tidsperioden, **för den datamängd och det datumintervall som du har markerat**. Någon kanske har tagit bort en datauppsättning i [!DNL Experience Platform]. Uppdaterades var 10:e minut.<p>I vissa scenarier kan det här värdet även innehålla ersatta poster, som sammanfogning eller vissa uppdateringar av uppslagsdatauppsättningar. Titta på det här exemplet:</p><ul><li>Du överför en post till en XDM-datauppsättning för enskild profil, som Customer Journey Analytics har konfigurerats att importera som profilsökningsdata. I anslutningsinformationen skulle den här datauppsättningen visa 1 post som lagts till.</li><li>Du överför en kopia av den ursprungliga posten till samma AEP-datauppsättning, som nu innehåller två poster. Customer Journey Analytics importerar den extra posten från profilsökningsdatauppsättningen. Eftersom Customer Journey Analytics redan har infogat en profilpost i anslutningen för det person-ID:t, tas dess tidigare version bort och nya profildata läggs till. I anslutningsinformationen representerar den här åtgärden 1 post som lagts till och 1 post som tagits bort, eftersom Customer Journey Analytics endast behåller den senaste profilsökningsinformationen för alla inkapslade person-ID:n.</li><li>Totalt innehåller AEP-datauppsättningen två poster som råkar vara identiska. I anslutningsinformationen för Customer Journey Analytics visas status för inkapslade data separat: 2 poster har lagts till och 1 post har tagits bort för profildatauppsättningen. </li></ul> |
| ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Sök efter datauppsättningsnamn eller ID_ | Sökfält för datauppsättning. Du kan söka i datamängdstabellen efter datauppsättningsnamn eller [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets table] | De datauppsättningar som ingår i anslutningen. |
| [!UICONTROL Datasets] | Namnet på datauppsättningen som är en del av anslutningen. Du kan markera hyperlänken för att öppna datauppsättningen i användargränssnittet för Experience Platform på en ny flik. Du kan markera raden eller kryssrutan om du bara vill visa information för den markerade datauppsättningen. |
| [!UICONTROL Dataset ID] | Automatiskt genererad av Experience Platform. |
| [!UICONTROL Records added] | Antalet datauppsättningsposter (rader) som lagts till i en anslutning under det valda tidsintervallet. |
| [!UICONTROL Records skipped] | Antalet datauppsättningsposter (rader) som hoppats över under dataöverföring för en anslutning under det valda tidsintervallet. |
| [!UICONTROL Records deleted] | Antalet datauppsättningsposter (rader) som tagits bort från en anslutning under det valda tidsintervallet. |
| [!UICONTROL Batches added] | Antalet datauppsättningsbatchar har lagts till i en anslutning. |
| [!UICONTROL Last added] | Tidsstämpeln för den senaste batchen från datauppsättningen som har lagts till i en anslutning. |
| [!UICONTROL Data source type] | Datamängdens källtyp. Du definierar källtypen när du skapar en anslutning. |
| [!UICONTROL Dataset type] | Datamängdstypen för den här datauppsättningen. Typen kan vara [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] eller [!UICONTROL Summary]. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| Schema | Det Experience Platform-schema som datauppsättningen baseras på. |
| [!UICONTROL Import new data] | Status för import av nya data för datauppsättningen: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**om datauppsättningen är konfigurerad att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** om datauppsättningen är konfigurerad att inte importera ny dataimport. |
| [!UICONTROL Transform data] | Transformeringsstatus för tillämpliga B2B-sökdatauppsättningar. Mer information finns i [Omforma datauppsättningar för B2B-sökningar](transform-datasets-b2b-lookups.md).<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**för tillämpliga datauppsättningar aktiverade för omvandling, <p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för tillämpliga datamängder som inte har aktiverats för omformning, och<p>**[!UICONTROL N/A]** för alla andra datauppsättningar, inte tillämpligt för transformering. |
| [!UICONTROL Backfill data] | Status för data för bakgrundsfyllning för datauppsättningen.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**för antal efterfyllningar som bearbetas,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antal slutförda backfiller, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om bakåtfyllningar inte har konfigurerats. |
| [!UICONTROL Import new data] | Status för import av nya data för datauppsättningen: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**om datauppsättningen är konfigurerad att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** om datauppsättningen är konfigurerad att inte importera nya data. |
| [!UICONTROL Backfill data] | Status för data för bakgrundsfyllning för datauppsättningen.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**för antal efterfyllningar som bearbetas,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antal slutförda backfiller, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om inga bakåtfyllningar är konfigurerade. |

>[!IMPORTANT]
>
>Data som har importerats före den 13 augusti 2021 visas inte i gränssnittet [!UICONTROL Connections].

#### Anslutningspanelen

När ingen datauppsättning har valts i datamängdstabellen visas anslutningsalternativ och detaljer på en panel till höger i anslutningsgränssnittet.

| Alternativ | Beskrivning |
| --- | --- |
| ![Uppdatera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Refresh] | Om du vill uppdatera anslutningen och tillåta att nyligen tillagda poster återspeglas väljer du ![Uppdatera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]**. |
| ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** | [Ta bort](#delete-a-connection) den här anslutningen. |
| ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** | [Skapa en datavy](#create-a-data-view) utifrån den här anslutningen. Mer information finns i [Datavyer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views). |
| [!UICONTROL Connection name] | Anslutningens egna namn. |
| [!UICONTROL Connection description] | En mer detaljerad beskrivning som beskriver syftet med anslutningen. |
| [!UICONTROL Sandbox] | Sandlådan [Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) som den här anslutningen ritar sina datauppsättningar från. Den här sandlådan valdes när du först skapade anslutningen. Den kan inte ändras. |
| [!UICONTROL Connection ID] | Detta ID genereras i Experience Platform. Du kan använda ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) för att kopiera ID:t. |
| [!UICONTROL Data views using connection] | Visar alla datavyer som använder den här anslutningen. |
| [!UICONTROL Import new data] | Status för import av nya data för datauppsättningar: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**för hur många datauppsättningar som har konfigurerats för att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för hur många datauppsättningar som ny dataimport är inaktiverad. |
| [!UICONTROL Backfill data] | Status för data för bakgrundsfyllning för datauppsättningar.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills across datasets,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**för antal bearbetning av efterfyllningar i datauppsättningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antalet slutförda efterfyllningar för datauppsättningar, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om det inte finns några bakåtfyllningar definierade för datauppsättningarna i anslutningen. |
| Omforma data | Transformeringsstatus för tillämpliga B2B-sökdatauppsättningar. Mer information finns i [Omforma datauppsättningar för B2B-sökningar](transform-datasets-b2b-lookups.md).<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**för antalet datauppsättningar som har aktiverats för omformning. |
| [!UICONTROL Created by] | Namnet på den person som skapade anslutningen. |
| [!UICONTROL Last modified] | Tidsstämpeln för den senaste ändringen av anslutningen. |
| [!UICONTROL Last modified by] | Den person som senast ändrade anslutningen. |

#### Panelen Datauppsättning

När en datauppsättning väljs i datamängdstabellen visas information om den valda datauppsättningen på en panel till höger om anslutningsgränssnittet.

| Information | Beskrivning |
| --- | --- |
| [!UICONTROL Person ID] | En identitet som definierades i datauppsättningsschemat i Experience Platform. Den här identiteten är det person-ID som du valde när anslutningen skapades. Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du vill sammanfoga datauppsättningar måste du använda samma person-ID för alla datauppsättningar. |
| [!UICONTROL Key] | Nyckeln som du har angett för en uppslagsdatauppsättning. |
| [!UICONTROL Matching Key] | Den matchande nyckel som du har angett för en uppslagsdatauppsättning. |
| [!UICONTROL Timestamp] | Tidsstämpeln som har definierats för en händelsedatamängd. |
| [!UICONTROL Records available] | Det totala antalet rader som har kapslats in för den här datauppsättningen, för den angivna tidsperioden som valts genom kalendern. Det finns ingen fördröjning när det gäller att få fram data som ska visas i rapporter när de har lagts till. När du skapar en helt ny anslutning visas [latens](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq). |
| [!UICONTROL Records added] | Hur många rader som lades till under den valda tidsperioden. |
| [!UICONTROL Records deleted] | Hur många poster som togs bort under den valda tidsperioden. |
| [!UICONTROL Batches added] | Hur många datagrupper som har lagts till i den här datauppsättningen. |
| [!UICONTROL Records skipped] | Hur många rader hoppades över under intag under den valda tidsperioden.<p>Orsaker till att hoppa över poster är bland annat: Tidsstämplar saknas, person-ID saknas eller är ogiltigt osv. Uppdaterades var 10:e minut.<p>Ogiltiga person-ID:n (till exempel `undefined` eller `00000000`, eller en kombination av siffror och bokstäver i en [!UICONTROL Person ID] som visas i en händelse mer än 1 miljon gånger i en viss månad) är ID:n som inte kan tilldelas någon specifik användare eller person. Dessa rader kan inte infogas i systemet och resulterar i felbenägen inmatning och rapportering. Du kan åtgärda ogiltiga person-ID:n på tre sätt:<ul><li>Använd [Stitching](/help/stitching/overview.md) för att fylla i användar-ID:n som inte definierats eller är helt noll med giltiga användar-ID:n.</li><li>Ta bort användar-ID:t, som sedan hoppas över vid förtäring (helst inte med ett ogiltigt eller helt nollfritt användar-ID).</li><li>Korrigera ogiltiga användar-ID:n i systemet innan data hämtas.</li></ul> |
| [!UICONTROL Last added] | När den sista batchen lades till. |
| [!UICONTROL Import new data] | Status för import av nya data för datauppsättningen: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**om datauppsättningen är konfigurerad att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** om datauppsättningen är konfigurerad att inte importera nya data. |
| [!UICONTROL Backfill data] | Status för data för bakgrundsfyllning för datauppsättningen.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**för antal efterfyllningar som bearbetas,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antal slutförda backfiller, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om inga bakåtfyllningar är konfigurerade.<p>Om du vill visa en dialogruta med en översikt över de tidigare efterfyllningarna för datauppsättningen väljer du <img src="./assets/pastbackfill.svg" alt="Tidigare bakåtfyllningar" width="15"/> **[!UICONTROL Past backfills]**. |
| [!UICONTROL Data source type] | Datakälltyp som definieras när datauppsättningen läggs till i anslutningen. |
| [!UICONTROL Dataset type] | Antingen [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] eller [!UICONTROL Summary]. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| [!UICONTROL Schema] | Det Experience Platform-schema som den här datauppsättningen baseras på. |
| [!UICONTROL Dataset ID] | Detta datauppsättnings-ID genereras i Experience Platform. |


## Användning

Gränssnittet [!UICONTROL Usage] visar hur inkapslade och rapportbara rader används i alla anslutningar. Med det här gränssnittet kan du avgöra om din användning i Customer Journey Analytics överensstämmer med det som avtalats. Förutom övervakningsfunktioner kan du använda användargränssnittet för att planera förnyelsen av din Customer Journey Analytics-licens.

Du kan välja ett tidsintervall (mellan de senaste sex månaderna, året till datum eller de senaste två åren) och ett intervall (mellan månads- eller kvartalsvis) för att övervaka Customer Journey Analytics användning. Gränssnittet är uppdelat i två delar:

* Inmatade rader: totalt antal rader som importerats/skickats från händelsedatamängder över alla Customer Journey Analytics-anslutningar, inklusive poster som hoppats över vid förtäring
* Rapporteringsbara rader: totalt antal rader som kan rapporteras och som innehåller alla händelsedata för alla Customer Journey Analytics-anslutningar

![användningsvy](assets/usage-view.png)

Välj fliken **[!UICONTROL Usage]** för att komma åt gränssnittet.

### Rapport om användning

1. Välj en **[!UICONTROL Time range]**. Du kan välja mellan **[!UICONTROL Last 6 months]**, **[!UICONTROL Year to date]** eller **[!UICONTROL Last 2 Years]**.
1. Välj en **[!UICONTROL Interval]**. Du kan välja mellan **[!UICONTROL Monthly]** eller **[!UICONTROL Quarterly]**.

För [!UICONTROL Ingested rows]:

* På en panel visas det totala antalet inkapslade rader som innehåller alla händelsedata för alla anslutningar som uppdateras varannan dag i månaden. I panelen:
   * I en ruta visas antalet kapslade rader för den senaste månaden och ändringen i % (anges av ▼) från föregående månad.
   * ett linjediagram visar ◼︎ [!UICONTROL Monthly ingested rows].<br/>Om du vill visa ett popup-fönster som visar antalet kapslade rader per månad för en månad håller du pekaren över en datapunkt i linjediagrammet.


För [!UICONTROL Reportable rows]:

* På en panel visas totalt antal rader som kan rapporteras och som innehåller alla händelsedata för alla anslutningar som uppdateras varannan dag i månaden. I panelen:
   * en ruta visar det sammanlagda antalet rader som kan rapporteras.
   * I en ruta visas det totala antalet rader som ska rapporteras för den senaste månaden och ändringen i % (anges av ▼ eller liknande) från den föregående månaden.
   * ett linjediagram visar ◼︎ [!UICONTROL Monthly reportable rows].<br/>Om du vill visa ett popup-fönster som visar antalet kumulativa rapportbara rader för en viss månad håller du pekaren över en datapunkt i linjediagrammet.
   * ett linjediagram visar ◼︎ [!UICONTROL Cumulative reportable rows].<br/>Om du vill visa ett popup-fönster som visar antalet månatliga rapportbara rader för en månad, håller du pekaren över en datapunkt i linjediagrammet.


>[!MORELIKETHIS]
>
>[Visa, felsök och ändra anslutningsinställningar](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja) - självstudiekurs.
