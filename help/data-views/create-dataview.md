---
title: Skapa eller redigera en datavy
description: Alla inställningar som du kan justera för att skapa eller redigera en datavy.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c106e178c5aecdaf061001247a1ee6ef183d043e
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 0%

---

# Skapa eller redigera en datavy

När du skapar en datavy måste du antingen skapa mått och mått från schemaelement eller använda standardkomponenter. De flesta schemaelement kan antingen vara en dimension eller ett mått beroende på företagets behov. När du drar ett schemaelement till en datavy visas alternativ till höger, där du kan justera hur dimensionen eller mätningen fungerar i Customer Journey Analytics.

Här är en video om ämnet:

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

Så här skapar eller redigerar du en datavy:

1. Logga in på [Customer Journey Analytics](https://analytics.adobe.com) och går till **[!UICONTROL Data views]** -fliken.
1. Om du vill skapa en datavy väljer du **[!UICONTROL Create new data view]**. Du kan också välja en befintlig datavy i listan över datavyer för att redigera den.


## Konfigurera

Så här konfigurerar du en ny eller befintlig datavy:

1. Välj **[!UICONTROL Configure]** -flik (om den inte redan är aktiv).

   ![Konfigurera datavy](assets/dataview-configure.png)
1. Ange [!UICONTROL Settings], [!UICONTROL Container]och [!UICONTROL Calendar] information (se nedan).
1. Välj **[!UICONTROL Save and continue]** för att fortsätta konfigurera din nya eller befintliga datavy. Välj **[!UICONTROL Save]** för att spara konfigurationen för den befintliga datavyn.


### Inställningar

Innehåller övergripande inställningar för datavyn.

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Connection] | Det här fältet länkar datavyn till anslutningen som du upprättade tidigare, som innehåller en eller flera Adobe Experience Platform-datauppsättningar. |
| [!UICONTROL Name] | Obligatoriskt. Datavyns namn. Värdet visas i den övre högra listrutan i Analysis Workspace. |
| [!UICONTROL Description] | Valfritt. Adobe rekommenderar en detaljerad beskrivning så att användarna förstår varför datavyn finns och vem den är avsedd för. |

{style="table-layout:auto"}

### Behållare

Anger namnet på behållare för datavyn. Behållarnamn används ofta i [filter](/help/components/filters/filters-overview.md#Filter-containers).

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Person container name] | [!UICONTROL Person] (standard). The [!UICONTROL Person] behållare innehåller alla sessioner och händelser för personer inom den angivna tidsramen. Om din organisation använder en annan term (till exempel &quot;Besökare&quot; eller &quot;Användare&quot;) kan du byta namn på behållaren här. |
| [!UICONTROL Session container name] | [!UICONTROL Session] (standard). The [!UICONTROL Session] kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session. Du kan byta namn på den här behållaren till &#39;Besök&#39; eller någon annan term som din organisation föredrar. |
| [!UICONTROL Event container name] | [!UICONTROL Event] (standard). The [!UICONTROL Event] container definierar enskilda händelser i en datamängd. Om din organisation använder en annan term (till exempel &quot;träffar&quot; eller &quot;Sidvisningar&quot;) kan du byta namn på behållaren här. |

{style="table-layout:auto"}

### Kalender

Anger det kalenderformat som du vill att datavyn ska följa. Du kan ha flera datavyer baserade på samma [Anslutning](/help/connections/create-connection.md) och ge dem olika kalendertyper eller tidszoner. Dessa datavyer kan göra det möjligt för team som använder olika kalendertyper att tillgodose sina respektive behov med samma underliggande data.

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Time zone] | Välj vilken tidszon du vill att dina data ska visas i. Om du väljer en tidszon som fungerar med sommartid justeras data automatiskt för att återspegla det. På våren, när klockorna justerar en timme framåt, finns det en lucka på en timme. I fallet, när klockorna justeras en timme bakåt, upprepas en timme under DST-skiftet. |
| [!UICONTROL Calendar Type] | Bestäm hur veckors i månaden ska grupperas.<br>**Gregorianska:** Standardkalenderformat. Kvartal grupperas efter månad.<br>**4-5-4 Detaljhandel:** En standardiserad 4-5-4-kalender för detaljhandeln. Den första och sista månaden i kvartalet innehåller 4 veckor, medan den andra månaden i kvartalet består av 5 veckor.<br>**Anpassad (4-5-4):** Liknar kalendern 4-5-4 förutom att du kan välja den första dagen på året och vilket år som den extra veckan inträffar.<br>**Anpassad (4-4-5):** Den första och den andra månaden i varje kvartal innehåller 4 veckor, medan den sista veckan i varje kvartal består av 5 veckor.<br>**Anpassad (5-4-4):** Den första månaden i varje kvartal består av 5 veckor, medan den andra och tredje månaden i varje kvartal består av 4 veckor. |
| [!UICONTROL First month of the year] och [!UICONTROL First day of week] | Synlig för den gregorianska kalendertypen. Ange vilken månad du vill att kalenderåret ska börja på och vilken dag du vill att varje vecka ska börja på. |
| [!UICONTROL First day of current year] | Synlig för anpassade kalendertyper. Ange vilken dag på året som du vill att det aktuella året ska börja. Kalendern formaterar automatiskt den första dagen i varje vecka baserat på det här värdet. |
| [!UICONTROL Year in which the "extra" week occurs] | Med de flesta 364-dagars kalendrar (52 veckor på 7 dagar vardera) ackumulerar varje år kvarvarande dagar tills de blir upp till en extra vecka. Den här extra veckan läggs sedan till den sista månaden under det året. Ange vilket år du vill lägga till den extra veckan i. |

{style="table-layout:auto"}

## Komponenter

Sedan kan du ange komponenterna i en datavy, vilket betyder att du kan skapa mått och mått utifrån schemaelement. Du kan också använda standardkomponenter.

>[!IMPORTANT]
>
>Upp till 5 000 mätvärden och 5 000 dimensioner kan läggas till i en enda datavy.

1. Välj **[!UICONTROL Components]** -fliken.

   ![Fliken Komponenter](assets/dataview-components.png)

   Du kan se [!UICONTROL Connection] överst till vänster, som innehåller datauppsättningarna, och [!UICONTROL Schema fields] nedan.  Komponenterna som redan ingår är standardkomponenter (systemgenererade) som krävs för alla datavyer (som händelser, personer, sessionsmätningar och måtten Minute, Quarter, Week). Adobe använder också filtret **[!UICONTROL Contains data]** och **[!UICONTROL is not deprecated]** som standard visas endast schemafält som innehåller data och som inte är inaktuella.

1. Sök efter ett schemafält med ![Ikonen Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Search schema fields]** eller hitta ett fält genom att flytta till någon av datauppsättningssamlingarna, som ![Mappikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg) **[!UICONTROL Event datasets]**.<br/>Du kan också skapa ett härlett fält med ![Dataikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Skapa härlett fält** . Se [Härledda fält](./derived-fields/derived-fields.md) för mer information.

1. När du har hittat ett specifikt schemafält eller definierat det härledda fältet drar du det fältet, till exempel ![Hantera, ikon](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Page Name]**från den vänstra listen till avsnittet Metrisk eller Dimension.
Du kan dra samma schemafält till dimensionerna eller måttavsnitten flera gånger och konfigurera samma mått eller mätvärden på olika sätt. I fältet pageName kan du till exempel skapa en dimension med namnet&quot;Produktsidor&quot; och en annan&quot;Felsidor&quot; genom att använda en annan [Komponentinställningar](component-settings/overview.md) till höger.
Om du drar en mapp för schemafält från den vänstra listen sorteras de automatiskt i vanliga avsnitt. Strängfält hamnar i [!UICONTROL Dimensions] -avsnitt och numeriska schematyper hamnar i [!UICONTROL Metrics] -avsnitt. Du kan också klicka **[!UICONTROL Add all]** och alla schemafält läggs till på respektive plats.

1. När du har valt en komponent visas inställningarna till höger.

   ![Datavy-komponent vald](assets/dataview-component-pagename.png)

   Konfigurera komponenten med [Komponentinställningar](component-settings/overview.md). Vilka komponentinställningar som är tillgängliga beror på om komponenten är en dimension/mätare och schemadatatypen. Inställningarna inkluderar:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Behavior]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Include exclude values]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Metric deduplication]](component-settings/metric-deduplication.md)
   * [[!UICONTROL No value options]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistence]](component-settings/persistence.md)
   * [[!UICONTROL Value bucketing]](component-settings/value-bucketing.md)

1. Välj **[!UICONTROL Save and continue]** för att fortsätta konfigurera din nya eller befintliga datavy. Välj **[!UICONTROL Save]** för att spara konfigurationen för den befintliga datavyn.

**Duplicera mått eller dimensioner**

Att duplicera mått och dimensioner och sedan ändra specifika inställningar är ett enkelt sätt att skapa flera mått eller dimensioner från ett enda schemafält. Välj [!UICONTROL Duplicate] inställningen under måttets eller dimensionernas namn högst upp till höger. Ändra den nya dimensionen eller måttet och spara det under ett mer beskrivande namn.

**Filtrera schemafält eller datauppsättningar**

Du kan filtrera ![Filterikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) schemafält i den vänstra listen med [!UICONTROL data type], [!UICONTROL datasets], [!UICONTROL data governance]och [!UICONTROL other] kriterier ([!UICONTROL contains data], [!UICONTROL is identity]och [!UICONTROL is not deprecated]):

![Filtrera fält](assets/dataview-components-filter.png)

>[!TIP]
>
>Om komponenterna inte läses in korrekt i datavyn och du får ett felmeddelande istället, se [Brist på behörigheter](../troubleshooting/lack-of-permissions.md) för en lösning.



## Inställningar

1. Välj **[!UICONTROL Settings]** -fliken.
1. Konfigurera filter som ska användas i hela datavyn. Se [Inställningar (filter)](#settings-filters) nedan.
1. Konfigurera timeout och mått för sessioner. Se [Sessionsinställningar](#session-settings) nedan.
1. Välj **[!UICONTROL Save and continue]** för att fortsätta konfigurera din nya eller befintliga datavy. Välj **[!UICONTROL Save]** för att spara konfigurationen för den befintliga datavyn.

### Inställningar (filter)

Du kan lägga till filter som gäller för en hel datavy. Det här filtret tillämpas på alla rapporter som du kör i Workspace. Dra ett filter från listan i den vänstra listen till vänster [!UICONTROL Add filters] fält.

### Sessionsinställningar

Fastställ inaktivitetstiden mellan händelser innan en session förfaller och en ny påbörjas. En tidsperiod krävs. Du kan också tvinga en ny session att starta när en händelse innehåller ett visst mått. Se [Sessionsinställningar](session-settings.md) för mer information.

När du har angett alla inställningar klickar du på **[!UICONTROL Save and finish]**.
