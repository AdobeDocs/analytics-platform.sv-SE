---
title: Komponentinställningar för inga värdealternativ
description: Bestäm hur en dimension ska hanteras om den är tom.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Inga inställningar för värdealternativ {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="Inga värdealternativ"
>abstract="Konfigurera standardbeteendet för när det inte finns något värde i en dimension."

<!-- markdownlint-enable MD034 -->


[!UICONTROL No value options] låter dig avgöra hur Analysis Workspace hanterar situationer där en händelse i en datauppsättning innehåller ett mått, men dimensionen inte innehåller något värde. Du kan välja namnet på dimensionsobjektet, dölja det helt eller till och med behandla det som ett faktiskt värde.

![Inga värdealternativ](../assets/no-value-options.png)

## Inställningar {#settings}

| Inställning | Beskrivning |
| --- | --- |
| **[!UICONTROL If shown, call "No value"]** | Ett textfält där du kan byta namn på dimensionsobjektet **[!UICONTROL No value]** till något annat. |
| **[!UICONTROL Don't show "No value" by default]** | Visar inte det här värdet vid rapportering. Måttförekomster som inte är kopplade till den här dimensionen visas inte i rapporten. |
| **[!UICONTROL Show "No value" by default]** | Visar det här värdet i rapporteringen. |
| **[!UICONTROL Treat "No value" as a value]** | (Stöds inte för numeriska dimensioner) Ersätter tomma värden i data med texten som du angav under [!UICONTROL If shown, call "No value"]. Om du t.ex. har Mobile-enhetstyper som dimension kan du byta namn på objektet **[!UICONTROL No value]** till Desktop. När du ändrar det här fältet till ett anpassat värde behandlas det anpassade värdet som ett giltigt strängvärde. Om du anger värdet &quot;Red&quot; i det här fältet kommer alla instanser av strängen &quot;Red&quot; som visas i själva data att hamna under samma radobjekt som du har angett. |

## &quot;Inget värde&quot;-stöd för numeriska dimensioner {#numeric}

När du använder ett numeriskt värde som dimension kan du

* Konfigurera alternativet&quot;Inget värde&quot; i en datavy. Observera att alla konfigurationsinställningar som visas ovan stöds förutom för **[!UICONTROL Treat "No value" as a value]**.
* Använd **[!UICONTROL Include "No value"]** för numeriska dimensioner i en friformstabell i Workspace.
* Använd operatorerna **[!UICONTROL exists]** eller **[!UICONTROL does not exist]** med numeriska mått i segmentverktyget.


>[!MORELIKETHIS]
>
>Här är ett relaterat blogginlägg om att [hantera&quot;inget värde&quot; i Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339).

