---
description: Bryt ned dimensioner och dimensionsobjekt i Analysis Workspace.
keywords: Analysis Workspace
title: Dela upp dimensioner
topic: Reports and analytics
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
translation-type: tm+mt
source-git-commit: cee89d021e9cd034246fe9367bc8910dac7ca7cf
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 13%

---


# Dela upp dimensioner

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Bryt ned dimensioner och dimensionsobjekt i Analysis Workspace.

Analysera data på obegränsade sätt efter just era behov och bygg frågor med hjälp av relevanta mätvärden, mått, segment, tidslinjer och andra analysvärden.

1. [Skapa ett projekt](/help/analysis-workspace/home.md) med en datatabell.
1. Högerklicka på ett radobjekt i datatabellen och välj **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Stegresultat](assets/fa_data_table_actions.png)

   Du kan dela upp mått efter dimensionsposter eller målgruppssegment över valda tidsperioder. Du kan också gå ned längre till en mer granulär nivå.

   >[!NOTE]
   >
   >Antalet uppdelningar som ska visas i tabellen är begränsat till 200. Denna gräns kommer att höjas för exportindelningar.

[Dimensioner i Analysis Workspace på YouTube](https://www.youtube.com/watch?v=P9W0hhIHhCs&amp;index=12&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) 4:54

[Dimension-uppdelningar på YouTube](https://www.youtube.com/watch?v=3mQ2HN7-lIc&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=13) 2:02

## Tillämpa attributmodeller på uppdelningar

Vid uppdelning i en tabell kan också någon tilldelningsmodell tillämpas på den. Den här attributmodellen kan vara densamma eller annorlunda än den överordnade kolumnen. Du kan t.ex. analysera linjära order på dimensionen marknadsföringskanaler, men tillämpa U-formade order på de specifika spårningskoderna inom en kanal. Om du vill redigera attributmodellen som används för en uppdelning håller du över fördelningsmodellen och klickar på **[!UICONTROL Edit]**:

![Uppdelningsinställningar](assets/breakdown_settings.png)
