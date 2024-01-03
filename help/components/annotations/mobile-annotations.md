---
title: Mobil styrkortsanteckning
description: Lär dig hur du visar kommentarer i mobila styrkort.
solution: Customer Journey Analytics
feature: Components
exl-id: c0f276b4-3514-4f93-8b6c-6896eb4da6e4
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---


# Dela anteckningar i mobila styrkort

Du kan visa anteckningar som har skapats i Workspace - i Mobile Scorecards. På så sätt kan ni dela kontextuella datanunkter och insikter om organisationen och kampanjer direkt i Mobile Scorecard-projekt, som kan visas i mobilappen för kontrollpaneler i Analytics.

## Ytanteckningar i Mobile Scorecards

Om du vill visa kommentarer i mobila styrkort skapar du först anteckningen från arbetsyteprojekt eller från komponentmenyn.

Mer information om hur du skapar anteckningar finns i [Skapa anteckningar](create-annotations.md). Anteckningar är som standard inaktiverade i mobila styrkort och måste aktiveras för varje styrkort som du vill visa i mobila styrkort.

1. Aktivera anteckningar. Information om hur du aktiverar anteckningar finns i [Aktivera eller inaktivera anteckningar](overview.md#annotations-on-off).

1. Skapa en anteckning och se till att den delas med alla dina projekt. Information om hur du skapar en anteckning i arbetsytan finns i [Skapa anteckningar](create-annotations.md).

1. Välj **[!UICONTROL Show annotations]** för att visa anteckningen i mobila styrkort.

   ![Mobila anteckningsalternativ för styrkort.](assets/show-annotations.png)

1. Bekräfta att visa anteckningar är markerat, gå till **[!UICONTROL Project]** > **[!UICONTROL Project info and settings]**.

   ![Alternativ för mobila anteckningar för projektinformation och inställningar som markerar alternativet Visa anteckningar.](assets/project-info-settings.png)

## Visa anteckningar i mobila styrkort

När anteckningar är aktiverade visas anteckningsikoner i styrkortsverktyget. Anteckningar visas bara i diagram och tabeller i den detaljerade vyn. Anteckningar visas inte i styrkortets huvudsida.

![Styrkortverktyget markerar anteckningsikonerna.](assets/view-annotations.png)

När anteckningsikoner visas kan du inte helt visa eller interagera med anteckningar på arbetsytan i verktyget. Använd förhandsgranskningsläget för att visa och interagera med anteckningar så som de visas i programmet. ![Ikonen Förhandsgranska](assets/preview-icon.png)

Anteckningsfärger markeras när anteckningen skapas i arbetsytan. Grå anteckningar indikerade förekomsten av mer än en anteckning. ![Anteckningsikoner](assets/gray-annotations1.png) ![Mobil styrkort med anteckningsikonen markerad.](assets/gray-annotations2.png)

## Visa diagramanteckningar

| Datum | Utseende |
| --- | --- |
| **[!UICONTROL Single da]y** | ![](assets/single-day-mobile-annotations.png)<br></br> |
| **[!UICONTROL Date range]** | ![](assets/date-range.png) |
| **[!UICONTROL Overlapping annotations]** | ![](assets/overlapping-annotations.png)<br></br>Om du vill visa anteckningsinformation i kontrollpanelsappen för Analytics trycker du på en anteckningsikon. <br></br>När du visar en anteckning i ett diagram kan du svepa åt vänster och höger för att navigera bland alla anteckningar som finns i diagrammet. När du visar en anteckning i tabellen sveper du åt vänster och höger för att navigera i alla anteckningar som är kopplade till det radobjektet i tabellen. <br></br>![](assets/swipe-multiple-annotations.png) <br></br>I diagram som inte har tidsbaserade *x-axel*, t.ex. munnen eller vågräta stapeldiagram, kan anteckningar som gäller diagrammet visas genom att man trycker på ikonen längst ned till höger.<br></br> ![](assets/charts-without-timebase.png) |
