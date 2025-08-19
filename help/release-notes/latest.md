---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2929a8034fe7ef1602a2a04eb76dbb9e7c4a9b81
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (augusti 2025)

**Senast uppdaterad**: 14 augusti 2025


Versionsanteckningarna gäller från den 13 augusti till den 16 september 2025. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mappningsvisualisering** | Kartvisualiseringen är en visualisering i Analysis Workspace som gör att du kan skapa en visuell karta över alla mätvärden (inklusive beräknade värden). Det är användbart när du vill identifiera och jämföra mätdata för olika geografiska regioner.<p>Tidigare var kartvisualiseringen bara tillgänglig i Adobe Analytics.</p><p>Kartvisualiseringen i Customer Journey Analytics innehåller följande förbättringar från kartvisualiseringen i Adobe Analytics:</p><ul><li>Använd valfritt segment från datavyn som datakälla.</li><li>Noggrannhet upp till en enda meter genom att konfigurera dimensionen i datavyn.</li><li>Med ett nytt markeringsverktyg kan du skapa ett segment, en målgrupp, en trend eller en nedbrytning från vilket område som helst som du markerar i visualiseringen.</li></ul><p>Mer information finns i [Karta](/help/analysis-workspace/visualizations/map.md).</p> | 13 augusti 2025 | 25 augusti 2025 |
| **Realtidsrapportering** | Realtidsrapportering i Customer Journey Analytics visar och uppdaterar data och visualiseringar inom en eller flera paneler i Analysis Workspace i realtid. | | 17 september 2025 (ursprungligen planerat att släppas den 15 augusti 2025) |
| **B2B-mallar** | Om du har licens för Customer Journey Analytics B2B edition finns följande ytterligare B2B-mallar nu i Adobe-mallens användargränssnitt: <ul><li>Översikt över B2B-kontoengagemang</li><li>Översikt över B2B-säljprojektsengagemang</li><li>B2B Buying Group Activity</li></ul><p>(Dokumentationslänk som ska följas.)</p> |  | 15 augusti 2025 |
| **Projekt som hämtas som PDF-filer hämtas till din arbetsstation** | När du laddar ned ett projekt som PDF laddas PDF ned till nedladdningsmappen på din arbetsstation. <p>Tidigare startades PDF på en ny webbläsarflik med en unik URL när du laddade ned ett projekt som PDF.</p><p>Mer information finns i [Hämta projekt och data](/help/analysis-workspace/export/download-send.md).</p> |  | 25 augusti 2025 |
| **Stöd för ad hoc-scheman** | [Ad-hoc-scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/ad-hoc) används i olika arbetsflöden för datainmatning för Experience Platform, inklusive inmatning av CSV-filer och skapande av vissa typer av källanslutningar. <p>Med den här funktionen kan du använda ad hoc-scheman i Customer Journey Analytics. Som en del av definitionen av en anslutning kan du nu välja en datauppsättning baserat på ett ad hoc-schema och använda data i dina datavyer och arbetsyteprojekt.</p> <p>(Dokumentationslänk som ska följas.)</p> |  | 28 augusti 2025 |
| **Strömning i anslutningar** | Förenklar sammanfogning av Customer Journey Analytics. Istället för att duplicera en datauppsättning och använda sammanfogning på den duplicerade datauppsättningen görs nu sammanfogning av data till Customer Journey Analytics, vilket eliminerar behovet av duplicerade datauppsättningar och scheman. <p>I stället för att behöva beställa sydda via kundsupport kan du nu börja sy ihop dig själv från ett uppdaterat gränssnitt för anslutningar.</p><p> *Tidigare meddelade releasedatum har flyttats på grund av ytterligare åtgärder som krävs. De nya releasedatumen överlappar julsäsongen, vilket medför ytterligare releasebegränsningar. En fasad utrullning planeras nu för att garantera stabilitet och minimera störningar under semesterperioden.*</p> | I slutet av oktober 2025 | I slutet av januari 2026 |
| **Gräns för utökade söknycklar** | Beroende på ditt Customer Journey Analytics-paket kan du nu ha upp till en miljard unika nycklar i en uppslagsdatauppsättning. <p>Mer information finns i [Gränser för dataöverföring](/help/technotes/guardrails.md#data-transfer-limits) i dokumentationen för Customer Journey Analytics [GuarDRAils](/help/technotes/guardrails.md).</p> |  | 29 augusti 2025 |
| **Skapa mått och mått baserat på användardefinierade kartfält från plattformsschemat** | Användardefinierade kartfält som du definierar i ditt Experience Platform-schema kan nu användas i Customer Journey Analytics.<p>Du kan använda följande kartfält när du skapar mått i Customer Journey Analytics:</p><ul><li>Sträng till sträng</li><li>Sträng till heltal</li></ul><p>(Dokumentationslänk som ska följas.)</p><p>Mer information om kartfält i Experience Platform finns i [Definiera kartfält i användargränssnittet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/map).</p> |  | Slutet av augusti 2025 |
| **Borttagna projekt är omedelbart inte tillgängliga av URL och tas bort från schemalagda leveranser** | Projekt som tas bort raderas omedelbart från schemalagda leveranser och är inte längre tillgängliga via sin URL.<p>Tidigare ingick projekt i schemalagda leveranser och de kunde nås med sin URL i 60 dagar efter att de tagits bort.</p><p>Mer information om hur du tar bort projekt finns i [Projektöversikt](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Slutet av augusti 2025 |
| **Direktuppspelningsmedia: Uppdaterade XDM-fält för insamling av direktuppspelningsmediedata i Adobe Experience Platform** | När Streaming Media-data samlas in i Adobe Experience Platform bör de XDM-fältsökvägar som visas under rubriken &quot;XDM Field Path&quot; i dokumentationen för Streaming Media-parametrar inte längre användas. I stället måste kunder som implementerat Analytics-källkopplingen för att samla in Streaming Media-data till Platform före 9 maj 2025 migrera sina befintliga konfigurationer till MediaReporting-fältsökvägarna, vilket visas under rubriken&quot;Reporting XDM Field Path&quot; i dokumentationen för Streaming Media-parametrar.<p> De här fältsökvägarna finns på följande sidor och markeras som &quot;Undertryckta&quot;: [Parametrar för ljud- och videoinnehåll](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Lägg till parametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametrar för spelartillstånd](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) och [Kvalitetsparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). (Ingen åtgärd krävs för kunder som implementerar källkopplingen för Analytics efter 9 maj 2025 och som redan använder enbart XDM-sökvägar för mediaReporting.)</p><p>Inmatningen av data i de borttagna XDM-fältsökvägarna fortsätter till slutet av oktober 2025. Efter det kommer inaktuella fältsökvägar att tas bort helt och inte längre visas i användargränssnittet för Adobe Experience Platform Schema, och data skickas endast med fältsökvägarna för mediaReporting.</p><p>Mer information finns i [Migrera en Analytics Source Connector-implementering till uppdaterade XDM Streaming Media-fält](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Kontakta Adobe Consulting-tjänsterna eller kontoteamet för att få migreringssupport. </p> |  | Oktober 2025 |

## Korrigeringar i Customer Journey Analytics

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387 089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**Komponenter**:
**Content Analytics**:
**Guidad analys**: AN-384426
**Plattform**: AN-384410
**Report Builder**: AN-389336; AN-382775
**Rapportering**:
**Segmentering**:
**Delade mått och mått**:
**Annan**: AN-388222; AN-384898; AN-387169


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
