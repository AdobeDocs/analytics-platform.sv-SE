---
title: Importera data från Google Analytics till Adobe Experience Platform
description: 'Beskriver hur du kan använda Customer Journey Analytics (CJA) för att importera Google Analytics-data till Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 0%

---


# Importera data från Google Analytics till Adobe Experience Platform

I det här användningsexemplet fokuseras på hur du importerar data från Google Analytics som en datauppsättning till Adobe Experience Platform. Vi förklarar hur man importerar både historiska och livedata. När du är klar kan du kombinera båda datauppsättningarna i Customer Journey Analytics för att få en översikt över användarens resa på olika enheter.

Datauppsättningarna i Experience Platform består av två saker: ett schema och de faktiska posterna i datauppsättningen. Schemat (vi kallar Experience Data Model eller XDM för kort) är som kolumnerna i datauppsättningen och liknar planen eller reglerna som beskriver själva data. Inom plattformen tillhandahåller Adobe två typer av scheman:

* Körklara scheman som du kan mappa Google Analytics-data till automatiskt (kallas Experience Event-schema)
* Anpassade scheman som du kan skapa och enkelt mappa Google Analytics data till

En av de mest kraftfulla aspekterna i Adobe datamodell är att den gör det möjligt att standardisera alla era kundinteraktionsdata i ett gemensamt schema, vilket gör det mycket enklare att sammanfoga data i CJA.

## Förutsättningar

För att kunna utföra dessa uppgifter behöver du följande åtkomst och behörigheter:

* Tillgång till Adobe Experience Platform
* Tillgång till Universal Google Analytics (Google Analytics 360-versionen) eller Google Analytics 4 (kostnadsfri version eller Google Analytics 360-versionen)
* Tillgång till Customer Journey Analytics och dess [Administratörsbehörigheter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html#admin-access-permissions).

Hur du överför Google Analytics data till Adobe Experience Platform beror på vilken version av Google Analytics du använder:

| Om du använder ... | Du behöver också den här licensen.. | Och gör det här.. |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | Utför steg 1-3 i instruktionerna nedan |
| **Google Analytics 4** | Kostnadsfri GA-version eller Google Analytics 360 | Utför steg 1 och 3 i instruktionerna nedan. Inget behov av steg 2. |

## Ingest history (backfill) data

### 1. Koppla Google Analytics-data till BigQuery

Mer information finns i [dessa instruktioner](https://support.google.com/analytics/answer/3416092?hl=en). Observera att dessa instruktioner bygger på Universal Google Analytics.

### 2. Omvandla sessioner med Google Analytics till händelser i BigQuery och exportera till Google Cloud-lagring

>[!IMPORTANT]
>
>Detta steg gäller endast kunder som har Universal Analytics

GA-data lagrar varje post i sina data som en användarsession i stället för som enskilda händelser. Du måste skapa en SQL-fråga för att omvandla data från den universella analysen till ett Experience-Platform-kompatibelt format. Du använder funktionen &quot;unest&quot; för fältet &quot;hits&quot; i GA-schemat. Här är SQL-exemplet som du kan använda:

```
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )
```

När frågan är klar sparar du de fullständiga resultaten i en BigQuery-tabell.

Se [dessa instruktioner](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql), som innehåller instruktioner för SQL-frågan.

I följande video förklaras också nästa steg, som är att exportera Google Analytics-händelserna till Google Cloud-lagring i JSON-format. Klicka bara **Exportera > Exportera till GCS**. När informationen finns tillgänglig kan den hämtas till Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Importera data från Google Cloud Storage till Experience Platform och mappa till XDM-schema

I Experience Platform väljer du **[!UICONTROL Sources]** och hitta **[!UICONTROL Google Cloud Storage]** alternativ. Därifrån behöver du bara hitta den datauppsättning du sparat från BigQuery.

Tänk på detta:

* Se till att du väljer JSON-format.
* Du kan välja en befintlig datauppsättning eller skapa en ny (rekommenderas).
* Se till att du väljer samma schema för historiska data om Google Analytics och liveströmmande Google Analytics, även om de finns i separata datauppsättningar. Du kan sedan sammanfoga datauppsättningarna i en [CJA-anslutning](/help/connections/combined-dataset.md).

Instruktioner finns i den här videon:

>[!VIDEO](https://video.tv.adobe.com/v/332676)

Du kan mappa GA-händelsedata till en befintlig datauppsättning som du skapade tidigare, eller skapa en ny datauppsättning, med det XDM-schema som du väljer. När du har valt schemat använder Experience Platform maskininlärning för att automatiskt mappa varje fält i Google Analytics till dina [XDM-schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html#ui).

![](assets/schema-map.png)

Mappningar är mycket enkla att ändra och du kan till och med skapa härledda eller beräknade fält från Google Analytics data. När du är klar med mappningen av fälten i XDM-schemat kan du schemalägga den här importen regelbundet och tillämpa felvalidering under importen. Detta säkerställer att det inte uppstår några problem med de data du har importerat.

**Beräkningsfältet Tidsstämpel**

För `timestamp` schemafält i Google Analytics-data måste du skapa ett särskilt beräkningsfält i användargränssnittet för Experience Platform-schemat. Klicka **[!UICONTROL Add calculated field]** och radbryta `timestamp` sträng i en `date` så här:

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

Du måste sedan spara det här beräknade fältet i tidsstämpeldatastrukturen i schemat:

![](assets/timestamp.png)

**&#39;_id&#39; beräknat fält**

The `_id` schemafältet måste ha ett värde - CJA bryr sig inte om vad värdet är. Du kan bara lägga till&quot;1&quot; i fältet:

![](assets/_id.png)

## Importera data från Google Analytics som strömmas live

Du kan också spela in direktuppspelningshändelser från Google Tag Manager direkt till Adobe Experience Platform.

### 1. Lägg till anpassade variabler

När du har loggat in på Google Tag Manager-kontot måste du lägga till vissa anpassade konstantvariabler för Adobe. Du har antagligen redan variabler i Google Tag Manager som skickas till Google Analytics, som kundens e-postadress, kundens namn, språk och kundens inloggningsstatus. Du måste definiera fem nya anpassade variabler:

* Adobe Experience Cloud org-ID
* Slutpunkt för DCS-direktuppspelning
* Experience Platform dataset-ID
* Schemareferens
* Sidtidsstämpel

Om du hämtar dessa värden skickas alla data från Google Analytics till rätt datauppsättning och har rätt schema. Om du inte känner till din Experience Cloud-organisation eller någon av de andra variablerna som vi just nämnde kan din kontoansvarige på Adobe hjälpa dig att hitta den.

När du har definierat de här anpassade variablerna kan vi ställa in en utlösare för att skicka alla data som du redan skickar till Google Analytics till Experience Platform.

### 2. Konfigurera en utlösare i Google Tag Manager

I det här exemplet har utlösaren för att skapa konto definierats, där `pageUrl equals account-creation`. Genom att lägga till viss information i den här utlösaren kan du se till att data skickas till både Google Analytics och AEP när användaren autentiserar och sidan där kontot skapas läses in.

Du kan även referera till [Datainmatning och Google Tag Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html#module9).

Instruktioner finns i den här videon:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Skapa en anslutning i CJA till datauppsättningen Google Analytics

När Adobe Experience Platform har börjat ta emot data från live-Google Analytics och du har fyllt i de historiska Google Analytics från BigQuery är du redo att börja använda CJA och [skapa din första anslutning](/help/connections/create-connection.md). Den här anslutningen sammanfogar GA-data med alla dina andra kunddata med ett gemensamt&quot;Kund-ID&quot;.

## Nästa steg

* Skapa en [datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#cja-dataviews) baserat på den anslutning som innehåller Google Analytics data.

* Gör några fantastiska [analys i arbetsytan](/help/use-cases/ga-to-cja-reporting.md).