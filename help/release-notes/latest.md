---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: eb860cf67f8174838837816a781f3f5ef9015683
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (augusti 2025)

**Senast uppdaterad**: 4 september 2025


Versionsanteckningarna gäller från den 13 augusti till den 16 september 2025. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Uppdateringar i användargränssnittet** | [Användningsgränssnittet](/help/connections/manage-connections.md#usage) lägger nu till information om kärndatavolymen och den genomsnittliga radstorleken.<p>Mer information finns i [Hantera anslutningar](/help/connections/manage-connections.md#usage).</p> | | 4 september 2025 |
| **Förbättringar när projekt och komponenter migreras till Customer Journey Analytics** | Följande förbättringar är nu tillgängliga när du migrerar projekt och komponenter från Adobe Analytics till Customer Journey Analytics:<ul><li>Migrera flera projekt samtidigt.<br/>Du kan migrera upp till 20 projekt samtidigt.<br/>Tidigare kunde du bara migrera ett projekt åt gången.</li><li>Uppdatera mappningar för dimensioner och mätvärden som redan har mappats med en tidigare projektmigrering.<br/>Du kan nu uppdatera de här mappningarna varje gång du migrerar ett projekt, även om samma mått och mått tidigare har mappats med en tidigare migrering.<br/>Tidigare var alla mappningar du valde permanenta för alla framtida projektmigreringar.</li><li>Förbättrade prestanda för organisationer med många projekt.</li></ul><p>Den här funktionen finns i Adobe Analytics gränssnitt. Mer information finns i [Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/analytics/admin/admin-tools/component-migration/component-migration).</p> | 15 september 2025 | 18 september 2025 |
| **Antalet söknycklar har ökat till upp till 1 miljard** | Det maximala antalet unika nycklar för en uppslagsdatauppsättning är nu upp till 1 miljard, beroende på ditt Customer Journey Analytics-berättigande. <p>Tidigare var det högsta antalet 10 miljoner för alla berättiganden.<p>Mer information finns i [Guardrails](/help/technotes/guardrails.md).</p> | | 18 september 2025 |
| **Stöd för ad hoc-scheman** | [Ad hoc-scheman](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/tutorials/ad-hoc) används i olika arbetsflöden för datainmatning för Experience Platform, inklusive inmatning av CSV-filer och skapande av vissa typer av källanslutningar. <p>Med den här funktionen kan du använda ad hoc-scheman i Customer Journey Analytics. Som en del av definitionen av en anslutning kan du nu välja en datauppsättning baserat på ett ad hoc-schema och använda data i dina datavyer och arbetsyteprojekt.</p> <p>(Dokumentationslänk som ska följas.)</p> |  | 18 september 2025 (ursprungligen planerat att släppas den 28 augusti 2025) |
| **Realtidsrapportering** | Realtidsrapportering i Customer Journey Analytics visar och uppdaterar data och visualiseringar inom en eller flera paneler i Analysis Workspace i realtid.<br/><br/>(Dokumentationslänk att följa.) | | 18 september 2025 (ursprungligen planerat att släppas den 15 augusti 2025) |
| **Stöd för dataspegling** | Med stöd för modellbaserade scheman och funktioner för datainhämtning (CDC) för specifika källanslutningar i Experience Platform, kommer Customer Journey Analytics att ha stöd för datautspeglingsfunktioner för datalagerlösningar för Snowflake, Databricks och Google BigQuery. <p>Kontakta ditt Adobe-kontoteam för att få tillgång till betaversionen.</p><p>(Dokumentationslänk som ska följas.)</p> | Beta från 24 september | TBD |
| **Direktuppspelningsmedia: Uppdaterade XDM-fält för insamling av direktuppspelningsmediedata i Adobe Experience Platform** | När Streaming Media-data samlas in i Adobe Experience Platform bör de XDM-fältsökvägar som visas under rubriken &quot;XDM Field Path&quot; i dokumentationen för Streaming Media-parametrar inte längre användas. I stället måste kunder som implementerat Analytics-källkopplingen för att samla in Streaming Media-data till Platform före 9 maj 2025 migrera sina befintliga konfigurationer till MediaReporting-fältsökvägarna, vilket visas under rubriken&quot;Reporting XDM Field Path&quot; i dokumentationen för Streaming Media-parametrar.<p> De här fältsökvägarna finns på följande sidor och markeras som &quot;Undertryckta&quot;: [Parametrar för ljud- och videoinnehåll](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Lägg till parametrar](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparametrar](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametrar för spelartillstånd](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/player-state-parameters) och [Kvalitetsparametrar](https://experienceleague.adobe.com/sv/docs/media-analytics/using/implementation/variables/quality-parameters). (Ingen åtgärd krävs för kunder som implementerar källkopplingen för Analytics efter 9 maj 2025 och som redan använder enbart XDM-sökvägar för mediaReporting.)</p><p>Inmatningen av data i de borttagna XDM-fältsökvägarna fortsätter till slutet av oktober 2025. Efter det kommer inaktuella fältsökvägar att tas bort helt och inte längre visas i användargränssnittet för Adobe Experience Platform Schema, och data skickas endast med fältsökvägarna för mediaReporting.</p><p>Mer information finns i [Migrera en Analytics Source Connector-implementering till uppdaterade XDM Streaming Media-fält](https://experienceleague.adobe.com/sv/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Kontakta Adobe Consulting-tjänsterna eller kontoteamet för att få migreringssupport. </p> |  | Oktober 2025 |
| **Strömning i anslutningar** | Förenklar sammanfogning av Customer Journey Analytics. Istället för att duplicera en datauppsättning och använda sammanfogning på den duplicerade datauppsättningen görs nu sammanfogning av data till Customer Journey Analytics, vilket eliminerar behovet av duplicerade datauppsättningar och scheman. <p>I stället för att behöva beställa sydda via kundsupport kan du nu börja sy ihop dig själv från ett uppdaterat gränssnitt för anslutningar.</p><p> *Tidigare meddelade releasedatum har flyttats på grund av ytterligare åtgärder som krävs. De nya releasedatumen överlappar julsäsongen, vilket medför ytterligare releasebegränsningar. En fasad utrullning planeras nu för att garantera stabilitet och minimera störningar under semesterperioden.*</p> <p>(Dokumentationslänk som ska följas.)</p> | I slutet av oktober 2025 | I slutet av januari 2026 |

## Korrigeringar i Customer Journey Analytics

**Analysis Workspace**: AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391 404, AN-393064, AN-379337
**Komponenter**: AN-393810
**Content Analytics**:
**Guidad analys**:
**Plattform**:
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Rapportering**: AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-39304
**Segmentering**:
**Schemalagda rapporter**: AN-391150, AN-390474
**Delade mått och mått**:
**Annan**: AN-387858


## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

## Relaterade resurser

* [Tidigare versionsinformation för Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=sv-SE)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=sv-SE)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv-SE)
* [Customer Journey Analytics dokumentationsuppdateringar](/help/release-notes/doc-changes.md)
