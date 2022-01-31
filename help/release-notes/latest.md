---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
source-git-commit: 6585e3b3f5a48edcf4357f710630ebbd36175e7d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Versionsinformation för Customer Journey Analytics

## Viktiga uppdateringar

|[!UICONTROL Persistence] alternativ för bindningsdimensioner och bindningsmått| När du skapar eller redigerar en datavy kan du binda en dimensions beständighet till en annan dimension eller mätvärde. Detta koncept kallas _varuexponering_ i Rapporter och analyser och stöds nu i CJA. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)| 19 januari 2022 |

## Andra uppdateringar

| Funktion | Beskrivning | Måldatum |
| ----------- | ---------- | ----- |
| [!UICONTROL First Known] och [!UICONTROL Last Known] allokeringsmodeller | Dessa två nya allokeringsmodeller tar det första eller sista observerade värdet för en dimension inom ett angivet beständigt omfång (session, person eller anpassad tidsperiod med summering). Sedan tillämpar de allokeringsmodellen på alla händelser inom det angivna omfånget. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#allocation-settings) | 19 januari 2022 |
| [!UICONTROL PersonID] och [!UICONTROL PersonID namespace] som dimensioner | Exponerar `personID` (eller `customerID`eller något annat ID som du använder för att sammanfoga datauppsättningar i en anslutning) som en dimension i datavyer. Den här förbättringen gör det enklare för dig att inkludera `personID` som en dimension i datavyn genom att dra in den från anslutningen. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional-standard-components) | 19 januari 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Dokumentationsuppdateringar för Customer Journey Analytics](/help/doc-changes.md)
