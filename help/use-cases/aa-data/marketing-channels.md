---
title: Använd mått för marknadsföringskanal
description: Lär dig hur du använder Analytics-källkopplingen för att överföra regler för bearbetning av marknadsföringskanaler till Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 0%

---

# Använd mått för marknadsföringskanal

Om din organisation använder [Analytics-källkopplingen](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) för att hämta rapportsvitsdata till Customer Journey Analytics kan du konfigurera en anslutning i Customer Journey Analytics för att rapportera om mått för marknadsföringskanalen.

>[!IMPORTANT]
>
>Se mallen [Härledda fält - marknadsföringskanaler](/help/data-views/derived-fields/derived-fields.md#marketing-channels) för inbyggda produktfunktioner för att rapportera mått för marknadsföringskanaler.
>


## Förutsättningar

* Rapportsvitens data måste redan importeras till Adobe Experience Platform med [Analytics-källkopplingen](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics). Andra datakällor stöds inte, eftersom marknadsföringskanaler använder bearbetningsregler i en Analytics-rapportserie.
* Bearbetningsregler för marknadsföringskanaler måste redan vara konfigurerade. Se [Bearbetningsregler för marknadsföringskanaler](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules) i guiden för Adobe Analytics-komponenter.

## Schemaelement för marknadsföringskanal

När du har upprättat Analytics-källkopplingen för en önskad rapportsvit skapas ett XDM-schema åt dig. Det här schemat innehåller alla analysdimensioner och mätvärden som rådata. Dessa rådata innehåller inte attribuering eller beständighet. I stället kör varje händelse igenom regler för hantering av marknadsföringskanaler och registrerar den första regeln som den matchar. Du anger attribuering och beständighet när du skapar en datavy i Customer Journey Analytics.

1. [Skapa en anslutning](/help/connections/create-connection.md) som innehåller en datauppsättning baserad på Analytics-källkopplingen.
2. [Skapa en datavy](/help/data-views/create-dataview.md) som innehåller följande dimensioner:
   * **`channel.typeAtSource`**: Motsvarar dimensionen [Marknadskanal](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/marketing-channel).
   * **`channel._id`**: Motsvarar [Marknadskanalinformationen](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/marketing-detail)
3. Ge varje dimension önskad attribueringsmodell och beständighet. Om du vill ha både den första och sista beröringsdimensionen drar du varje marknadsföringskanaldimension till komponentområdet flera gånger. Ge varje dimension önskad attribueringsmodell och beständighet. Adobe rekommenderar också att du ger varje dimension ett visningsnamn som gör det enklare att använda i Workspace.
4. Skapa datavyn.

Nu kan du använda dina mått för marknadsföringskanalen i Analysis Workspace.

>[!NOTE]
>
> Analyskällans koppling kräver att både `channel.typeAtSource` (marknadsföringskanal) och `channel._id` (marknadsföringskanaldetalj) fylls i. I annat fall överförs ingetdera till XDM ExperienceEvent. En tom marknadsföringskanaldetalj i källrapportsviten resulterar i en tom `channel._id` och Analytics-källkopplingen kommer också att tömma `channel.typeAtSource`. Dessa blanksteg kan leda till att rapportskillnader rapporteras mellan Adobe Analytics och Customer Journey Analytics.

## Bearbetnings- och arkitekturskillnader

>[!IMPORTANT]
>
>Det finns flera grundläggande dataskillnader mellan rapportsvitens data och plattformsdata. Adobe rekommenderar starkt att man justerar reglerna för hur marknadsföringskanalen i din rapportsvit hanteras för att underlätta en korrekt datainsamling i Experience Platform.

>[!NOTE]
>
>För att maximera effekten av marknadsföringskanaler för attribuering och Customer Journey Analytics finns det [reviderade bästa praxis](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/mchannel-best-practices).

Inställningarna för marknadsföringskanaler fungerar annorlunda mellan plattformsdata och rapportsvitsdata. Tänk på följande skillnader när du skapar marknadsföringskanaler för Customer Journey Analytics:

* **Är första sidan av besök**: Det här regelvillkoret är vanligt i flera standarddefinitioner av marknadsföringskanaler. Alla bearbetningsregler som innehåller det här villkoret ignoreras i Plattform (andra villkor i samma regel gäller fortfarande). Sessionerna bestäms vid datafrågetiden i stället för vid datainsamlingen, vilket förhindrar att den här specifika regelkriterierna används av plattformen. Adobe rekommenderar att man omvärderar alla regler för bearbetning av marknadsföringskanaler som innehåller villkoret&quot;Är första sidan i besöket&quot; och väljer alternativa strategier för att uppnå era mål.

  ![Första sidan av besöket](../assets/first-page-of-visit.png)

* **Åsidosätt sista-beröringskanal**: Den här inställningen i Marketing Channel Manager förhindrar normalt att vissa kanaler får senaste beröringskanalkredit. Plattformen ignorerar den här inställningen, vilket gör att breda kanaler som &quot;Direkt&quot; eller &quot;Intern&quot; kan attributera mot mätvärden på potentiellt oönskade sätt. Adobe rekommenderar att du tar bort kanaler där alternativet Åsidosätt sista tryckkanalen inte är markerat.
   * Du kan ta bort marknadsföringskanalen &quot;Direkt&quot; i Marketing Channel Manager och sedan förlita dig på Customer Journey Analytics Dimensionsobjekt &quot;Inget värde&quot; för den kanalen. Du kan också byta namn på dimensionsobjektet till &quot;Direkt&quot; eller exkludera dimensionsobjektet helt när du konfigurerar en datavy.
   * Du kan också skapa en klassificering av marknadsföringskanaler, som klassificerar varje värde efter sig själv, förutom de kanaler som du vill utesluta i Customer Journey Analytics. Du kan sedan använda den här klassificeringsdimensionen när du skapar en datavy i stället för `channel.typeAtSource`.

  ![Åsidosätt den senaste beröringskanalen](../assets/override-last-touch-channel.png)

* **Förfallotid för marknadsföringskanal**: Den här inställningen för engagemangsperiod avgör inaktivitetsperioden innan en person kan få en ny första beröringskanal i rapportsvitens data. Platform använder sina egna attribueringsinställningar, så den här inställningen ignoreras helt i Customer Journey Analytics.

  ![Utgångsdatum för marknadsföringskanal](../assets/marketing-channel-expiration.png)

## Jämföra data mellan Customer Journey Analytics och Adobe Analytics

Eftersom Adobe Experience Platform arkitektur skiljer sig från Adobe Analytics kan man inte vara säker på att resultatet matchar. Du kan dock använda följande tips för att göra jämförelsen enklare:

* Kontrollera att de arkitektoniska skillnader som anges ovan inte påverkar jämförelsen. Skillnaderna är bland annat att ta bort kanaler som inte åsidosätter den senaste beröringskanalen och att ta bort regelvillkor som är den första träffen i ett besök (session).
* Kontrollera att din anslutning använder samma rapportserie som Adobe Analytics. Om din Customer Journey Analytics-anslutning innehåller flera rapportsviter med egna regler för bearbetning av marknadsföringskanaler är det inte enkelt att jämföra den med Adobe Analytics. Du vill skapa en separat anslutning för varje rapportsserie för att jämföra data.
* Se till att du jämför samma datumintervall och att tidszonsinställningen i datavyn är densamma som rapportsvitens tidszon.
* Använd en anpassad attribueringsmodell när du visar rapportsvitens data. Använd till exempel dimensionen [Marknadskanal](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/marketing-channel) med mått som använder en icke-standardattribueringsmodell. Adobe rekommenderar att du inte jämför standardmåtten [Första beröringskanalen](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/first-touch-channel) eller [Sista beröringskanalen](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/last-touch-channel) eftersom de är beroende av attribuering som samlas in i rapportsviten. Customer Journey Analytics förlitar sig inte på en rapportsvits attribueringsdata, utan beräknas när en Customer Journey Analytics-rapport körs.
* Vissa mätvärden har ingen rimlig jämförelse på grund av skillnader i arkitektur mellan rapportsvitdata och plattformsdata. Exempel är besök/sessioner, personer/människor och förekomster/evenemang.
