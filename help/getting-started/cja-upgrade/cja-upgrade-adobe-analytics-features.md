---
title: Förstå Adobe Analytics funktionssupport vid uppgradering till Customer Journey Analytics
description: Läs om Adobe Analytics funktionssupport när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 1%

---

# Förstå Adobe Analytics funktionssupport vid uppgradering till Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Komponenter och projekt"
>abstract="Komponenter från Adobe Analytics: Projekt (med tillhörande frihandstabeller och visualiseringar), segment och beräknade värden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Övertäckning för aktivitetskarta och länkspårning"
>abstract="Ett webbläsartillägg som gör att du kan visa länkspårningsdata som en övertäckning på webbplatsen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="Det finns ännu inget stöd för övertäckning av aktivitetskarta"
>abstract="Activity Map övertäckningsstöd finns ännu inte i Customer Journey Analytics. Den planeras bli tillgänglig i framtiden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="Klassificeringsdata"
>abstract="Gruppera eller kategorisera data som separata dimensioner."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="Marknadsföringskanaler"
>abstract="Skapa regler som kategoriserar hur kunderna kommer till er webbplats."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="Dataflöden"
>abstract="Exportera rådata från Adobe Analytics för användning i externa verktyg och processer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Exportera bearbetade data från Adobe Analytics i kalkylbladsformat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="Direktuppspelande mediedata"
>abstract="Ett tillägg till Adobe Analytics och Customer Journey Analytics som specialiserar sig på datainsamling av media, som ljud, video eller direktuppspelat innehåll."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="Migrera projekt och komponenter"
>abstract="Använd Adobe Analytics-projekt och tillhörande komponenter i Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

I följande lista visas endast de Adobe Analytics-funktioner som behöver övervägas under uppgraderingen till Customer Journey Analytics. En omfattande lista som visar vilka Adobe Analytics-funktioner som stöds, stöds delvis eller inte stöds i Customer Journey Analytics finns i [Stöd för Customer Journey Analytics-funktioner](/help/getting-started/aa-vs-cja/cja-aa.md).

Ta en titt på vilka av följande Adobe Analytics-funktioner du vill fortsätta använda när du uppgraderar till Customer Journey Analytics:

| Funktionen Adobe Analytics | Motsvarande funktion i Customer Journey Analytics |
|---------|----------|
| [Komponenter och projekt från Adobe Analytics](https://experienceleague.adobe.com/sv/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrera projekt och tillhörande komponenter till Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Övertäckning för aktivitetskarta och länkspårning](https://experienceleague.adobe.com/sv/docs/analytics/analyze/activity-map/overview) | Inte tillgängligt ännu |
| [Klassificeringsdata](https://experienceleague.adobe.com/sv/docs/analytics/components/classifications/c-classifications) | Uppslagsdatauppsättningar är en metod för att klassificera data i Customer Journey Analytics.<p>[Skapa en uppslagsdatauppsättning för varje dimension som innehåller klassificeringsdata.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Marknadskanaler](https://experienceleague.adobe.com/sv/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Härledda fält skapas i en datavy. <p>[Skapa ett härlett fält för marknadsföringskanal.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Datafeeds](https://experienceleague.adobe.com/sv/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform och Customer Journey Analytics har ett antal funktioner som, antingen separat eller tillsammans, kan lösa de olika exportkraven. Dessa funktioner omfattar [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=sv-SE), [Experience Platform Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=sv-SE), [Customer Journey Analytics Full Table Export](/help/analysis-workspace/export/export-cloud.md) och [BI Tool Integration](/help/data-views/bi-extension.md).<p>Mer information om exportalternativ finns i [Användningsexempel för dataexport](/help/use-cases/data-export/overview.md).</p> |
| [Data Warehouse](https://experienceleague.adobe.com/sv/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics Fullständig tabellexport](/help/analysis-workspace/export/export-cloud.md) är utvecklingen av Data Warehouse-rapporter i Adobe Analytics, med många nya, ofta efterfrågade funktioner som inte är tillgängliga i Data Warehouse idag. |
| [Direktuppspelande mediedata](https://experienceleague.adobe.com/sv/docs/media-analytics/using/media-overview) | Direktuppspelande mediedata är tillgängliga med Analytics-källkopplingen som en del av panelen Media Concurrent Viewer och panelen Media Playback Time Spent (Tid för uppspelning i Workspace). |
