---
title: Använd härledda fält för att rapportera mål
description: Förstå hur du kan använda härledda fält för att rapportera mål i dina Workspace-projekt.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: 53cf026531ac5690a3e5a31acaa5654a52747b69
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 1%

---


# Använd härledda fält för att rapportera mål

I det här användningsexemplet beskrivs hur du använder styrkan i härledda fält för att ange mål för en viss dimension och sedan använda dessa mål i Workspace-projektet.

Om du inte känner till härledda fält kan du läsa [självstudiekurs](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=en) och [dokumentation](../data-views/derived-fields/derived-fields.md) för en introduktion.


## Definiera mål

Om du vill definiera mål skapar du ett nytt härlett fält där du uttryckligen anger egna numeriska värden direkt eller indirekt med de värden som härrör från regler tidigare i den härledda fältdefinitionen.


### Mål för månatliga gipscertifikatorder

Du vill uttryckligen ange mål för dina presentkortsbeställningar för fyra månader, från juli 2023 till oktober 2023. Så här gör du:

1. Skapa ett nytt härlett fält med namnet `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Ange statiska värden, med en CASE WHEN RULE, för varje månad genom att ange en **[!UICONTROL Custom numeric value]**. Se regeln för månatliga produktmål nedan.

   ![Produktmål](assets/goals-derived-field-product-goals-1.png)


### Intäktsmål för marknadsföringskanaler

Ni vill ange ett månatligt intäktsmål för varje marknadsföringskanal. Så här gör du:

1. Skapa ett nytt härlett fält med [Funktionsmall för marknadsföringskanaler](/help/data-views/derived-fields/derived-fields.md#marketing-channels) med namnet `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Definiera alla regler för att korrekt identifiera var och en av marknadsföringskanalerna baserat på en kombination av reglerna URL PARSE och CASE WHEN. Exempel:

   ![Definition av regler för härlett marknadsföringskanalfält](assets/goals-derived-field-marketing-channel-1.png)

1. Ange explicit statiska värden, som representerar månatliga intäktsmål, för specifika marknadsföringskanaler i en slutgiltig WHEN-regel genom att ange en **[!UICONTROL Custom numeric value]**. Se [!DNL Monthly Goal] efter stycke.

   ![Månadsmål](assets/goals-derived-field-marketing-channel-2.png)



## Använd mål

Om du vill använda mål i ditt Workspace-projekt använder du funktionen för beräknade mått för att&quot;normalisera&quot; det härledda fältet tillbaka till det ursprungliga statiska värdet.

### Mål för månatliga gipscertifikatorder

1. Skapa ett beräknat måttfält med namnet `Monthly Gift Certificate Orders Goal`, definierad som:

   ![Ordermål](assets/calculated-metric-ordersgoals.png)

1. Du kan t.ex. skapa ytterligare beräknade fält `% of Monthly Gift Certificate Orders Goal`, för att visa faktiska framsteg mot mål, till exempel:

   ![Målprocent för order](assets/calculated-metric-ordersgoalspercent.png)

Du kan använda dessa beräknade värden för att rapportera förloppet i frihandstabeller och visualiseringar. Exempel:

![Frihandsregister som visar mål för marknadsföringsintäkter](assets/freeform-table-product-order-goals.png)


### Intäktsmål för marknadsföringskanaler

1. Skapa ett beräknat måttfält med namnet `Marketing Channel Revenue Goal`, definierad som:

   ![Intäktsmål](assets/calculated-metric-revenuegoals.png)

1. Du kan t.ex. skapa ytterligare beräknade fält `% of Marketing Channel Revenue Goal`, för att visa faktiska framsteg mot mål, till exempel:

   ![Procentandel för intäktsmål](assets/calculated-metric-revenuegoalspercent.png)

Du kan använda dessa beräknade värden för att rapportera förloppet i frihandstabeller och visualiseringar. Exempel:

![Frihandsregister som visar mål för marknadsföringsintäkter](assets/freeform-table-marketing-channel-revenue-goals.png)