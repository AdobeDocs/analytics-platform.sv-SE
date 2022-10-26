---
title: Visa versionsinformation för Customer Journey Analytics
description: Senaste versionsinformation för CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 07842c9f1e2f4708d0881dec75c067d93611626c
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 4%

---

# Versionsinformation för Customer Journey Analytics (CJA) (oktober/november 2022)

**Senaste uppdatering**: 25 oktober 2022

Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Viktiga funktioner och uppdateringar

| Funktion | Beskrivning | [Början av utrullning](/help/release-notes/releases.md) | [Allmän tillgänglighet](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **[!UICONTROL Key metric summary]visualisering** | The [!UICONTROL Key metric summary] visualisering gör att du kan se hur viktiga mätvärden trendar inom en enda tidsram. Du kan också jämföra mätprestanda över två tidsramar. [Läs mer](/help/analysis-workspace/visualizations/key-metric.md) | 5 oktober 2022 | 19 oktober 2022 |
| **Skiftlägesokänsliga multivärdesvariabler** | För skiftlägesokänsliga multivärdesvariabler lagras värdena i `mvvar1` - `mvvar3` kommer inte längre att sänkas automatiskt. I stället kommer data som skickas via Analytics Source Connector till Adobe Experience Platform och CJA att återspegla det ursprungliga fallet som skickades från sidan. | Ej tillämpligt | 24 oktober 2022 |
| **CJA-granskningslogg** | Med Customer Journey Analytics (CJA) kan du granska användaraktivitet för olika tjänster och funktioner i form av granskningsloggar. Loggarna utgör en verifieringskedja som kan hjälpa till med felsökningsproblem och hjälpa ditt företag att effektivt följa företagets policyer för datahantering och krav som t.ex. HIPAA (Health Insurance Portability and Accounability Act). Dessa loggar var tidigare bara tillgängliga via API:t för granskningsloggar. [Läs mer](/help/privacy/audit-log.md) | Ej tillämpligt | 26 oktober 2022 |
| **HIPAA-beredskap** | Adobe stöder nu mottagning, användning, underhåll eller överföring av skyddad hälsoinformation i Customer Journey Analytics och andra Experience Platform-baserade tillämpningar enbart för vårdkunder. Sjukvården är endast avsedd för vårdkunder som är antingen en enhet som omfattas eller en Business Associate i USA. [Läs mer](https://www.adobe.com/trust/compliance/hipaa-ready.html) | Ej tillämpligt | 7 november 2022 |
| **Lösenordsskydd för schemalagda projekt** | Den här funktionen är en del av beredskapen för HIPAA och gäller endast för vårdkunder. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#password) | Ej tillämpligt/ | 7 november 2022. |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar

* Ett problem har korrigerats där de senaste MacOS-versionerna felaktigt namngavs som &quot;Macintosh&quot;. Med den här korrigeringen börjar OS-dimensionen använda versionsnumrering från&quot;MacOS&quot;, med början från MacOS 11. (AN-301834)

### Andra korrigeringar

AN-302367; AN-302562; AN-304036

## Viktiga meddelanden för CJA-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| **Standardstartsida** | 29 september 2023 | The [ny landningssida](/help/getting-started/landing.md) som introducerades tidigare i år kommer att bli standardupplevelsen för alla användare i **Januari 2023**. Den aktuella sidan kommer att bli inaktuell och alla kommer att behöva använda den nya upplevelsen. |
| **Förbättrad mappning av IP-till-geopositionering** | 29 september 2022 | Adobe för IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för mappning från IP till geopositionering. Adobe Analytics har senarelagt antagandet av den nya datauppsättningen till **Januari 2023**. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p> CJA-data som tillhandahålls via [!UICONTROL Analytics Source Connector] utnyttjar automatiskt de nya mappningarna. |
| **[!UICONTROL Anomaly detection]autokörningsförhållanden** | 29 september 2022 | Idag [!UICONTROL Anomaly detection] körs automatiskt på alla kolumner i friformstabeller i tidsserier. För att säkerställa att data är tillgängliga för analys och att projekt läses in snabbare kommer Adobe att ändra hur [!UICONTROL Anomaly detection] kör automatiskt. Startar **26 oktober 2022**, körs avvikelseidentifiering bara automatiskt på den första måttkolumnen i en tabell. Du kan konfigurera kolumninställningar så att de körs [!UICONTROL Anomaly detection] på andra kolumner, om det behövs. |

{style=&quot;table-layout:auto&quot;}


## Relaterade resurser

* [Tidigare CJA-versionsinformation för 2022](/help/release-notes/2022.md)

* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)

* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
