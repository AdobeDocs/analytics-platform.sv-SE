---
description: Med ett interdimensionellt flöde kan du undersöka användarbanor över olika dimensioner.
title: Intradimensionella flöden
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 1%

---


# Intradimensionella flöden

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Med ett interdimensionellt flöde kan du undersöka användarbanor över olika dimensioner.

En dimensionsetikett högst upp i varje flödeskolumn gör det mer intuitivt att använda flera dimensioner i en flödesvisualisering:

![](assets/flow.png)

Vi kommer att titta på två användningsfall: ett programanvändningsfall och ett webbanvändningsfall.

## Använd fall ett: app

De [!UICONTROL Action Name] dimensionen lades till i flödet, med det översta returnerade objektet [!UICONTROL ItemAdded]:

![](assets/multi-dimensional-flow.png)

Om du vill utforska interaktionen mellan skärmar/sidor och åtgärder i den här appen kan du sedan dra siddimensionen till flera platser, beroende på vad du vill utforska:

* Dra den till endera änden av släppzonen (inuti den svarta rektangulära zonen som visas) för att **ersätta** de högsta resultaten i ändarna:

   ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* Dra den till det vita utrymmet i slutet (markera den svarta parentesen) för att **lägg till i** visualisering:

   ![](assets/multi-dimensional-flow4.png)

Här är resultatet om du bestämmer dig för att ersätta objektet ItemScaled i den högra kolumnen med dimensionen Page. Det översta resultatet ändras nu till det översta resultatet för siddimensionen:

![](assets/multi-dimensional-flow5.png)

Nu kan du se hur kunderna rör sig genom åtgärder och sidor. Du kan utforska flödet ytterligare genom att klicka på olika noder:

![](assets/multi-dimensional-flow6.png)

Detta sker om du lägger till en annan Action Name-dimension i slutet av visualiseringen:

![](assets/multi-dimensional-flow7.png)

Detta möjliggör vissa djupgående insikter och möjliga ändringar av den app du analyserar.

## Använd fall två: webbsida

I det här användningsfallet visas hur du kan analysera vilka kampanjer som kör de flesta posterna till en webbplats.

Dra dimensionen Kampanjnamn till ett nytt flöde:

![](assets/multi-dimensional-flow8.png)

Nu vill jag se till vilka sidor dessa kampanjer driver trafiken, så jag drar siddimensionen till höger om flödesresultaten för att lägga till ytterligare visualisering:

![](assets/multi-dimensional-flow9.png)
