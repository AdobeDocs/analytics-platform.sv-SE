---
title: Använd mått för marknadsföringskanaler i Adobe Experience Platform
description: Använd Analytics Data Connector för att överföra regler för bearbetning av marknadsföringskanaler till Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: b5ed4c65877fa8e2de83810a3c4bd1a4048f5b31
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 0%

---


# Använd mått för marknadsföringskanaler i Adobe Experience Platform

Om din organisation använder [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) för att hämta rapportsvitsdata till CJA, kan du konfigurera en anslutning i CJA för att rapportera mått för marknadsföringskanalen.

## Förutsättningar

* Rapportsvitens data måste redan importeras till Adobe Experience Platform med [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). Andra datakällor stöds inte, eftersom marknadsföringskanaler använder bearbetningsregler i en Analytics-rapportserie.
* Bearbetningsregler för marknadsföringskanaler måste redan vara konfigurerade. Se [Bearbetningsregler för marknadsföringskanaler](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-rules.html) i den traditionella guiden för Analytics-komponenter.

## Schemaelement för marknadsföringskanal

När du har upprättat Analytics Data Connector för en önskad rapportserie skapas ett XDM-schema åt dig. Det här schemat innehåller alla analysdimensioner och mätvärden som rådata. Dessa rådata innehåller inte attribuering eller beständighet. I stället kör varje händelse igenom regler för hantering av marknadsföringskanaler och registrerar den första regeln som den matchar. Du anger attribuering och beständighet när du skapar en datavy i CJA.

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

Inställningarna för marknadsföringskanaler fungerar annorlunda mellan plattformsdata och rapportsvitsdata. Tänk på följande skillnader när du skapar marknadsföringskanaler för CJA:

* **Är första sidan av besök**: Det här regelvillkoret är vanligt för flera standarddefinitioner av marknadsföringskanaler. Alla bearbetningsregler som innehåller det här villkoret ignoreras i Plattform (andra villkor i samma regel gäller fortfarande). Sessionerna bestäms vid datafrågetiden i stället för vid datainsamlingen, vilket förhindrar att den här specifika regelkriterierna används av plattformen. Adobe rekommenderar att villkoret&quot;Är första sidan i besöket&quot; tas bort från varje regel för hantering av marknadsföringskanaler.

   ![Första sidan av besöket](assets/first-page-of-visit.png)

* **Åsidosätt sista tryckkanal**: Den här inställningen i Marketing Channel Manager förhindrar normalt att vissa kanaler får sista beröringskanalkredit. Plattformen ignorerar den här inställningen, vilket gör att breda kanaler som &quot;Direkt&quot; eller &quot;Intern&quot; kan attributera mot mätvärden på potentiellt oönskade sätt. Adobe rekommenderar att du tar bort kanaler där alternativet Åsidosätt sista tryckkanalen inte är markerat.
   * Du kan ta bort marknadsföringskanalen &quot;Direkt&quot; i Marketing Channel Manager och sedan förlita dig på CJA:s dimensionsobjekt &quot;Inget värde&quot; för den kanalen. Du kan också byta namn på dimensionsobjektet till &quot;Direkt&quot; eller exkludera dimensionsobjektet helt när du konfigurerar en datavy.
   * Du kan också skapa en klassificering av marknadsföringskanaler, som klassificerar varje värde efter sig själv, förutom de kanaler som du vill utesluta i CJA. Du kan sedan använda den här klassificeringsdimensionen när du skapar en datavy i stället för `channel.typeAtSource`.

   ![Åsidosätt den senaste pekkanalen](assets/override-last-touch-channel.png)

* **Utgångsdatum** för marknadsföringskanal: Inställningen för den här interaktionsperioden avgör inaktivitetsperioden innan en besökare kan få en ny första beröringskanal i rapportsvitens data. Plattformen använder sina egna attribueringsinställningar, så den här inställningen ignoreras helt i CJA.

   ![Utgångsdatum för marknadsföringskanal](assets/marketing-channel-expiration.png)

## Jämföra data mellan CJA och traditionell analys

Eftersom Adobe Experience Platform arkitektur skiljer sig från en traditionell Analytics-rapportserie är det inte säkert att resultaten matchar. Du kan dock använda följande tips för att göra jämförelsen enklare:

* Kontrollera att de arkitektoniska skillnader som anges ovan inte påverkar jämförelsen. Detta inkluderar borttagning av kanaler som inte åsidosätter den senaste beröringskanalen och borttagning av regelvillkor som är den första träffen av ett besök (session).
* Kontrollera att din anslutning använder samma rapportserie som traditionell Analytics. Om din CJA-anslutning innehåller flera rapportsviter med sina egna regler för bearbetning av marknadsföringskanaler, finns det inget enkelt sätt att jämföra den med traditionell Analytics. Du vill skapa en separat anslutning för varje rapportsserie för att jämföra data.
* Se till att du jämför samma datumintervall och att tidszonsinställningen i datavyn är densamma som rapportsvitens tidszon.
* Använd en anpassad attribueringsmodell när du visar rapportsvitens data. Använd till exempel dimensionen [Marknadskanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) med mått som använder en icke-standardattribueringsmodell. Adobe rekommenderar att du inte jämför standarddimensionerna [Första beröringskanalen](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html) eller [Senaste beröringskanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html) eftersom de är beroende av attribuering som samlas in i rapportsviten. CJA förlitar sig inte på en rapportsvits attribueringsdata. i stället beräknas det när en CJA-rapport körs.
* Vissa mätvärden har ingen rimlig jämförelse på grund av skillnader i arkitektur mellan rapportsvitdata och plattformsdata. Exempel är besök/sessioner, besökare/människor och förekomster/händelser.
