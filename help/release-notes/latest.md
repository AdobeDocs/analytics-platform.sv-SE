---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7260c9cadbd5b6e5e85f778547635330b8bfc49a
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 1%

---

# Aktuell versionsinformation för Customer Journey Analytics (februari 2026)

**Senast uppdaterad**: 12 februari 2026

Versionskommentarerna gäller versionsperioden från februari 2026. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion och beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ------- | ---- |
| **Sidhuvud åsidosätter** <p>Du kan ange rubriknamn och hemligt rubrikvärde i Content Analytics. Denna [header åsidosätter konfigurationen](/help/content-analytics/config/guided.md#header-overrides) och ser till att Content Analytics skickar anpassade HTTP-huvuden för att kringgå eventuella robotdetekterings- eller gattrattekniker som du har implementerat.</p> |  | 2 februari 2026 |
| **Inkludera flera dimensionskolumner i en frihandstabell**<p>Du kan nu inkludera upp till 5 dimensionskolumner i en frihandstabell, så att du kan visa flera dimensionsobjekt sida vid sida. Varje rad med dimensionsobjekt fungerar som en enda sammanfogad dimensionspost.</p><p>Du kan använda filter, sortering, uppdelningar med mera i frihandstabeller med flera dimensionskolumner för att skapa en djupare och mer anpassad analys.</p><p>Tidigare kunde du bara ta med 1 dimensionskolumn i en friformstabell.</p><p>Mer information finns i [Inkludera flera dimensionskolumner i en friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | 28 januari 2026 | 18 februari 2026 |
| **Sortera tabeller efter flera kolumner**<p>Nu kan du sortera data i en frihandstabell efter flera kolumner i Analysis Workspace, oavsett om det är dimensioner eller mätvärden.</p><p>När du sorterar data för flera kolumner sorteras data efter den prioritet som du tilldelar varje kolumn. Prioritetsnumrering visas bredvid sorteringsikonen.</p><p>Mer information finns i [Filtrera och sortera tabeller på frihand](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | 28 januari 2026 | 18 februari 2026 |
| **Förbättringar av fullständig tabellexport**<p>Fullständig tabellexport innehåller följande förbättringar:</p><p>Förbättringar av exportskapande och konfiguration</p><ul><li>Skapa en export på sidan Exporter. Tidigare kunde du bara skapa en export från Analysis Workspace genom att högerklicka på tabellen.</li><li>Lägg till ett nytt konto eller en plats när du skapar en export.</li><li>Automatisera skapandet av filnamn och mappplaceringen av exporterade filer. På så sätt kan filnamn på ett logiskt sätt förtydliga och ordnas i mappar. Tidigare var filnamnen oförutsägbara och grupperade i en enda mapp.</li><li>Stöd för export av data som Parquet-filer för förbättrad datalagerkompatibilitet. Tidigare hade bara CSV och JSON stöd.</li></ul><p>Förbättrad exporthantering</p><ul><li>Förnya eller avbryta en eller flera exporter från sidan Exporter.</li><li>Skicka om en eller flera exporter från sidan Loggar.</li><li>Skicka e-post till enskilda användare eller grupper när en export misslyckas eller snart upphör att gälla.</li><li>Mer exakta felmeddelanden för misslyckade exporter.</li></ul><p>Beräknade mått-, segment- och dimensionsförbättringar</p><ul><li>Stöd för mer beräknade mätfunktioner. Tidigare stöddes endast enkla matematiska funktioner.</li><li>Använd segment när du skapar en export.</li><li>Stöd för dubbeldatatypsdimensioner för bättre precision.</li></ul><p>Administrativa förbättringar</p><ul><li>Administratörer kan nu visa alla exporter och loggar, oavsett vem som skapade dem.</li></ul><p>(Dokumentationslänk som ska följas.)</p> | 18 februari 2026 | 4 mars 2026 |
| **Content Analytics: Miniatyrbilder och förhandsvisningar för punktvisualisering** <p>När du visar en punktvisualisering i Content Analytics visas nu en miniatyrbild av resursen när du hovrar över en punkt i diagrammet. Med den här miniatyrbilden kan du snabbt och enkelt se vilket innehåll som visas i diagrammet.</p><p>(Dokumentationslänk som ska följas.)</p> | 17 februari 2026 | 2 mars 2026 |
| **Content Analytics: Miniatyrbilder och förhandsgranskningar av stapelvisualisering** <p>När du visar en vågrät fältvisualisering i Content Analytics visas nu en miniatyrbild av resursen när du hovrar över ett fält i diagrammet. Med den här miniatyrbilden kan du snabbt och enkelt se vilket innehåll som visas i diagrammet.</p><p>(Dokumentationslänk som ska följas.)</p> | 23 februari 2026 | 9 mars 2026 |
| **Uppdatera till funktionen Approximate Count Distinct**<p>Den HLL-algoritm som används i funktionen Approximate Count Distinct kommer snart att uppdateras. Resultatet för tal som använder den här funktionen kan ändras något från historiska tal enligt följande:<ul><li>När mycket små mängder unika värden räknas kommer resultatet att förbättras så att exakta räkningar används i stället för uppskattningar.</li><li>När du räknar med något större kommer antalet uppskattningar att behålla samma noggrannhet som före den här uppdateringen (uppskattningarna är exakta inom 5 procent av det exakta talet, 95 procent av tiden).</li></ul><p>Mer information om funktionen Approximate Count Distinct finns i [Distinkt antal](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) i [Avancerade funktioner](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | Mars 2026 |
| **Stöd för dataspegling**  <p>Med stöd för modellbaserade scheman och CDC-funktionalitet (Change Data Capture) för specifika källanslutningar i Experience Platform kan Customer Journey Analytics stödja [dataspegling](/help/data-mirror/data-mirror.md) i datalagerlösningar som [!DNL Snowflake], [!DNL Azure Databricks] och [!DNL Google BigQuery].</p><p>Kontakta ditt Adobe-kontoteam för att få tillgång till betaversionen.</p> | Beta-version: 24 september 2025 | TBD |
| **Direktuppspelande medietjänster: Supportschemadata** <p>Nu kan du överföra schemadata från tidigare direktuppspelat mediematerial för att enklare och exaktare kunna spåra tittandet.</p><p>Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:</p><ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul><p>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment.</p><p>Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.</p><p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment.</p><p>Mer information finns i [Överför schemadata för att spåra livematerial](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 oktober 2025 | Första halvåret 2026<p>(Ursprungligen planerat att släppas den 29 oktober 2025)</p> |
| **Kombinera rapportsviter från flera IMS-organ**<p>Du kan använda Analytics Source Connector för att kombinera rapportsviter från flera IMS-organ. Med den här [funktionen för korsvis IMS-datamappning](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md) kan organisationer få en kombinerad vy av sina kunddata, även när kunddata sprids över flera IMS-organisationer. <p>**Obs!** Den här konfigurationen är bara tillgänglig genom att skicka en begäran till Adobe kundtjänst.</p> |  | 12 februari 2026 |

## Korrigeringar i Customer Journey Analytics

**Analysis Workspace**: AN-421930, AN-424997, AN-424194, AN-425515, AN-425254, AN-423174, AN-428 834, AN-306540, AN-426014, AN-427801
**Komponenter**:
**Content Analytics**:
**Guidad analys**:
**Exporter**: AN-422041, AN-421599, AN-422112
**Datavyer**:
**Implementering**:
**Report Builder**: AN-391415, AN-425125
**Rapportering**: AN-425817, AN-424362, AN-425752, AN-425278, AN-42249, AN-403446, AN-444 24727, AN-426791, AN-427985
**Segmentering**: AN-428905, AN-428232
**Schemalagda rapporter**: AN-425484, AN-425137
**Delade mått**:
**Annan**: AN-428833, AN-425074


## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| **Borttagning av TLS 1.2-chiffersviter** | 11 februari 2026 | Meddelande till administratörer: Adobe planerar att ta bort stödet för följande TLS 1.2-chiffersviter från Adobe datainsamlingsservrar den 27 maj 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>Ingen kundåtgärd krävs för de flesta implementeringar. Den här ändringen påverkar i första hand analysdata som skickas från äldre inbyggda program som använder inaktuella TLS-bibliotek och ett fåtal webbbesökare i inaktuella webbläsare eller operativsystem. Genom att ta bort stödet för dessa chiffreringssviter förbättras säkerheten och Adobe anpassas till moderna krypteringsstandarder. Färre än 0,1 % av datainsamlingstrafiken är för närvarande beroende av dessa chiffersviter.</p> |

## Relaterade resurser

* [Tidigare versionsinformation för Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics dokumentationsuppdateringar](/help/release-notes/doc-changes.md)
