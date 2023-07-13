---
title: Vyn Första användningen
description: Mät effekten av förstagångsanvändning på nyckelindikatorer.
feature: Guided Analysis
source-git-commit: 9fa4b894e69a25b26632a93f00a655eec8e8aa86
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# Vyn Första användningen

{{release-limited-testing}}

The **Första användningen** visar en jämförelse av hur nyckelindikatorer har utförts före och efter det att en användare vidrör en viss händelse för första gången. Den vågräta axeln i den här rapporten är ett relativt tidsintervall före och efter händelsen, medan den lodräta axeln mäter de önskade nyckelindikatorerna. Ett lodrätt streck mitt i diagrammet representerar när händelsen inträffar för en viss användare.

![Frigör](../assets/first-use.png)

## Användningsexempel

Exempel:

* **Ny funktionsanalys**: Om du startar en ny funktion i produkten kan du jämföra hur viktiga indikatorer har utförts före och efter det att användarna exponerats för den nya funktionen för första gången.
* **Kampanjeffektivitet**: När en användare tittar på en viss kampanj kan ni jämföra hur nyckelindikatorer utfördes före och efter det att användaren såg eller interagerade med kampanjen.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Viktiga indikatorer**: De händelser som du vill mäta per användare. Varje markerad tangentindikator representeras som en färgad linje. En rad som representerar händelsen läggs till i tabellen. Du kan inkludera upp till tre händelser.
* **Faktorer**: Det finns två faktorer för den här vyn:
   * **Datum**: Hur långt tillbaka du vill leta efter en händelse första gången.
   * **Händelse**: Händelsen som du vill jämföra före och efter det att den berördes.
* **Folk**: Det segment som du vill mäta. Det valda segmentet filtrerar data så att de bara fokuserar på de personer som matchar dina segmentkriterier.

## Diagraminställningar

I vyn Första användning finns följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **Mått**: Det mått som du vill mäta. Alternativen inkluderar [!UICONTROL Events per user], [!UICONTROL Events], [!UICONTROL Sessions]och [!UICONTROL Users].
* **Diagramtyp**: Den typ av visualisering som du vill använda. Alternativen är Line.

## Datumintervall

Datumval i effektrapporter fungerar annorlunda än andra analystyper, eftersom rapporten kretsar kring en viss händelse som rör sig för första gången (anges i frågespelaren). Följande alternativ är tillgängliga:

* **Intervall**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly]och [!UICONTROL Quarterly]. Om du ändrar intervallet påverkas alternativen för perioden Före och efter.
* **Före och efter punkt**: Hur lång tid det tar att analysera före och efter den berörda händelsen som anges i frågerinjen. Vilka alternativ som är tillgängliga beror på [!UICONTROL Interval] markering.
