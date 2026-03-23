---
description: Lär dig hur du använder dataflöden för att få ut rådata från Customer Journey Analytics. Ta reda på vad som krävs för att använda dataflöden.
keywords: klickström;datafeed;datafeed;datafeed
title: Översikt över Analytics-dataflöden
feature: Components
hide: true
hidefromtoc: true
source-git-commit: b0b86424399ea79deca8f1d522d52354dfaaa8c7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---

# Översikt över dataflöden

Dataflöden är ett kraftfullt sätt att få ut rådata från Customer Journey Analytics. Dessa rådata kan användas på andra plattformar utanför Adobe efter eget gottfinnande. Data levereras i timbatchar vid varje timmes slut, eller i dagliga satser vid varje dags slut.

## Förutsättningar

Kontrollera att du uppfyller alla följande krav innan du använder dataflöden.

* En fungerande implementering med data som importeras till Adobe Customer Journey Analytics. <!-- For more information, see Data ingestion overview - add link -->
* Ditt konto är en produktadministratör för Analytics, eller så tillhör ditt konto en produktprofil med tillgång till dataflöden. <!--???-->
* En bucket konfigurerad på Amazon S3, Google Cloud Platform, Azure RBAC eller Azure SAS.<!--Which cloud providers do we support??-->
* (Äldre: Krävs endast för äldre måltyper för FTP och SFTP) Har en FTP-plats och autentiseringsuppgifter tillgängliga (FTP-autentiseringsuppgifter tillhandahålls av din organisation.)<!--Delete???-->

## Jämför dataflöden i Customer Journey Analytics och Adobe Analytics

Datafeedfunktionaliteten i Customer Journey Analytics skiljer sig från Adobe Analytics. Mer information finns i [Jämför dataflöden i Customer Journey Analytics och Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).


## Nästa steg

Följande resurser hjälper dig att förstå det grundläggande arbetsflödet för att hämta dataflöden. När du har förstått det grundläggande arbetsflödet kan du arbeta med team inom organisationen för att lagra eller importera rådata till en databas.

* Bästa praxis för dataflöden<!--add link-->: Bästa tillvägagångssätt för att skapa och hantera dataflöden.
* Skapa en datafeed<!--add link-->: Teknisk information för att skapa en datafeed, som förklarar enskilda fält mer i detalj
* Hantera datafeeds<!--add link-->: Läs mer om hur du navigerar i gränssnittet för datafeeds
* Innehåll i datafeed <!--add link-->: Förstå vad som finns i den komprimerade filen <!-- Is this still the output users can download from the destination? I aske Jun. -->
* Datakolumndefinitioner <!--add link-->: En omfattande lista över alla tillgängliga kolumner.

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navigera i dataflödesgränssnittet](https://video.tv.adobe.com/v/3428568?captions=swe&quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Hitta ditt datafeed-id](https://video.tv.adobe.com/v/3480886?captions=swe&quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]
