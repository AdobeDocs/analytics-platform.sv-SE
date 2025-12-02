---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 1%

---

# Aktuell versionsinformation för Customer Journey Analytics (oktober 2025)

**Senast uppdaterad**: 14 oktober 2025

Versionsinformationen gäller från oktober till början av november 2025. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Filtervillkor ingår i radinvisualiseringar och miniatyrbilder** | Alla sökfiltervillkor som du tillämpar på ett frihandsfilter finns nu alltid med i miniatyrbilder. Dessutom kan du inkludera sökfiltervillkor i all visning av anslutna rader.<p>Du kan konfigurera radvisualiseringar så att de omfattar sökfiltervillkor genom att välja miniatyrdiagram i kolumnrubriken för mätvärden i den anslutna tabellen.</p><p>Tidigare ingick inte sökfiltervillkor i miniatyrdiagram eller anslutna linjevisualiseringar.</p><p>Mer information finns i [Visa trenddata för en frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).</p> | | 15 oktober 2025 |
| **Data storytelling: Generera bildpresentationer från Workspace-rapporter** | Nu kan du automatiskt generera en bildpresentation (i .pptx-format) som baseras på en Analysis Workspace-rapport. Workspace identifierar viktiga insikter i rapporten och konverterar dem till bilder som är klara för intressenter.<p>Den här funktionen minskar den tid och det arbete som krävs för att ta fram resultaten, bygga upp chefsberättelser och kommunicera affärsmässiga effekter.</p><p>Mer information finns i [Data storytelling: Generate slide presentations from Workspace reports](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 oktober 2025 | Januari 2026 |
| **Realtidsrapportering** | [Realtidsrapportering i Customer Journey Analytics](/help/components/real-time/real-time.md) visar och uppdaterar data och visualiseringar inom en eller flera paneler i Analysis Workspace i realtid. | 18 september 2025 (ursprungligen planerat att släppas den 15 augusti 2025) | 22 oktober 2025 |
| **Stöd för dataspegling** | Med stöd för modellbaserade scheman och CDC-funktionalitet (Change Data Capture) för specifika källanslutningar i Experience Platform kan Customer Journey Analytics stödja [dataspegling](/help/data-mirror/data-mirror.md) i datalagerlösningar som [!DNL Snowflake], [!DNL Azure Databricks] och [!DNL Google BigQuery].<p>Kontakta ditt Adobe-kontoteam för att få tillgång till betaversionen.</p> | Beta-version: 24 september 2025 | TBD |
| **Strömning i anslutningar** | Förenklar sammanfogning av Customer Journey Analytics. Istället för att duplicera en datauppsättning och använda sammanfogning på den duplicerade datauppsättningen görs nu sammanfogning av data till Customer Journey Analytics, vilket eliminerar behovet av duplicerade datauppsättningar och scheman. <p>I stället för att behöva begära sammanslagning via kundsupport kan du nu [initiera sammanslagning från ett uppdaterat anslutningsgränssnitt](/help/stitching/use-stitching-ui.md).</p><p> *Tidigare meddelade releasedatum har flyttats på grund av ytterligare åtgärder som krävs. De nya releasedatumen överlappar julsäsongen, vilket medför ytterligare releasebegränsningar. En fasad utrullning planeras nu för att garantera stabilitet och minimera störningar under semesterperioden.*</p> | 28 oktober 2025 | 30 april 2026 |
| **Direktuppspelande medietjänster: Supportschemadata** | Nu kan du överföra schemalagda data från tidigare direktuppspelat mediematerial för att enklare och exaktare spåra tittandet.<p>Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:</p><ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul><p>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment.</p><p>Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.</p><p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment.</p><p>Mer information finns i [Överför schemadata för att spåra livematerial](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 oktober 2025 | Första halvåret 2026<p>(Ursprungligen planerat att släppas den 29 oktober 2025)</p> |
| **Källanslutning för analys: Sök i rapportsviter i Experience Platform** | Om du har ett stort antal rapportsviter kan du nu [söka efter rapportsviten](/help/data-ingestion/analytics.md#set-up-an-adobe-analytics-source-connector) som du vill ansluta till i arbetsflödet för dataflödet i Analytics Source Connector. | | 30 oktober 2025 |
| **Direktuppspelningsmedia: Uppdaterade XDM-fält för insamling av direktuppspelningsmediedata i Adobe Experience Platform** | När Streaming Media-data samlas in i Adobe Experience Platform bör de XDM-fältsökvägar som visas under rubriken &quot;XDM Field Path&quot; i dokumentationen för Streaming Media-parametrar inte längre användas. I stället måste kunder som implementerat Analytics-källkopplingen för att samla in Streaming Media-data till Platform före 9 maj 2025 migrera sina befintliga konfigurationer till MediaReporting-fältsökvägarna, vilket visas under rubriken&quot;Reporting XDM Field Path&quot; i dokumentationen för Streaming Media-parametrar.<p> De här fältsökvägarna finns på följande sidor och markeras som &quot;Undertryckta&quot;: [Parametrar för ljud- och videoinnehåll](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Lägg till parametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametrar för spelartillstånd](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) och [Kvalitetsparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). (Ingen åtgärd krävs för kunder som implementerar källkopplingen för Analytics efter 9 maj 2025 och som redan använder enbart XDM-sökvägar för mediaReporting.)</p><p>Inmatningen av data i de borttagna XDM-fältsökvägarna fortsätter till slutet av oktober 2025. Efter det kommer inaktuella fältsökvägar att tas bort helt och inte längre visas i användargränssnittet för Adobe Experience Platform Schema, och data skickas endast med fältsökvägarna för mediaReporting.</p><p>Mer information finns i [Migrera en Analytics Source Connector-implementering till uppdaterade XDM Streaming Media-fält](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Kontakta Adobe Consulting-tjänsterna eller kontoteamet för att få migreringssupport. </p> |  | Oktober 2025 |

## Korrigeringar i Customer Journey Analytics

**Analysis Workspace**: AN-400507, AN-400265, AN-399209, AN-397146, AN-394992, AN-390795
**Komponenter**:
**Content Analytics**:
**Exporter**: AN-399012, AN-388578
**Guidad analys**:
**Implementering**: AN-397551, AN-397550, AN-397190, AN-396127
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**Rapportering**:
**Segmentering**:
**Schemalagda rapporter**:
**Delade värden och dimensioner**:
**Annan**:


## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

## Relaterade resurser

* [Tidigare versionsinformation för Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics dokumentationsuppdateringar](/help/release-notes/doc-changes.md)
