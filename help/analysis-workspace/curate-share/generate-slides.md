---
description: Lär dig generera presentationer i pptx-format från Workspace-rapporter.
keywords: Analysis Workspace
title: Generera presentationer från Workspace-rapporter
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Data storytelling: Generera bildpresentationer från Workspace-rapporter {#generate-powerpoint}

Du kan automatiskt generera .pptx-presentationer från Analysis Workspace-projekt. När man skapar presentationer identifierar Customer Journey Analytics automatiskt viktiga insikter och konverterar dem till bilder som är klara för intressenter.

Denna funktionalitet minskar den tid och det arbete som krävs för att ta fram resultat från era Workspace-projekt, och gör det möjligt att snabbt skapa chefsberättelser och förmedla affärsmässiga effekter.

## Generera en .pptx-presentation baserad på ett Workspace-projekt

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Inkluderade paneler och visualiseringar"
>abstract="Välj paneler och visualiseringar som du vill ta med i presentationen. Du kan inkludera upp till 50 visualiseringar."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Viktiga komponenter"
>abstract="Välj upp till 5 mätvärden och 5 dimensioner från dina visualiseringar som du vill betona i presentationen. De mätvärden du väljer visas i kursiv stil, måtten visas i fet stil och dimensionsobjekten visas i en kontrasterande färg."

<!-- markdownlint-enable MD034 -->

1. Gå till det Workspace-projekt som innehåller de data du vill använda som grund för presentationen.

1. Välj **[!UICONTROL Generate slides]** i det övre högra hörnet på sidan.

1. Ange följande information:

   | Alternativ | Beskrivning |
   |---------|----------|
   | **[!UICONTROL Cover title]** | Ange en rubrik för presentationen. Den här rubriken visas på presentationens rubrikbild. |
   | **[!UICONTROL Include presenter name]** | Ange namnet på presentatören. Namnet visas på presentationens rubrikbild, under omslagets rubrik. |
   | **[!UICONTROL Panels and visualizations to include]** | Välj paneler och visualisering som du vill ta med i presentationen. Du kan inkludera upp till 50 visualiseringar.<p>De flesta paneler och visualiseringar stöds. Mer information om paneler och visualisering som inte stöds finns i [Projektelement och funktioner som inte stöds](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Panel and visualization descriptions]** | |
   | **[!UICONTROL Annotations]** | |
   | **[!UICONTROL Emphasize components]** | Välj upp till 5 mätvärden och 5 dimensioner från dina visualiseringar som du vill betona i presentationen.<p>När ingen betoning används visas komponenterna i presentationer enligt följande:<ul><li>**Mätvärden och dimensioner:** Kursiv</li><li>**Dimension-objekt:** Citattecken</li></ul></p><p>När betoning används visas komponenterna i presentationer enligt följande:</p><ul><li>**Mätvärden och dimensioner:** Kursiv och fet</li><li>**Dimension-objekt:** Fet när motsvarande dimension framhävs<p>En färg används också på dimensionsobjektet när dimensionsobjektet är markerat i diagrammet.</p></li></ul> |

(Villkorligt) Välj **[!UICONTROL Default theme]** om du vill att dina bilder ska skapas med standardtemat.

1. Välj om du vill använda ett standardtema eller överföra en anpassad mall:

   * **[!UICONTROL Default theme]**:

   * **[!UICONTROL Upload template]**:





## Redigera bilder från en tidigare genererad presentation


## Hämta en genererad PPTX-presentation

## Projektelement och funktioner som inte stöds {#unsupported}

Följande Analysis Workspace-element och -funktioner som används i ett projekt stöds inte när bilder skapas:

* Attributionspanelen

  Panelen visas som nedtonad när konfigurationsalternativen visas.

  Alla andra paneler kan inkluderas i bilder som genereras från ett Workspace-projekt.

* Vissa visualiseringar

  De flesta visualiseringar kan inkluderas i bilder som skapas från ett Workspace-projekt. Följande visualiseringar kan dock inte inkluderas och visas som nedtonade när konfigurationsalternativen visas:

   * Kohortabell

   * Reseduk

   * Punkt

   * Kombination

   * Spridning

   * Treemap

* Uppdelningar

* Guidade analyser


