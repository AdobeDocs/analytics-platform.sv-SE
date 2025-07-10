---
title: Inställningar för beteendekomponent
description: Ange hur en dimension eller ett mått fungerar vid rapportering.
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 50599b36d333cae3735c6d4fd1b0af6fcabe9177
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Inställningar för beteendekomponent {#behavior-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_behavior"
>title="Beteende"
>abstract="Gäller för mått och måttkomponenter. Bestäm hur radartiklar för det här måttet ska aggregeras. Ange om strängvärden för den här dimensionen ska vara lägre."

<!-- markdownlint-enable MD034 -->


Beteendeinställningar är tillgängliga för både mått och mått. Vilka inställningar som är tillgängliga beror på komponenttypen och schemadatatypen.

![Beteendeinställningar](../assets/behavior-settings.png)

## Dimension beteendeinställningar

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Lower case] | Raderar rader som har samma värde men olika skiftläge. Om det här alternativet är aktiverat rapporteras alla instanser av en dimension med samma värde som gemener. Dina data innehåller till exempel värdena `"liverpool"`, `"Liverpool"` och `"LIVERPOOL"` i en strängdimension. Om [!UICONTROL Lower case] är aktiverat kombineras alla tre värdena till `"liverpool"`. Om det är inaktiverat behandlas alla tre värdena som distinkta. |

{style="table-layout:auto"}

>[!NOTE]
>
>Om du aktiverar [!UICONTROL Lower case] för en sökdatauppsättningsdimension kan det finnas flera uppslagsvärden för samma identifierare. Om den här konflikten inträffar använder Customer Journey Analytics det första ASCII-sorterade värdet (versalvärden före gemener). Adobe rekommenderar att du inte använder uppslagsdatauppsättningar som innehåller samma värde när [!UICONTROL Lower case] är aktiverat.

![Skiftlägeskänslig dimension](../assets/case-sens-workspace.png)

## Inställningar för mätbeteende

| Inställning | Beskrivning/användningsfall |
| --- | --- |
| [!UICONTROL Count values] | Synlig för datatyperna Integer och Double schema. Öka måttet med den angivna mängden. Ökar till exempel måttet med 50 om värdet för kolumnen är `50`. |
| [!UICONTROL Count instances] | Synlig för datatyperna Integer och Double schema. Öka måttet med ett, oavsett värde. Förekomsten av ett värde ökar mätvärdet. Ökar till exempel måttet med 1 om värdet för kolumnen är `50`. |
| [!UICONTROL Values to count] | Synlig för datatyperna Boolean-schema. Låter dig avgöra om måttet ökar genom att räkna `true`, `false` eller båda. |

{style="table-layout:auto"}

Du kan generera både ett ordervärde och ett intäktsmått i Analysis Workspace med samma kolumn för händelsedatamängd med olika beteenden. Dra datamängdskolumnen för &#39;Intäkter&#39; två gånger till datavyn och ställ in den ena på &#39;Antal värden&#39; och den andra på &#39;Antal instanser&#39;. Mätvärdena för Orders räknar instanser medan måttet Intäkter räknar.
