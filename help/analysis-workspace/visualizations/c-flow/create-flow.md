---
description: Lär dig hur du använder flödesvisualisering i ett Workspace-projekt.
title: Konfigurera en flödesvisualisering
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1371'
ht-degree: 0%

---

# Konfigurera en flödesvisualisering {#configure-a-flow-visualization}

>[!CONTEXTUALHELP]
>id="workspace_flow_container"
>title="Flödesbehållare"
>abstract="Välj den behållare som ska användas för att visa (siffror för) banan."


Flödesvisualiseringar hjälper er att förstå den resa som följer av en specifik konverteringshändelse på er webbplats eller i er app. Eller leda upp till en viss konverteringshändelse. Visualiseringen spårar en bana genom dina dimensioner (och dimensionsobjekt) eller mätvärden.

Du kan konfigurera början eller slutet av sökvägen som du är intresserad av. Eller analysera alla banor som flödar genom en dimension eller dimensionspost.

![Skärmen Flödeskonfiguration visar fälten Börjar med, Innehåller och Slutar med.](assets/new-flow.png)

## Använd

1. Lägg till en ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]**-visualisering. Se [Lägga till en visualisering på en panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Förankra Flödesvisualiseringen med något av följande alternativ:

   * [!UICONTROL **Börjar med**] (mått, dimensioner eller objekt), eller
   * [!UICONTROL **Innehåller**] (dimensioner eller objekt), eller
   * [!UICONTROL **Slutar med**] (mått, dimensioner eller objekt)

   Var och en av dessa kategorier visas på skärmen som en *släppzon*. Du kan fylla i släppzonen på tre sätt:

   * Använd listrutan för att välja mått eller mått.
   * Dra mått eller mätvärden från den vänstra panelen.
   * Börja skriva namnet på en dimension eller ett mått och markera det sedan när det visas i listrutan.

   >[!IMPORTANT]
   >
   >Beräknade mått kan inte användas i fälten **[!UICONTROL Starts with]** eller **[!UICONTROL Ends with]**.

1. Om du väljer ett mätvärde måste du även ange en [!UICONTROL **Sökväg-Dimension**] som du kan använda som sökväg som leder till eller kommer från den markerade komponenten, vilket visas här. Standardvärdet är [!UICONTROL **Sida**].

   ![Flödeskonfiguration](assets/flow-configure.png)

1. (Valfritt) Välj **[!UICONTROL Show advanced settings]** om du vill konfigurera något av följande alternativ:


   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Etiketterna på Flow-elementen trunkeras normalt för att spara skärmutrymme, men du kan göra hela etiketten synlig genom att markera den här rutan.  Standard = avmarkerat. |
   | **[!UICONTROL Include repeat instances]** | Flödesvisualiseringar baseras på instanser av en dimension. Den här inställningen ger dig möjlighet att inkludera eller exkludera upprepade instanser, till exempel Sidomladdning. Det går dock inte att ta bort upprepningar från Flow-visualiseringar som innehåller flervärdesdimensioner, som listVars, listProps, s.product, merchandising eVars osv. <p>Det här alternativet är inaktiverat som standard.</p> |
   | **[!UICONTROL Limit to first/last occurrence]** | Begränsa banor till banor som börjar eller slutar med den första eller sista förekomsten av en dimension, artikel eller mätvärde. Mer information finns i [Begränsa till första/sista förekomsten](#example-scenario-for-limit-to-firstlast-occurrence). |
   | **[!UICONTROL Number of columns]** | Antalet kolumner som du vill ha i flödesdiagrammet. Du kan ange högst fem kolumner. |
   | **[!UICONTROL Items expanded per column]** | Antalet objekt som du vill ha i varje kolumn. Du kan ange högst 10 objekt utökade per kolumn. |
   | **[!UICONTROL Flow container]** | Du kan växla mellan **[!UICONTROL Global Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Buying Group]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Sessions]** och **[!UICONTROL Person]** för att analysera målningen. Dessa inställningar hjälper dig att förstå en persons engagemang på personnivå (mellan sessioner) eller begränsa analysen till en enda session. |

   >[!IMPORTANT]
   >
   >Kombinationen av **[!UICONTROL Number of columns]** och **[!UICONTROL Items expanded per column]** avgör antalet underliggande begäranden som krävs för att skapa flödesvisualiseringen. Ju högre tal, desto längre tid tar det att återge en visualisering.


1. Välj **[!UICONTROL Build]**.


### Exempel

Anta att du vill spåra sökvägen som användare tog både till och från de mest populära sidorna på din webbplats.

1. Skapa en flödesvisualisering enligt beskrivningen ovan.
1. Dra dimensionen [!UICONTROL **Sida**] till fältet **[!UICONTROL Contains]** och välj sedan [!UICONTROL **Skapa**].
1. Flödesvisualiseringen byggs, med den mest visade sidan synlig i fokusnoden, i mitten av visualiseringen. Du kan även se de översta sidorna som leder till den sidan (till vänster om fokusnoden) samt de översta sidorna som leder ut från den sidan (till höger om fokusnoden).
1. Analysera data i flödet enligt beskrivningen i [Konfigurera](#configure).


## Konfigurera

En sammanfattning av flödeskonfigurationen visas högst upp i visualiseringarna. Banorna i diagrammet är proportionella. Banor med mer aktivitet ser tjockare ut.

![Exempel på flödesutdata som visar Slut med besök, Sökningsdimension: Sida och Flödesbehållare: Stors.](assets/flow-output.png)

Om du vill gå längre ned i informationen har du flera alternativ:

* Flödesdiagrammet är interaktivt. För musen över diagrammet för att ändra de detaljer som visas.

* När du markerar en nod i diagrammet visas information om den noden. Markera noden igen för att komprimera den.

  ![Exempel på interaktivt flödesdiagram med nodinformation.](assets/node-details.png)

* Du kan filtrera en kolumn så att endast vissa resultat visas, t.ex. inkludera och exkludera, ange villkor osv.

* Välj ![AddCircle](/help/assets/icons/AddCircle.svg) till vänster eller höger för att expandera en kolumn.

* Använd alternativen på [snabbmenyn](#context-menu) om du vill anpassa utdata.

* Om du vill redigera flödet eller återskapa det med andra alternativ väljer du ![Redigera](/help/assets/icons/Edit.svg) bredvid konfigurationssammanfattningen.

## Filter

Ovanför varje kolumn visas ett filter, ![Filter](/help/assets/icons/Filter.svg), när du hovrar över den. Genom att markera filtret får du samma filterdialogruta som finns i friformstabellen. Se [Filtrera och sortera](freeform-table/../../freeform-table/filter-and-sort.md).

* Använd **[!UICONTROL Show advanced]** om du vill konfigurera avancerade inställningar så att vissa villkor inkluderas eller exkluderas med en lista över operatorer. Mer information finns i [Filter och sortering](../freeform-table/filter-and-sort.md).
* När du har filtrerat en kolumn återspeglas filtreringen i den kolumnen. Ett blått ![filter](/help/assets/icons/FilterColored.svg) anger att kolumnen är filtrerad.  Filtret minskar antingen kolumnen så att bara det objekt som är tillåtet i filtret visas. Eller så tas alla objekt bort, förutom det objekt som du vill ha med i filtret.
* Alla kolumner som är nedströms och uppströms bevaras, så länge som det finns data som flödar in i de återstående noderna.
* Om du vill ta bort ett filter väljer du ![Filter](/help/assets/icons/Filter.svg) för att öppna filtermenyn. Ta bort eventuella filter som använts och välj sedan **[!UICONTROL Save]**. Flödet bör återgå till det tidigare, ofiltrerade läget.

## Snabbmeny

Använd en snabbmeny på en nod i flödesvisualiseringen med följande alternativ:

| Alternativ | Beskrivning |
|--- |--- |
| **[!UICONTROL Focus on this node]** | Ändra fokus till den valda noden. Flödesdiagrammets fokusnod visas i mitten. |
| **[!UICONTROL Start over]** | Gå tillbaka till Frihandsdiagramverktyget där du kan skapa ett nytt flödesdiagram. |
| **[!UICONTROL Create a segment for this path]** | Skapa ett segment. Det här valet tar dig in i segmentbyggaren, där du kan konfigurera det nya segmentet. |
| **[!UICONTROL Breakdown]** | Dela upp noden efter tillgängliga mått, mått eller tid. |
| **[!UICONTROL Filter column]** | Samma filteralternativ visas som de är tillgängliga i frihandstabellen. Mer information om de tillgängliga alternativen finns i avsnittet Använda ett enkelt eller avancerat filter i en tabell i [Filtrera och sortera tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| **[!UICONTROL Exclude item]** eller **[!UICONTROL Restore excluded items]** | Tar bort en specifik nod från kolumnen och skapar den automatiskt som ett filter överst i kolumnen. Om du vill återställa det uteslutna objektet väljer du **[!UICONTROL Restore Excluded Item]** på snabbmenyn. Du kan också öppna segmentet överst i kolumnen och ta bort rutan med det objekt du just uteslutit. |
| **[!UICONTROL Trend]** | Skapa ett trenddiagram för noden. |
| **[!UICONTROL Show next column]** / **[!UICONTROL Show previous column]** | Visar nästa (höger) eller föregående (vänster) kolumn i visualiseringen. |
| **[!UICONTROL Hide colum]**n | Döljer den markerade kolumnen från visualiseringen. |
| **[!UICONTROL Expand entire column]** | Expandera en kolumn om du vill visa alla noder. Som standard visas bara de fem översta noderna. |
| **[!UICONTROL Create audience from selection]** | Skapar en målgrupp baserat på den markerade kolumnen. |
| **[!UICONTROL Collapse entire column]** | Dölj alla noder i en kolumn. |

## Begränsa till första/sista förekomsten

Tänk på följande när du använder det här alternativet:

* **[!UICONTROL Limit to first/last occurrence]** räknar endast den första/sista förekomsten i serien. Alla andra förekomster av villkoret **[!UICONTROL Starts with]** eller **[!UICONTROL Ends with]** ignoreras.
* Om den används med ett **[!UICONTROL Starts with]**-flöde inkluderas endast den första förekomsten som matchar startvillkoret.
I exemplet nedan inkluderas **alla** förekomster av *Lägg i kundvagnen* och *huvudkategorin för produkten* i varje steg i flödet.
  ![Ingen begränsning, först](assets/limitofffirst.png)

  I exemplet nedan inkluderas bara de **första** förekomsterna av *Lägg till i kundvagnen* och *produkthuvudkategorin* i varje steg i flödet.
  ![Lint, start](assets/limitonfirst.png)
* Om den används med ett **[!UICONTROL Ends with]**-flöde inkluderas endast den sista förekomsten som matchar slutvillkoret.
I exemplet nedan inkluderas **alla** förekomster av *huvudkategorin för produkten* och *Lägg till i kundvagnen* i varje steg i flödet.
  ![Ingen begränsning, först](assets/limitofflast.png)

  I exemplet nedan inkluderas bara de **sista** förekomsterna av *huvudkategorin för produkten* och *Lägg i kundvagnen* i varje steg i flödet.
  ![Lint, start](assets/limitonlast.png)
* Serien som används skiljer sig åt beroende på behållaren. Om du använder behållaren **[!UICONTROL Person]** är händelserierna sessionen. Om du använder behållaren **[!UICONTROL Session]** är händelserierna alla händelser för en viss användare i det angivna datumintervallet.
* Alternativet **[!UICONTROL Limit to first/last occurrence]** kan konfigureras i de avancerade inställningarna när du använder ett mått eller ett Dimension-objekt i fälten **[!UICONTROL Starts with]** eller **[!UICONTROL Ends with]**.


>[!MORELIKETHIS]
>
>[Lägg till en visualisering på en panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualiseringsinställningar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Snabbmenyn Visualisering ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

