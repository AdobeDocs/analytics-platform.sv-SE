---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 56f62d8af96e64a6867e38a9701219bcefc62a6a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 1%

---

# Versionsinformation för Customer Journey Analytics (CJA) (april 2022)

>[!NOTE]
>
>Den här sidan innehåller information om förhandsversioner som kan ändras.

**Senaste uppdatering**: 13 april 2022

## Viktiga funktioner

| Funktion | Beskrivning | [Måldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Dimensionens delsträngar | Innehåller flera metoder för att extrahera den önskade delen av en sträng för användning som dimensionsobjekt. Med den här funktionen kan du också behandla en strängdimension som en array om strängen innehåller avgränsade värden. [Läs mer](../data-views/component-settings/substring.md) | 20 april 2022 |
| Dataförberedelse för Analytics-källkoppling | The [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) är nu integrerat med [Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) funktioner från Adobe Experience Platform. Adobe Real-time Customer Data Platform (RTCDP)-, CJA- och Adobe Journey Optimizer-kunder (AJO) kan nu utöka fältgruppen Analytics med ytterligare fältgrupper. De kan också utnyttja över 100 Data Prep-operatorer för att berika analysdata vid intag i Adobe Experience Platform (AEP). RTCDP-kunder kan nu aktivera flera rapportsviter som har aktiverats för dataprep för profilen.<p>CJA-kunder som importerar flera rapportsviter via Analytics Source Connector kan nu frigöra kolumnskillnader mellan olika rapportsviter. Om&quot;Sökord&quot; till exempel lagras i `eVar1` i en rapportserie och `eVar2` i en annan rapportserie kan du med Data Prep utöka fältgruppen Analytics med en ny kolumn som sammanfogar värdena från de två eVars-elementen. | 25 april 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
