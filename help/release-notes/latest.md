---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 785ea95049135adef888c20a6d9fef9f31439a7d
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 3%

---

# Versionsinformation för Customer Journey Analytics (CJA) (oktober 2022)

**Senaste uppdatering**: 18 oktober 2022

Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Relaterade resurser

* [Tidigare CJA-versionsinformation för 2022](/help/release-notes/2022.md)

* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)

* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## Viktiga funktioner och uppdateringar

| Funktion | Beskrivning | [Måldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Mappar i arbetsyteprojekt** | Mappar i Workspace Projects hjälper användarna att ordna och kategorisera sina projekt med hjälp av mappar för bättre hämtning och åtkomst. Med en delad företagsmapp kan administratörer enkelt skapa och dela innehåll med alla Workspace-användare [Läs mer](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md) | 19 oktober 2022 |
| **Panelen Experimentation** | Med den nya Workspace-panelen kan CJA-användare utvärdera hur stort A/B-experimentet blir och hur säkert det är från alla källor - online, offline, från Adobe-lösningar, Adobe Journey Optimizer och till och med BYO-data. [Läs mer](/help/analysis-workspace/c-panels/experimentation.md) | 5 oktober 2022 |
| **[!UICONTROL Key metric summary]visualisering** | The [!UICONTROL Key metric summary] visualisering gör att du kan se hur viktiga mätvärden trendar inom en enda tidsram. Du kan också jämföra mätprestanda över två tidsramar. Läs mer | Avfasad utrullning från 5 oktober 2022 |
| **Stöd för datumfält i CJA** | Tillåter CJA att rapportera datum- och datumfält. [Läs mer](/help/data-views/data-views-usecases.md#date) | 5 oktober 2022 |
| **Mobilapp: Anpassade detaljvyer** | Med anpassade detaljvyer kan ni målinrikta er ännu mer om vilken information ni delar med er målgrupp genom att låta dem fokusera på det som är viktigast. Du kan ändra layouten för den detaljvy som är kopplad till varje styrkortsplatta och du kan lägga till text för att bättre förklara vad slutanvändaren kan se i data. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=en) | 5 oktober 2022 |
| **Skiftlägesokänsliga multivärdesvariabler** | För skiftlägesokänsliga multivärdesvariabler lagras värdena i `mvvar1` - `mvvar3` kommer inte längre att sänkas automatiskt. I stället kommer data som skickas via Analytics Source Connector till Adobe Experience Platform och CJA att återspegla det ursprungliga fallet som skickades från sidan. | 24 oktober 2022 |

{style=&quot;table-layout:auto&quot;}

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Standardstartsida** | 29 september 2023 | The [ny landningssida](/help/getting-started/landing.md) som introducerades tidigare i år kommer att bli standardupplevelsen för alla användare i **Januari 2023**. Den aktuella sidan kommer att bli inaktuell och alla kommer att behöva använda den nya upplevelsen. |
| **Förbättrad mappning av IP-till-geopositionering** | 29 september 2022 | Adobe för IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för mappning från IP till geopositionering. Adobe Analytics har senarelagt antagandet av den nya datauppsättningen till **Januari 2023**. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p> CJA-data som tillhandahålls via [!UICONTROL Analytics Source Connector] utnyttjar automatiskt de nya mappningarna. |
| **[!UICONTROL Anomaly detection]autokörningsförhållanden** | 29 september 2022 | Idag [!UICONTROL Anomaly detection] körs automatiskt på alla kolumner i friformstabeller i tidsserier. För att säkerställa att data är tillgängliga för analys och att projekt läses in snabbare kommer Adobe att ändra hur [!UICONTROL Anomaly detection] kör automatiskt. Startar **26 oktober 2022**, körs avvikelseidentifiering bara automatiskt på den första måttkolumnen i en tabell. Du kan konfigurera kolumninställningar så att de körs [!UICONTROL Anomaly detection] på andra kolumner, om det behövs. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
