---
description: Med verktyget Beräknade mätvärden kan du dra och släppa dimensioner, mått, segment och funktioner på en arbetsyta för att skapa anpassade mätvärden baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla beräknade mätvärden eller komplexa avancerade beräknade mätvärden.
title: Bygg beräknade värden
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: ec2fc88372814b01a04d4cc824181222ee55a83d
workflow-type: tm+mt
source-wordcount: '1466'
ht-degree: 0%

---

# Bygg beräknade värden {#build-metrics}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Produktkompatibilitet"
>abstract="Anger var i Customer Journey Analytics det här beräknade måttet kan användas, t.ex. i Analysis Workspace, Report Builder o.s.v. Vissa beräknade värden kan inte användas med experimenterande."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Använd beräknade mätvärden i experimenterande"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="Externt ID"
>abstract="Om du ändrar det externa ID:t kan det påverka hur det beräknade mätvärdet visas i externa källor, t.ex. affärsinformationsverktyg"

Customer Journey Analytics har en arbetsyta där du kan dra och släppa dimensioner, mätvärden, segment och funktioner för att skapa anpassade mätvärden baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla eller komplexa beräknade mätvärden.

Du kan använda verktyget för beräknade mätvärden för att skapa eller redigera beräknade mätvärden. När de skapas på det här sättet är beräknade värden tillgängliga i komponentlistan och kan sedan användas i projekt i hela organisationen. Du kan också snabbt skapa ett beräknat mått som bara är tillgängligt för det projekt där det skapades, vilket beskrivs i [Skapa beräknade värden för ett enskilt projekt](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) i [Metrisk](/help/components/apply-create-metrics.md).

[Skapa ett beräknat mått](cm-workflow.md) beskriver de olika alternativ som är tillgängliga för att skapa ett nytt beräknat mått.

## Områden för verktyget för beräknade mätvärden

Dialogrutan **[!UICONTROL Calculated metric builder]** används för att skapa nya eller redigera befintliga beräknade värden. Dialogrutan heter **[!UICONTROL New calculated metric]** eller **[!UICONTROL Edit calculated metric]** för mått som du skapar eller hanterar från [[!UICONTROL Calculated metrics]-hanteraren ](/help/components/calc-metrics/cm-workflow/cm-manager.md).

>[!BEGINTABS]

>[!TAB Bygg beräknade mätvärden]

![Fönstret Beräknad mätinformation visar fält och alternativ som beskrivs i nästa avsnitt.](assets/calculated-metric-builder.png)

>[!TAB Skapa eller redigera beräknade mått]

![Fönstret Beräknad mätinformation visar fält och alternativ som beskrivs i nästa avsnitt.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Ange följande information (![Obligatorisk](/help/assets/icons/Required.svg) krävs):

   | Element | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Data view]** | Du kan välja datavyn för det beräknade måttet.  Det beräknade mätvärde som du definierar är tillgängligt i Workspace-projekt baserat på den valda datavyn. |
   | **[!UICONTROL Project-only metric]** | En informationsruta visas högst upp i den här dialogrutan när du redigerar ett beräknat mått som har skapats för ett enskilt projekt, vilket beskrivs i [Skapa beräknade värden för ett enskilt projekt](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). <p>Om du vill göra det här beräknade måttet tillgängligt för alla projekt väljer du alternativet **[!UICONTROL Make this metric available to all your projects and add it to your component list]**.</p> |
   | **[!UICONTROL Title]** ![Krävs](/help/assets/icons/Required.svg) | Namnge det beräknade måttet, till exempel `Conversion Rate`. |
   | **[!UICONTROL External ID]** ![Krävs](/help/assets/icons/Required.svg) | Namnet på det beräknade måttet när ett externt BI-verktyg och BI-tillägget används. Värdet definieras automatiskt som `undefined_xxx` om du inte åsidosätter värdet. |
   | **[!UICONTROL Description]** | Ange en beskrivning för segmentet, till exempel `Calculated metric to define the conversion rate.` Det finns ingen anledning att beskriva formeln för det beräknade måttet eftersom formeln redan är automatiskt tillgänglig i [!UICONTROL Summary]. |
   | **[!UICONTROL Format]** | Välj ett format för det beräknade måttet: Du kan välja mellan **[!UICONTROL Decimal]**, **[!UICONTROL Time]**, **[!UICONTROL Percent]** och **[!UICONTROL Currency]**. |
   | **[!UICONTROL Decimal places]** | Ange antalet decimaler för det valda formatet. Endast aktiverat när det valda formatet är Decimal, Currency och Percent. |
   | **[!UICONTROL Show upward trend as]** | Ange om en uppåtgående trend för det beräknade måttet visas som ▲ **[!UICONTROL Good (Green)]** eller som ▼ **[!UICONTROL Bad (Red)]**. |
   | **[!UICONTROL Currency]** | Ange valutan för det beräknade måttet. Endast aktiverat när det valda formatet är Valuta. |
   | **[!UICONTROL Tags]** | Organisera det beräknade måttet genom att skapa eller använda en eller flera taggar. Börja skriva för att hitta befintliga taggar som du kan markera. Eller tryck på **[!UICONTROL ENTER]** för att lägga till en ny tagg. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort en tagg. |
   | **[!UICONTROL Preview]** | Förhandsvisningen täcker de senaste 90 dagarna och är ett sätt att mäta om du har definierat mätvärdena korrekt. |
   | **[!UICONTROL Summary]** | Visar en sammanfattning av definitionen av det beräknade måttet. <br/>Till exempel: ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]**. |
   | **[!UICONTROL Definition]** ![Krävs](/help/assets/icons/Required.svg) | Definiera ditt segment med [Definitionsverktyget](#definition-builder). |

1. Om du vill verifiera om den beräknade måttdefinitionen är korrekt använder du den ständigt uppdaterade **[!UICONTROL Preview]** av resultaten för det beräknade måttet. **[!UICONTROL Preview]** täcker de senaste 90 dagarna och utvärderar definitionen av ditt beräknade mått kontinuerligt.

   **[!UICONTROL Product compatibility]** anger om det beräknade måttet kan användas i försök. Möjliga värden är:
   * **[!UICONTROL Everywhere in Customer Journey Analytics]**: Det beräknade måttet kan användas i hela Customer Journey Analytics.
   * **[!UICONTROL Everywhere in Customer Journey Analytics (excluding experimentation)]**: Det beräknade måttet kan användas i hela Customer Journey Analytics, förutom på panelen Experimentation.

1. Välj:
   * **[!UICONTROL Save]** om du vill spara det beräknade måttet.
   * **[!UICONTROL Save As]** om du vill spara en kopia av det beräknade måttet.
   * **[!UICONTROL Cancel]** om du vill avbryta alla ändringar du har gjort i det beräknade måttet eller avbryta skapandet av ett nytt beräknat mätvärde.


## Definition builder

Du använder Definitionsverktyget för att dra och släppa dimensioner, mått, segment och funktioner för att skapa anpassade mätvärden baserat på behållarhierarkilogik, regler och operatorer. I den konstruktionen kan du använda standardvärden, Adobe-definierade mått, beräknade värden, segment, dimensioner och funktioner. Alla de här komponenterna är tillgängliga från komponentpanelen i verktyget Beräknade mått. Dessutom kan du använda operatorer och behållare i definitionen.

![Skapa beräknat mått](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

Endast mätvärden definieras som enskilda komponenter i området **[!UICONTROL Definition]**. Alla andra komponenter definieras som en behållare, radbrytningsmått eller andra behållare. Mer information finns i [Behållare](#containers).

### Mätvärden

Så här lägger du till ett mått:

* Dra och släpp en ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Metrics]**-komponent från komponentpanelen till **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Du kan använda ![sökfunktionen](/help/assets/icons/Search.svg) i komponentfältet för att söka efter specifika komponenter.

När du använder ett beräknat mätvärde som en del av definitionen expanderas det beräknade mätvärdet.

Så här ändrar du ett mått:

1. Välj ![Inställning](/help/assets/icons/Setting.svg) i en måttkomponent i området **[!UICONTROL Definition]**.
1. I popup-dialogrutan kan du definiera typen av mätvärden och en attribueringsmodell. Se [Mättyp och Attribution](m-metric-type-alloc.md).

Så här tar du bort ett mått:

* Välj ![Stäng](/help/assets/icons/Close.svg) i måttet.

### Operatorer

Med operatorer kan du ange operatorn mellan komponenter eller behållare. Operatorer visas automatiskt mellan

* två eller flera mätvärden i en behållare,
* två eller flera behållare i en behållare,
* en eller flera mätvärden och en eller flera behållare i en behållare.

Du kan välja:

| Symbol | Operator |
|:---:|---|
| ![Dela](/help/assets/icons/Divide.svg) | Dela (standard) |
| ![Stäng](/help/assets/icons/Close.svg) | Multiplicera |
| ![Ta bort](/help/assets/icons/Remove.svg) | Ta bort |
| ![Lägg till](/help/assets/icons/Add.svg) | Lägg till |

### Statiskt nummer

Du kan lägga till ett statiskt tal i den beräknade måttdefinitionen. Så här lägger du till ett statiskt nummer:

* Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** inifrån en behållare.
* Välj **[!UICONTROL Static number]**. En statisk nummerbehållare visas.
* Välj [!UICONTROL *Klicka för att lägga till ett värde*] och skriv ett värde.


### Behållare

Du lägger till dimensioner, segment och funktioner som behållare i en beräknad måttdefinition. Du kan också lägga till en allmän behållare. Behållare fungerar som ett matematiskt uttryck och avgör ordningen på operationerna. Allt i en behållare bearbetas före nästa komponent eller behållare.


#### Segmentbehållare

Du använder konceptet med en segmentbehållare för att skapa ett [segmenterat mått](metrics-with-segments.md). Du kan skapa en segmentbehållare med ett segment eller med ett segment som du skapar från en dimension.

* Så här lägger du till en segmentbehållare från en dimension:

   1. Dra och släpp en ![Dimensions](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensions]**-komponent från komponentpanelen till **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Du kan använda ![sökfunktionen](/help/assets/icons/Search.svg) i komponentfältet för att söka efter specifika komponenter.
   1. Ange villkoret för segmentet i popup-menyn **[!UICONTROL Create Segment from Dimension]**. Välj i listan med operatorer och välj ett värde eller ange ett värde. Till exempel **[!UICONTROL Month]** **[!UICONTROL equals]** ![SparrboxDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Välj **[!UICONTROL Done]**. En segmentbehållare läggs till i **[!UICONTROL Definition]**.


* Om du vill lägga till en segmentbehållare från ett segment kan du använda:

   * Dra och släpp en ![segmenteringskomponent](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** från komponentpanelen till **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Du kan använda ![sökfunktionen](/help/assets/icons/Search.svg) i komponentfältet för att söka efter specifika segment.
En segmentbehållare läggs automatiskt till i **[!UICONTROL Definition]** med segmentets namn.

   * Dra och släpp en ![segmenteringskomponent](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]** från komponentpanelen till en generisk behållare. Behållaren ändras till en segmentbehållare.

   * Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** inifrån en behållare:

      1. Välj **[!UICONTROL Segment]**. En segmentbehållare läggs till i **[!UICONTROL Definition]**.
      1. I den nya segmentbehållaren väljer du ett segment i listrutan [!UICONTROL *Markera...*].

  >[!TIP]
  >
  >Du kan lägga till mer än ett segment i en behållare.

  Segmenten i behållaren namnges efter segmentkomponenten. Exempel: ![Segmentering](/help/assets/icons/Segmentation.svg) **[!UICONTROL Web sessions]**. Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg) om du vill visa ett popup-fönster med information om segmentet. I popup-fönstret väljer du ![Redigera](/help/assets/icons/Edit.svg) för att redigera segmentdefinitionen.

Så här tar du bort ett segment från en behållare:

* Välj ![Stäng](/help/assets/icons/Close.svg) bredvid segmentnamnet.

Mer information och exempel finns i [Segmenterade mätvärden](metrics-with-segments.md).

#### Funktionsbehållare

Om du vill lägga till en funktionsbehållare kan du använda:

* Dra och släpp:

   1. Dra och släpp en ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL Functions]**-komponent från komponentpanelen till **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. Du kan använda ![sökfunktionen](/help/assets/icons/Search.svg) i komponentfältet för att söka efter specifika funktioner.
   1. En funktionsbehållare läggs automatiskt till i **[!UICONTROL Definition]** med funktionens namn.

* Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** inifrån en behållare:

   1. Välj **[!UICONTROL Function]**.
   1. Välj en funktion i listrutan [!UICONTROL *Välj...*] i behållaren.

Funktionsbehållaren namnges efter funktionskomponenten. Exempel: ![Funktion](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT (metric)]**. Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg) om du vill visa ett popup-fönster med information om funktionen. Välj **[!UICONTROL Learn more]** om du vill ha mer information om funktionen.

Mer information om hur du använder funktioner och vilka funktioner som är tillgängliga för att skapa ett beräknat mått finns i [Använd funktioner](cm-using-functions.md).


#### Allmän behållare

Så här lägger du till en allmän behållare:

* Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** inifrån en behållare
* Välj **[!UICONTROL Container]**. En ny tom generisk behållare läggs till i **[!UICONTROL Definition]**. Du kan använda en generisk behållare för att kapsla in eller skapa en hierarki i definitionen av det beräknade måttet.


#### Ta bort en behållare

Om du vill ta bort en behållare väljer du ![Stäng](/help/assets/icons/Close.svg) på behållarnivå.

>[!MORELIKETHIS]
>
>[Använda funktioner](cm-using-functions.md)
>&#x200B;>[Segment](/help/components/segments/seg-overview.md)
>
