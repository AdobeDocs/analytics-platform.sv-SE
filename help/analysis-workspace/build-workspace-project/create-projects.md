---
description: Lär dig hur du skapar ett projekt i Analysis Workspace.
title: Skapa projekt
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 518bebc18611136873fce5c23dd7041afafe1220
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 2%

---

# Skapa projekt {#create-projects}


Med [Projekt](/help/analysis-workspace/build-workspace-project/freeform-overview.md) i Analysis Workspace kan du skapa och visa affärskritiska analyser.  Dessa analyser kan delas med intressenter inom eller utanför organisationen.

1. I Customer Journey Analytics väljer du **[!UICONTROL Workspace]**.

1. Välj **[!UICONTROL Projects]** i den vänstra panelen och välj sedan **[!UICONTROL Create project]**.

1. Välj **Tomt Workspace-projekt** om du vill skapa ditt Workspace-projekt med en webbläsare.

   Mer information om hur du skapar ett Mobile Scorecard-projekt som du kan dela med andra intressenter via en mobilapp finns i [Tomt mobilstyrkort](/help/mobile-app/curator.md) . Och se [Guidad analys](/help/guided-analysis/overview.md) för mer information om de olika alternativ som finns för att skapa ditt guidade analysprojekt.

1. Välj [!UICONTROL **Skapa**].


Nu när du har skapat ett tomt Workspace-projekt måste du känna till användargränssnittet i [Analysis Workspace](/help/analysis-workspace/home.md). När du är klar kan du skapa ditt projekt. Så här gör du:

![Exempelprojekt](assets/example-project.png)

* Lägg till [paneler](/help/analysis-workspace/c-panels/panels.md) i ditt projekt. Till exempel **[!DNL Example Panel]** ➊.

* Lägg till [visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) på panelerna. Exempel:
   * **[!DNL Line Graph]** [Radvisualisering ](/help/analysis-workspace/visualizations/line.md) ➋
   * **[!DNL Countries]** [Visualisering av frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ➌
* Lägg till [komponenter](/help/components/overview.md) i dina visualiseringar. Exempel:
   * **[!DNL Store Country]** [dimension](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [metrisk](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [beräknat mått ](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [segment](/help/components/segments/seg-overview.md) ➐
   * **[!DNL Last Month]** [datumintervall](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [anteckning](/help/components/annotations/overview.md) ➒


## Projektinformation och inställningar {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Antal upprepande instanser"
>abstract="Anger om upprepade instanser räknas i rapporter.<br/><br/>Obs! Den här inställningen gäller inte för visualiseringar av flöde och utfall."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Antal upprepande instanser"
>abstract="Anger om upprepade instanser räknas i rapporter.<br/>Obs! Den här inställningen gäller inte för visualiseringar av flöde och utfall."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Tillåt kommentarer"
>abstract="När det här alternativet är aktiverat finns det ett kommentarsområde till höger om projektet i Analysis Workspace."


Projektinställningar innehåller information på projektnivå om det aktiva projektet.

![Fönstret Projektinformation och inställningar.](./assets/projectinfo.png)

Inställningarna inkluderar:

| Inställning | Beskrivning |
|---|---|
| Projektnamn | Namnet på projektet. Du kan dubbelklicka på namnet för att redigera det. |
| Ägare | Projektägarnamn |
| Senast ändrad | Datum för senaste ändring av projektet. |
| Taggar | Visar alla taggar som har använts i ett projekt för enklare kategorisering. |
| Beskrivning | En beskrivning är användbar för att förtydliga syftet med ett projekt. Du kan dubbelklicka på beskrivningen för att redigera den. |
| Antal upprepande instanser | Ange om upprepade instanser ska räknas i rapporter. Obs! Den här inställningen gäller inte för visualiseringar av flöde och utfall. |
| Visa anteckningar | Ange om anteckningar ska visas för det här projektet eller inte. |
| [Projektfärgpalett](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Du kan ändra den kategoriska färgpalett som används i Workspace genom att välja bland färdiga paletter som har optimerats för färgblindhet, eller genom att ange en anpassad palett. Den här funktionen påverkar många saker i Workspace, bland annat de flesta visualiseringar. |
| [Visa densitet](/help/analysis-workspace/build-workspace-project/view-density.md) | Gör att du kan se mer data på skärmen genom att minska den lodräta utfyllnaden för den vänstra panelen, frihandstabeller och kohorttabeller. |
| Tillåt kommentarer | När det här alternativet är aktiverat finns det ett kommentarsområde till höger om projektet i Analysis Workspace. Mer information finns i [Lägga till och hantera kommentarer i projekt](/help/analysis-workspace/build-workspace-project/comment-projects.md). |



