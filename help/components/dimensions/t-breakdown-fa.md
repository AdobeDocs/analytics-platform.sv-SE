---
description: Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.
keywords: Analysis Workspace
title: Dela upp dimensioner
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 5%

---

# Dela upp dimensioner

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.

Anpassa era data på ett obegränsat sätt efter era specifika behov. skapa frågor med hjälp av relevanta mått, dimensioner, filter, tidslinjer och andra analysvärden.

1. [Skapa ett ](/help/analysis-workspace/home.md) projekt med en datatabell.
1. Högerklicka på ett radobjekt i datatabellen och välj **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Stegresultat](assets/fa_data_table_actions.png)

   Du kan dela upp mätvärden efter dimensionsobjekt eller målgruppsfilter över valda tidsperioder. Du kan även gå ned mer i detalj.

   >[!NOTE]
   >
   >Antalet uppdelningar i tabellen är begränsat till 200. Den här gränsen kommer att öka för export av uppdelningar.

**Video: Dimensioner i Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Video: Dimensioner**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Tillämpa attribueringsmodeller på uppdelningar

Alla uppdelningar i en tabell kan också ha en attribueringsmodell. Den här attribueringsmodellen kan vara densamma eller en annan än den överordnade kolumnen. Du kan till exempel analysera linjära beställningar i dimensionen marknadsföringskanaler, men använda U-formade beställningar på specifika spårningskoder i en kanal. Om du vill redigera attribueringsmodellen som används för en uppdelning håller du pekaren över nedbrytningsmodellen och klickar på **[!UICONTROL Edit]**:

![Brytningsinställningar](assets/breakdown_settings.png)
