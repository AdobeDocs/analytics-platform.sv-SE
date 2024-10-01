---
title: Inkludera inställningar för komponenten Uteslut värden
description: Inkludera eller exkludera en dimensionsartikel beroende på dess värde.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---

# Inkludera inställningar för komponenten Uteslut värden {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_includeexcludevalues"
>title="Inkludera exkluderingsvärden"
>abstract="Filtrera ett mätvärde så att endast värden som matchar specifika villkor räknas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_includeexcludevalues"
>title="Inkludera exkluderingsvärden"
>abstract="Begränsa en dimension så att den endast innehåller värden som matchar specifika villkor. Inkluderingar och undantag sker före allokering och filter i rapporter.<br/><br/>**Parametrar **<br/>**Skiftlägeskänsliga**: Kontrollera om filterlogiken nedan är skiftlägeskänslig."

<!-- markdownlint-enable MD034 -->



Med Inkludera exkluderade värden kan du skapa regler som är beroende av värdet för en dimensionspost. Värden som inte uppfyller villkoren som du anger behandlas i Analysis Workspace som om de aldrig fanns, även om data fortfarande finns i den underliggande datauppsättningen.

![Fönstret Datavyer där Inkludera exkluderade värden markeras ](../assets/include-exclude.png)

| Inställning | Beskrivning/användningsfall |
| --- | --- |
| [!UICONTROL Set include/exclude values] | En kryssruta som gör att du kan aktivera villkor där data inkluderas i en datavy. |
| [!UICONTROL Case sensitive] | Synlig för datatyperna String-schema. Standardvärdet är på. Den här inställningen gäller bara för logiken [!UICONTROL Include/Exclude Values], inte för resultatvärdet. Du kan ange om regeln är skiftlägeskänslig. |
| [!UICONTROL Match] | Här kan du ange vilka värden du vill ta hänsyn till för rapportering före attribuering och filter (t.ex. endast använda värden som innehåller frasen &quot;error&quot;). Du kan ange **[!UICONTROL If all criteria are met]** eller **[!UICONTROL If any criteria are met]**. |
| [!UICONTROL Criteria] | Här kan du ange den matchningslogik som ska användas för en viss filterregel.<ul><li>**Sträng**: Innehåller frasen, Innehåller valfri term, Innehåller alla termer, Innehåller inte någon term, Innehåller inte frasen, Lika med, Inte lika med, Börjar med, Slutar med</li><li>**Dubbel/heltal**: är lika med, inte lika med, är större än, är mindre än, är större än eller lika med, är mindre än eller lika med</li><li>**Datum**: är lika med, är inte lika med, är senare än, är före, inträffar inom</li></ul> |
| [!UICONTROL Match operand] | Här kan du ange den matchningsoperand som matchningsoperatorn ska användas på.<ul><li>**Sträng**: Textfält</li><li>**Dubbel/heltal**: Textfält med upp-/nedpilar för numeriska värden</li><li>**Datum**: Väljare för daggranularitet (kalender)</li><li>**Datumtid**: Val för datum- och tidsgranularitet</li></ul> |
| [!UICONTROL Add rule] | Här kan du ange ytterligare en matchningsoperator och -operand. |

{style="table-layout:auto"}
