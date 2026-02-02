---
title: Använd härledda fält för att rapportera mål
description: Förstå hur du kan använda härledda fält för att rapportera om mål i dina Workspace-projekt.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 39d3a233166e2ce2035df2ce821dd16181e5e13e
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# Använd härledda fält för att rapportera mål

I det här användningsexemplet beskrivs hur du använder funktionerna i härledda fält för att ange mål för en viss dimension och sedan använda dessa mål i ditt Workspace-projekt.

Om du inte känner till härledda fält kan du få en introduktion i [självstudiekursen](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html) och [dokumentationen](../data-views/derived-fields/derived-fields.md) .


## Definiera mål

Om du vill definiera mål skapar du ett nytt härlett fält där du uttryckligen anger egna numeriska värden direkt eller indirekt med de värden som härrör från regler tidigare i den härledda fältdefinitionen.


### Mål för månatliga gipscertifikatorder

Du vill uttryckligen ange mål för dina presentkortsbeställningar för fyra månader, från juli 2023 till oktober 2023. Så här gör du:

1. Skapa ett nytt härlett fält med namnet `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Ange statiska värden med en CASE WHEN-REGEL för varje månad genom att ange en **[!UICONTROL Custom numeric value]**. Se regeln för månatliga produktmål nedan.

   ![Månadsmål för produkt](assets/goals-derived-field-product-goals-1.png)


### Intäktsmål för marknadsföringskanaler

Ni vill ange ett månatligt intäktsmål för varje marknadsföringskanal. Så här gör du:

1. Skapa ett nytt härlett fält med [marknadsföringskanalernas funktionsmall](/help/data-views/derived-fields/derived-fields.md#marketing-channels) och namnet `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Definiera alla regler för att korrekt identifiera var och en av marknadsföringskanalerna baserat på en kombination av reglerna URL PARSE och CASE WHEN. Exempel:

   ![Definition av regler för härlett fält för marknadsföringskanal](assets/goals-derived-field-marketing-channel-1.png)

1. Ange explicit statiska värden, som representerar månatliga intäktsmål, för specifika marknadsföringskanaler i en slutgiltig WHEN-regel genom att ange en **[!UICONTROL Custom numeric value]**. Se regeln [!DNL Monthly Goal] nedan.

   ![Månadsmål](assets/goals-derived-field-marketing-channel-2.png)



## Använd mål

Om du vill använda mål i ditt Workspace-projekt använder du den beräknade mätfunktionen för att&quot;normalisera&quot; det härledda fältet tillbaka till det ursprungliga statiska värdet. Denna normalisering krävs eftersom de statiska värden som du anger för de härledda fälten som definierar mål ökas med varje händelse.

### Mål för månatliga gipscertifikatorder

1. Skapa ett beräknat måttfält med namnet `Monthly Gift Certificate Orders Goal`, definierat som:

   ![Ordermål](assets/calculated-metric-ordersgoals.png)

1. Du kan skapa ytterligare beräknade fält, till exempel `% of Monthly Gift Certificate Orders Goal`, för att visa faktisk förlopp mot mål, till exempel:

   ![Målprocent för order](assets/calculated-metric-ordersgoalspercent.png)

Du kan använda dessa beräknade värden för att rapportera förloppet i frihandstabeller och visualiseringar. Exempel:

![Frihandsregister som visar mål för marknadsföringsintäkter](assets/freeform-table-marketing-channel-revenue-goals.png)




### Intäktsmål för marknadsföringskanaler

1. Skapa ett beräknat måttfält med namnet `Marketing Channel Revenue Goal`, definierat som:

   ![Intäktsmål](assets/calculated-metric-revenuegoals.png)

1. Du kan skapa ytterligare beräknade fält, till exempel `% of Marketing Channel Revenue Goal`, för att visa faktisk förlopp mot mål, till exempel:

   ![Procentandel för intäktsmål](assets/calculated-metric-revenuegoalspercent.png)

Du kan använda dessa beräknade värden för att rapportera förloppet i frihandstabeller och visualiseringar. Exempel:

![Frihandsregister som visar mål för marknadsföringsintäkter](assets/freeform-table-product-order-goals.png)
