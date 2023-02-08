---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 13c697331004b715271a7256c671293afb3c9b1f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 8%

---

# Versionsinformation för Customer Journey Analytics (CJA) (februari 2023)

**Senaste uppdatering**: 6 februari 2023

Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Viktiga funktioner och uppdateringar

| Funktion | Beskrivning | [Början av utrullning](/help/release-notes/releases.md) | [Allmän tillgänglighet](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Uppdatera till CJA-målgrupper** | När du har skapat en målgrupp skapar Adobe ett direktuppspelningssegment för Experience Platform för varje ny CJA-målgrupp. Ett direktuppspelningssegment skapas bara om din organisation är inställd för direktuppspelningssegmentering. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created) | Ej tillämpligt | 3 februari 2023 |
| **Dölj datumintervall för jämförelse i Mobile Scorecards** | Med Mobile Scorecards kan du nu dölja datumintervall för jämförelse. | Ej tillämpligt/ | 8 februari 2023 |
| **Kalenderuppdateringar på arbetsytan** | <ul><li>Datum för ankarpanel: Du kan göra datumintervallets komponenter relativa till panelkalendern. [Läs mer](/help/components/date-ranges/calendar.md)</li><li>Uppdateringar av kalenderformat: Kalenderformaten i hela användargränssnittet har uppgraderats för att ge ett mer konsekvent och lättanvänt arbetsflöde.</li><li>Uppdateringar av kalenderformel: Om du använder relativa datum återspeglar alla kalenderformler början av panelens datumintervall. [Läs mer](/help/components/date-ranges/calendar.md)</li></ul> | Ej tillämpligt | 8 februari 2023 |
| **Rad-/kolumnfiltrering för Adobe Analytics Source Connector-direktuppspelning** | Med Analytics Source Connector i Adobe Experience Platform går det nu att filtrera analysdata som används för att fylla i profiler i [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en).<p>Filtrering på radnivå minskar antalet händelser som är associerade med profiler. Filtrering på kolumnnivå bidrar till att minska detaljrikedomen i själva händelserna och gör att du kan optimera användningen av profilberättiganden. Denna filtrering gäller endast data som skickas till kundprofilen i realtid och [Identitetstjänst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en).<p>**Filtreringen påverkar inte data som skickas till Data Lake för användning i program som Customer Journey Analytics**. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | Ej tillämpligt | 22 februari 2023 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Customer Journey Analytics

AN-309106

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Inga aktuella meddelanden | Ej tillämpligt | Ej tillämpligt |

{style=&quot;table-layout:auto&quot;}

## Relaterade resurser

* [Tidigare CJA-versionsinformation för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
