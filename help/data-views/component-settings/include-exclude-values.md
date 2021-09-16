---
title: Inkludera inställningar för komponenten Uteslut värden
description: Inkludera eller exkludera en dimensionsartikel beroende på dess värde.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# Inkludera inställningar för komponenten Uteslut värden

Med Inkludera exkluderade värden kan du skapa regler som är beroende av värdet för en dimensionspost. Värden som inte uppfyller villkoren som du anger behandlas i Analysis Workspace som om de aldrig fanns, även om data fortfarande finns i den underliggande datauppsättningen.

![Inkludera exkludering](../assets/include-exclude.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Set include/exclude values] | En kryssruta där du kan aktivera villkor där data inkluderas i en datavy. |
| [!UICONTROL Case sensitive] | Synlig för datatyperna String-schema. Standardvärdet är på. Den här inställningen gäller bara för logiken [!UICONTROL Include/Exclude Values], inte för resultatvärdet. Du kan ange om regeln är skiftlägeskänslig. |
| [!UICONTROL Match] | Här kan du ange vilka värden du vill ta hänsyn till för rapportering före attribuering och filter (t.ex. endast använda värden som innehåller frasen &quot;error&quot;). Du kan ange **[!UICONTROL If all criteria are met]** eller **[!UICONTROL If any criteria are met]**. |
| [!UICONTROL Criteria] | Här kan du ange den matchningslogik som ska användas för en viss filterregel.<ul><li>**Sträng**: Innehåller frasen, Innehåller valfri term, Innehåller alla termer, Innehåller ingen term, Innehåller inte frasen, Lika med, Är inte lika, Börjar med, Slutar med</li><li>**Dubbel/heltal**: är lika med, inte lika med, är större än, är mindre än, är större än eller lika med, är mindre än eller lika med</li><li>**Datum**: är lika med, inte lika med, är senare än, är före, finns i</li></ul> |
| [!UICONTROL Match operand] | Här kan du ange den matchningsoperand som matchningsoperatorn ska användas på.<ul><li>**Sträng**: Textfält</li><li>**Dubbel/heltal**: Textfält med upp-/nedpilar för numeriska värden</li><li>**Datum**: Väljare för daggranularitet (kalender)</li><li>**Datum och tid**: Val för datum- och tidsgranularitet</li></ul> |
| [!UICONTROL Add rule] | Här kan du ange ytterligare en matchningsoperator och -operand. |
