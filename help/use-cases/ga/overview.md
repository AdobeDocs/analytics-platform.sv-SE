---
title: Migrera data från Google Analytics till Customer Journey Analytics
description: Lär dig det övergripande arbetsflödet om hur du flyttar data från Google Analytics till Adobe Experience Platform och visar rapporter i Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# Migrera data från Google Analytics till Customer Journey Analytics

Om du inte är i Customer Journey Analytics tidigare är det möjligt att din organisation har befintliga data på en annan analysplattform, som Google Analytics. Du kan följa de här övergripande stegen för att flytta data till Adobe Experience Platform så att du kan visa rapporter i Customer Journey Analytics.

Arbetsflöden tillhandahålls för både historiska data och aktuell datainsamling. Du kan följa ett eller båda av dessa arbetsflöden, beroende på organisationens databehov.

## Hämta historiska data från Google Analytics till Adobe Experience Platform

Inmatning av historiska data (bakåtfyllnad) innebär att data exporteras från Google och importeras till Adobe Experience Platform. Se [Ingest Google Analytics data in Adobe Experience Platform](backfill.md).

När du väl har samlat in historiska data i Platform kan du antingen [Konfigurera strömmande aktuella data](streaming.md)eller omedelbart börja rapportera data i Customer Journey Analytics med [Skapa en anslutning](/help/connections/create-connection.md).

## Konfigurera en befintlig Google Analytics-implementering för Adobe Experience Platform {#configure}

Inmatning av aktuella (strömmande) data innebär att data skickas till Adobe Experience Edge, som sedan vidarebefordrar dessa data till Adobe Experience Platform. Se [Ställ in data för direktuppspelad Google Analytics i Adobe Experience Platform](streaming.md).

## Konfigurera en anslutning och datavy i Customer Journey Analytics

När du har importerat historiska data och/eller konfigurerat datainsamling till Adobe Experience Platform kan du [Skapa en anslutning](/help/connections/create-connection.md) så att Customer Journey Analytics kan referera till dessa data.

Använd anslutningen för att skapa en eller flera [Datavyer](/help/data-views/create-dataview.md) för användning i Analysis Workspace.

## Skapa rapporter

När du har konfigurerat mått och mätvärden i en datavy kan du börja använda Analysis Workspace för att generera de önskade rapporterna. Se [Rapport om Google Analytics data i Customer Journey Analytics](report.md).
