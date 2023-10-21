---
title: Versionsvy
description: Jämför prestanda i lika stora perioder före och efter lanseringen.
feature: Guided Analysis
keywords: produktanalys
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
source-git-commit: 02044961612a3d0f4f40bdc71c3f00585d702c92
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# [!UICONTROL Release] visa

The **[!UICONTROL Release]** visar en jämförelse av hur nyckelindikatorer utfördes före och efter ett visst datum. Den vågräta axeln i den här rapporten är ett tidsintervall, medan den lodräta axeln mäter de önskade nyckelindikatorerna. Ett lodrätt streck mitt i diagrammet representerar det datum som du vill jämföra före och efter. Detta datum är vanligtvis en betydande ändring av den produkt som du vill mäta mot, till exempel en uppdatering av produkten eller en kampanjstart.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Användningsexempel

Exempel:

* **Övergripande resultatutvärdering:** Genom att jämföra övergripande nyckelindikatorer, t.ex. engagemangsåtgärder, kan du avgöra om en given release var framgångsrik i stort.
* **Övervakning**: Spåra viktiga mätvärden som du kan förvänta dig ska vara enhetliga när ändringar görs, som inläsningstid eller antal inloggningar. Använd den här analystypen för att jämföra dem före och efter en release för att säkerställa att den inte fick några oönskade konsekvenser.
* **Antagande av nya funktioner**: Om en produktuppdatering är inriktad på att förbättra en viss funktion kan du använda den här vyn för att direkt jämföra den funktionens användning före och efter produktuppdateringen.
* **Felsökning**: Att spåra antalet fel före och efter en release kan ge en tidig indikation på kundproblem. Om antalet fel ökar direkt efter en release kan ni tillsammans med konstruktions- eller utvecklingsteamen identifiera och korrigera problemet och på så sätt förhindra att kunderna påverkas ytterligare.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Key indicators]**: De händelser som du vill mäta per användare. Varje markerad tangentindikator representeras som en färgad linje. En rad som representerar händelsen läggs till i tabellen. Du kan inkludera upp till tre händelser.
* **[!UICONTROL Factors]**: Det datum som du vill jämföra före och efter.
* **[!UICONTROL People]**: Det segment som du vill mäta. Det valda segmentet filtrerar data så att de bara fokuserar på de personer som matchar dina segmentkriterier.

## Diagraminställningar

I vyn Releaser finns följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **[!UICONTROL Metric]**: Det mått som du vill mäta. Alternativen inkluderar [!UICONTROL Events per user], [!UICONTROL Percentage of users], [!UICONTROL Events], [!UICONTROL Sessions]och [!UICONTROL Users].
* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen inkluderar [!UICONTROL Line] och [!UICONTROL Bar].

## Datumintervall

Datumvalet i effektanalysen fungerar annorlunda än andra analystyper, eftersom rapporten kretsar kring det datum som anges i frågerefältet. Följande alternativ är tillgängliga:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly]och [!UICONTROL Quarterly]. Om du ändrar intervallet påverkas alternativen för perioden Före och efter.
* **[!UICONTROL Before and after period]**: Den tid som ska analyseras före och efter det datum som anges i frågerefältet. Vilka alternativ som är tillgängliga beror på [!UICONTROL Interval] markering.
