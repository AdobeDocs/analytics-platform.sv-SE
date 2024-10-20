---
title: Versionsvy
description: Jämför prestanda i lika stora perioder före och efter lanseringen.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: ce04e69d2c933f893eeeff04abb0f56fb4000e6f
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# [!UICONTROL Release impact]-vy

Vyn ![Version](/help/assets/icons/Release.svg) **[!UICONTROL Release impact]** visar en jämförelse av hur nyckelindikatorer utfördes före och efter ett visst datum. Den vågräta axeln i den här rapporten är ett tidsintervall, medan den lodräta axeln mäter de önskade nyckelindikatorerna. Ett lodrätt streck mitt i diagrammet representerar det datum som du vill jämföra före och efter. Detta datum är vanligtvis en betydande ändring av den produkt som du vill mäta mot, till exempel en uppdatering av produkten eller en kampanjstart.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Användningsexempel

Exempel:

* **Allmän prestandautvärdering:** En jämförelse av övergripande nyckelindikatorer, t.ex. engagemangsmått, kan hjälpa dig att avgöra om en given release totalt sett var framgångsrik.
* **Övervakning**: Spåra viktiga mätvärden som du kan förvänta dig ska vara platta när ändringar görs, som inläsningstid eller antal inloggningar. Använd den här analystypen för att jämföra dem före och efter en release för att säkerställa att den inte fick några oönskade konsekvenser.
* **Funktionsanpassning**: Om en produktuppdatering är inriktad på att förbättra en viss funktion kan du använda den här vyn för att direkt jämföra den funktionens användning före och efter produktuppdateringen.
* **Felidentifiering**: Genom att spåra antalet fel före och efter en release kan du få en tidig indikation på kundproblem. Om antalet fel ökar direkt efter en release kan ni tillsammans med konstruktions- eller utvecklingsteamen identifiera och korrigera problemet och på så sätt förhindra att kunderna påverkas ytterligare.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan den här vytypen och [Första användningen](first-use-impact.md).
* **[!UICONTROL Key indicators]**: De händelser som du vill mäta per användare. Varje markerad tangentindikator representeras som en färgad linje. En rad som representerar händelsen läggs till i tabellen. Du kan inkludera upp till tre händelser.
* **[!UICONTROL Counted as]**: Den beräkningsmetod som du vill använda för de markerade händelserna. Alternativen är [!UICONTROL Events per user], [!UICONTROL Percentage of users], [!UICONTROL Events], [!UICONTROL Sessions] och [!UICONTROL Users].
* **[!UICONTROL Factors]**: Det datum som du vill jämföra före och efter.
* **[!UICONTROL Segments]**: Det segment som du vill mäta. Det valda segmentet filtrerar data så att de bara fokuserar på de personer som matchar dina segmentkriterier.

## Diagraminställningar

I vyn Releaser finns följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen är [!UICONTROL Line] och [!UICONTROL Bar].

## Datumintervall

Datumvalet i effektanalysen fungerar annorlunda än andra analystyper, eftersom rapporten kretsar kring det datum som anges i frågerefältet. Följande alternativ är tillgängliga:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly] och [!UICONTROL Quarterly]. Om du ändrar intervallet påverkas alternativen för perioden Före och efter.
* **[!UICONTROL Before and after period]**: Den tid som ska analyseras före och efter det datum som anges i frågerefälten. Vilka alternativ som är tillgängliga beror på valet av [!UICONTROL Interval].
