---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b633e3e70c24d9b00b1ab2f80954ad698b12ce29
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 7%

---

# Versionsinformation för Customer Journey Analytics (CJA) (januari 2023)

**Senaste uppdatering**: 6 februari 2023

Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Viktiga funktioner och uppdateringar

| Funktion | Beskrivning | [Början av utrullning](/help/release-notes/releases.md) | [Allmän tillgänglighet](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Uppdatera till CJA-målgrupper** | När du har skapat en publik [Adobe skapar ett direktuppspelningssegment för Experience Platform för varje ny CJA-publik](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created). Ett AEP-direktuppspelningssegment skapas bara om organisationen är inställd för direktuppspelningssegmentering. | Ej tillämpligt | 3 februari 2023 |
| **Stöd för objektmatriser för profil- och uppslagsdatauppsättningar** | Profildatamängder och uppslagsdatamängder har nu stöd för objektarrayer som kan användas i CJA. | 11 januari 2023 | 19 januari 2023 |
| **Mappar på arbetsytan** | Med mappar kan du ordna och kategorisera dina projekt så att de blir lättare att hämta och komma åt. Dessutom har en delad **[!UICONTROL Company]** kan administratörer enkelt skapa och dela innehåll med alla Workspace-användare. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html) | Ej tillämpligt | 11 januari 2023 |
| **Standardstartsida** | The [ny landningssida](/help/getting-started/landing.md) som introducerades tidigare 2022 kommer att bli standardupplevelsen för alla användare på **11 januari 2023**. Den gamla landningssidan kommer att bli inaktuell och alla kommer att behöva använda den nya upplevelsen. | Ej tillämpligt | 11 januari 2023 |
| **Project Manager-sidan är inaktuell** | I och med lanseringen av den nya landningssidan har vi ersatt **[!UICONTROL Project Manager]** enligt **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Components]**. Den nya landningssidan har alla funktioner som finns på den gamla Project Manager-sidan och mycket mer. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | Ej tillämpligt | 11 januari 2023 |
| **Schemalägg arbetsböcker i Report Builder** | I Customer Journey Analytics kan du skapa scheman för att skicka arbetsböcker med regelbundna intervall. Nu kan mottagarna regelbundet få de senaste uppdateringarna av arbetsböckerna. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | Ej tillämpligt | 11 januari 2023 |
| **Spara nya projekt automatiskt** | Analysis Workspace sparar nu automatiskt nya projekt. Om du av någon anledning oväntat förlorar åtkomsten till ett nyligen skapat projekt innan du sparar det manuellt, är en återställningsversion av ditt projekt nu tillgänglig. Tidigare sparades projekt bara automatiskt efter att de först sparats manuellt. [Läs mer](/help/analysis-workspace/build-workspace-project/save-projects.md) | Ej tillämpligt | 11 januari 2023 |
| **Förbättrade användarinställningar** | Nu kan du konfigurera ytterligare inställningar på användarnivå (i [!UICONTROL Components] > [!UICONTROL Preferences]). När du anger användarinställningar spänner markeringarna över flera projekt, tabeller och visualiseringar. Sidan Inställningar innehåller nu följande nya flikar som alla innehåller många nya konfigurationsalternativ:<ul><li>Frihandstabell</li><li>Visualiseringar>/li></ul>. Fler inställningar finns nu på **[!UICONTROL General]** och **[!UICONTROL Project]** -tabbar.<p>Tidigare var många av dessa inställningar endast konfigurerbara för enskilda projekt, tabeller och visualiseringar. [Läs mer](/help/analysis-workspace/user-preferences.md) | Ej tillämpligt | 11 januari 2023 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar

AN-287349; AN-301684; AN-305491; AN-305769; AN-307912

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| **Förbättrad mappning av IP-till-geopositionering** | 29 september 2022 | Adobe för IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för mappning från IP till geopositionering. Adobe Analytics har senarelagt antagandet av den nya datauppsättningen till **11 januari 2023**. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p> CJA-data som tillhandahålls via [!UICONTROL Analytics Source Connector] utnyttjar automatiskt de nya mappningarna. |

{style=&quot;table-layout:auto&quot;}


## Relaterade resurser

* [Tidigare CJA-versionsinformation för 2022](/help/release-notes/2022.md)

* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)

* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv)

* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
