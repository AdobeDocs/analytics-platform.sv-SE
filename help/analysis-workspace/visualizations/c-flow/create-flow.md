---
description: Lär dig hur du använder flödesvisualisering i ett Workspace-projekt.
title: Konfigurera en flödesvisualisering
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: b196b8c05ba05a3f46d71c10fdcaa2ad8ef0dcd6
workflow-type: tm+mt
source-wordcount: '1483'
ht-degree: 0%

---

# Konfigurera en flödesvisualisering

Flödesvisualiseringar hjälper er att förstå den resa som härrör från eller leder fram till en specifik konverteringshändelse på er webbplats eller i er app. Den spårar en bana genom dina dimensioner (och dimensionsobjekt) eller mätvärden.

Med flödesvisualiseringar kan du konfigurera början eller slutet av den sökväg du är intresserad av, eller analysera alla banor som flödar genom en dimension eller dimensionspost.

![Skärmen Flödeskonfiguration visar fälten Börjar med, Innehåller och Slutar med.](assets/new-flow.png)

## Skapa en flödesvisualisering {#configure}

1. Lägg till en tom panel i projektet, markera ikonen Visualiseringar i den vänstra listen och dra sedan [!UICONTROL **Flödesvisualiseringen**] till panelen.

   eller

   Lägg till en visualisering på något av de sätt som beskrivs i avsnittet Lägg till visualiseringar i en panel i [Översikt över visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Förankra Flödesvisualiseringen med något av följande alternativ:

   * [!UICONTROL **Börjar med**] (mått, dimensioner eller objekt), eller
   * [!UICONTROL **Innehåller**] (dimensioner eller objekt), eller
   * [!UICONTROL **Slutar med**] (mått, dimensioner eller objekt)

   Var och en av dessa kategorier visas på skärmen som en&quot;släppzon&quot;. Du kan fylla i släppzonen på tre sätt:

   * Använd listrutan för att välja mått eller mått.
   * Dra mått eller mätvärden från den vänstra listen.
   * Börja skriva namnet på en dimension eller ett mått och markera det sedan när det visas i listrutan.

   >[!IMPORTANT]
   >
   >Beräknade mått kan inte användas i fälten **[!UICONTROL Starts with]** eller **[!UICONTROL Ends with]**.

1. Om du väljer ett mätvärde måste du även ange en [!UICONTROL **Dimension**] som du kan använda som sökväg som leder till eller kommer från den markerade komponenten, vilket visas här. Standardvärdet är [!UICONTROL **Sida**].

   ![Målningsdimensionen.](assets/pathing-dim.png)

1. (Valfritt) Välj **[!UICONTROL Show advanced settings]** om du vill konfigurera något av följande alternativ:

   ![Avancerade inställningar med visningsalternativ, Antal kolumner och Flödesbehållare.](assets/adv-settings.png)

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Etiketterna på Flow-elementen trunkeras normalt för att spara skärmutrymme, men du kan göra hela etiketten synlig genom att markera den här rutan.  Standard = avmarkerat. |
   | **[!UICONTROL Include repeat instances]** | Flödesvisualiseringar baseras på instanser av en dimension. Den här inställningen ger dig möjlighet att inkludera eller exkludera upprepade instanser, t.ex. sidomladdning. Det går dock inte att ta bort upprepningar från Flow-visualiseringar som innehåller flervärdesdimensioner, som listVars, listProps, s.product, merchandising eVars osv. <p>Det här alternativet är inaktiverat som standard.</p> |
   | **[!UICONTROL Limit to first/last occurrence]** | Begränsa banor till dem som börjar/slutar med den första/sista förekomsten av en dimension/artikel/mått. Se avsnittet nedan, [Exempelscenario för &#39;begränsning till första/sista förekomsten&#39;](#example-scenario-for-limit-to-firstlast-occurrence), för en mer detaljerad förklaring. |
   | **[!UICONTROL Number of columns]** | Antalet kolumner som du vill ha i flödesdiagrammet. Du kan ange högst fem kolumner. |
   | **[!UICONTROL Items expanded per column]** | Antalet objekt som du vill ha i varje kolumn. Du kan ange högst 10 objekt utökade per kolumn. |
   | **[!UICONTROL Flow container]** | <ul><li>Besök</li><li>Besökare</li></ul> Gör att du kan växla mellan Besök och Besök för att analysera besökarbanan. Dessa inställningar hjälper er att förstå besökarnas engagemang på besökarnivå (mellan besök) eller begränsa analysen till ett enda besök. |

   >[!IMPORTANT]
   >
   >Kombinationen av **[!UICONTROL Number of columns]** och **[!UICONTROL Items expanded per column]** avgör antalet underliggande begäranden som krävs för att skapa flödesvisualiseringen. Ju högre tal, desto längre tid tar det att återge en visualisering.


1. Välj **[!UICONTROL Build]**.

>[!INFO]
>
>**Exempel:** Anta att du vill spåra sökvägen som användare tog både till och från de populäraste sidorna på din webbplats.
>
>För att göra detta skulle du
>
>1. Börja skapa en flödesvisualisering enligt beskrivningen ovan.
>1. Dra dimensionen [!UICONTROL **Sida**] till fältet **[!UICONTROL Contains]** och välj sedan [!UICONTROL **Skapa**].
>1. Flödesvisualiseringen byggs med den mest visade sidan synlig i fokusnoden mitt i visualiseringen. Du kan även se de översta sidorna som leder till den sidan (till vänster om fokusnoden) samt de översta sidorna som leder ut från den sidan (till höger om fokusnoden).
>1. Analysera data i flödet enligt beskrivningen i [Visa och ändra Flödesutdata](#view-and-change-the-flow-output).

## Visa och ändra flödesutdata {#output}

![Exempel på flödesutdata som visar Slut med besök, Sökningsdimension: Sida och Flödesbehållare: Stors.](assets/flow-output.png)

En sammanfattning av flödeskonfigurationen visas högst upp i diagrammet. Banorna i diagrammet är proportionella. Banor med mer aktivitet ser tjockare ut.

Om du vill gå längre ned i informationen har du flera alternativ:

* Flödesdiagrammet är interaktivt. För musen över diagrammet för att ändra de detaljer som visas.

* När du klickar på en nod i diagrammet visas information om den noden. Klicka på noden igen för att komprimera den.

  ![Exempel på interaktivt flödesdiagram med nodinformation.](assets/node-details.png)

* Du kan filtrera en kolumn så att endast vissa resultat visas, t.ex. inkludera och exkludera, ange villkor osv.

* Klicka på plustecknet (+) till vänster för att expandera en kolumn.

* Använd de högerklicksalternativ som förklaras nedan för att anpassa utdata ytterligare.

* Klicka på pennikonen bredvid konfigurationssammanfattningen om du vill redigera flödet ytterligare eller återskapa det med andra alternativ.

* Du kan också exportera och ytterligare analysera flödesdiagrammet som en del av ett projekts .CSV-fil genom att gå till **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

## Filtrering

Ovanför varje kolumn visas ett filter när du håller pekaren över den. Genom att klicka på filtret får du samma filterdialogruta som finns i friformstabellen idag. Det här filtret fungerar på samma sätt som i frihandstabellen.

* Använd avancerade inställningar för att inkludera eller exkludera vissa villkor med vår lista över operatorer.
* När du har filtrerat ett objekt från listan återspeglas filtreringen i den kolumnen. (Filtret minskar det antingen så att bara det objekt som är tillåtet i filtret visas, eller så tas alla objekt bort utom det som du vill ha i filtret.
* Alla kolumner som är nedströms och uppströms ska finnas kvar så länge som det finns data som flödar in i de återstående noderna.
* När filterikonen har använts visas den i blått ovanför den kolumn den filtrerar.
* Om du vill ta bort ett filter klickar du på filterikonen för att öppna filtermenyn. Ta bort eventuella filter och klicka sedan på **[!UICONTROL Save]**. Flödet bör återgå till det tidigare, ofiltrerade läget.

## Alternativ för högerklick {#right-click}

| Alternativ | Beskrivning |
|--- |--- |
| [!UICONTROL Focus on this node] | Ändra fokus till den valda noden. Flödesdiagrammets fokusnod visas i mitten. |
| [!UICONTROL Start over] | Returnerar dig till Frihand-diagramverktyget, där du kan skapa ett nytt flödesdiagram. |
| [!UICONTROL Create filter for this path] | Skapa ett filter. Detta tar dig in i Filter Builder där du kan konfigurera det nya filtret. |
| [!UICONTROL Breakdown] | Dela upp noden efter tillgängliga Dimensioner, mått eller tid. |
| [!UICONTROL Filter column] | Samma filteralternativ visas som de är tillgängliga i frihandstabellen. Mer information om de tillgängliga alternativen finns i avsnittet Använda ett enkelt eller avancerat filter i en tabell i [Filtrera och sortera tabeller](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| [!UICONTROL Exclude item]/[!UICONTROL Restore excluded items] | Tar bort en specifik nod från kolumnen och skapar den automatiskt som ett filter överst i kolumnen. Om du vill återställa det uteslutna objektet högerklickar du igen och väljer **[!UICONTROL Restore Excluded Item]**. Du kan också öppna filtret längst upp i kolumnen och ta bort rutan med det objekt du just uteslutit. |
| [!UICONTROL Trend] | Skapa ett trenddiagram för noden. |
| Visa nästa kolumn/Visa föregående kolumn | Visar nästa (höger) eller föregående (vänster) kolumn i visualiseringen. |
| Dölj kolumn | Döljer den markerade kolumnen från visualiseringen. |
| [!UICONTROL Expand entire column] | Expandera en kolumn om du vill visa alla noder. Som standard visas bara de fem översta noderna. |
| Skapa målgrupp från urval | Skapar en målgrupp baserat på den markerade kolumnen. |
| [!UICONTROL Collapse entire column] | Dölj alla noder i en kolumn. |

## Exempelscenario för &#39;begränsa till första/sista förekomsten&#39;

Tänk på följande när du använder det här alternativet:

* **[!UICONTROL Limit to first/last occurrence]** räknar endast den första/sista förekomsten i serien. Alla andra förekomster av villkoret **[!UICONTROL Starts with]** eller **[!UICONTROL Ends with]** ignoreras.
* Om den används med ett **[!UICONTROL Starts with]**-flöde inkluderas endast den första förekomsten som matchar startvillkoret.
* Om den används med ett **[!UICONTROL Ends with]**-flöde inkluderas endast den sista förekomsten som matchar slutvillkoret.
* Serien som används skiljer sig åt beroende på behållaren. Om du använder behållaren **[!UICONTROL Visit]** blir händelserierna sessionen. Om du använder behållaren **[!UICONTROL Visitor]** kommer händelserierna att vara alla händelser för en viss användare i det angivna datumintervallet.
* Alternativet **[!UICONTROL Limit to first/last occurrence]** kan konfigureras i de avancerade inställningarna när du använder ett mått- eller Dimension-objekt i fälten Börjar med eller Slutar med.

Exempelserie med händelser:

Hem > Produkter > Lägg till i kundvagn > Produkter > Lägg till i kundvagn > Fakturering > Orderbekräftelse

### Fundera på en flödesanalys med följande inställningar:

* Börja med [!UICONTROL  Add to cart] (Dimension)
* [!UICONTROL Page]-målningsdimension
* [!UICONTROL Visit] behållare

Om Begränsa till första/sista förekomsten är inaktiverat räknas den här enskilda serien med händelser som 2 förekomster av Lägg till i kundvagnen.
Förväntat flöde:
&quot;Lägg i kundvagnen&quot; (2) —> &quot;Produkter&quot; (1)
->&quot;Fakturering&quot; (1)

Om alternativet Begränsa till första/sista förekomsten är aktiverat inkluderas endast den första förekomsten av Lägg till i kundvagnen i analysen.
Förväntat flöde:
&quot;Lägg i kundvagnen&quot; (1) —> &quot;Produkter&quot; (1)

### Tänk på samma händelsesekvens men använd följande inställningar:

* Slutar med [!UICONTROL Add to cart] (Dimension Item)
* [!UICONTROL Page]-målningsdimension
* [!UICONTROL Visit] behållare

Om **[!UICONTROL Limit to first/last occurrence]** är *inaktiverad* räknas två förekomster av&quot;Lägg i kundvagnen&quot; av den här enskilda händelsesekvensen.
Förväntat flöde:
&quot;Produkter&quot; (2) &lt;— &quot;Lägg i kundvagn&quot; (2)

Om **[!UICONTROL Limit to first/last occurrence]** däremot är *aktiverad* inkluderas bara den sista förekomsten av [!UICONTROL Add to cart] i analysen.
Förväntat flöde:
&quot;Produkter&quot; (1) &lt;— &quot;Lägg i kundvagn&quot; (1)
