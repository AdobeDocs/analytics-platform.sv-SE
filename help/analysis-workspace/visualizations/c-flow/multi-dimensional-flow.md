---
description: Med ett interdimensionellt flöde kan du undersöka användarsökvägar i olika dimensioner.
title: Flerdimensionella flöden
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 1eeba4dc9de52f2890cf25794e767f199a4aa04c
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Flerdimensionella flöden

Med ett interdimensionellt flöde kan du undersöka användarsökvägar i olika dimensioner. Den här artikeln visar hur du använder det här flödet för två användningsområden: interaktioner och händelser för mobilappar och hur kampanjer leder till webbbesök

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Interaktioner och händelser för mobilappar

Dimensionen [!UICONTROL Screen Name] används i det här exempelflödet för att se hur användare använder de olika skärmarna (scenerna) i appen. Den översta skärmen som returneras är **[!UICONTROL luma: content: ios: en: home]**, som är appens startsida:

![Ett flöde som visar det tillagda objektet.](assets/flowapp.png)

Om du vill utforska interaktionen mellan skärmar och händelsetyper (som att lägga till i kundvagn, inköp med mera) i den här appen drar och släpper du dimensionen **[!UICONTROL Event Types]**:

* Ovanför alla tillgängliga steg i flödet för att ersätta dimensionen:

  ![Ett flöde som visar siddimensionen som har dragits till flera områden.](assets/flowapp-replace.png)

* Utanför den aktuella flödesvisualiseringen lägger du till dimensionen:

  ![Ett flöde som visar siddimensionen som dras till det tomma utrymmet i slutet.](assets/flowapp-add.png)

Flödesvisualiseringen nedan visar resultatet av att lägga till dimensionen **[!UICONTROL Event Types]**. Visualiseringen ger insikter om hur mobilappsanvändare förflyttar sig mellan olika skärmar i appen innan de lägger till produkter i en kundvagn, stänger appen, presenteras ett erbjudande med mera.

![En fLow som visar siddimensionens resultat högst upp i listan.](assets/flowapp-result.png)

## Hur kampanjer lockar webbbesök

Ni vill analysera vilka kampanjer som leder till besök på webbplatsen. Du skapar en flödesvisualisering med **[!UICONTROL Campaign Name]** som dimension

![Namndimension för webbkampanj för flöde](assets/flowweb.png)

Du ersätter den sista **[!UICONTROL Campaign Name]**-dimensionen med dimensionen **[!UICONTROL Formatted Page Name]** och lägger till ytterligare en **[!UICONTROL Formatted Page Name]**-dimension i slutet av flödesvisualiseringen.

![Flöda webbkampanjnamn och webbsidesdimension](assets/flowweb-replace.png)

Du kan hålla muspekaren över något av flödena för att se mer information. Till exempel vilka kampanjer som har resulterat i en kundvagnsutcheckning.

![Flöda webbkampanjens namn och hovring över webbsidans dimension](assets/flowweb-hover.png)
