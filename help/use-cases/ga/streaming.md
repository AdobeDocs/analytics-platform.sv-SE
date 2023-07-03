---
title: Konfigurera strömmande Google Analytics-data i Adobe Experience Platform
description: Lär dig hur du konfigurerar implementeringen för att skicka ett Google-datalager till Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Konfigurera strömmande Google Analytics-data i Adobe Experience Platform

På den här sidan fokuseras på hur du importerar data i Google Analytics live till Adobe Experience Platform, så att du kan referera till den datauppsättningen i en datavy i Customer Journey Analytics. Du kan kombinera stegen på den här sidan med [Ingest Google Analytics history data into Adobe Experience Platform](backfill.md), som genererar en datauppsättning som innehåller historiska data. Kombinera en strömmande datauppsättning med en datauppsättning för bakgrundsfyllning för att få en sömlös vy över tidigare och nuvarande data i Customer Journey Analytics.

När du konfigurerar datainsamling utför du följande steg:

1. Implementera [Taggar för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html). Se [Snabbstartguide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) för att komma igång med en grundläggande implementering.
1. Installera [Google Data Layer-tillägg](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Det här tillägget fungerar som ett alternativ till att installera Web SDK-tillägget, som är specifikt anpassat till ett Google-datalager.
1. [Skapa ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) i Adobe Experience Platform Data Collection. Konfigurera dataströmmen för att skicka data till Adobe Experience Platform. Du måste mappa varje datalager-objekt från Google till ett tillämpligt XDM-fält här. Adobe planerar att förenkla detta arbetsflöde för kartläggning i framtiden.

När du har implementerat och publicerat de önskade taggarna på webbplatsen kan du fortsätta med [Skapa en anslutning](/help/connections/create-connection.md)sedan [Skapa en datavy](/help/data-views/create-dataview.md).
