---
title: Förstå Adobe Analytics funktionssupport när du uppgraderar till Customer Journey Analytics
description: Läs om Adobe Analytics funktionssupport när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8d14bb23283107402332106df36e8f7898ea5d30
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 1%

---

# Förstå Adobe Analytics funktionssupport när du uppgraderar till Customer Journey Analytics {#feature-support-upgrade}

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
>abstract="Ett tillägg till Adobe Analytics som specialiserar sig på datainsamling av media, som ljud, video eller direktuppspelat innehåll."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i checklistan för uppgradering av [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

I följande lista visas endast de Adobe Analytics-funktioner som behöver övervägas under uppgraderingsprocessen för Customer Journey Analytics. En omfattande lista som visar vilka Adobe Analytics-funktioner som stöds, stöds delvis eller inte alls i Customer Journey Analytics finns i [Funktionsstöd för Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Ta en titt på vilka av följande Adobe Analytics-funktioner du vill fortsätta använda när du uppgraderar till Customer Journey Analytics:

| Funktionen Adobe Analytics | Motsvarande funktion i Customer Journey Analytics |
|---------|----------|
| [Komponenter och projekt från Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrera projekt och tillhörande komponenter till Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Övertäckning för aktivitetskarta och länkspårning](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | Inte tillgängligt ännu |
| [Klassificeringsdata](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | Uppslagsdatauppsättningar är en metod för att klassificera data i Customer Journey Analytics.<p>[Skapa en uppslagsdatauppsättning för varje dimension som innehåller klassificeringsdata.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Marknadskanaler](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Härledda fält skapas i en datavy. <p>[Skapa ett härlett fält för marknadsföringskanal.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Datafeeds](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | Första generationens dataexport av datauppsättningar är tillgänglig via [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html) och via [Experience Platform Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html). Dessa alternativ ger händelse-/radnivåexport av alla data som samlats in eller importerats till Experience Platform Data Lake. Postprocessdatakolumner är inte tillgängliga eftersom postkolumner beräknas vid frågetiden. Det går att exportera postkolumner genom rapportering. |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [Fullständig tabellexport i Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) är utvecklingen av Data Warehouse i Adobe Analytics, med många nya, ofta efterfrågade funktioner som inte är tillgängliga i Datan Warehouse idag. |
| [Direktuppspelande mediedata](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-overview) | Direktuppspelande mediedata är tillgängliga med Analytics-källkopplingen som en del av panelen Media Concurrent Viewer och panelen Media Playback Time Spent (Tid för uppspelning i Workspace). |

