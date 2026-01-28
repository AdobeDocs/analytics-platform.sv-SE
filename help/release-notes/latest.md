---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3955f7c8da90481610328c0657b33e81ad6c0057
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 1%

---

# Aktuell versionsinformation för Customer Journey Analytics (januari 2026)

**Senast uppdaterad**: 14 januari 2026

Versionsinformationen gäller januari 2026-versionsperioden. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysera målgrupper från Experience Platform profildatauppsättningar i Customer Journey Analytics** | Du kan nu importera målgruppsmedlemskapsdata från Experience Platform Profile-datauppsättningar till en Customer Journey Analytics-anslutning. Publiken blir tillgänglig som nya dimensioner för användning i Analysis Workspace.<p>Detta är möjligt tack vare en ny funktion i Customer Journey Analytics för att importera XDM-objektkartor, som gör det möjligt att importera AudienceID:n för profiler.</p><p>Tidigare kunde endast enkla XDM-kartor hämtas till Customer Journey Analytics.</p><p>Förutom att kunna lägga till målgruppsdata som dimensioner i alla projekt i Analysis Workspace finns även följande nya Workspace-mallar:</p><ul><li>Audience Analytics - översikt</li><li>Samtyckesprincip - översikt</li></ul><p>Mer information finns i [Översikt över målgruppsanalys](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html).</p> | 22 oktober 2025 | 27 januari 2026 <p> (ursprungligen planerat till 22 januari 2026)</p> |
| **Data storytelling: Generera bildpresentationer från Workspace-rapporter** | Nu kan du automatiskt generera en bildpresentation (i .pptx-format) som baseras på en Analysis Workspace-rapport. Workspace identifierar viktiga insikter i rapporten och konverterar dem till bilder som är klara för intressenter.<p>Den här funktionen minskar den tid och det arbete som krävs för att ta fram resultaten, bygga upp chefsberättelser och kommunicera affärsmässiga effekter.</p><p>Mer information finns i [Data storytelling: Generate slide presentations from Workspace reports](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 oktober 2025 | 28 januari 2026 |
| **Inkludera flera dimensionskolumner i en frihandstabell** | Du kan nu inkludera upp till 5 dimensionskolumner i en frihandstabell, så att du kan visa flera dimensionsobjekt sida vid sida. Varje rad med dimensionsobjekt fungerar som en enda sammanfogad dimensionspost.<p>Du kan använda filter, sortering, uppdelningar med mera i frihandstabeller med flera dimensionskolumner för att skapa en djupare och mer anpassad analys.</p><p>Tidigare kunde du bara ta med 1 dimensionskolumn i en friformstabell.</p><p>Mer information finns i [Inkludera flera dimensionskolumner i en friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | 28 januari 2026 | 18 februari 2026 |
| **Sortera tabeller efter flera kolumner** | Nu kan du sortera data i en frihandstabell efter flera kolumner i Analysis Workspace, oavsett om det är dimensioner eller mätvärden.<p>När du sorterar data för flera kolumner sorteras data efter den prioritet som du tilldelar varje kolumn. Prioritetsnumrering visas bredvid sorteringsikonen.</p><p>(Dokumentationslänk att följa.)<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | 28 januari 2026 | 18 februari 2026 |
| **Kombinera datakällor från flera IMS-organ** | Nu kan du använda Analytics Source Connector för att kombinera flera datakällor från flera IMS-organ. På så sätt kan organisationer få en kombinerad bild av sina kunddata, även när kunddata sprids över flera IMS-organ. <p>**Obs!** Den här konfigurationen är bara tillgänglig genom att skicka en begäran till Adobe kundtjänst.</p>  <p>(Dokumentationslänk som ska följas.)</p> |  | 30 januari 2026 |
| **Strömning i anslutningar** | Nu är det enklare att sy ihop stygn i Customer Journey Analytics. Istället för att duplicera en datauppsättning och använda sammanfogning på den duplicerade datauppsättningen görs nu sammanfogning av data till Customer Journey Analytics, vilket eliminerar behovet av duplicerade datauppsättningar och scheman. <p>Dessutom kan du nu [initiera sammanslagning genom ett uppdaterat anslutningsgränssnitt](/help/stitching/use-stitching-ui.md) i stället för att behöva begära sammanslagning via Adobe kundtjänst.</p><p> *Tidigare meddelade releasedatum har skjutits upp på grund av ytterligare insatser som krävdes och semestersäsongen. En fasad utrullning planeras nu för att garantera stabilitet och minimera störningar under semesterperioden.*</p> | 28 oktober 2025 | 30 januari 2026 |
| **Stöd för dataspegling** | Med stöd för modellbaserade scheman och CDC-funktionalitet (Change Data Capture) för specifika källanslutningar i Experience Platform kan Customer Journey Analytics stödja [dataspegling](/help/data-mirror/data-mirror.md) i datalagerlösningar som [!DNL Snowflake], [!DNL Azure Databricks] och [!DNL Google BigQuery].<p>Kontakta ditt Adobe-kontoteam för att få tillgång till betaversionen.</p> | Beta-version: 24 september 2025 | TBD |
| **Direktuppspelande medietjänster: Supportschemadata** | Nu kan du överföra schemalagda data från tidigare direktuppspelat mediematerial för att enklare och exaktare spåra tittandet.<p>Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:</p><ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul><p>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment.</p><p>Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.</p><p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment.</p><p>Mer information finns i [Överför schemadata för att spåra livematerial](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 oktober 2025 | Första halvåret 2026<p>(Ursprungligen planerat att släppas den 29 oktober 2025)</p> |

## Korrigeringar i Customer Journey Analytics

**Analysis Workspace**: AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422 027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-4057 96, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502, AN-40435 3, AN-404352, AN-404048, AN-403241, AN-402523, AN-400795, AN-396149, AN-39090 AN-390646, AN-383484, AN-376980, AN-371729, AN-347570, AN-404835
**Komponenter**:
**Content Analytics**:
**Guidad analys**: AN-421274
**Exporterar**:
**Datavyer**: AN-421891, AN-404627
**Implementering**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Rapportering**:
**Segmentering**:
**Schemalagda rapporter**: AN-423087, AN-422686
**Delade mått**:
**Övrigt**: AN-422946, AN-422775, AN-42273, AN-422100, AN-420045, AN-404891, AN-3 90912


## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt |  |  |

## Relaterade resurser

* [Tidigare versionsinformation för Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics dokumentationsuppdateringar](/help/release-notes/doc-changes.md)
