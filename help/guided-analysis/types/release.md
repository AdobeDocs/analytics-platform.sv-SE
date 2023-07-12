---
title: Versionsvy
description: Jämför prestanda i lika stora perioder före och efter lanseringen.
feature: Guided Analysis
source-git-commit: aca4a5091c65d7243f79551be7cee615ba98bb26
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Versionsvy

{{release-limited-testing}}

The **Frigör** visar en jämförelse av hur nyckelindikatorer utfördes före och efter ett visst datum. Den vågräta axeln i den här rapporten är ett tidsintervall, medan den lodräta axeln mäter de önskade nyckelindikatorerna. Ett lodrätt streck mitt i diagrammet representerar det datum som du vill jämföra före och efter. Detta datum är vanligtvis en betydande ändring av den produkt som du vill mäta mot, till exempel en uppdatering av produkten eller en kampanjstart.

![Frigör](../assets/release.png)

## Användningsexempel

Exempel:

* **Övergripande resultatutvärdering:** Genom att jämföra övergripande nyckelindikatorer, t.ex. intäkter, kan du avgöra om en viss release var lyckad i stort.
* **Antagande av nya funktioner**: Om en produktuppdatering är inriktad på att förbättra en viss funktion kan du använda den här vyn för att direkt jämföra den funktionens användning före och efter produktuppdateringen.
* **Felsökning**: Att spåra antalet fel före och efter en release kan ge en tidig indikation på kundproblem. Om antalet fel ökar direkt efter en release kan ni tillsammans med konstruktions- eller utvecklingsteamen identifiera och korrigera problemet och på så sätt förhindra att kunderna påverkas ytterligare.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Viktiga indikatorer**: De händelser som du vill mäta per användare. Varje markerad tangentindikator representeras som en färgad linje. En rad som representerar händelsen läggs till i tabellen. Du kan inkludera upp till tre händelser.
* **Faktorer**: Det datum som du vill jämföra före och efter.
* **Folk**: Det segment som du vill mäta. Det valda segmentet filtrerar data så att de bara fokuserar på de personer som matchar dina segmentkriterier.

## Diagraminställningar

I vyn Releaser finns följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **Mått**: Det mått som du vill mäta. Alternativen inkluderar [!UICONTROL Events per user], [!UICONTROL Percentage of users], [!UICONTROL Events], [!UICONTROL Sessions]och [!UICONTROL Users].
* **Diagramtyp**: Den typ av visualisering som du vill använda. Alternativen är Line.

## Datumintervall

Datumval i effektrapporter fungerar annorlunda än andra analystyper, eftersom rapporten kretsar kring det datum som anges i frågerefältet. Följande alternativ är tillgängliga:

* **Intervall**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly]och [!UICONTROL Quarterly]. Om du ändrar intervallet påverkas alternativen för perioden Före och efter.
* **Före och efter punkt**: Den tid som ska analyseras före och efter det datum som anges i frågerefältet. Vilka alternativ som är tillgängliga beror på [!UICONTROL Interval] markering.
