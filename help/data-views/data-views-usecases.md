---
title: Använd exempel för datavyer i Customer Journey Analytics
description: Flera användningsfall som visar flexibiliteten och kraften i datavyer i Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 80f31a77df68dca91c1f9f5a0d521b0ea7d450ce
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 0%

---

# Datavyer använder exempel

De här användningsexemplen visar hur flexibla och kraftfulla datavyer är i Customer Journey Analytics.

## 1. Skapa ett mått från ett strängschemafält {#string}

När du skapar en datavy kan du till exempel skapa en [!UICONTROL Orders] mått från en [!UICONTROL pageTitle] schemafält som är en sträng. Så här gör du:

1. På fliken Komponenter drar du [!UICONTROL pageTitle] till [!UICONTROL Metrics] avsnitt under [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Markera nu måttet som du just drog in och döp om det under [!UICONTROL Component Settings] till höger:
   ![](assets/orders.png)
1. Öppna [!UICONTROL Include/Exclude Values] till höger och ange följande:
   ![](assets/orders2.png)

   &quot;Bekräftelsefrasen&quot; anger att detta är en order. När du har granskat alla sidrubriker där dessa kriterier uppfylls räknas &quot;1&quot; för varje förekomst. Resultatet är ett nytt mått (inte ett beräknat mått). Ett mätvärde som har inkluderade/exkluderade värden kan användas överallt där andra mätvärden kan användas. Det fungerar med Attribution IQ, filter och var du än är kan du använda standardvärden.
1. Du kan ange en attribueringsmodell för det här måttet ytterligare, till exempel [!UICONTROL Last Touch], med [!UICONTROL Lookback window] av [!UICONTROL Session].
Du kan också skapa en annan [!UICONTROL Orders] mätvärden från samma fält och ange en annan attribueringsmodell för det, till exempel [!UICONTROL First Touch]och en annan [!UICONTROL Lookback window], till exempel [!UICONTROL 30 days].

Ett annat exempel är att använda besökar-ID, en dimension, som ett mått för att avgöra hur många besökar-ID ditt företag har.

## 2. Använd heltal som dimensioner {#integers}

Tidigare behandlades heltal automatiskt som mått i CJA. Nu kan numeriska värden (inklusive anpassade händelser från Adobe Analytics) behandlas som dimensioner. Här är ett exempel:

1. Dra [!UICONTROL call_length_min] heltal i [!UICONTROL Dimensions] avsnitt under [!UICONTROL Included Components]:

   ![](assets/integers.png)

1. Nu kan du lägga till [!UICONTROL Value Bucketing] för att presentera denna dimension på ett krånglat sätt vid rapportering. (Utan att låsa visas varje instans av den här dimensionen som ett radobjekt i Workspace-rapporten.)

   ![](assets/bucketing.png)

## 3. Använd numeriska mått som&quot;mått&quot; i flödesdiagram {#numeric}

Du kan använda en numerisk dimension för att få in &quot;mått&quot; i [!UICONTROL  Flow] visualisering.

1. På datavyer [Komponenter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings) -fliken, dra [!UICONTROL Marketing Channels] schemafält till [!UICONTROL Metrics] areal under [!UICONTROL Included components].
2. I Workspace-rapporter visas det här flödet [!UICONTROL Marketing Channels] flöda in i [!UICONTROL Orders]:

![](assets/flow.png)

## 4. Gör underhändelsefiltrering {#sub-event}

Den här funktionen gäller specifikt för matrisbaserade fält. Med funktionerna för att inkludera/exkludera kan du filtrera på underhändelsenivå, medan filter (segment) som är inbyggda i filterverktyget bara ger dig filtrering på händelsenivå. Du kan alltså filtrera efter händelser genom att använda Inkludera/Exkludera i datavyer och sedan referera till det nya måttet/måttet i ett filter på händelsenivå.

Använd till exempel funktionerna Inkludera/exkludera i datavyer om du bara vill fokusera på produkter som genererade mer än 50 dollar för försäljning. Om du har en beställning som innehåller ett produktköp på 50 dollar och ett inköp på 25 dollar tar vi bara bort 25 dollar, inte hela beställningen.

1. På datavyer [Komponenter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings) -fliken, dra [!UICONTROL Revenue] schemafält till [!UICONTROL Metrics] areal under [!UICONTROL Included components].
1. Markera måtten och konfigurera följande på höger sida: a. Under [!UICONTROL Format], markera [!UICONTROL Currency].
b. Under [!UICONTROL Currency]väljer du USD.
c. Under [!UICONTROL Include/Exclude Values]markerar du kryssrutan bredvid [!UICONTROL Set include/exclude values].
d. Under [!UICONTROL Match], markera [!UICONTROL If all criteria are met].
e. Under [!UICONTROL Criteria], markera [!UICONTROL is greater than or equal].
f. Ange&quot;50&quot; som värde.

Med de här nya inställningarna kan du bara visa värdefulla intäkter och filtrera bort vad som helst under 50 dollar.

## 5. Använd [!UICONTROL No Value Options] inställning {#no-value}

Företaget kan ha ägnat tid åt att utbilda dina användare så att de förväntar sig&quot;Ospecificerat&quot; i rapporter. Standardvärdet i datavyer är &quot;Inget värde&quot;. Nu kan du [ändra namn på &quot;Inget värde&quot; till &quot;Ospecificerat&quot;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-no-value-options-settings) i användargränssnittet för datavyer.

Ett annat exempel är en dimension för registrering av medlemsprogram. I det här fallet kan du ändra namnet&quot;Inget värde&quot; till&quot;Inget medlemskap i programmet&quot;.

## 6. Skapa flera mätvärden med olika [!UICONTROL Attribution] inställningar {#attribution}

Använda [!UICONTROL Duplicate] i det övre högra hörnet skapar du ett antal intäktsmått med olika attribueringsinställningar som [!UICONTROL First Touch], [!UICONTROL Last Touch]och [!UICONTROL Algorithmic].

Glöm inte att byta namn på varje mätvärde för att återspegla skillnaderna, t.ex.&quot;Algoritmisk omsättning&quot;:

![](assets/algo-revenue.png)

Mer information om andra datavyinställningar finns i [Skapa datavyer](/help/data-views/create-dataview.md).
En konceptuell översikt över datavyer finns på [Översikt över datavyer](/help/data-views/data-views.md).

## 7. Ny sessionsrapportering {#new-repeat}

Du kan avgöra om en session faktiskt är den första sessionen någonsin för en användare eller inte, baserat på det rapportfönster som du har definierat för datavyn och ett 13-månaders uppslagsfönster. Med den här rapporten kan du till exempel avgöra:

* Hur stor procentandel av dina beställningar kommer från nya sessioner?

* För en viss marknadsföringskanal, eller en viss kampanj, riktar ni er till förstagångsanvändare? Hur påverkar detta valet konverteringsgraden?

Ett mått underlättar den här rapporteringen:

<!--* 1 dimension: [Session type](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional) - This dimension has two values: 1) [!UICONTROL New] and 2) [!UICONTROL Returning]. The [!UICONTROL New] line item includes all of the behavior (i.e. metrics against this dimension) from a session that has been determined to be a person's defined first session. Everything else is included in the [!UICONTROL Returning] line item (assuming everything belongs to a session). Where metrics are not part of any session, they fall into the 'Not applicable' bucket for this dimension.-->

* [Nya sessioner](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional). En ny session definieras som en persons definierade första session i rapportfönstret.

   <!--* [Return sessions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional) Return sessions is the number of sessions that were not a person's first-ever session.-->

Så här kommer du åt den här komponenten:

1. Gå till datavyredigeraren.
1. Klicka på **[!UICONTROL Components]** > **[!UICONTROL Optional Standard components]** tabben i den vänstra listen.
1. Dra dessa komponenter till datavyn.

95-99 % av tiden rapporteras nya sessioner korrekt. De enda undantagen är:

* När en första session ägde rum före 13-månaders uppslagsfönster. Den här sessionen kommer att ignoreras.

* När en session sträcker sig över både uppslagsfönstret och rapportfönstret. Låt oss säga att du har en rapport från 1 juni till 15 juni 2022. Fönstret för uppslag skulle omfatta 1 maj 2021 till 31 maj 2022. Om en session skulle påbörjas den 30 maj 2022 och avslutas den 1 juni 2022 eftersom sessionen ingår i uppslagsfönstret, räknas alla sessioner i rapportfönstret som retursessioner.

<!--## Use the Date and Date-Time functionality {#date}

Schemas in Adobe Experience Platform contain [!UICONTROL Date] and [!UICONTROL Date-Time] fields. CJA data views now support these fields. When you drag these fields into a data view as a dimension, you can specify their [format](/help/data-views/component-settings/format.md). This format setting determines how the fields are displayed in reporting. For example:

* For the Date format, if you select **[!UICONTROL Day]** with the format **[!UICONTROL Month, Day, Year]**, an example output in reporting might look like: August 23, 2022.

* For the Date-Time format, if you select **[!UICONTROL Minute of Day]** with the format **[!UICONTROL Hour:Minute]**, your output might look like: 20:20.

### Example use cases:

* Date: A travel company is collecting the departure date for trips as a field in their data. They would like to have a report which compares the [!UICONTROL Day of Week] for all departure dates collected to understand which is most popular. They would like to do the same for [!UICONTROL Month of Year].

* Date-Time: A retail company is collecting the time for each of their in-store point-of-sale (POS) purchases. Over a given month, they would like to understand the busiest shopping periods by [!UICONTROL Hour of Day].

>[!MORELIKETHIS]
>[Date and Date-Time in the Format component setting](/help/data-views/component-settings/format.md)-->

