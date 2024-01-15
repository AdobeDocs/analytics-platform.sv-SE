---
title: Hantera anslutningar i Customer Journey Analytics
description: Beskriver hur du hanterar anslutningar till datauppsättningar i Experience Platform i Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 0b41cc80310c49bd1b0c73f1323f86c8b280e15f
workflow-type: tm+mt
source-wordcount: '2324'
ht-degree: 0%

---

# Hantera anslutningar

När du har [har skapat eller redigerat en eller flera anslutningar](/help/connections/create-connection.md)kan du hantera dem i **[!UICONTROL Connections]**. Med anslutningar kan du:

* Visa alla dina anslutningar i korthet, inklusive ägaren, sandlådan och när anslutningarna skapades och ändrades.
* Redigera en anslutning.
* Ta bort en anslutning.
* Skapa en datavy från en anslutning.
* Visa alla datauppsättningar i en anslutning.
* Kontrollera status för anslutningsens datauppsättningar och status för överföringsprocessen. Till exempel när är dina data tillgängliga så att du kan börja med rapporter och analyser i Analysis Workspace.
* Identifiera eventuella dataavvikelser på grund av felaktig konfiguration. Saknar du några rader? Om så är fallet, vilka rader saknas och varför? Har du felkonfigurerat anslutningar och orsakat saknade data i Customer Journey Analytics?


En tabell visar alla tillgängliga anslutningar. Du kan snabbt söka efter en anslutning med sökfunktionen ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) box.

Följande kolumner / ikoner är tillgängliga i tabellen.

| Kolumn/ikon | Beskrivning |
| --- | --- |
| [!UICONTROL Name] | Anslutningens egna namn. Om du vill visa information om anslutningen markerar du namnet på den hyperlänkade anslutningen. Se [Anslutningsinformation](#connection-details). |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Om du vill visa information om [!UICONTROL Datasets included], [!UICONTROL Sandbox], [!UICONTROL Owner]och mer, markera ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) bredvid anslutningsnamnet.<p>Ett popup-fönster visar information. <p><img src="./assets/conn-info.png" alt="Visa anslutningsinformation" width="50%" /> |
| ![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Till [skapa en datavy](#create-a-data-view) för anslutningen väljer ![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . Den här ikonen visas bara när ingen datavy redan är kopplad till anslutningen. |
| ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) till: <p>![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Redigera](#edit-a-connection) en anslutning.<p>![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Ta bort](#delete-a-connection) en anslutning.<p>![Datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Skapa ny datavy](#create-a-data-view). Använd det här alternativet om du vill skapa ytterligare datavyer för anslutningen. |
| [!UICONTROL Datasets] | Visar en eller flera länkar till de datauppsättningar som är en del av anslutningen. Du kan välja datauppsättningens hyperlänk för att visa datauppsättningen i anslutningen. Om fler datauppsättningar ingår i den valda anslutningen väljer du **[!UICONTROL +*x *mer]**för att visa **[!UICONTROL Datasets included]**-panelen. I den här panelen visas länkar till alla datauppsättningar och ett alternativ för att söka efter en specifik datauppsättning som är en del av anslutningen.<p><img src="./assets/datasets-included.png" alt="Inkluderade datatillgångar" width="50%" /><p>Om du väljer ett datauppsättningsnamn öppnas datauppsättningen i användargränssnittet för Experience Platform på en ny flik. |
| [!UICONTROL Sandbox] | Visar [Experience Platform sandlåda](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=sv) från vilken den här anslutningen ritar sina datauppsättningar. Den här sandlådan valdes när du först skapade anslutningen. Den kan inte ändras. |
| [!UICONTROL Owner] | Den person som skapade anslutningen. |
| [!UICONTROL Import new data] | Visar status för import av nya data för datauppsättningar: <p><span style="color:green">●</span>   **[!UICONTROL _x _På]**för hur många datauppsättningar som har konfigurerats för att importera nya data, och&lt;/<p><span style="color:gray">●</span>   **[!UICONTROL _x av_]** för hur många datauppsättningar som ny dataimport är inaktiverad. |
| [!UICONTROL Date created] | Tidsstämpeln när anslutningen skapades. |
| [!UICONTROL Last modified] | Tidsstämpeln när anslutningen senast uppdaterades. |
| [!UICONTROL Backfill data] | Visar status för data för bakgrundsfyllning över datauppsättningar.<p><span style="color:red">●</span>   **[!UICONTROL _x _backfills failed]**för antalet misslyckade efterfyllningar i datauppsättningar,<p><span style="color:orange">●</span>   **[!UICONTROL _x _bearbetning av bakåtfyllnad]**för antalet efterfyllningar som bearbetas över datauppsättningar,<p><span style="color:green">●</span>   **[!UICONTROL _x _bakåtfyllningar har slutförts]**för antalet slutförda efterfyllningar för datauppsättningar, och<p><span style="color:grey">●</span>   **[!UICONTROL _Av_]** om det inte finns några bakåtfyllningar definierade för datauppsättningarna i anslutningen. |

Du kan konfigurera vilka kolumner som ska visas med ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Det här visar **Anpassa tabell** som gör att du kan aktivera/inaktivera kolumner i tabellen.

## Redigera en anslutning

Tillåter administratörer att redigera anslutningen.

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet
1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** på snabbmenyn.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** från det blå fältet.

När du redigerar en anslutning kan du:

* Starta och sluta importera nya data.
* Byt namn på en anslutning.
* Uppdatera datauppsättningen/datauppsättningarna.
* Ta bort datauppsättningar från anslutningarna.

Se [Skapa eller redigera en anslutning](create-connection.md) för mer information.


## Ta bort en anslutning {#connections-delete}

Tillåter administratörer att ta bort anslutningen.

1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
1. Välj ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]**.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** från det blå fältet.

När du tar bort en anslutning visas en **[!UICONTROL Delete connection]** visas vilka datavyer som tas bort och vilka arbetsyteprojekt som påverkas.

<img src="./assets/delete-connection.png" alt="Ta bort anslutning" width="50%" />

Välj **[!UICONTROL Continue]** för att ta bort anslutningen.

Se [Ta bort konsekvenser](/help/admin/cja-deletion.md) för mer information om konsekvenserna av att ta bort en anslutning.


## Skapa en datavy

Tillåter administratörer att skapa en datavy för anslutningen.

* Om ingen datavy är associerad med anslutningen:

   1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) bredvid anslutningsnamnet.

* Om en eller flera datavyer redan har skapats för anslutningen:

   1. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) bredvid anslutningsnamnet.
   1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]**.

Du kan också:

1. Markera anslutningsraden.

1. Välj ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** i det blå knappfältet.

Se [Skapa eller redigera en datavy](/help/data-views/create-dataview.md) för mer information.

## Anslutningsinformation {#connection-detail}

Om du vill gå till informationen för en anslutning väljer du ett anslutningsnamn i anslutningstabellen.

![Alla datauppsättningsfönster som visar widgetar och inställningar](assets/conn-details.png)

Skärmen Anslutningsinformation innehåller en detaljerad vy över anslutningsstatus. Ni kan:

* Kontrollera status för anslutningsens datauppsättningar och för överföringsprocessen.
* Identifiera konfigurationsproblem som kan orsaka överhoppade eller borttagna poster.
* Se när data är tillgängliga för rapportering.

>[!IMPORTANT]
>
>Eventuella uppgifter som lämnats in före den 13 augusti 2021 återspeglas inte i detta [!UICONTROL Connections] -dialogrutan.

### Anslutningsinformation

| Användargränssnitt | Beskrivning |
| --- | --- |
| ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Edit Connection] | Om du vill redigera information om en anslutning väljer du ![Redigera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]** . Se [Skapa eller redigera en anslutning](create-connection.md) för mer information. |
| Datauppsättningsväljare | Gör att du kan välja en eller alla datauppsättningar i anslutningen. Du kan inte markera datauppsättningar i flera steg. Standardvärdet är [!UICONTROL All datasets]. |
| Kalender-/datumintervallväljare | Datumintervallet anger när du lade till data i anslutningen. Alla standardförinställningar för kalendrar ingår. Du kan anpassa datumintervallet, men inga anpassade datumintervall visas i listrutan. |
| [!UICONTROL Records of event data available] | Representerar det totala antalet händelsedatarader som är tillgängliga för rapportering, **för hela anslutningen**. Antalet är oberoende av eventuella kalenderinställningar. Antalet ändras om du väljer en datauppsättning från datauppsättningsväljaren eller genom att markera en datauppsättning i tabellen. När data har lagts till finns det en fördröjning på 1-2 timmar för att få data att visas vid rapportering. |
| [!UICONTROL Metrics] | Sammanfattar de händelseposter som lagts till/hoppats över/tagits bort och antalet batchar som lagts till, **för den datauppsättning och det datumintervall som du har valt**. |
| [!UICONTROL Records added] | Anger hur många rader som har lagts till under den valda tidsperioden, **för den datauppsättning och det datumintervall som du har valt**. Uppdaterades var 10:e minut. <p>**Anteckning**: Data för **[!UICONTROL Records added]** innehåller endast händelsedata för tillfället, inte profil- eller sökdata. |
| [!UICONTROL Records skipped] | Anger hur många rader som hoppades över under den valda tidsperioden. **för den datauppsättning och det datumintervall som du har valt**. Orsaker till att hoppa över poster är bland annat: Tidsstämplar saknas, person-ID saknas eller är ogiltigt osv. Uppdaterades var 10:e minut.<p>Ogiltiga person-ID:n (till exempel &quot;undefined&quot; eller &quot;000000&quot;) eller en kombination av siffror och bokstäver i en [!UICONTROL Person ID] som förekommer i en händelse (fler än 1 miljon gånger under en viss månad) inte kan tillskrivas någon specifik användare eller person. De kan inte importeras till systemet och leder till felbenägen intag och rapportering. Du kan åtgärda ogiltiga person-ID:n på tre sätt:<ul><li>Använd [Stitlar](/help/stitching/overview.md) för att fylla i användar-ID:n som inte definierats eller är helt noll med giltiga användar-ID:n.</li><li>Ta bort användar-ID:t, som sedan kommer att hoppas över vid förtäring (helst istället för ogiltiga eller helt nolla användar-ID:n).</li><li>Korrigera ogiltiga användar-ID:n i systemet innan data hämtas.</li></ul><p>**Anteckning**: Data för **[!UICONTROL Records skipped]** innehåller endast händelsedata för tillfället, inte profil- eller sökdata. |
| [!UICONTROL Records] borttagen | Anger hur många rader som har tagits bort under den valda tidsperioden, **för den datauppsättning och det datumintervall som du har valt**. Någon kan till exempel ha tagit bort en datauppsättning i Experience Platform. Uppdaterades var 10:e minut. <p>**Anteckning**: Data för **[!UICONTROL Records deleted]** innehåller endast händelsedata för tillfället, inte profil- eller sökdata. |
| ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Sök efter datauppsättningsnamn eller ID_ | Sökfält för datauppsättning. Du kan söka i datamängdstabellen efter datauppsättningsnamn eller [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets table] | Visar de datauppsättningar som ingår i anslutningen. |
| [!UICONTROL Datasets] | Visar namnet på datauppsättningen som är en del av anslutningen. Du kan markera hyperlänken för att öppna datauppsättningen i användargränssnittet för Experience Platform på en ny flik. Du kan markera raden eller kryssrutan om du bara vill visa information för den markerade datauppsättningen. |
| [!UICONTROL Dataset ID] | Automatiskt genererad av Experience Platform. |
| [!UICONTROL Records added] | Antalet datauppsättningsposter/rader som lagts till i en anslutning under det valda tidsintervallet. |
| [!UICONTROL Records skipped] | Antalet datauppsättningsposter/rader som hoppats över under dataöverföring för en anslutning under det valda tidsintervallet. |
| [!UICONTROL Records deleted] | Antalet datauppsättningsposter/rader som tagits bort från en anslutning under det valda tidsintervallet. |
| [!UICONTROL Batches added] | Antal datauppsättningsbatchar har lagts till i en anslutning. |
| [!UICONTROL Last added] | Tidsstämpeln för den senaste batchen från datauppsättningen som lagts till i en anslutning. |
| [!UICONTROL Data source type] | Datamängdens källtyp. Du definierar källtypen när du skapar en anslutning. |
| [!UICONTROL Dataset type] | Datamängdstypen för den här datauppsättningen. Typ kan [!UICONTROL Event], [!UICONTROL Lookup], eller [!UICONTROL Profile]. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset) |
| Schema | Det Experience Platform-schema som datauppsättningen baseras på. |
| [!UICONTROL Import new data] | Visar status för import av nya data för datauppsättningen: <p><span style="color:green">●</span>   **[!UICONTROL _x _På]**om datauppsättningen har konfigurerats för import av nya data, och<p><span style="color:gray">●</span>   **[!UICONTROL _x av_]** om datauppsättningen är konfigurerad att inte importera ny dataimport. |
| [!UICONTROL Backfill data] | Visar status för data för bakgrundsfyllning för datauppsättningen.<p><span style="color:red">●</span>   **[!UICONTROL _x _backfills failed]**för antalet misslyckade backfiller,<p><span style="color:orange">●</span>   **[!UICONTROL _x _bearbetning av bakåtfyllnad]**för antalet efterfyllningar,<p><span style="color:green">●</span>   **[!UICONTROL _x _bakåtfyllningar har slutförts]**för antalet slutförda efterfyllningar, och<p><span style="color:grey">●</span>   **[!UICONTROL _Av_]** om inga bakåtfyllningar har konfigurerats. |

### Anslutningspanelen

När ingen datauppsättning har valts i datamängdstabellen visas anslutningsalternativ och detaljer på en panel till höger i anslutningsgränssnittet.

| Alternativ / Detaljer | Beskrivning |
| --- | --- |
| ![Uppdatera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Refresh] | Om du vill uppdatera anslutningen och tillåta att nyligen tillagda poster återspeglas väljer du ![Uppdatera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]**. |
| ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** | [Ta bort](#delete-a-connection) den här anslutningen. |
| ![Lägg till datavy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** | [Skapa en datavy](#create-a-data-view) baserat på den här anslutningen. Se [Datavyer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html) för mer information. |
| [!UICONTROL Connection name] | Visar det egna namnet för anslutningen. |
| [!UICONTROL Connection description] | Visar en mer detaljerad beskrivning som beskriver syftet med anslutningen. |
| [!UICONTROL Sandbox] | The [Experience Platform sandlåda](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=sv) som den här anslutningen hämtar sina datauppsättningar från. Den här sandlådan valdes när du först skapade anslutningen. Den kan inte ändras. |
| [!UICONTROL Connection ID] | Detta ID genereras i Experience Platform. Du kan använda ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) för att kopiera ID:t. |
| [!UICONTROL Data views using connection] | Visar alla datavyer som använder den här anslutningen. |
| [!UICONTROL Import new data] | Visar status för import av nya data för datauppsättningar: <p><span style="color:green">●</span>   **[!UICONTROL _x _På]**för hur många datauppsättningar som har konfigurerats för att importera nya data, och<p><span style="color:gray">●</span>   **[!UICONTROL _x av_]** för hur många datauppsättningar som ny dataimport är inaktiverad. |
| [!UICONTROL Backfill data] | Visar status för data för bakgrundsfyllning för datauppsättningar.<p><span style="color:red">●</span>   **[!UICONTROL _x _backfills failed]**för antalet misslyckade efterfyllningar i datauppsättningar,<p><span style="color:orange">●</span>   **[!UICONTROL _x _bearbetning av bakåtfyllnad]**för antalet efterfyllningar som bearbetas över datauppsättningar,<p><span style="color:green">●</span>   **[!UICONTROL _x _bakåtfyllningar har slutförts]**för antalet slutförda efterfyllningar för datauppsättningar, och<p><span style="color:grey">●</span>   **[!UICONTROL _Av_]** om det inte finns några bakåtfyllningar definierade för datauppsättningarna i anslutningen. |
| [!UICONTROL Created by] | Visar namnet på den person som skapade anslutningen. |
| [!UICONTROL Last modified] | Visar tidsstämpeln för den senaste ändringen av anslutningen. |
| [!UICONTROL Last modified by] | Visar den person som senast ändrade anslutningen. |

### Panelen Datauppsättning

När en datauppsättning väljs i datamängdstabellen visas information om den valda datauppsättningen på en panel till höger om anslutningsgränssnittet.

| Information | Beskrivning |
| --- | --- |
| [!UICONTROL Person ID] | Visar en identitet som definierades i datauppsättningsschemat i Experience Platform. Detta är det person-ID som du valde när anslutningen skapades. Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du vill sammanfoga datauppsättningar måste du använda samma person-ID för alla datauppsättningar. |
| [!UICONTROL Key] | Visar den nyckel som du har angett för en uppslagsdatauppsättning. |
| [!UICONTROL Matching Key] | Visar den matchande nyckel som du har angett för en uppslagsdatauppsättning. |
| [!UICONTROL Timestamp] | Visa den tidsstämpel som har definierats för en händelsedatamängd. |
| [!UICONTROL Records available] | Representerar det totala antalet rader som kapslats in för den här datauppsättningen, för den angivna tidsperioden som valts genom kalendern. Det finns ingen fördröjning när det gäller att få fram data som ska visas i rapporter när de har lagts till. När du skapar en helt ny anslutning kommer det dock att finnas [latens](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#3.-getting-data-into-customer-travel-analytics). |
| [!UICONTROL Records added] | Anger hur många rader som har lagts till under den valda tidsperioden. <p>**Anteckning**: Data för **[!UICONTROL Records added]** innehåller endast händelsedata för tillfället, inte profil- eller sökdata. |
| [!UICONTROL Records deleted] | Anger hur många poster som togs bort under den valda tidsperioden. <p>**Anteckning**: Data för **[!UICONTROL Records deleted]** innehåller endast händelsedata för tillfället, inte profil- eller sökdata. |
| [!UICONTROL Batches added] | Anger hur många datagrupper som har lagts till i den här datauppsättningen. |
| [!UICONTROL Records skipped] | Anger hur många rader som hoppats över under intag under den valda tidsperioden.<p>Orsaker till att hoppa över poster är bland annat: Tidsstämplar saknas, person-ID saknas eller är ogiltigt osv. Uppdaterades var 10:e minut.<p>Ogiltiga person-ID:n (till exempel &quot;undefined&quot; eller &quot;000000&quot;) eller en kombination av siffror och bokstäver i en [!UICONTROL Person ID] som förekommer i en händelse (fler än 1 miljon gånger under en viss månad) inte kan tillskrivas någon specifik användare eller person. De kan inte importeras till systemet och leder till felbenägen intag och rapportering. Du kan åtgärda ogiltiga person-ID:n på tre sätt:<ul><li>Använd [Stitlar](/help/stitching/overview.md) för att fylla i användar-ID:n som inte definierats eller är helt noll med giltiga användar-ID:n.</li><li>Ta bort användar-ID:t, som sedan hoppas över vid förtäring (helst inte med ett ogiltigt eller helt nollfritt användar-ID).</li><li>Korrigera ogiltiga användar-ID:n i systemet innan data hämtas.</li></ul><p>**Anteckning**: Data för **[!UICONTROL Records skipped]** innehåller endast händelsedata för tillfället, inte profil- eller sökdata. |
| [!UICONTROL Last added] | Anger när den senaste batchen lades till. |
| [!UICONTROL Import new data] | Visar status för import av nya data för datauppsättningen: <p><span style="color:green">●</span>   **[!UICONTROL _x _På]**om datauppsättningen har konfigurerats för import av nya data, och<p><span style="color:gray">●</span>   **[!UICONTROL _x av_]** om datauppsättningen är konfigurerad att inte importera ny dataimport. |
| [!UICONTROL Backfill data] | Visar status för data för bakgrundsfyllning för datauppsättningen.<p><span style="color:red">●</span>   **[!UICONTROL _x _backfills failed]**för antalet misslyckade backfiller,<p><span style="color:orange">●</span>   **[!UICONTROL _x _bearbetning av bakåtfyllnad]**för antalet efterfyllningar,<p><span style="color:green">●</span>   **[!UICONTROL _x _bakåtfyllningar har slutförts]**för antalet slutförda efterfyllningar, och<p><span style="color:grey">●</span>   **[!UICONTROL _Av_]** om inga bakåtfyllningar har konfigurerats.<p>Om du vill visa en dialogruta med en översikt över de tidigare efterfyllningarna för datauppsättningen väljer du <img src="./assets/pastbackfill.svg" alt="Tidigare bakåtfyllningar" width="2%" /> **[!UICONTROL Past backfills]**. |
| [!UICONTROL Data source type] | Datakälltyp som definieras när datauppsättningen läggs till i anslutningen. |
| [!UICONTROL Dataset type] | Antingen [!UICONTROL Event], [!UICONTROL Lookup], eller [!UICONTROL Profile]. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset) |
| [!UICONTROL Schema] | Visar det Experience Platform-schema som den här datauppsättningen baseras på. |
| [!UICONTROL Dataset ID] | Detta datauppsättnings-ID genereras i Experience Platform. |


>[!MORELIKETHIS]
>
>[Visa, felsöka och ändra anslutningsinställningar](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html?lang=en) självstudie.
