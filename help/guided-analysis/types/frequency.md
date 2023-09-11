---
title: Frekvensvy
description: Mät engagemang efter användningsfrekvens.
feature: Guided Analysis
keywords: produktanalys
source-git-commit: 77192426a58e1560abe91b904452b9cd46c862e9
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# [!UICONTROL Frequency] visa

The **[!UICONTROL Frequency]** visa grupphändelsedata efter hur ofta en händelse visas. Den lodräta axeln i den här rapporten innehåller grupper som representerar frekvensen för händelser som visas. Den vågräta axeln mäter antalet användare eller sessioner för varje bucket.

![Skärmbild med frekvens](../assets/frequency-stacked.png)

## Användningsexempel

Exempel:

* **Engagemang**: Håll koll på hur engagerade användare är med alla händelser. Du kan klicka på ett vågrätt fält om du vill spara det som ett segment. Segment för kundsegment med låg engagemangsfrekvens kan hjälpa er att avgöra varför användarna inte interagerar med händelsen med den önskade frekvensen. Segment för större engagemang kan hjälpa er att förstå varför användarna interagerar med händelsen ofta. Därifrån kan du uppmuntra andra användare att använda liknande beteenden.
* **Kundlojalitet**: Ställ in händelsen på Beställningar och måttet på Användare. Med den här rapporten kan du gruppera användare efter hur många gånger de har gjort ett köp på din webbplats inom det angivna datumintervallet.
* **Supportoptimering**: Om du ser den här rapporten utifrån antalet supportsamtal eller öppna ärenden kan du få information om vilka användare som har mest problem. Sedan kan du skapa ett segment som fokuserar på deras upplevelse för att identifiera och lösa problem.
* **Prenumerationstjänster**: Den här rapporten är värdefull för organisationer som har prenumerationstjänster. Användare med lågt engagemang är mer benägna att försvinna, så du kan se den här rapporten för att analysera beteendet hos mycket engagerade användare. Att förstå hur mycket engagerade användare beter sig kan bidra till att uppmuntra liknande beteenden för användare med dåligt engagemang, vilket gör dem mindre benägna att avbryta prenumerationen.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Events]**: De händelser som du vill mäta. Varje markerad händelse representeras som ett separat diagram. En rad som representerar händelsen trended läggs till i tabellen. Du kan inkludera upp till fem händelser.
* **[!UICONTROL People]**: De segment som du vill mäta. Varje markerat segment dubblerar antalet rader i diagrammet och raderna i tabellen. Du kan inkludera upp till fem segment.

## Diagraminställningar

The [!UICONTROL Frequency] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Metric]**: Det mått som du vill mäta. Alternativen inkluderar [!UICONTROL Users] och [!UICONTROL Sessions].
* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen inkluderar [!UICONTROL Horizontal bar] och [!UICONTROL Stacked bar].

## Inställningar för Bucket

Anger hur händelsen kategoriseras i grupper.

* **[!UICONTROL Auto buckets]**: Identifiera automatiskt den optimala bucketstorleken baserat på datafördelningen.
* **[!UICONTROL Customized buckets]**: Styr hur rapporten grupperar data i grupper.
   * [!UICONTROL From]: Den första bucket. Frekvensen som är mindre än det här värdet undantas från rapportering.
   * [!UICONTROL To]: Frekvensen större än det här värdet grupperas i den sista bucket.
   * [!UICONTROL Size]: Bucketintervallet.

## Använd tidsjämförelse

{{apply-time-comparison}}

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Den här inställningen påverkar inte icke-trendvyer som Frekvens.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
