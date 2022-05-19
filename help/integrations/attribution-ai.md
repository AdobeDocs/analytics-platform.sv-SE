---
description: Find out how AEP Attribution AI integrates with Workspace in CJA.
title: Integrate Attribution AI with CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: e0b5e91897ce6cdcaebfb2d6663e565dff850d74
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 3%

---

# Integrate Attribution AI with CJA

>[!NOTE]
>
>This page is under construction.

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en) With Attribution AI, marketers can measure and optimize marketing and advertising spend by understanding the impact of every individual customer interaction across each phase of the customer journeys.

Attribution AI supports two categories of scores: algorithmic and rule-based. Algorithmic scores include incremental and influenced scores. Rule-based scores include First touch, Last touch, Linear, U-shaped, and Time-Decay. Attribution AI supports 3 Experience Platform schemas: Experience Event, Adobe Analytics, and Consumer Experience Event.

Attribution AI integrates with Customer Journey Analytics (CJA) to the extent that Attribution AI runs models against data and then CJA imports the output of those models as a data set, which can then be integrated with the rest of your CJA data sets. Attribution AI-enabled datasets can be then be leveraged in data views and reporting in CJA.

## Workflow

Some of the steps are performed in Adobe Experience Platform prior to working with the output in CJA.

### Step 1: Download Attribution AI scores

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores)

### Step 2: Create an Attribution AI instance

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html)

### Step 3: Set up a CJA connection to Attribution AI datasets

[](/help/connections/create-connection.md) These datasets appears with the &quot;Attribution AI Scores&quot; prefix, as shown here:

![](assets/aai-scores.png)

### Step 4: Create data views based on these connections

[](/help/data-views/create-dataview.md) (Would be great to have a screenshot here.)

### Step 5: Report on AAI data in CJA Workspace

Here is an example of a Workspace project with AAI data that shows...

## Differences between Attribution AI and Attribution IQ

[](/help/analysis-workspace/attribution/overview.md) This table shows some of the differences in functionality:

| Functionality | Attribution AI | Attribution IQ |
| --- | --- | --- |
| Does fractional attribution | Ja | Nej |
| Allows users to adjust model | Nej | Ja |
| Does attribution across channels (Note: AAI does not use the same stitched data that CJA does.) | Ja | Ja |
| Includes incremental and influenced scores | Ja | Nej |
| Does ML modeling | Ja | Ja |
| Does ML modeling with predictions | Ja | Nej |

{style=&quot;table-layout:auto&quot;}
