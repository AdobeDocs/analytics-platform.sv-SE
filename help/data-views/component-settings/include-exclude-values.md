---
title: Inkludera inställningar för komponenten Uteslut värden
description: Inkludera eller exkludera en dimensionsartikel beroende på dess värde.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Inkludera inställningar för komponenten Uteslut värden {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_includeexcludevalues"
>title="Inkludera exkluderingsvärden"
>abstract="Filtrera ett mätvärde så att endast värden som matchar specifika villkor räknas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_includeexcludevalues"
>title="Inkludera exkluderingsvärden"
>abstract="Begränsa en dimension så att den endast innehåller värden som matchar specifika villkor. Inkluderingar och undantag sker före allokering och filter i rapporter.<br/><br/>**Parametrar **<br/>**Skiftlägeskänsliga**: Kontrollera om filterlogiken nedan är skiftlägeskänslig."

<!-- markdownlint-enable MD034 -->

Med Inkludera exkluderade värden kan du skapa regler som är beroende av värdet för en dimensionspost. Värden som inte uppfyller villkoren som du anger behandlas i Analysis Workspace som om de aldrig fanns, även om data fortfarande finns i den underliggande datauppsättningen.

![Fönstret Datavyer där Inkludera exkluderade värden markeras ](../assets/include-exclude.png)

| Inställning | Beskrivning/användningsfall |
| --- | --- |
| [!UICONTROL Set include/exclude values] | En kryssruta som gör att du kan aktivera villkor där data inkluderas i en datavy. |
| [!UICONTROL Case sensitive] | Synlig för datatyperna String-schema. Standardvärdet är på. Den här inställningen gäller bara för logiken [!UICONTROL Include/Exclude Values], inte för resultatvärdet. Du kan ange om regeln är skiftlägeskänslig. |
| [!UICONTROL Match] | Här kan du ange vilka värden du vill ta hänsyn till för rapportering före attribuering och filter (t.ex. endast använda värden som innehåller frasen &quot;error&quot;). Du kan ange **[!UICONTROL If all criteria are met]** eller **[!UICONTROL If any criteria are met]**. Avgränsa varje värde med ett blanksteg. |
| [!UICONTROL Criteria] | Här kan du ange den matchningslogik som ska användas för en viss filterregel.<ul><li>**String**: [!UICONTROL Contains the phrase], [!UICONTROL Contains any term], [!UICONTROL Contains all terms], [!UICONTROL Does not contain any term], [!UICONTROL Does not contain the phrase], [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with]</li><li>**Dubbel/heltal**: [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Is greater than], [!UICONTROL Is less than], [!UICONTROL Is greater than or equal to], [!UICONTROL Is less than or equal to]</li><li>**Datum**: [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Is later than], [!UICONTROL Is before], [!UICONTROL Occurs within]</li></ul> |
| [!UICONTROL Match operand] | Här kan du ange den matchningsoperand som matchningsoperatorn ska användas på.<ul><li>**Sträng**: Textfält</li><li>**Dubbel/heltal**: Textfält med upp-/nedpilar för numeriska värden</li><li>**Datum**: Väljare för daggranularitet (kalender)</li><li>**Datumtid**: Val för datum- och tidsgranularitet</li></ul> |
| [!UICONTROL Add rule] | Här kan du ange ytterligare en matchningsoperator och -operand. |

{style="table-layout:auto"}
