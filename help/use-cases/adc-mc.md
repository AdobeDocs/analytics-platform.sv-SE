---
title: Importera marknadsföringskanaler till CJA med Analytics Data Connector
description: Använd rätt inställningar för Analytics Data Connector för att överföra regler för bearbetning av marknadsföringskanaler till Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Importera marknadsföringskanaler till CJA med Analytics Data Connector

Om din organisation använder [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) för att hämta rapportsvitsdata till CJA, kan du konfigurera en anslutning i CJA för att rapportera mått för marknadsföringskanalen.

## Förutsättningar

* Rapportsvitens data måste redan importeras till Adobe Experience Platform med [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html).
* Bearbetningsregler för marknadsföringskanaler måste redan vara konfigurerade. Se [Bearbetningsregler för marknadsföringskanaler](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-rules.html) i den traditionella guiden för Analytics-komponenter.

## Schemaelement för marknadsföringskanal

När du har använt Analytics Data Connector för en önskad rapportserie skapas ett XDM-schema åt dig. Det här schemat innehåller alla analysdimensioner och mätvärden som rådata. Dessa rådata innehåller inte attribuering eller beständighet. I stället kör varje träff igenom regler för hantering av marknadsföringskanaler och registrerar den första regeln som matchar. Du anger attribuering och beständighet när du skapar en datavy i CJA.

1. [Skapa en ](/help/connections/create-connection.md) anslutning som innehåller en datauppsättning som baseras på Analytics Data Connector.
2. [Skapa en ](/help/data-views/create-dataview.md) datavy som innehåller följande dimensioner:
   * **`channel.typeAtSource`**: Motsvarar  [marknadsföringens ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) kanaldimension.
   * **`channel._id`**: Motsvarar  [marknadsföringskanalinformationen](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Ge varje dimension önskad attribueringsmodell och beständighet. Om du vill ha både den första och sista beröringsdimensionen drar du varje marknadsföringskanaldimension till komponentområdet flera gånger. Ge varje dimension önskad attribueringsmodell och beständighet. Adobe rekommenderar också att du ger varje dimension ett visningsnamn som gör det enklare att använda i Workspace.
4. Skapa datavyn.

Nu kan du använda dina mått för marknadsföringskanalen i Analysis Workspace.

## Bearbetnings- och arkitekturskillnader

>[!IMPORTANT]
>
>Det finns flera grundläggande dataskillnader mellan rapportsvitens data och plattformsdata. Adobe rekommenderar starkt att man justerar reglerna för hur marknadsföringskanalen i din rapportsvit hanteras för att underlätta en korrekt datainsamling i Platform.


Eftersom dimensionerna för den första och sista beröringskanalen i princip är samma dimension med olika attribueringsmodeller, kan du återskapa liknande dimensioner när du [skapar en datavy](/help/data-views/create-dataview.md). Du kan skapa flera dimensioner baserade på samma schemaelement och ge dem olika attribueringsmodeller och beständighet.

## Skillnader mellan

