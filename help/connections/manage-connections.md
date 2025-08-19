---
title: Hantera anslutningar i Customer Journey Analytics
description: Beskriver hur du hanterar anslutningar till Experience Platform-datauppsättningar i Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 0daca8437312900335826f20614ea8b0c7b49aea
workflow-type: tm+mt
source-wordcount: '4370'
ht-degree: 0%

---

# Hantera anslutningar {#manage-connections}

>[!CONTEXTUALHELP]
>id="connections_use_ajo"
>title="Använd Journey Optimizer-anslutning"
>abstract="Utnyttja de avancerade rapportfunktionerna i Customer Journey Analytics med Journey Optimizer."

>[!CONTEXTUALHELP]
>id="connections_cancel_ajo"
>title="Avbryt Journey Optimizer-anslutning"
>abstract="Avbryter de avancerade rapportfunktionerna i Customer Journey Analytics med Journey Optimizer."


När du har [skapat eller redigerat en eller flera anslutningar](/help/connections/create-connection.md) kan du hantera dem i **[!UICONTROL Connections]**. Med gränssnittet [!UICONTROL Connections] kan du:

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

Gränssnittet **[!UICONTROL List]** är standardgränssnittet för anslutningar. Om det inte är markerat väljer du fliken **[!UICONTROL List]** för att komma åt gränssnittet.

![listvy](assets/list-view.png)

Gränssnittet [!UICONTROL List] visar en tabell med alla tillgängliga anslutningar.

### Sök efter en anslutning

Du kan snabbt söka efter en anslutning med sökrutan ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

### Använda ett filter på listan med anslutningar

Om du vill använda ett filter på listan med anslutningar väljer du filterikonen och sedan något av följande filteralternativ:

| Filteralternativ | Beskrivning |
|---------|----------|
| **[!UICONTROL Datasets]** | Endast anslutningar som är kopplade till de datauppsättningar du väljer visas. |
| **[!UICONTROL Owner]** | Endast anslutningar som ägs av de personer du väljer visas. |
| **[!UICONTROL Sandbox]** | Endast anslutningar som är tillgängliga i de sandlådor du väljer visas. |
| **[!UICONTROL Use in CJA]** | Välj **[!UICONTROL On]** om du bara vill visa anslutningar som har aktiverats för användning med Customer Journey Analytics. Välj **[!UICONTROL Off]** om du bara vill visa anslutningar som ännu inte har aktiverats för användning med Customer Journey Analytics. |

### Tillgängliga kolumner

Följande kolumner eller ikoner är tillgängliga i tabellen.

| Kolumn eller ikon | Beskrivning |
| --- | --- |
| **[!UICONTROL _Namn_]** | Anslutningens egna namn. Markera det hyperlänkade namnet om du vill visa [information om anslutningen](#connection-details). |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Om du vill visa information om [!UICONTROL Datasets included], [!UICONTROL Sandbox], [!UICONTROL Owner] och mer väljer du ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) bredvid anslutningsnamnet.<p>Ett popup-fönster visar information om datauppsättningen. <p>![Popup för anslutningsinformation](assets/connection-info-popup.png) |
| ![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Om du vill [skapa en datavy](#create-a-data-view) för anslutningen väljer du ![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Den här ikonen visas bara när ingen datavy redan är kopplad till anslutningen. |
| ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) om du vill öppna en snabbmeny. Du kan välja: <p>![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** om du vill [redigera](#edit-a-connection) en anslutning.<p>![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** för att [ta bort](#delete-a-connection) en anslutning.<p>![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]** för att [skapa en ny datavy](#create-a-data-view) för anslutningen.<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Connection map]** om du vill visa en [anslutningskarta](#map-a-connection) för anslutningen. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Connection type]** | Typ av anslutning: **[!UICONTROL Person]**-baserad eller **[!UICONTROL Account]**-baserad anslutning. |
| **[!UICONTROL Datasets]** | En eller flera länkar till de datauppsättningar som är en del av anslutningen. Du kan välja datauppsättningens hyperlänk för att visa datauppsättningen i anslutningen. Om fler datauppsättningar ingår i den valda anslutningen väljer du **[!UICONTROL +*x *more]**&#x200B;för att visa en **[!UICONTROL Datasets included]**-panel. I den här panelen visas länkar till alla datauppsättningar och ett alternativ för att ![söka](/help/assets/icons/Search.svg) efter specifika datauppsättningar som ingår i anslutningen.<p>![Datauppsättningar ingår](assets/datasets-included.png)<p>Välj ett datauppsättningsnamn om du vill öppna datauppsättningen i Experience Platform-gränssnittet på en ny flik. |
| **[!UICONTROL Sandbox]** | [Experience Platform-sandlådan](https://experienceleague.adobe.com/sv/docs/experience-platform/sandbox/home) som den här anslutningen ritar sina datauppsättningar från. Du markerar den här sandlådan när du skapade anslutningen. Du kan inte ändra sandlådan när en anslutning har sparats. |
| **[!UICONTROL Owner]** | Den person som skapade anslutningen. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningar: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**&#x200B;för datauppsättningar som konfigurerats för att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för datauppsättningar som inte har konfigurerats för import av nya data. |
| **[!UICONTROL Date created]** | Tidsstämpeln när anslutningen skapades. |
| **[!UICONTROL Last modified]** | Tidsstämpeln när anslutningen senast uppdaterades. |
| **[!UICONTROL Backfill data]** | Status för data som fylls i bakåt över datauppsättningar.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**&#x200B;for number of failed backfills across datasets,<p>![Statusorange](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**&#x200B;för antal bearbetning av efterfyllningar i datauppsättningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**&#x200B;för antalet slutförda efterfyllningar för datauppsättningar, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om det inte finns några bakåtfyllningar definierade för datauppsättningarna i anslutningen. |
| **[!UICONTROL Integrations]** | Visar alla Experience Platform-program som är aktiverade med anslutningen. |
| **[!UICONTROL Use in CJA]** | Visar om anslutningen har aktiverats för användning med Customer Journey Analytics. |

Om du vill konfigurera vilka kolumner som ska visas i tabellen väljer du ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). I dialogrutan Anpassa tabell markerar du de kolumner som ska visas.

### Redigera en anslutning

Så här redigerar du en anslutning:

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet
1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** på snabbmenyn.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** i det blå åtgärdsfältet.

Mer information finns i [Skapa eller redigera en anslutning](create-connection.md).


### Ta bort en anslutning {#connections-delete}

Så här tar du bort en anslutning:

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
1. Välj ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]**.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** i det blå åtgärdsfältet.

När du tar bort en anslutning visar en **[!UICONTROL Delete connection]**-panel vilka datavyer som tas bort och vilka arbetsyteprojekt som påverkas.

* I ➊ **[!UICONTROL Info]** visas konsekvenserna av att anslutningen tas bort.

  ![Ta bort anslutning](assets/delete-connection.png)

  Markera **[!UICONTROL Continue]** för att bekräfta borttagningen.

* I ➋ **[!UICONTROL Confirmation]** anger du namnet på anslutningen i **[!UICONTROL Type connection name]** och väljer **[!UICONTROL Delete]** för att ta bort anslutningen. Välj **[!UICONTROL Cancel]** om du vill avbryta.

Mer information om hur du tar bort en anslutning finns i [Ta bort konsekvenser](/help/technotes/deletion.md).


### Skapa en datavy för en anslutning

Så här skapar du en datavy för en anslutning:

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]**.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** i det blå åtgärdsfältet.

Mer information finns i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).

### Journey Optimizer-anslutningar

Du kan använda en Journey Optimizer-anslutning i Customer Journey Analytics för att ge din anslutning följande ytterligare värde:

* Utför en djupgående analys av Journey Optimizer-data i Customer Journey Analytics (med knappen **[!UICONTROL Analyze in CJA]** i Journey Optimizer).

  Mer information finns i [Analysera i Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/reporting/channel-report/report-cja-manage#cja-template) i Journey Optimizer-dokumentationen.

* Redigera Journey Optimizer-anslutningen och associerade datavyer.

  Mer information om redigeringsalternativ finns i [Redigera en anslutning](#edit-a-connection).


>[!IMPORTANT]
>
>När du aktiverar en Journey Optimizer-anslutning för användning med Customer Journey Analytics enligt beskrivningen i det här avsnittet, räknas varje datarad i anslutningen mot dina licensierade datarader för Customer Journey Analytics varje månad och visas i användargränssnittet för anslutningsanvändning. Välj bara alternativet **[!UICONTROL Use in CJA]** för anslutningen om du känner dig bekväm med att använda rader med data i Customer Journey Analytics.
>
>**Om du var berättigad till både Customer Journey Analytics och Journey Optimizer mellan oktober 2024 och oktober 2025 läser du följande dokument om [AJO-aktiverade anslutningar](https://view.adobe.com/viewer/1ed94fc35c7860b260766c620889e7a0#1)**.

Om du vill aktivera den här funktionen måste din organisation ha tillgång till Customer Journey Analytics. Om du inte har tillgång till tjänsten kontaktar du Adobe säljare.

#### Använda en Journey Optimizer-anslutning {#use-connection-in-cja}

Så här använder du en Journey Optimizer-anslutning i Customer Journey Analytics:

1. Leta reda på den Journey Optimizer-anslutning som du vill använda med Customer Journey Analytics.

   1. Välj ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** på fliken **[!UICONTROL Connections]**.

   1. Välj **[!UICONTROL Use in CJA]** i avsnittet **[!UICONTROL Off]**.

      Här visas alla Journey Optimizer-anslutningar som inte är konfigurerade för användning i Customer Journey Analytics.

      ![Filter som visar anslutningar som inte har aktiverats för AJO](assets/remove-ajo-connection.png)

1. Markera namnet på Journey Optimizer-anslutningen.

1. Välj ![UsersShare](/help/assets/icons/UseInCJA.svg) **[!UICONTROL Use in CJA]**.

   ![Knappen Använd i CJA](assets/connection-use-in-cja.png)

   Dialogrutan **[!UICONTROL Use this connection in Customer Journey Analytics]** visas.

1. Aktivera växlingen, **[!UICONTROL Use connection in CJA]**.

1. Välj **[!UICONTROL Use connection]**. <!-- double-check these dialog button names -->

#### Ta bort en Journey Optimizer-anslutning {#remove-connection-in-cja}

Du kan när som helst ta bort en Journey Optimizer-anslutning från Customer Journey Analytics. Om du tar bort anslutningen från Customer Journey Analytics efter att den har använts får du dock följande resultat:

* Journey Optimizer-anslutningen och associerade datavyer återställs till standardläget och kan inte längre redigeras

* Alla anpassade härledda fält som är associerade med anslutningen tas bort.

* Du kan inte längre göra djupgående analyser av Journey Optimizer-data i Customer Journey Analytics.

  Det innebär att knappen **[!UICONTROL Analyze in CJA]** i Journey Optimizer är inaktiverad.

>[!IMPORTANT]
>
>Fakturering för anslutningen i Customer Journey Analytics omfattar hela månaden under vilken anslutningen tas bort.


Så här tar du bort anslutningen från Customer Journey Analytics:

1. Leta reda på den Journey Optimizer-anslutning som du vill ta bort från Customer Journey Analytics.

   1. Välj ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** på fliken **[!UICONTROL Connections]**.

   1. Välj **[!UICONTROL Use in CJA]** i avsnittet **[!UICONTROL On]**.

      Här visas alla Journey Optimizer-anslutningar som är konfigurerade för användning i Customer Journey Analytics.

      ![Filter för att visa anslutningar som är aktiverade för AJO](assets/enabled-ajo-connection.png)

1. Om du vill visa anslutningen markerar du namnet på den Journey Optimizer-anslutning som du vill ta bort från Customer Journey Analytics.

1. Välj **[!UICONTROL Remove from CJA]** när du visar Journey Optimizer-anslutningen.

   Dialogrutan **[!UICONTROL Remove this connection from Customer Journey Analytics]** visar:

   ![Knappen Ta bort från CJA](assets/connection-remove-from-cja.png)

1. Inaktivera alternativet, **[!UICONTROL Remove connection from CJA]**.

1. Välj **[!UICONTROL Remove connection]**.

### Mappa en anslutning

Så här visar du en [anslutningskarta](/help/connections/create-connection.md#connection-map) som detaljerar relationerna mellan de datauppsättningar som ingår i en anslutning:

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
1. Välj ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Connection map]**.

### Anslutningsinformation {#connection-detail}

Om du vill gå till informationen för en anslutning väljer du ett namn på en hyperlänkad anslutning i anslutningstabellen.

![Alla datauppsättningsfönster med widgetar och inställningar](assets/conn-details.png)

Gränssnittet Anslutningsinformation ger en detaljerad vy över anslutningsstatus. Ni kan:

* Kontrollera status för anslutningsens datauppsättningar och för överföringsprocessen.
* Identifiera konfigurationsproblem som kan orsaka överhoppade eller borttagna poster.
* Se när data är tillgängliga för rapportering.

| Användargränssnitt | Beskrivning |
| --- | --- |
| ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]** | Om du vill redigera information om en anslutning väljer du ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]**. Mer information finns i [Skapa eller redigera en anslutning](create-connection.md). |
| **[!UICONTROL *Datauppsättningsväljare *]** | Välj en eller alla datauppsättningar som du vill visa information för i anslutningen. Du kan inte markera datauppsättningar i flera steg. Standardvärdet är **[!UICONTROL All datasets]**. |
| **[!UICONTROL *Datumintervallväljare *]** | Välj ett dataområde som du vill visa information om i anslutningen. Redigera startdatum, slutdatum eller välj ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) för att öppna datumintervallväljaren. Välj ett datumintervall i datumintervallväljaren genom att använda någon av de fördefinierade perioderna (till exempel **[!UICONTROL Last 6 months]**) eller använd kalendern för att välja start- och slutdatum. Välj **[!UICONTROL Apply]** om du vill använda det nya datumintervallet på anslutningsinformationen. |
| **[!UICONTROL Records of event data available]** | Det totala antalet händelsedatamängdsrader som är tillgängliga för rapportering, **för hela anslutningen**. Antalet är oberoende av datumintervall eller datauppsättningsval. |
| [!UICONTROL **[!UICONTROL Metrics]**] | Sammanfatta de poster för händelse, sökning, profil och sammanfattning av datauppsättningar som har lagts till, hoppats över och tagits bort samt antalet grupper som har lagts till. Dessa mått baseras på **den datamängd och det datumintervall som du har valt**.<p>Välj **[!UICONTROL Check detail]** om du vill visa popup-fönstret **[!UICONTROL Check skipped detail]**. I popup-fönstret visas antalet poster som hoppats över och orsaken till alla händelsedatamängder eller valda datauppsättningar.<p>![Överhoppade poster](assets/skipped-records.png)<p>Välj popup-fönstret ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) med mer information. Av vissa orsaker som hoppats över, som [!UICONTROL Empty visitor ID], visas **[!UICONTROL Sample PSQL for EQS]** (Experience Platform for Query Service) som du kan använda i [frågetjänsten](https://experienceleague.adobe.com/sv/docs/experience-platform/query/home) för att fråga efter de poster som hoppats över i datauppsättningen. Välj ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copy sample PSQL for EQS]** om du vill kopiera SQL:en. |
| **[!UICONTROL Records added]** | En visualisering som visar hur många rader som har lagts till under den valda tidsperioden, **för den datamängd och det datumintervall som du har valt**. Uppdateringar var 10:e minut. |
| **[!UICONTROL Records skipped]** | En visualisering som visar hur många rader som hoppades över under den valda tidsperioden, **för den datamängd och det datumintervall som du har valt**. Orsaker till att poster hoppas över är bland annat: saknade tidsstämplar, person-ID eller konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} saknas eller är ogiltigt. Uppdateringar var 10:e minut. <p>Ogiltiga ID:n (till exempel `undefined` eller `00000000`, eller en kombination av siffror och bokstäver i en [!UICONTROL Person ID] som förekommer i en händelse mer än 1 miljon gånger i en viss månad) är ID:n som inte kan tilldelas någon specifik användare eller person. Dessa rader kan inte infogas i systemet och resulterar i felbenägen inmatning och rapportering. Om du vill korrigera ogiltiga person-ID:n eller konto-ID:n [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} har du tre alternativ:<ul><li>Använd [Stitching](/help/stitching/overview.md) för att fylla i användar-ID:n som inte definierats eller är helt noll med giltiga användar-ID:n.</li><li>Ta bort användar-ID:n, som sedan hoppas över vid förtäring (helst ogiltiga eller helt nolla användar-ID:n).</li><li>Korrigera ogiltiga användar-ID:n i systemet innan data hämtas.</li></ul> |
| **[!UICONTROL Records deleted]** | En visualisering som visar hur många rader som har tagits bort under den valda tidsperioden, **för den datamängd och det datumintervall som du har valt**. Någon kanske har tagit bort en datauppsättning i [!DNL Experience Platform]. Uppdateringar var 10:e minut.<p>I vissa scenarier kan det här värdet även innehålla ersatta poster, som sammanfogning eller vissa uppdateringar av uppslagsdatauppsättningar. Titta på det här exemplet:</p><ul><li>Du överför en post till en XDM-datauppsättning för enskild profil, som Customer Journey Analytics har konfigurerats att importera som profilsökningsdata. I anslutningsinformationen skulle den här datauppsättningen visa 1 post som lagts till.</li><li>Du överför en kopia av den ursprungliga posten till samma AEP-datauppsättning, som nu innehåller två poster. Customer Journey Analytics importerar den extra posten från profilen eller kontot [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} i uppslagsdatauppsättningen. Eftersom en profil- eller kontopost redan är inkapslad i anslutningen för detta person-ID eller konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} tar Customer Journey Analytics bort den tidigare versionen och lägger till nya profildata. I anslutningsinformationen representerar den här åtgärden 1 post som lagts till och 1 post som tagits bort, eftersom Customer Journey Analytics bara behåller de senaste profilsökningsdata för inkapslade person-ID:n eller konto-ID:n [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}.</li><li>Sammanlagt innehåller AEP datauppsättning två poster som råkar vara identiska. Customer Journey Analytics anslutningsinformation visar status för inkapslade data separat: 2 poster har lagts till och 1 post har tagits bort för profildatauppsättningen. </li></ul> |
| ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Sökfält för datauppsättning. Du kan söka i datamängdstabellen efter datauppsättningsnamn eller datauppsättnings-ID. |
| [!UICONTROL Datasets table] | De datauppsättningar som ingår i anslutningen. Se tabellen nedan för mer information. Välj ![SelectBox](/help/assets/icons/SelectBox.svg) om du bara vill visa anslutningsinformation för den valda datauppsättningen. Detta motsvarar valet av en datauppsättning från **[!UICONTROL _datauppsättningsväljaren_]**. |

I datatabellen visas följande kolumner för varje datauppsättning:

| Kolumn | Beskrivning |
| --- | --- |
| **[!UICONTROL Datasets]** | Datauppsättningens namn. Du kan välja hyperlänken för att öppna datauppsättningen i Experience Platform-gränssnittet på en ny flik. Du kan markera raden eller kryssrutan om du bara vill visa information för den markerade datauppsättningen. |
| **[!UICONTROL Dataset ID]** | Datauppsättnings-ID som genererats av Experience Platform. |
| **[!UICONTROL Records added]** | Antalet datauppsättningsposter (rader) som lagts till i en anslutning under det valda datumintervallet. |
| **[!UICONTROL Records skipped]** | Antalet datauppsättningsposter (rader) som hoppades över under dataöverföring för en anslutning under det valda datumintervallet. |
| **[!UICONTROL Records deleted]** | Antalet datauppsättningsposter (rader) som tagits bort från en anslutning under det valda datumintervallet. |
| **[!UICONTROL Batches added]** | Antalet batchar som har lagts till i en anslutning under det valda datumintervallet. |
| **[!UICONTROL Last added]** | Tidsstämpeln för den senaste batchen som har lagts till i en anslutning. |
| **[!UICONTROL Data source type]** | Källtypen. Du definierar källtypen när du lägger till en datauppsättning i en anslutning. |
| **[!UICONTROL Dataset type]** | Datamängdstypen [&#128279;](create-connection.md#dataset-types). Typen kan vara [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] eller [!UICONTROL Summary]. |
| **[!UICONTROL Schema]** | Det Experience Platform-schema som datauppsättningen baseras på. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningen: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**&#x200B;om datauppsättningen är konfigurerad att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** om datauppsättningen är konfigurerad att inte importera ny dataimport. |
| **[!UICONTROL Transform data]** | Transformeringsstatus för tillämpliga B2B-sökdatauppsättningar. Mer information finns i [Omforma datauppsättningar för B2B-sökningar](transform-datasets-b2b-lookups.md).<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**&#x200B;för tillämpliga datauppsättningar aktiverade för omvandling, <p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för tillämpliga datamängder som inte har aktiverats för omformning, och<p>**[!UICONTROL N/A]** för alla andra datauppsättningar, inte tillämpligt för transformering. |
| **[!UICONTROL Backfill data]** | Status för data för bakgrundsfyllning för datauppsättningen.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**&#x200B;for number of failed backfills,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _backfills processing]**&#x200B;för antal bearbetning av bakåtfyllningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**&#x200B;för antal slutförda backfiller, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om bakåtfyllningar inte har konfigurerats. |

>[!IMPORTANT]
>
>Data som har importerats före den 13 augusti 2021 visas inte i gränssnittet [!UICONTROL Connections].
>

#### Anslutningspanelen

När ingen enskild datauppsättning har valts i datamängdstabellen visas anslutningsalternativ och detaljer på den högra panelen.

| Alternativ | Beskrivning |
| --- | --- |
| ![Uppdatera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]** | Om du vill uppdatera anslutningen och tillåta att nyligen tillagda poster återspeglas väljer du ![Uppdatera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]**. |
| ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** | [Ta bort](#delete-a-connection) den här anslutningen. |
| ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** | [Skapa en datavy](#create-a-data-view) utifrån den här anslutningen. Mer information finns i [Datavyer](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/data-views). |
| **[!UICONTROL Use in CJA]** | Använd en Journey Optimizer-anslutning i Customer Journey Analytics för att ge ytterligare värde åt din Journey Optimizer-anslutning. Mer information finns i [Använda en Journey Optimizer-anslutning i Customer Journey Analytics](#use-a-journey-optimizer-connection-in-customer-journey-analytics). |
| **[!UICONTROL Connection name]** | Anslutningens egna namn. |
| **[!UICONTROL Connection description]** | En mer detaljerad beskrivning som beskriver syftet med anslutningen. |
| **[!UICONTROL Sandbox]** | [Experience Platform-sandlådan](https://experienceleague.adobe.com/sv/docs/experience-platform/sandbox/home) som den här anslutningen ritar sina datauppsättningar från. Du markerar den här sandlådan när du skapade anslutningen. Du kan inte ändra sandlådan när en anslutning har sparats. |
| **[!UICONTROL Connection ID]** | En genererad identifierare för anslutningen. Du kan använda ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) för att kopiera värdet. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Primary ID type]** | Den primära ID-typen för anslutningen **[!UICONTROL Person]** för en personbaserad anslutning, **[!UICONTROL Account]** för en kontobaserad anslutning. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Containers]** | De konfigurerade behållarna för anslutningen. |
| **[!UICONTROL Data views using connection]** | De datavyer som använder den här anslutningen. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningar: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**&#x200B;för hur många datauppsättningar som har konfigurerats för att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** för hur många datauppsättningar som ny dataimport är inaktiverad. |
| **[!UICONTROL Backfill data]** | Status för data för bakgrundsfyllning för datauppsättningar.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**&#x200B;for number of failed backfills across datasets,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _efterfyllnadsbearbetning]**&#x200B;för antal bearbetning av efterfyllningar i datauppsättningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**&#x200B;för antalet slutförda efterfyllningar för datauppsättningar, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om det inte finns några bakåtfyllningar definierade för datauppsättningarna i anslutningen. |
| **[!UICONTROL Transform data]** | Transformeringsstatus för tillämpliga B2B-sökdatauppsättningar. Mer information finns i [Omforma datauppsättningar för B2B-sökningar](transform-datasets-b2b-lookups.md).<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**&#x200B;för antalet datauppsättningar som har aktiverats för omformning. |
| **[!UICONTROL Created by]** | Namnet på den person som skapade anslutningen. |
| **[!UICONTROL Last modified]** | Tidsstämpeln för den senaste ändringen av anslutningen. |
| **[!UICONTROL Last modified by]** | Namnet på den person som senast ändrade anslutningen. |

#### Panelen Datauppsättning

När en datauppsättningsrad väljs i datamängdstabellen visas information för den valda datauppsättningen på en panel till höger i anslutningsgränssnittet.

| Information | Beskrivning |
| --- | --- |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Global Account ID]** | Identiteten som du har angett som ID för det globala kontot för anslutningen. Gäller endast för en kontobaserad anslutning för vilken en global kontobehållare har konfigurerats. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Account ID]** | Identiteten som du har angett som konto-ID för anslutningen. Gäller endast för en kontobaserad anslutning där ingen global kontobehållare har konfigurerats. |
| **[!UICONTROL Person ID]** | Identiteten som du har angett som telefon-ID för anslutningen. |
| **[!UICONTROL Key]** | Nyckeln som du har angett för en uppslagsdatauppsättning. |
| **[!UICONTROL Matching Key]** | Den matchande nyckel som du har angett för en uppslagsdatauppsättning. |
| **[!UICONTROL Timestamp]** | Tidsstämpeln som har definierats för en händelsedatamängd. |
| **[!UICONTROL Records available]** | Det totala antalet rader som har kapslats in för den här datauppsättningen, för den angivna tidsperioden som valts genom kalendern. Det finns ingen fördröjning när det gäller att få fram data som ska visas i rapporter när de har lagts till. När du skapar en helt ny anslutning visas [latens](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq). |
| **[!UICONTROL Records added]** | Antalet datauppsättningsposter (rader) som lagts till i en anslutning under det valda datumintervallet. |
| **[!UICONTROL Records skipped]** | Antalet datauppsättningsposter (rader) som hoppades över under dataöverföring för en anslutning under det valda datumintervallet. |
| **[!UICONTROL Batches added]** | Antalet batchar som har lagts till i en anslutning. |
| **[!UICONTROL Records deleted]** | Antalet datauppsättningsposter (rader) som tagits bort från en anslutning under det valda datumintervallet. |
| **[!UICONTROL Last added]** | Tidsstämpeln för den senaste batchen som har lagts till i en anslutning. |
| **[!UICONTROL Import new data]** | Status för import av nya data för datauppsättningen: <p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _On]**&#x200B;om datauppsättningen är konfigurerad att importera nya data, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _x Av_]** om datauppsättningen är konfigurerad att inte importera nya data. |
| **[!UICONTROL Backfill data]** | Status för data för bakgrundsfyllning för datauppsättningen.<p>![Status röd](assets/status-red.svg)   **[!UICONTROL _x _backfills failed]**&#x200B;for number of failed backfills,<p>![Status röd](assets/status-orange.svg)   **[!UICONTROL _x _backfills processing]**&#x200B;för antal bearbetning av bakåtfyllningar,<p>![Status grön](assets/status-green.svg)   **[!UICONTROL _x _backfills completed]**&#x200B;för antal slutförda backfiller, och<p>![Statusgrå](assets/status-gray.svg)   **[!UICONTROL _Av_]** om inga bakåtfyllningar är konfigurerade.<p>Om du vill visa en dialogruta med en översikt över de tidigare efterfyllningarna för datauppsättningen väljer du <img src="./assets/pastbackfill.svg" alt="Tidigare bakåtfyllningar" width="15"/> **[!UICONTROL Past backfills]**. |
| **[!UICONTROL Data source type]** | Datakälltyp som definierades när datauppsättningen lades till i anslutningen. |
| **[!UICONTROL Dataset type]** | Datamängdstypen [&#128279;](create-connection.md#dataset-types). |
| **[!UICONTROL Schema]** | Det Experience Platform-schema som den här datauppsättningen baseras på. |
| **[!UICONTROL Dataset ID]** | Datauppsättnings-ID som genererats i Experience Platform. |


## Användning {#connections-usage}

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Viktiga användningsmått"
>abstract="Ange månads- och totaldata för rader som ska rapporteras, både för kärnrader och historiska rader."

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Månatliga kapslade rader"
>abstract="Mäter det totala antalet poster som läggs till i systemet varje månad för att ge insikter om datatillväxt och intagsfrekvens."

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Månatliga rapporteringsbara rader"
>abstract="Spårar antalet rader som är tillgängliga för rapportering. Rapporteringsbara rader är de inkapslade raderna minus de rader som hoppas över och tas bort under intag. Rapporteringsbara rader fungerar som nyckeltal för fakturering och dataanvändning."

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Detaljuppdelning."
>abstract="Du kan visa detaljerade mått efter anslutning, datauppsättning, sandlåda och taggar, med alternativet att hämta en CSV-fil med data."

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Andra datauppsättningar"
>abstract="För månaderna före september 2024 samlades data in på datauppsättningsnivå och visas som *Andra datauppsättningar* för tydlighet. Från och med september 2024 samlas data in på en detaljerad datauppsättningsnivå och *andra datauppsättningar* visas inte längre."

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Okända datauppsättningar eller anslutningar"
>abstract="Okända datauppsättningar eller anslutningar visas med deras ID."

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Data är inte tillgängliga"
>abstract="Historiska data före september 2024 är inte tillgängliga på grund av systembegränsningar. Mätvärden samlas in och visas från och med september 2024. Diagrammet visar de 18 senaste månaderna på tidslinjen och framtida data visas när data blir tillgängliga."

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Centrala rapporteringsbara rader"
>abstract="Det totala antalet rader som är tillgängliga de senaste 13 månaderna. Den 1 februari 2024 visar till exempel antalet totalt antal rader som är tillgängliga med en händelsetidsstämpel från januari 2023 till januari 2024."

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Historiska rader som ska rapporteras"
>abstract="Det totala antalet rader som är tillgängliga för perioden som är äldre än 13 månader. Den 1 februari 2024 visar till exempel antalet alla rader som är tillgängliga med en händelselägestidsstämpel som är äldre än januari 2023."


>[!CONTEXTUALHELP]
>id="connections_averagerowsize"
>title="Genomsnittlig radstorlek"
>abstract="Den genomsnittliga mängden lagringsutrymme som förbrukas av varje rad med data som har importerats och lagrats i Customer Journey Analytics (i kB) för den aktuella månaden, med en procentuell ändring jämfört med föregående månad."


>[!CONTEXTUALHELP]
>id="connections_coredatavolume"
>title="Kärndatavolym"
>abstract="Den totala mängden data som lagras på disken som är tidsstämplade för den aktuella månaden (i GB eller TB), med en procentuell ändring jämfört med föregående månad."


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


Gränssnittet [!UICONTROL Usage] visar hur inkapslade och rapportbara rader används i alla anslutningar. Om det inte är markerat väljer du fliken **[!UICONTROL Usage]** för att komma åt gränssnittet.

Med det här gränssnittet kan du avgöra om din Customer Journey Analytics-användning överensstämmer med det som avtalats. Förutom övervakningsfunktioner kan du använda användargränssnittet för att planera förnyelsen av din Customer Journey Analytics-licens.

Följande mått används i användargränssnittet:

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

  Panelen visar en visualisering som innehåller:

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
>[Visa, felsök och ändra anslutningsinställningar](https://experienceleague.adobe.com/sv/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja) - självstudiekurs.
>&#x200B;>[Hantera din Customer Journey Analytics-användning](/help/technotes/estimate-usage.md)
>
