---
title: Översikt över produktanvändning
description: Få insikter och rapporter om hur er organisation använder Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Översikt över produktanvändning

Med produktanvändning kan organisationen visa analysdata om hur organisationen använder Customer Journey Analytics. Det är tillgängligt för alla organisationer som använder Customer Journey Analytics. När den är aktiverad skapas och sammanfogas följande Adobe Experience Platform-komponenter automatiskt. Dessa komponenter ägs av systemet, är skrivskyddade och kan inte redigeras.

* Ett schema i Adobe Experience Platform
* En datauppsättning i Adobe Experience Platform
* En anslutning i Customer Journey Analytics
* En datavy i Customer Journey Analytics

Alla datainsamlingar och inställningar konfigureras automatiskt när de är aktiverade. Varje gång en användare gör en åtgärd i Analysis Workspace spåras den åtgärden och är tillgänglig för rapportering.

>[!IMPORTANT]
>
>Den här funktionen är viktig för dina avtalsenliga radbegränsningar i Adobe Experience Platform. Se till att din organisation kan hantera data som genereras av den här funktionen innan du aktiverar den.

## Aktivera produktanvändning

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]**

Om du navigerar till det här avsnittet av gränssnittet i Customer Journey Analytics går du till [Datainställningar](data-settings.md) där du kan aktivera den här funktionen.

## Tillgängliga dimensioner

När du aktiverar produktanvändning är följande dimensioner tillgängliga. Om du vill ändra några dimensionsinställningar skapar du en kopia av den systemägda datavyn och använder den kopierade datavyn i Analysis Workspace.

* **[!UICONTROL Action Name]**: Den typ av åtgärd som användaren vidtagit. Du kan använda den här dimensionen som önskat mått genom att skapa en kopia i datavyinställningarna. Dimension innehåller följande:
   * [!UICONTROL Add attribution]
   * [!UICONTROL Add component]
   * [!UICONTROL Add panel]
   * [!UICONTROL Add visualization]
   * [!UICONTROL Create new guided analysis]
   * [!UICONTROL Create new project]
   * [!UICONTROL Curate components]
   * [!UICONTROL Download CSV]
   * [!UICONTROL Download PDF]
   * [!UICONTROL Load guided analysis]
   * [!UICONTROL Load project]
   * [!UICONTROL New scorecard loaded]
   * [!UICONTROL Open data dictionary]
   * [!UICONTROL Open intelligent captions]
   * [!UICONTROL Project share]
   * [!UICONTROL Run Experimentation panel]
   * [!UICONTROL Save project]
   * [!UICONTROL Scorecard saved]
   * [!UICONTROL Send file]
   * [!UICONTROL Send file on schedule]
   * [!UICONTROL Share project with anyone]
   * [!UICONTROL Share project with Workspace users]
* **[!UICONTROL Attribution Model Used]**: Den typ av attribueringsmodell som komponenten använder. Dimension innehåller följande:
   * [!UICONTROL Last touch]
   * [!UICONTROL First touch]
   * [!UICONTROL Linear]
   * [!UICONTROL Participation]
   * [!UICONTROL Same touch]
   * [!UICONTROL U shaped]
   * [!UICONTROL J curve]
   * [!UICONTROL Inverse J]
   * [!UICONTROL Time decay]
   * [!UICONTROL Custom]
   * [!UICONTROL Algorithmic]
* **[!UICONTROL Component Name]**: Namnet på komponenten som lades till, togs bort eller ändrades.
* **[!UICONTROL Component Type]**: Den typ av komponent som lades till, togs bort eller ändrades. Dimension innehåller följande:
   * [!UICONTROL Dimension]
   * [!UICONTROL Metric]
   * [!UICONTROL Segment]
   * [!UICONTROL Calculated metric]
   * [!UICONTROL Date range]
   * [!UICONTROL Annotation]
   * [!UICONTROL Alert]
* **[!UICONTROL Login User]**: Användaren som utförde åtgärden.
* **[!UICONTROL Panel Used]**: Panelen där komponenten lades till, togs bort eller ändrades. Dimension innehåller följande:
   * [!UICONTROL Attribution]
   * [!UICONTROL Blank panel]
   * [!UICONTROL Experimentation]
   * [!UICONTROL Freeform]
   * [!UICONTROL Next or previous item]
   * [!UICONTROL Quick insights]
   * [!UICONTROL Trends]
   * [!UICONTROL Funnel]
   * [!UICONTROL User growth]
   * [!UICONTROL Impact]
   * [!UICONTROL User stream]
   * [!UICONTROL Retention]
   * [!UICONTROL Feature matrix]
* **[!UICONTROL Project Name]**: Projektets egna namn.
* **[!UICONTROL Project Type]**: Projekttypen. Dimension innehåller följande:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Visualization Used]**: Den visualisering som lades till, togs bort eller ändrades. Dimension innehåller följande:
   * [!UICONTROL Freeform table]
   * [!UICONTROL Cohort table]
   * [!UICONTROL Fallout]
   * [!UICONTROL Flow]
   * [!UICONTROL Journey Canvas reportlet]
   * [!UICONTROL Area]
   * [!UICONTROL Area stacked]
   * [!UICONTROL Bar]
   * [!UICONTROL Bar stacked]
   * [!UICONTROL Bullet]
   * [!UICONTROL Combo]
   * [!UICONTROL Donut]
   * [!UICONTROL Histogram]
   * [!UICONTROL Horizontal bar]
   * [!UICONTROL Horizontal bar stacked]
   * [!UICONTROL Key metric summary]
   * [!UICONTROL Line]
   * [!UICONTROL Map]
   * [!UICONTROL Scatter]
   * [!UICONTROL Section header]
   * [!UICONTROL Summary change]
   * [!UICONTROL Summary number]
   * [!UICONTROL Text]
   * [!UICONTROL Treemap]
   * [!UICONTROL Venn]

Produktanvändningen spårar inte enskilda projektkomponenter när ett projekt bara öppnas eller visas. Användaråtgärden för att öppna ett projekt spåras emellertid.
