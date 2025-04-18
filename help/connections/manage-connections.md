---
title: Hantera anslutningar i Customer Journey Analytics
description: Beskriver hur du hanterar anslutningar till Experience Platform-datauppsättningar i Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '4052'
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
| ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) för att: <p>![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Redigera](#edit-a-connection) en anslutning.<p>![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Ta bort](#delete-a-connection) en anslutning.<p>![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Skapa ny datavy](#create-a-data-view). Om du vill skapa ytterligare datavyer för anslutningen.<p>![Anslutningskarta för GraphPathing](/help/assets/icons/GraphPathing.svg). Om du vill visa en anslutningskarta för anslutningen. |
| **[!UICONTROL Datasets]** | En eller flera länkar till de datauppsättningar som är en del av anslutningen. Du kan välja datauppsättningens hyperlänk för att visa datauppsättningen i anslutningen. Om fler datauppsättningar ingår i den valda anslutningen väljer du **[!UICONTROL +*x *more]**för att visa en **[!UICONTROL Datasets included]**-panel. I den här panelen visas länkar till alla datauppsättningar och ett alternativ för att söka efter en specifik datauppsättning som är en del av anslutningen.<p><img src="./assets/datasets-included.png" alt="Inkluderade datatillgångar" width="400"/><p>Om du väljer ett datauppsättningsnamn öppnas datauppsättningen i Experience Platform-gränssnittet på en ny flik. |
| **[!UICONTROL Sandbox]** | [Experience Platform-sandlådan](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) som den här anslutningen ritar sina datauppsättningar från. Den här sandlådan valdes när du först skapade anslutningen. Den kan inte ändras. |
| **[!UICONTROL Owner]** | Den person som skapade anslutningen. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningar: <p>![Status grön](assets/status-green.svg)    **[!UICONTROL _x _On]**för datauppsättningar som konfigurerats för att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för datauppsättningar som inte har konfigurerats för import av nya data. |
| **[!UICONTROL Date created]** | Tidsstämpeln när anslutningen skapades. |
| **[!UICONTROL Last modified]** | Tidsstämpeln när anslutningen senast uppdaterades. |
| **[!UICONTROL Backfill data]** | Status för data som fylls i bakåt över datauppsättningar.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills across datasets,<p>![Statusorange](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**för antal bearbetning av efterfyllningar i datauppsättningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antalet slutförda efterfyllningar för datauppsättningar, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om det inte finns några bakåtfyllningar definierade för datauppsättningarna i anslutningen. |

Om du vill konfigurera vilka kolumner som ska visas väljer du ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), som visar dialogrutan **Anpassa tabell** där du kan aktivera och inaktivera kolumner i tabellen.

### Redigera en anslutning

Så här redigerar du en anslutning:

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

Så här tar du bort en anslutning:

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

Skapa en ny datavy för en anslutning

* Om ingen datavy är associerad med anslutningen:

   1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) bredvid anslutningsnamnet.

* Om en eller flera datavyer redan har skapats för anslutningen:

   1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
   1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]**.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** i det blå knappfältet.

Mer information finns i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).


### Mappa en anslutning

Så här visar du en [anslutningskarta](/help/connections/create-connection.md#connection-map) som detaljerar relationerna mellan de datauppsättningar som ingår i en anslutning:

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
1. Välj ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Connection map]**.

### Anslutningsinformation {#connection-detail}

Om du vill gå till informationen för en anslutning väljer du ett anslutningsnamn i anslutningstabellen.

![Alla datauppsättningsfönster med widgetar och inställningar](assets/conn-details.png)

Gränssnittet Anslutningsinformation ger en detaljerad vy över anslutningsstatus. Ni kan:

* Kontrollera status för anslutningsens datauppsättningar och för överföringsprocessen.
* Identifiera konfigurationsproblem som kan orsaka överhoppade eller borttagna poster.
* Se när data är tillgängliga för rapportering.

| Användargränssnitt | Beskrivning |
| --- | --- |
| ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]** | Om du vill redigera information om en anslutning väljer du ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]**. Mer information finns i [Skapa eller redigera en anslutning](create-connection.md). |
| **[!UICONTROL *Datauppsättningsväljare *]** | Gör att du kan välja en eller alla datauppsättningar i anslutningen. Du kan inte markera datauppsättningar i flera steg. Standardvärdet är **[!UICONTROL All datasets]**. |
| **[!UICONTROL *Datumintervallväljare *]** | Redigera startdatum, slutdatum eller välj ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) för att öppna datumintervallväljaren. Välj ett datumintervall i datumintervallväljaren genom att använda någon av de fördefinierade perioderna (till exempel **[!UICONTROL Last 6 months]**) eller använd kalendern för att välja start- och slutdatum. Välj **[!UICONTROL Apply]** om du vill använda det nya datumintervallet. |
| **[!UICONTROL Records of event data available]** | Det totala antalet händelsedatamängdsrader som är tillgängliga för rapportering, **för hela anslutningen**. Antalet är oberoende av eventuella kalenderinställningar. Antalet ändras om du väljer en datauppsättning från datauppsättningsväljaren eller genom att markera en datauppsättning i tabellen. När data har lagts till finns det en fördröjning på 1-2 timmar för att få data att visas vid rapportering. |
| [!UICONTROL **[!UICONTROL Metrics]**] | Sammanfatta de poster för händelse, sökning, profil och sammanfattning av datauppsättningar som har lagts till, hoppats över och tagits bort samt antalet grupper som har lagts till. Dessa mått baseras på **den datamängd och det datumintervall som du har valt**.<p>Välj **[!UICONTROL Check detail]** om du vill visa popup-fönstret **[!UICONTROL Check skipped detail]**. I popup-fönstret visas antalet poster som hoppats över och orsaken till alla händelsedatamängder eller valda datauppsättningar.<p><img src="./assets/skipped-records.png" width="500"/><p>Välj popup-fönstret ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) med mer information. Av vissa orsaker som hoppats över, som [!UICONTROL Empty visitor ID], visar popup-fönstret exempel-PSQL för EQS (Experience Platform för frågetjänst) som du kan använda i [ frågetjänst ](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) för att fråga efter de överhoppade posterna i datauppsättningen. Välj ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copy sample PSQL for EQS]** om du vill kopiera SQL:en. |
| **[!UICONTROL Records added]** | Anger hur många rader som har lagts till under den valda tidsperioden, **för den datamängd och det datumintervall som du har valt**. Uppdaterades var 10:e minut. |
| **[!UICONTROL Records skipped]** | Anger hur många rader som hoppades över under den valda tidsperioden, **för den datamängd och det datumintervall som du har valt**. Orsaker till att poster hoppas över är: saknade tidsstämplar, saknade eller ogiltiga eller konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} osv. Uppdaterades var 10:e minut. <p>Ogiltiga ID:n (till exempel `undefined` eller `00000000`, eller en kombination av siffror och bokstäver i en [!UICONTROL Person ID] som förekommer i en händelse mer än 1 miljon gånger i en viss månad) är ID:n som inte kan tilldelas någon specifik användare eller person. Dessa rader kan inte infogas i systemet och resulterar i felbenägen inmatning och rapportering. Du kan åtgärda ogiltiga person-ID:n eller konto-ID:n [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} genom att välja mellan tre alternativ:<ul><li>Använd [Stitching](/help/stitching/overview.md) för att fylla i användar-ID:n som inte definierats eller är helt noll med giltiga användar-ID:n.</li><li>Töm användar-ID:t som sedan tas bort vid förtäring (helst med ett ogiltigt eller helt nollfritt användar-ID).</li><li>Korrigera ogiltiga användar-ID:n i systemet innan data hämtas.</li></ul> |
| **[!UICONTROL Records deleted]** | Anger hur många rader som har tagits bort under den valda tidsperioden, **för den datamängd och det datumintervall som du har markerat**. Någon kanske har tagit bort en datauppsättning i [!DNL Experience Platform]. Uppdaterades var 10:e minut.<p>I vissa scenarier kan det här värdet även innehålla ersatta poster, som sammanfogning eller vissa uppdateringar av uppslagsdatauppsättningar. Titta på det här exemplet:</p><ul><li>Du överför en post till en XDM-datauppsättning för enskild profil, som Customer Journey Analytics har konfigurerats att importera som profilsökningsdata. I anslutningsinformationen skulle den här datauppsättningen visa 1 post som lagts till.</li><li>Du överför en kopia av den ursprungliga posten till samma AEP-datauppsättning, som nu innehåller två poster. Customer Journey Analytics importerar den extra posten från profilen eller kontot [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} i uppslagsdatauppsättningen. Eftersom en profil- eller kontopost redan är inkapslad i anslutningen för det person-ID:t eller konto-ID:t [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} tar Customer Journey Analytics bort den tidigare versionen och lägger till nya profildata. I anslutningsinformationen representerar den här åtgärden 1 post som lagts till och 1 post har tagits bort, eftersom Customer Journey Analytics bara behåller de senaste profilsökningsdata för inkapslade person-ID:n eller konto-ID:n [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}.</li><li>Sammanlagt innehåller AEP datauppsättning två poster som råkar vara identiska. Customer Journey Analytics anslutningsinformation visar status för inkapslade data separat: 2 poster har lagts till och 1 post har tagits bort för profildatauppsättningen. </li></ul> |
| ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Sökfält för datauppsättning. Du kan söka i datamängdstabellen efter datauppsättningsnamn eller [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets table] | Visar de datauppsättningar som ingår i anslutningen. Se tabellen nedan för ytterligare förklaring. |

I datamängdstabellen visas följande kolumner:

| Kolumn | Beskrivning |
| --- | --- |
| **[!UICONTROL Datasets]** | Namnet på datauppsättningen som är en del av anslutningen. Du kan välja hyperlänken för att öppna datauppsättningen i Experience Platform-gränssnittet på en ny flik. Du kan markera raden eller kryssrutan om du bara vill visa information för den markerade datauppsättningen. |
| **[!UICONTROL Dataset ID]** | Automatiskt genererad av Experience Platform. |
| **[!UICONTROL Records added]** | Antalet datauppsättningsposter (rader) som lagts till i en anslutning under det valda tidsintervallet. |
| **[!UICONTROL Records skipped]** | Antalet datauppsättningsposter (rader) som hoppats över under dataöverföring för en anslutning under det valda tidsintervallet. |
| **[!UICONTROL Records deleted]** | Antalet datauppsättningsposter (rader) som tagits bort från en anslutning under det valda tidsintervallet. |
| **[!UICONTROL Batches added]** | Antalet datauppsättningsbatchar har lagts till i en anslutning. |
| **[!UICONTROL Last added]** | Tidsstämpeln för den senaste batchen från datauppsättningen som har lagts till i en anslutning. |
| **[!UICONTROL Data source type]** | Datamängdens källtyp. Du definierar källtypen när du skapar en anslutning. |
| **[!UICONTROL Dataset type]** | Datamängdstypen för den här datauppsättningen. Typen kan vara [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] eller [!UICONTROL Summary]. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL Schema]** | Det Experience Platform-schema som datauppsättningen baseras på. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningen: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**om datauppsättningen är konfigurerad att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** om datauppsättningen är konfigurerad att inte importera ny dataimport. |
| **[!UICONTROL Transform data]** | Transformeringsstatus för tillämpliga B2B-sökdatauppsättningar. Mer information finns i [Omforma datauppsättningar för B2B-sökningar](transform-datasets-b2b-lookups.md).<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**för tillämpliga datauppsättningar aktiverade för omvandling, <p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för tillämpliga datamängder som inte har aktiverats för omformning, och<p>**[!UICONTROL N/A]** för alla andra datauppsättningar, inte tillämpligt för transformering. |
| **[!UICONTROL Backfill data]** | Status för data för bakgrundsfyllning för datauppsättningen.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _backfills processing]**för antal bearbetning av bakåtfyllningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antal slutförda backfiller, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om bakåtfyllningar inte har konfigurerats. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningen: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**om datauppsättningen är konfigurerad att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** om datauppsättningen är konfigurerad att inte importera nya data. |
| **[!UICONTROL Backfill data]** | Status för data för bakgrundsfyllning för datauppsättningen.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _backfills processing]**för antal bearbetning av bakåtfyllningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antal slutförda backfiller, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om inga bakåtfyllningar är konfigurerade. |

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
| **[!UICONTROL Connection name]** | Anslutningens egna namn. |
| **[!UICONTROL Connection description]** | En mer detaljerad beskrivning som beskriver syftet med anslutningen. |
| **[!UICONTROL Sandbox]** | [Experience Platform-sandlådan](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) som den här anslutningen ritar sina datauppsättningar från. Den här sandlådan valdes när du först skapade anslutningen. Den kan inte ändras. |
| **[!UICONTROL Connection ID]** | Detta ID genereras i Experience Platform. Du kan använda ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) för att kopiera ID:t. |
| **[!UICONTROL Data views using connection]** | Visar alla datavyer som använder den här anslutningen. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningar: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**för hur många datauppsättningar som har konfigurerats för att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för hur många datauppsättningar som ny dataimport är inaktiverad. |
| **[!UICONTROL Backfill data]** | Status för data för bakgrundsfyllning för datauppsättningar.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills across datasets,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**för antal bearbetning av efterfyllningar i datauppsättningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antalet slutförda efterfyllningar för datauppsättningar, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om det inte finns några bakåtfyllningar definierade för datauppsättningarna i anslutningen. |
| **[!UICONTROL Transform data]** | Transformeringsstatus för tillämpliga B2B-sökdatauppsättningar. Mer information finns i [Omforma datauppsättningar för B2B-sökningar](transform-datasets-b2b-lookups.md).<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**för antalet datauppsättningar som har aktiverats för omformning. |
| **[!UICONTROL Created by]** | Namnet på den person som skapade anslutningen. |
| **[!UICONTROL Last modified]** | Tidsstämpeln för den senaste ändringen av anslutningen. |
| **[!UICONTROL Last modified by]** | Den person som senast ändrade anslutningen. |

#### Panelen Datauppsättning

När en datauppsättningsrad väljs i datamängdstabellen visas information för den valda datauppsättningen på en panel till höger i anslutningsgränssnittet.

| Information | Beskrivning |
| --- | --- |
| **[!UICONTROL Person ID]** | En identitet som definierades i datauppsättningsschemat i Experience Platform. Den här identiteten är det person-ID som du valde när anslutningen skapades. Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du vill sammanfoga datauppsättningar måste du använda samma person-ID för alla datauppsättningar. |
| **[!UICONTROL Key]** | Nyckeln som du har angett för en uppslagsdatauppsättning. |
| **[!UICONTROL Matching Key]** | Den matchande nyckel som du har angett för en uppslagsdatauppsättning. |
| **[!UICONTROL Timestamp]** | Tidsstämpeln som har definierats för en händelsedatamängd. |
| **[!UICONTROL Records available]** | Det totala antalet rader som har kapslats in för den här datauppsättningen, för den angivna tidsperioden som valts genom kalendern. Det finns ingen fördröjning när det gäller att få fram data som ska visas i rapporter när de har lagts till. När du skapar en helt ny anslutning visas [latens](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq). |
| **[!UICONTROL Records added]** | Hur många rader som lades till under den valda tidsperioden. |
| **[!UICONTROL Records deleted]** | Hur många poster som togs bort under den valda tidsperioden. |
| **[!UICONTROL Batches added]** | Hur många datagrupper som har lagts till i den här datauppsättningen. |
| **[!UICONTROL Records skipped]** | Hur många rader hoppades över under intag under den valda tidsperioden.<p>Orsaker till att poster hoppas över är: Tidsstämplar saknas, person-ID saknas eller är ogiltigt eller konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} osv. Uppdaterades var 10:e minut.<p>Ogiltiga ID:n (till exempel `undefined` eller `00000000`, eller en kombination av siffror och bokstäver i en [!UICONTROL Person ID] som visas i en händelse mer än 1 miljon gånger i en given månad) är ID:n som inte kan tilldelas någon specifik användare eller person. Dessa rader kan inte infogas i systemet och resulterar i felbenägen inmatning och rapportering. Du kan åtgärda ogiltiga person-ID:n eller konto-ID:n genom att välja mellan tre alternativ:<ul><li>Använd [Stitching](/help/stitching/overview.md) för att fylla i användar-ID:n som inte definierats eller är helt noll med giltiga användar-ID:n.</li><li>Ta bort användar-ID:t, som sedan hoppas över vid förtäring (helst inte med ett ogiltigt eller helt nollfritt användar-ID).</li><li>Korrigera ogiltiga användar-ID:n i systemet innan data hämtas.</li></ul> |
| **[!UICONTROL Last added]** | Tidsstämpeln som den senaste batchen lades till. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningen: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**om datauppsättningen är konfigurerad att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** om datauppsättningen är konfigurerad att inte importera nya data. |
| **[!UICONTROL Backfill data]** | Status för data för bakgrundsfyllning för datauppsättningen.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**for number of failed backfills,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _backfills processing]**för antal bearbetning av bakåtfyllningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**för antal slutförda backfiller, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om inga bakåtfyllningar är konfigurerade.<p>Om du vill visa en dialogruta med en översikt över de tidigare efterfyllningarna för datauppsättningen väljer du <img src="./assets/pastbackfill.svg" alt="Tidigare bakåtfyllningar" width="15"/> **[!UICONTROL Past backfills]**. |
| **[!UICONTROL Data source type]** | Datakälltyp som definieras när datauppsättningen läggs till i anslutningen. |
| **[!UICONTROL Dataset type]** | Antingen [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] eller [!UICONTROL Summary]. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL Schema]** | Det Experience Platform-schema som den här datauppsättningen baseras på. |
| **[!UICONTROL Dataset ID]** | Detta datauppsättnings-ID genereras i Experience Platform. |


## Användning {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="Viktiga användningsmått"
>abstract="Ange månads- och totaldata för rader som ska rapporteras, både för kärnrader och historiska rader."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="Månatliga kapslade rader"
>abstract="Mäter det totala antalet poster som läggs till i systemet varje månad för att ge insikter om datatillväxt och intagsfrekvens."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="Månatliga rapporteringsbara rader"
>abstract="Spårar antalet rader som är tillgängliga för rapportering. Rapporteringsbara rader är de inkapslade raderna minus de rader som hoppas över och tas bort under intag. Rapporteringsbara rader fungerar som nyckeltal för fakturering och dataanvändning."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="Detaljuppdelning."
>abstract="Du kan visa detaljerade mått efter anslutning, datauppsättning, sandlåda och taggar, med alternativet att hämta en CSV-fil med data."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="Andra datauppsättningar"
>abstract="För månaderna före september 2024 samlades data in på datauppsättningsnivå och visas som *Andra datauppsättningar* för tydlighet. Från och med september 2024 samlas data in på en detaljerad datauppsättningsnivå och *andra datauppsättningar* visas inte längre."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="Okända datauppsättningar eller anslutningar"
>abstract="Okända datauppsättningar eller anslutningar visas med deras ID."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="Data är inte tillgängliga"
>abstract="Historiska data före september 2024 är inte tillgängliga på grund av systembegränsningar. Mätvärden samlas in och visas från och med september 2024. Diagrammet visar de 18 senaste månaderna på tidslinjen och framtida data visas när data blir tillgängliga."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="Centrala rapporteringsbara rader"
>abstract="Visar det totala antalet rader som är tillgängliga de senaste 13 månaderna. Den 1 februari 2024 visar till exempel antalet totalt antal rader som är tillgängliga med en händelsetidsstämpel från januari 2023 till januari 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Historiska rader som ska rapporteras"
>abstract="Visar det totala antalet rader som är tillgängliga för en period som är äldre än 13 månader. Den 1 februari 2024 visar till exempel antalet alla rader som är tillgängliga med en händelselägestidsstämpel som är äldre än januari 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Viktiga användningsmått"
>abstract="Ange månads- och totaldata för rader som ska rapporteras, både för kärnrader och historiska rader."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Månatliga kapslade rader"
>abstract="Mäter det totala antalet poster som läggs till i systemet varje månad för att ge insikter om datatillväxt och intagsfrekvens."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Månatliga rapporteringsbara rader"
>abstract="Spårar antalet rader som är tillgängliga för rapportering. Rapporteringsbara rader är de inkapslade raderna minus de rader som hoppas över och tas bort under intag. Rapporteringsbara rader fungerar som nyckeltal för fakturering och dataanvändning."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Detaljuppdelning."
>abstract="Du kan visa detaljerade mått efter anslutning, datauppsättning, sandlåda och taggar, med alternativet att hämta en CSV-fil med data."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Andra datauppsättningar"
>abstract="För månaderna före september 2024 samlades data in på datauppsättningsnivå och visas som *Andra datauppsättningar* för tydlighet. Från och med september 2024 samlas data in på en detaljerad datauppsättningsnivå och *andra datauppsättningar* visas inte längre."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Okända datauppsättningar eller anslutningar"
>abstract="Okända datauppsättningar eller anslutningar visas med deras ID."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Data är inte tillgängliga"
>abstract="Historiska data före september 2024 är inte tillgängliga på grund av systembegränsningar. Mätvärden samlas in och visas från och med september 2024. Diagrammet visar de 18 senaste månaderna på tidslinjen och framtida data visas när data blir tillgängliga."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Centrala rapporteringsbara rader"
>abstract="Visar det totala antalet rader som är tillgängliga de senaste 13 månaderna. Den 1 februari 2024 visar till exempel antalet totalt antal rader som är tillgängliga med en händelsetidsstämpel från januari 2023 till januari 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Historiska rader som ska rapporteras"
>abstract="Visar det totala antalet rader som är tillgängliga för en period som är äldre än 13 månader. Den 1 februari 2024 visar till exempel antalet alla rader som är tillgängliga med en händelselägestidsstämpel som är äldre än januari 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Centrala rapporteringsbara rader"
>abstract="Huvudrader som ska rapporteras är ögonblicksbildsvärden, inte aggregerade summor. Dessa värden uppdateras dynamiskt baserat på den sista månaden i det valda datumintervallet. Om en kund väljer Januari-Mars återspeglar värdena ögonblicksbilden från mars."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Historiska rader som ska rapporteras"
>abstract="Historiska rapportbara rader är ögonblicksbildsvärden, inte aggregerade summor. Dessa värden uppdateras dynamiskt baserat på den sista månaden i det valda datumintervallet. Om en kund väljer Januari-Mars återspeglar värdena ögonblicksbilden från mars."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Ackumulerade rapporteringsbara rader"
>abstract="Kumulativa rapportbara rader är ögonblicksbildsvärden, inte aggregerade summor. Dessa värden uppdateras dynamiskt baserat på den sista månaden i det valda datumintervallet. Om en kund väljer Januari-Mars återspeglar värdena ögonblicksbilden från mars."

<!-- markdownlint-enable MD034 -->



Gränssnittet [!UICONTROL Usage] visar hur inkapslade och rapportbara rader används i alla anslutningar. Om det inte är markerat väljer du fliken **[!UICONTROL Usage]** för att komma åt gränssnittet.

Med det här gränssnittet kan du avgöra om din Customer Journey Analytics-användning överensstämmer med det som avtalats. Förutom övervakningsfunktioner kan du använda användargränssnittet för att planera förnyelsen av din Customer Journey Analytics-licens.

Gränssnittet Användning använder följande mått:

| Måttnamn | Beskrivning |
|---|---|
| Historiska rader som ska rapporteras | Antal rader för perioden äldre än 13 månader. |
| Centrala rapporteringsbara rader | Antal rader under de senaste 13 månaderna. |
| Indragna rader | Hur många rader som har importerats för den specifika perioden. |
| Rapporteringsbara rader | Hur många rader med data har du som en del av anslutningen för den angivna perioden. |
| Ackumulerade rader | Hur många rader som kapslas upp till den angivna månaden. |

>[!NOTE]
>
>Data samlas in från och med juli 2024 för de viktigaste, historiska och totala posterna. Kontakta din kontoansvarige för att få information om tidigare historiska data.
>



Användargränssnittet består av två paneler:

* Panelen **[!UICONTROL Key usage metrics]**: innehåller rader som kan rapporteras för kärndata och historiska data. Panelen håller också reda på procentuella ändringar jämfört med föregående månad för både kärndatarader och historiska datarader.

  Panelen visas i en visualisering:

   * **[!UICONTROL Core data reportable rows]**.

     Hur många rapporteringsbara rader har du under de senaste 13 månaderna? Sammanfattningsnumret är antalet rader som ska rapporteras (till exempel 741M) för den senaste månaden (till exempel december 2024).

   * **[!UICONTROL Historical data reportable rows]**.

     Hur många rapporteringsbara rader har du för en period som är äldre än 13 månader. Sammanfattningsnumret är antalet historiskt rapportbara rader (till exempel 127M) för den senaste månaden (till exempel december 2024).

  När du hovrar över ett staplat fält i visualiseringen visas ett popup-fönster med antalet rader för den specifika delen av fältet (till exempel).


  ![Nyckelanvändningsmått](assets/usage-key-usage-metrics.png)

* En kombinerad panel med tre underpaneler för:

+++ Indragna rader

  Underpanelen **[!UICONTROL Ingested rows]** mäter det totala antalet poster som läggs till i systemet varje månad, vilket ger insikt i datatillväxt och intagsfrekvens. Underpanelen innehåller en sammanfattning av den här månadens totala antal infogade rader och ändringen från föregående månad.

  ![Inkapslade rader](assets/usage-ingested-rows.png)

  Du kan hovra över datapunkter i visualiseringen om du vill visa ett popup-fönster med mer information.

+++

+++ Rapporteringsbara rader

  Visualiseringen av **[!UICONTROL Reportable rows]** håller reda på antalet rader som är tillgängliga för rapportering genom att ta bort överhoppade och borttagna rader från kapslade rader, vilket är ett nyckelmått för fakturering och dataanvändning. Underpanelen innehåller två sammanfattningar:

   * **[!UICONTROL Last month total]**: En sammanfattning av det totala antalet rader som kan rapporteras fram till den här månaden.
   * **[!UICONTROL This month]**: En sammanfattning av månadens totala rapporteringsbara rader och ändringen från föregående månad.

  ![Rapporteringsbara rader](assets/usage-reportable-rows.png)

  Du kan hovra över datapunkter i visualiseringarna om du vill visa ett popup-fönster med mer information.

+++

+++ Detaljuppdelning

  Du kan använda tabellen **[!UICONTROL Detail breakdown]** för att visa detaljerade mått efter anslutning, datauppsättning, sandlåda och taggar. Datauppsättningar rapporteras med ID i stället för namn, eftersom datauppsättningsnamn kan ändras under en rapportperiod. Okända datauppsättningar eller anslutningar rapporteras med hjälp av ID.

  För månaderna före september 2024 samlades data in på datauppsättningsnivå och visas som [!UICONTROL Other datasets] för tydlighet. Från och med september 2024 samlas data in på en detaljerad datauppsättningsnivå och [!UICONTROL Other datasets] visas inte längre.

   * Välj en kombination för **[!UICONTROL View by]** och **[!UICONTROL Breakdown by]** om du vill ändra nedbrytningen.

     | Alternativ för **[!UICONTROL View by]** | Alternativ för **[!UICONTROL Breakdown by]** |
     |---|---|
     | **[!UICONTROL Connection]** | **[!UICONTROL -]** och **[!UICONTROL Dataset]** |
     | **[!UICONTROL Dataset]** | **[!UICONTROL -]** |
     | **[!UICONTROL Sandbox]** | **[!UICONTROL Connection]** |
     | **[!UICONTROL Tag]** | **[!UICONTROL Connection]** |

  ![Detaljuppdelning](assets/usage-detail-breakdown.png)

+++

  Du kan definiera en **[!UICONTROL Time range]** i månader att rapportera om. Använd ![Kalender](/help/assets/icons/Calendar.svg) för att välja tidsintervall.

>[!MORELIKETHIS]
>
>[Visa, felsök och ändra anslutningsinställningar](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja) - självstudiekurs.
>[Hantera din Customer Journey Analytics-användning](/help/technotes/estimate-usage.md)
>
