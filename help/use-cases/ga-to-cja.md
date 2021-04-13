---
title: Hämta Google Analytics data till Adobe Experience Platform för analys i Customer Journey Analytics (CJA)
description: 'Beskriver hur du kan använda Customer Journey Analytics (CJA) för att importera Google Analytics- och Firebase-data till Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---


# Importera data från Google Analytics till Adobe Experience Platform

I det här användningsexemplet fokuseras på hur du importerar data från Google Analytics som en datauppsättning till Adobe Experience Platform. (Detta gäller både historiska data och livedata.) När du är klar kan du kombinera båda datauppsättningarna för att få en överblick över användarens resa på olika enheter.

Datauppsättningarna i Experience Platform består av två saker: ett schema och de faktiska posterna i datauppsättningen. Schemat (vi kallar Experience Data Model eller XDM för kort) är som kolumnerna i datauppsättningen och liknar planen eller reglerna som beskriver själva data. Inom plattformen tillhandahåller Adobe två typer av scheman:

* Körklara scheman som du kan mappa Google Analytics-data till automatiskt (kallas Experience Event-schema)
* Anpassade scheman som du kan skapa och enkelt mappa Google Analytics data till

En av de mest kraftfulla aspekterna i Adobe datamodell är att den gör det möjligt att standardisera alla era kundinteraktionsdata i ett gemensamt schema, vilket gör det mycket enklare att sammanfoga data i CJA.

## Förutsättningar

För att kunna utföra dessa uppgifter behöver du följande åtkomst och behörigheter:

* Tillgång till Adobe Experience Platform
* Tillgång till Universal Google Analytics (Google Analytics 360-versionen) eller Google Analytics 4 (kostnadsfri version eller Google Analytics 360-versionen)
* Åtkomst till Customer Journey Analytics och dess [administratörsbehörigheter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#admin-access-permissions).

Hur du överför Google Analytics data till Adobe Experience Platform beror på vilken version av Google Analytics du använder:

| Om du använder ... | Du behöver också den här licensen.. | Och gör det här.. |
| --- | --- | --- |
| **Universal Google Analytics** | Google Analytics 360 | Utför steg 1-5 i instruktionerna nedan |
| **Google Analytics 4** | Kostnadsfri GA-version eller Google Analytics 360 | Utför steg 1 och 3-5 i instruktionerna nedan. Inget behov av steg 2. |

## 1. Koppla Google Analytics-data till BigQuery

Observera att följande instruktioner är baserade på Universal Google Analytics.

Mer information finns i [dessa instruktioner](https://support.google.com/analytics/answer/3416092?hl=en).

## 2. Omvandla sessioner med Google Analytics till händelser i BigQuery

>[!IMPORTANT]
>
>Detta steg gäller endast kunder som har Universal Analytics

GA-data lagrar varje post i sina data som en användarsession i stället för som enskilda händelser. När data omvandlas blir de kompatibla med Adobe Experience Platform.

Mer information finns i [dessa instruktioner](https://support.google.com/analytics/answer/3437618?hl=en).

Du måste skapa en SQL-fråga för att omvandla data från den universella analysen till ett Experience-Platform-kompatibelt format. I den här videon finns instruktioner:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3. Exportera Google Analytics-händelser i JSON-format till Google Cloud-lagring och spara dem i en hink

Mer information finns i [dessa instruktioner](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

## 4. Hämta data från Google Cloud-lagring till Experience Platform

I den här videon finns instruktioner:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. Importera GCS-händelser till Adobe Experience Platform och mappa till XDM-schema

Export av BigQuery-schema (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
