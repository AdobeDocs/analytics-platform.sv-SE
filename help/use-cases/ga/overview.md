---
title: Migrera data från Google Analytics till Customer Journey Analytics
description: Lär dig det övergripande arbetsflödet om hur du flyttar data från Google Analytics till Adobe Experience Platform och hur du visar rapporter i Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Migrera data från Google Analytics till Customer Journey Analytics

Om du inte är i Customer Journey Analytics tidigare är det möjligt att din organisation har befintliga data på en annan Analytics-plattform, till exempel Google Analytics. Du kan följa de här övergripande stegen för att flytta data till Adobe Experience Platform så att du kan visa rapporter i Customer Journey Analytics.

Arbetsflöden tillhandahålls för både historiska data och aktuell datainsamling. Du kan följa ett eller båda av dessa arbetsflöden, beroende på organisationens databehov.

## Hämta historiska data från Google Analytics till Adobe Experience Platform

Inmatning av historiska data (bakåtfyllnad) innebär att data exporteras från Google och importeras till Adobe Experience Platform. Se [Importera Google Analytics-data i Adobe Experience Platform](backfill.md).

När du har överfört historiska data till plattformen kan du antingen [konfigurera strömmande aktuella data](streaming.md) eller omedelbart börja rapportera om data som har fyllts i i Customer Journey Analytics genom att [skapa en anslutning](/help/connections/create-connection.md).

## Konfigurera en befintlig Google Analytics-implementering för Adobe Experience Platform {#configure}

Inmatning av aktuella (strömmande) data innebär att data skickas till Adobe Experience Platform Edge Network, som sedan vidarebefordrar dessa data till Adobe Experience Platform. Se [Konfigurera Google Analytics-data för direktuppspelning i Adobe Experience Platform](streaming.md).

## Konfigurera en anslutning och datavy i Customer Journey Analytics

När du har importerat historiska data och/eller konfigurerat datainsamling till Adobe Experience Platform kan du [skapa en anslutning](/help/connections/create-connection.md) så att Customer Journey Analytics kan referera till dessa data.

Använd anslutningen för att skapa en eller flera [datavyer](/help/data-views/create-dataview.md) som kan användas i Analysis Workspace.

## Skapa rapporter

När du har konfigurerat mått och mätvärden i en datavy kan du börja använda Analysis Workspace för att generera de önskade rapporterna. Se [Rapport om Google Analytics-data i Customer Journey Analytics](report.md).
