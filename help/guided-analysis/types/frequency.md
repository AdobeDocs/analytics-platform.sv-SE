---
title: Frekvensanalys
description: Mät engagemang efter användningsfrekvens.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 0%

---

# [!UICONTROL Frequency]-analys {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_frequency_button"
>title="Frekvens"
>abstract="Visa distribution av upprepad användaraktivitet för specifika händelser."

<!-- markdownlint-enable MD034 -->

Analysen av ![frekvens](/help/assets/icons/Histogram.svg) **[!UICONTROL Frequency]** grupperar händelsedata efter hur ofta händelser inträffar i din produkt. Den lodräta axeln i den här analysen innehåller bucket som representerar händelsens frekvens. Den vågräta axeln mäter antalet användare eller sessioner för varje bucket.

>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/frequency)

## Användningsexempel

Användningsexempel för den här analysen är:

* **Engagemang**: Spåra hur engagerade användare är med alla händelser i produkten. Du kan klicka på valfri del av stapeldiagrammet för att spara det som ett segment. Segment för kundsegment med låg engagemangsfrekvens kan hjälpa er att avgöra varför användarna inte interagerar med händelsen med den önskade frekvensen. Segment för större engagemang kan hjälpa er att förstå varför användarna interagerar med händelsen ofta. Därifrån kan du uppmuntra andra användare att använda liknande beteenden.
* **Kundlojalitet**: Ange händelsen till Beställningar och måttet till Användare. Med den här analysen kan du gruppera användare efter hur många gånger de har gjort ett köp på webbplatsen inom det angivna datumintervallet.
* **Supportoptimering**: Visa antalet supportsamtal eller öppna ärenden per användare för att få information om vilka användare som har mest problem. Sedan kan du skapa ett segment som fokuserar på deras upplevelse för att identifiera och lösa problem.
* **Prenumerationstjänster**: Användare med lågt engagemang är mer benägna att försvinna. Att förstå hur mycket engagerade användare beter sig kan bidra till att uppmuntra liknande beteenden för användare med dåligt engagemang, vilket gör dem mindre benägna att avbryta prenumerationen.

## Gränssnitt

I [Gränssnitt](../overview.md#interface) finns en översikt över gränssnittet för guidad analys. Följande inställningar är specifika för den här analysen:

### Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan den här analysen och [Trends](trends.md).
* **[!UICONTROL Events]**: De händelser som du vill mäta. Varje markerad händelse representeras som ett separat diagram. En rad som representerar händelsen trended läggs till i tabellen. Du kan inkludera upp till fem händelser.
* **[!UICONTROL Counted as]**: Den beräkningsmetod som du vill använda för de markerade händelserna. Alternativen är [!UICONTROL Users], [!UICONTROL Sessions], [!UICONTROL Percentage of users] och [!UICONTROL Percentage of sessions]. Nämnaren för procentbaserade mått i den här analysen är användare eller sessioner som gjorde de valda händelserna, inte alla aktiva användare av produkten.
* **[!UICONTROL Segments]**: Segmenten som du vill mäta. Varje markerat segment dubblerar antalet staplar i diagrammet och raderna i tabellen. Du kan inkludera upp till fem segment.

### Diagraminställningar

Analysen av [!UICONTROL Frequency] innehåller följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen är [!UICONTROL Horizontal bar] och [!UICONTROL Stacked bar].

### Inställningar för Bucket

Avgör hur händelsen kategoriseras i grupper (grupper). I den trendade tabellvyn är användarna paketerade baserat på användningsfrekvens i totalt och i varje intervall, vilket innebär att 1 användare kan räkna till olika bucklar i olika intervall.

* **[!UICONTROL Auto buckets]**: Identifiera automatiskt den optimala bucketstorleken baserat på datafördelningen.
* **[!UICONTROL Customized buckets]**: Anpassa hur data grupperas i grupper.
   * [!UICONTROL From]: Den första bucket. Frekvensen som är mindre än det här värdet undantas från rapportering.
   * [!UICONTROL To]: Frekvensen som är större än det här värdet grupperas i den sista haken.
   * [!UICONTROL Size]: Bucket-intervallet.

### Tidsjämförelse

{{apply-time-comparison}}

### Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Diagrammet och tabellen visar aggregerade data som standard, med möjlighet att expandera tabellen till en trendvy. I trendvyn är användarna paketerade baserat på användningsfrekvens i totalt och i varje intervall, vilket innebär att 1 användare kan räkna till olika bucklar i olika intervall.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
