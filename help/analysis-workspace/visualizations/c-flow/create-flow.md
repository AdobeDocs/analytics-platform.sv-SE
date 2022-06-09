---
description: Använd flödesvisualisering i ett Workspace-projekt.
title: Konfigurera en flödesvisualisering
feature: Visualizations
role: User, Admin
source-git-commit: 62243ccd3d0f4b6ef09e57d850c0d7eb03f879e0
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 2%

---

# Konfigurera en flödesvisualisering

>[!NOTE]
>
>Den nya versionen av [!UICONTROL Flow] visualisering är för närvarande i begränsad testning. Den kommer att släppas den 15 juni 2022.

Med den uppdaterade Flow-visualiseringen kan ni förstå den resa som härrör från eller leder fram till en specifik konverteringshändelse på er webbplats eller i er app. Den spårar en bana genom dina dimensioner (och dimensionsobjekt) eller mätvärden. Med Flow kan du konfigurera början eller slutet av sökvägen som du är intresserad av, eller analysera alla sökvägar som flödar genom en dimension eller dimensionspost.

Den nya [!UICONTROL flow] arbetsflödet har förbättrats på flera sätt:

* Nu kan du välja att starta eller avsluta din bana med en kombination av mått och en målningsdimension.
* Innehåller [!UICONTROL Advanced Settings] så att du kan anpassa [!UICONTROL flow].
* Den nya knappen &quot;Bygg&quot; sparar tid genom att du kan konfigurera hela resan samtidigt, ställa frågor och sedan automatiskt bygga ut flera kolumner och noder samtidigt &#x200B;.

![nytt flödesgränssnitt](assets/new-flow.png)

## Konfigurationssteg {#configure}

1. Om du vill börja skapa ett flödesdiagram lägger du till en tom panel i projektet och klickar på ikonen för visualiseringar i den vänstra listen. Dra sedan Flödesvisualiseringen till panelen. Eller dra [!UICONTROL Flow] visualisering i ett befintligt projekt.

1. Förankra Flödesvisualiseringen med ett av tre alternativ:

   * [!UICONTROL Starts with] (mått, dimensioner eller objekt), eller
   * [!UICONTROL Contains] (mått, eller objekt), eller
   * [!UICONTROL Ends with] (mått, dimensioner eller objekt)

   Var och en av dessa kategorier visas på skärmen som en&quot;släppzon&quot;. Dra objekt från måttlistan eller mätningslistan och släpp dem i önskad släppzon.

   Låt oss anta att du vill spåra allt som leder till en utcheckningshändelse. Du drar en utcheckningsrelaterad dimension eller mätvärden (som [!UICONTROL Order exists]) till **[!UICONTROL Ends with]** släppzon.

1. Om du väljer ett mätvärde måste du även ange [!UICONTROL Pathing Dimension], som visas här, som du använder för att skapa sökvägen. Standardvärdet är [!UICONTROL Page].

   ![målningsdimension](assets/pathing-dim.png)

   >[!IMPORTANT]
   >
   >Beräknade mått kan inte tas med i  **[!UICONTROL Starts with]** eller **[!UICONTROL Ends with]** släppzoner.

1. (Valfritt) Klicka på **[!UICONTROL Show Advanced Settings]** för att konfigurera avancerade inställningar:

   ![avancerade inställningar](assets/adv-settings.png)

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Include repeat instances]** | Flödesvisualiseringar baseras på instanser av en dimension. Den här inställningen ger dig möjlighet att inkludera eller exkludera upprepade instanser, t.ex. sidomladdning. Det går dock inte att ta bort upprepningar från Flow-visualiseringar som innehåller flervärdesdimensioner, som listVars, listProps, s.product, merchandising eVars osv. Standard = avmarkerat. |
   | **[!UICONTROL Wrap labels]** | Etiketterna på Flow-elementen trunkeras normalt för att spara skärmutrymme, men du kan göra hela etiketten synlig genom att markera den här rutan.  Standard = avmarkerat. |
   | **[!UICONTROL Limit to first/last occurrence]** | Begränsa banor till dem som börjar/slutar med den första/sista förekomsten av en dimension/artikel/mått. |
   | **[!UICONTROL Number of Columns]** | Anger hur många kolumner du vill ha i flödesdiagrammet. |
   | **[!UICONTROL Items expanded per Column]** | Hur många objekt du vill ha i varje kolumn. |
   | **[!UICONTROL Flow Container]** | <ul><li>Gå in på</li><li>Besökare</li></ul> Gör att du kan växla mellan Besök och Besök för att analysera besökarbanan. Dessa inställningar hjälper er att förstå besökarnas engagemang på besökarnivå (mellan besök) eller begränsa analysen till ett enda besök. |

1. Klicka på **[!UICONTROL Build]**.

## Visa och ändra flödesutdata {#output}

![flödesutdata](assets/flow-output.png)

En sammanfattning av flödeskonfigurationen visas högst upp i diagrammet. Banorna i diagrammet är proportionella. Banor med mer aktivitet ser tjockare ut.

Om du vill gå längre ned i informationen har du flera alternativ:

* Flödesdiagrammet är interaktivt. För musen över diagrammet för att ändra de detaljer som visas.

* När du klickar på en nod i diagrammet visas information om den noden. Klicka på noden igen för att komprimera den.

   ![nodinformation](assets/node-details.png)

* Du kan filtrera en kolumn så att endast vissa resultat visas, t.ex. inkludera och exkludera, ange villkor osv.

* Klicka på plustecknet (+) till vänster för att expandera en kolumn.

* Använd de högerklicksalternativ som förklaras nedan för att anpassa utdata ytterligare.

* Klicka på pennikonen bredvid konfigurationssammanfattningen om du vill redigera flödet ytterligare eller återskapa det med andra alternativ.

* Du kan också exportera och ytterligare analysera flödesdiagrammet som en del av ett projekts .CSV-fil genom att gå till **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.


## Alternativ för högerklick {#right-click}

| Alternativ | Beskrivning |
|--- |--- |
| [!UICONTROL Focus on this node] | Ändra fokus till den valda noden. Flödesdiagrammets fokusnod visas i mitten. |
| [!UICONTROL Start Over] | Returnerar dig till Frihand-diagramverktyget, där du kan skapa ett nytt flödesdiagram. |
| [!UICONTROL Create Segment from this point in flow] | Skapa ett segment. Då kommer du till segmentbyggaren där du kan konfigurera det nya segmentet. |
| [!UICONTROL Breakdown] | Dela upp noden efter tillgängliga Dimensioner, mått eller tid. |
| [!UICONTROL Trend] | Skapa ett trenddiagram för noden. |
| [!UICONTROL Expand entire column] | Expandera en kolumn om du vill visa alla noder. Som standard visas bara de fem översta noderna. |
| [!UICONTROL Collapse entire column] | Dölj alla noder i en kolumn. |

>[!MORELIKETHIS]
>[Översikt över flöden](/help/analysis-workspace/visualizations/c-flow/flow.md)


