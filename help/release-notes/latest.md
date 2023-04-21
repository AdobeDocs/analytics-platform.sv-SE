---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 64a774d9151c40ea9eadb1fb80c07db168ac8667
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 6%

---

# Versionsinformation för Customer Journey Analytics (CJA) (april 2023)

**Senaste uppdatering**: 12 april 2023

Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Viktiga funktioner och uppdateringar

| Funktion | Beskrivning | [Början av utrullning](/help/release-notes/releases.md) | [Allmän tillgänglighet](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Rad-/kolumnfiltrering för Analytics Source Connector-direktuppspelning** | Med Analytics Source Connector i Adobe Experience Platform går det nu att filtrera analysdata som används för att fylla i profiler i [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en). Filtrering på radnivå minskar antalet händelser som är associerade med profiler. Filtrering på kolumnnivå bidrar till att minska detaljrikedomen i själva händelserna och gör att du kan optimera användningen av profilberättiganden. Denna filtrering gäller endast data som skickas till kundprofilen i realtid och [Identitetstjänst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en). **Filtreringen påverkar inte data som skickas till Data Lake för användning i program som Customer Journey Analytics**. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | Ej tillämpligt | 29 mars 2023 |
| **Dataordlista i Analysis Workspace** | Med Data Dictionary kan både användare och administratörer hålla reda på och bättre förstå komponenterna (dimensioner, mått) i sin CJA-miljö. [Läs mer](/help/components/data-dictionary/data-dictionary-overview.md) | 8 mars 2023 | 29 mars 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** | <p>Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Detta inkluderar delning med personer utanför organisationen eller personer inom organisationen som inte är tilldelade CJA. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)</p> <p>Den här funktionen är aktiverad som standard och kan inaktiveras av systemadministratören. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#company-preferences)</p> | 26 april 2023 (endast privat betaåtkomst) | Juni 2023 |
| **Adobe Product Analytics - endast privat betaåtkomst** | Den 21 mars 2023 presenterade Adobe Adobe Product Analytics, ett nytt sätt att interagera med data och insikter från olika kanaler i Customer Journey Analytics. Dessa nya funktioner gör det möjligt för produktteamen att självbetjäna data och insikter om sina produktupplevelser via guidade analysarbetsflöden &#x200B;. Team kan:<ul><li>Förstå mönster i användarengagemanget över tid &#x200B;</li><li>Analysera tillväxten av &#x200B;</li><li>Identifiera friktionsområden i en serie steg &#x200B;</li><li>Mät effekten av &#x200B;</li><li>Identifiera meningsfulla segment för att engagera och vårda under hela deras livslånga resa med &#x200B;</li><li>Öppna i Analysis Workspace för djupare analyser och samarbete med analytiker och mycket mer! &#x200B;</li></ul>Om du är CJA-kund och är intresserad av att gå med i den privata betaversionen kontaktar du ditt Adobe-kontoteam. [Läs mer](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | Ej tillämpligt | 17 juli 2023 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-313118; AN-313390; AN-314135; AN-316381; AN-316811

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | Ej tillämpligt | Ej tillämpligt |

{style="table-layout:auto"}

## Relaterade resurser

* [Tidigare CJA-versionsinformation för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
