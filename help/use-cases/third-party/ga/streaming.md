---
title: Konfigurera strömmande Google Analytics-data
description: Lär dig hur du konfigurerar implementeringen för att skicka ett Google-datalager till Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
source-git-commit: 8262539078c57e32bc3195ef669325fa4889bea0
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Konfigurera strömmande Google Analytics-data

På den här sidan fokuseras på hur du importerar dina Google Analytics-data till Adobe Experience Platform så att du kan referera till den datauppsättningen i en datavy inom Customer Journey Analytics. Du kan kombinera stegen på den här sidan med [Importera historiska data från Google Analytics till Adobe Experience Platform](backfill.md), som genererar en datauppsättning som innehåller historiska data. Kombinera en strömmande datauppsättning med en datauppsättning med bakgrundsfyllning för att få en sömlös vy över tidigare och aktuella data i Customer Journey Analytics.

När du konfigurerar datainsamling utför du följande steg:

1. Implementera [taggar för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html). Se [snabbstartsguiden](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) för att få en grundläggande implementering att fungera.
1. Installera [Google-datalagertillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Det här tillägget fungerar som ett alternativ till att installera Web SDK-tillägget, särskilt anpassat till ett Google-datalager.
1. [Skapa en datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) i Adobe Experience Platform Data Collection. Konfigurera dataströmmen för att skicka data till Adobe Experience Platform. Du måste mappa varje datalager-objekt från Google till ett tillämpligt XDM-fält här. Adobe planerar att förenkla det här arbetsflödet i framtiden.

När du har implementerat och publicerat de önskade taggarna på webbplatsen kan du sedan fortsätta med att [skapa en anslutning](/help/connections/create-connection.md) och sedan [skapa en datavy](/help/data-views/create-dataview.md).
