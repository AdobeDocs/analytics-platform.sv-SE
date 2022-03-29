---
title: Skapa eller redigera en datavy
description: Alla inställningar som du kan justera för att skapa eller redigera en datavy.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 48cc438032fb1df043b7caf085aadf3f2c2f1ecf
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Skapa eller redigera en datavy

När du skapar en datavy måste du antingen skapa mått och mått från schemaelement eller använda standardkomponenter. De flesta schemaelement kan antingen vara en dimension eller ett mått beroende på företagets behov. När du drar ett schemaelement till en datavy visas alternativ till höger, där du kan justera hur dimensionen eller måttet fungerar i CJA.

Här är en video om ämnet:

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

## Konfigurera en datavy {#configure}

1. Logga in på [Customer Journey Analytics](https://analytics.adobe.com) och går till **[!UICONTROL Data Views]** -fliken.
2. Klicka **[!UICONTROL Add]** om du vill skapa en datavy eller klicka på en befintlig datavy för att redigera den.

![Ny datavy](assets/new-data-view.png)

### Inställningar för datavy {#settings}

Innehåller övergripande inställningar för datavyn.

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Connection] | Det här fältet länkar datavyn till anslutningen som du upprättade tidigare, som innehåller en eller flera Adobe Experience Platform-datauppsättningar. |
| [!UICONTROL Name] | Obligatoriskt. Datavyns namn. Det här värdet visas i den övre högra listrutan i Analysis Workspace. |
| [!UICONTROL Description] | Valfritt. Adobe rekommenderar en detaljerad beskrivning så att användarna förstår varför datavyn finns och vem den är avsedd för. |

### Behållare {#containers}

Anger namnet på behållare för datavyn. Behållarnamn används ofta i [filter](/help/components/filters/filters-overview.md#Filter-containers).

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Person container name] | [!UICONTROL Person] (standard). The [!UICONTROL Person] behållare innehåller alla sessioner och händelser för besökare inom den angivna tidsramen. Om din organisation använder en annan term (till exempel &quot;Besökare&quot; eller &quot;Användare&quot;) kan du byta namn på behållaren här. |
| [!UICONTROL Session container name] | [!UICONTROL Session] (standard). The [!UICONTROL Session] kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session. Du kan byta namn på den här behållaren till &#39;Besök&#39; eller någon annan term som din organisation föredrar. |
| [!UICONTROL Event container name] | [!UICONTROL Event] (standard). The [!UICONTROL Event] container definierar enskilda händelser i en datamängd. Om din organisation använder en annan term (till exempel &quot;träffar&quot; eller &quot;Sidvisningar&quot;) kan du byta namn på behållaren här. |

### Kalender {#calendar}

Anger det kalenderformat som du vill att datavyn ska följa. Du kan ha flera datavyer baserade på samma [Anslutning](/help/connections/create-connection.md) och ge dem olika kalendertyper eller tidszoner. Dessa datavyer kan göra det möjligt för team som använder olika kalendertyper att tillgodose sina respektive behov med samma underliggande data.

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Time zone] | Välj vilken tidszon du vill att dina data ska visas i. Om du väljer en tidszon som fungerar med sommartid justeras data automatiskt för att återspegla det. På våren, när klockorna justerar en timme framåt, finns det en lucka på en timme. I fall där klockorna justeras en timme bakåt upprepas en timme under DST-skiftet. |
| [!UICONTROL Calendar Type] | Bestäm hur veckor i månaden ska grupperas.<br>**Gregorianska:** Standardkalenderformat. Kvartal grupperas efter månad.<br>**4-5-4 Detaljhandel:** En standardiserad 4-5-4-kalender. Den första och sista månaden i kvartalet innehåller 4 veckor, medan den andra månaden i kvartalet består av 5 veckor.<br>**Anpassad (4-5-4):** Liknar kalendern 4-5-4 förutom att du kan välja den första dagen på året och vilket år som den extra veckan inträffar.<br>**Anpassad (4-4-5):** Den första och andra månaden i varje kvartal innehåller 4 veckor, medan den sista veckan i varje kvartal består av 5 veckor.<br>**Anpassad (5-4-4):** Den första månaden i varje kvartal består av 5 veckor, medan den andra och tredje månaden i varje kvartal består av 4 veckor. |
| [!UICONTROL First month of the year] och [!UICONTROL First day of week] | Synlig för den gregorianska kalendertypen. Ange vilken månad du vill att kalenderåret ska börja på och vilken dag du vill att varje vecka ska börja på. |
| [!UICONTROL First day of current year] | Synlig för anpassade kalendertyper. Ange vilken dag på året som du vill att det aktuella året ska börja. Kalendern formaterar automatiskt den första dagen i varje vecka baserat på det här värdet. |
| [!UICONTROL Year in which the "extra" week occurs] | Med de flesta 364-dagars kalendrar (52 veckor på 7 dagar vardera) ackumulerar varje år kvarvarande dagar tills de utgör en extra vecka. Den här extra veckan läggs sedan till den sista månaden under det året. Ange vilket år du vill att den extra veckan ska läggas till i. |

## Ställa in komponenterna i en datavy {#set-components}

Sedan kan du skapa mått och mått utifrån schemaelement. Du kan också använda standardkomponenter.

1. Logga in på [Customer Journey Analytics](https://analytics.adobe.com) och går till **[!UICONTROL Data Views]** -fliken.
1. Klicka **[!UICONTROL Add]** om du vill skapa en datavy eller klicka på en befintlig datavy för att redigera den.
1. Klicka på **[!UICONTROL Components]** -fliken.

   ![Fliken Komponenter](assets/components-tab.png)

   Du kan se [!UICONTROL Connection] överst till vänster, som innehåller datauppsättningarna, och [!UICONTROL Schema fields] nedan. Observera att de komponenter som redan ingår är nödvändiga standardkomponenter (systemgenererade) för alla datavyer. Adobe använder också filtret **[!UICONTROL Contains data]** som standard så att endast schemafält som innehåller data visas. Om du vill ha ett fält som inte innehåller data tar du bort det här filtret.

1. Dra ett schemafält, till exempel `pageTitle`från den vänstra listen till avsnittet Metrisk eller Dimension.

   Du kan dra samma schemafält till dimensionerna eller måttavsnitten flera gånger och konfigurera samma mått eller mätvärden på olika sätt. Från `pageTitle` kan du skapa en dimension med namnet&quot;Produktsidor&quot; och en annan&quot;Felsidor&quot; genom att använda olika [Komponentinställningar](component-settings/overview.md) till höger.

   ![Flik 3](assets/components-tab-3.png)

   Om du drar en mapp för schemafält från den vänstra listen sorteras de automatiskt i vanliga avsnitt. Strängfält hamnar i [!UICONTROL Dimensions] -avsnitt och numeriska schematyper hamnar i [!UICONTROL Metrics] -avsnitt. Du kan också klicka **[!UICONTROL Add all]** och alla schemafält läggs till på respektive plats.

1. När du har valt komponenten visas ett antal inställningar till höger. Konfigurera komponenten med [Komponentinställningar](component-settings/overview.md). Vilka komponentinställningar som är tillgängliga beror på om komponenten är en dimension/mätare och schemadatatypen. Inställningarna inkluderar:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Behavior]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Include exclude values]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Metric deduplication]](component-settings/metric-deduplication.md)
   * [[!UICONTROL No value options]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistence]](component-settings/persistence.md)
   * [[!UICONTROL Value bucketing]](component-settings/value-bucketing.md)

## Duplicera mått eller dimensioner {#duplicate}

Att duplicera mått och dimensioner och sedan ändra specifika inställningar är ett enkelt sätt att skapa flera mått eller dimensioner från ett enda schemafält. Välj [!UICONTROL Duplicate] inställningen under måttets eller dimensionernas namn högst upp till höger. Ändra den nya dimensionen eller måttet och spara det under ett mer beskrivande namn.

![Duplicera](assets/duplicate.png)

## Filtrera schemafält eller datauppsättningar {#filter}

Du kan filtrera schemafält i den vänstra listen med följande datatyper:

![Filtrera fält](assets/filter-fields.png)

Du kan också filtrera efter datauppsättningar och efter om ett schemafält innehåller data eller om det är en identitet. Som standard använder Adobe från början **[!UICONTROL Contains data]** filtrera till alla datavyer.

![Filtrera andra](assets/filter-other.png)

## Fliken Inställningar {#settings-tab}

1. Logga in på [Customer Journey Analytics](https://analytics.adobe.com) och går till **[!UICONTROL Data Views]** -fliken.
1. Klicka **[!UICONTROL Add]** om du vill skapa en datavy eller klicka på en befintlig datavy för att redigera den.
1. Klicka på **[!UICONTROL Settings]** -fliken.

### Globalt filter {#global-filter}

Du kan lägga till filter som gäller för en hel datavy. Det här filtret tillämpas på alla rapporter som du kör i Workspace. Dra ett filter från listan i den vänstra listen till vänster [!UICONTROL Add filters] fält.

### Sessionsinställningar {#sessions}

Fastställ inaktivitetstiden mellan händelser innan en session förfaller och en ny påbörjas. En tidsperiod krävs. Du kan också tvinga en ny session att starta när en händelse innehåller ett visst mått.

När du har angett alla inställningar klickar du på **[!UICONTROL Save and finish]**.
