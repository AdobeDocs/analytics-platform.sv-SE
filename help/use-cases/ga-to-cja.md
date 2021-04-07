---
title: Ställ in Google Analytics-rapportering i Customer Journey Analytics
description: null
translation-type: tm+mt
source-git-commit: 9bbc625aca9e0b8384b3e95d79fd695fda863f0b
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Ställ in Google Analytics-rapportering i Customer Journey Analytics

konfigurera Google Cloud Storage Connector,

konfigurera Google Tag Manager

Export av BigQuery-schema (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. Konvertera GA-sessioner till händelser i Big Query
1. Exportera Google Analytics-händelser till Google Cloud-lagring
1. Importera GCS-händelser till Adobe Experience Platform och mappa till XDM-schema

## Förutsättningar

* Tillgång till Adobe Experience Platform
* Tillgång till Universal Google Analytics (Google Analytics 360-versionen) eller Google Analytics 4 (kostnadsfri version eller Google Analytics 360-versionen)
* Åtkomst till Customer Journey Analytics

## Koppla Google Analytics-data till Adobe Experience Platform

Hur du överför Google Analytics data till Adobe Experience Platform beror på vilken version av Google Analytics du använder:

| Om du använder ... | Du behöver också den här licensen.. | Och gör det här.. |
| --- | --- | --- |
| **Universal Google Analytics** | Google Analytics 360 | Utför steg 1 - x av instruktionerna nedan |
| **Google Analytics 4** | Kostnadsfri GA-version eller Google Analytics 360 | Inget behov av steg x i instruktionerna nedan. |

Följande instruktioner bygger på Universal Google Analytics.

1. Koppla Google Analytics-data till BigQuery och
Mer information finns i [dessa instruktioner](https://support.google.com/analytics/answer/3416092?hl=en).
1. (Endast kunder med Universal Analytics) Omvandla sessioner med Google Analytics till händelser i BigQuery.
Mer information finns i [dessa instruktioner](https://support.google.com/analytics/answer/3437618?hl=en).
1. Exportera Google Analytics-händelser till Google Cloud-lagring.
Mer information finns i [dessa instruktioner](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).
