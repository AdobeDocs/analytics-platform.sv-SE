---
title: Komponentinställningar för inga värdealternativ
description: Bestäm hur en dimension ska hanteras om den är tom.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 0bd632d9e748b567c7b946f4c7d1437f0a776ca2
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 1%

---

# Inga inställningar för värdealternativ

Med inga värdealternativ kan du bestämma hur Analysis Workspace ska hantera situationer där en händelse i en datauppsättning innehåller ett mått, men där dimensionen inte innehåller något värde. Du kan välja namnet på dimensionsobjektet, dölja det helt eller till och med behandla det som ett faktiskt värde.

![Inga värdealternativ](../assets/no-value-options.png)

## Inställningar {#settings}

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL If shown, call "No value"] | Ett textfält där du kan byta namn på **[!UICONTROL No value]** dimensionsobjekt till något annat. |
| [!UICONTROL Don't show No value by default] | Visar inte det här värdet vid rapportering. Måttförekomster som inte är kopplade till den här dimensionen visas inte i rapporten. |
| [!UICONTROL Show No value by default] | Visar det här värdet i rapporteringen. |
| [!UICONTROL Treat No value as a value] | Ersätter tomma värden i data med texten som du angav under [!UICONTROL If shown, call "No value"]. Om du t.ex. har Mobile-enhetstyper som dimension kan du byta namn på **[!UICONTROL No value]** objekt till&quot;Skrivbord&quot;. När du ändrar det här fältet till ett anpassat värde behandlas det anpassade värdet som ett giltigt strängvärde. Om du anger värdet &quot;Red&quot; i det här fältet kommer alla instanser av strängen &quot;Red&quot; som visas i själva data att hamna under samma radobjekt som du har angett. |

{style="table-layout:auto"}

## Blogginlägg

Här är ett relaterat blogginlägg om [hantering av&quot;inget värde&quot; i CJA](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339).
