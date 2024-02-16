---
title: Vyn Första användningen
description: Mät effekten av förstagångsanvändning på nyckelindikatorer.
feature: Guided Analysis
keywords: produktanalys
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: e448f6ddbff2673abbd2920aacf41d4268f3ce07
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# [!UICONTROL First use] visa

The **[!UICONTROL First use]** visar en jämförelse av hur nyckelindikatorer har utförts före och efter det att en användare använder en produktfunktion för första gången. Den vågräta axeln i den här rapporten är ett relativt tidsintervall före och efter händelsen, medan den lodräta axeln mäter de önskade nyckelindikatorerna. Ett lodrätt streck i mitten av diagrammet representerar dag 0 när en funktion först används av en viss användare. Eftersom användare inte alltid använder funktioner på samma dag och dina rollouter kan inträffa under flera dagar, kan dag 0 betyda något som skiljer sig åt för varje enskild användare.

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

## Användningsexempel

Exempel:

* **Ny funktionsanalys**: Om du startar en ny funktion i produkten kan du jämföra hur viktiga indikatorer utfördes före och efter det att användarna exponerades för den nya funktionen för första gången.
* **Avfasade utrullningar**: Eftersom analysen söker efter den första användningen av funktionen i stället för ett fast datum, är den här vyn användbar om du fasar ut utrullningen av funktionerna över tid.
* **Ny produktversionsanalys**: Om du startar en ny version av produkten kan du jämföra hur viktiga indikatorer utfördes före och efter det att användarna exponerades för den nya versionen för första gången. Välj&quot;any event&quot; som första användningshändelse och filtrera den till egenskapen för versionsnummer.
* **Befintliga funktionsförbättringar**: Om du gör förbättringar i en befintlig funktion i produkten kan du jämföra hur nyckelindikatorer som utfördes före och efter det att användarna exponerades för dessa nya förbättringar för första gången. Du kan utföra den här analysen på ett eller flera sätt beroende på vilken funktionsinstrumentation du har.
   * Välj en händelse som representerar förbättringen som första användningshändelse
   * Välj det datum då ändringarna började rulla ut
   * Segmentera analysen till den grupp personer som exponeras för förbättringarna
* **Kampanjeffektivitet**: När en användare klickar igenom från en viss kampanj kan du jämföra hur nyckelindikatorer utfördes före och efter att användaren interagerade med kampanjen.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan den här vytypen och [Frigör](release.md).
* **[!UICONTROL Key indicators]**: De händelser som du vill mäta per användare. Varje markerad tangentindikator representeras som en färgad linje. En rad som representerar händelsen läggs till i tabellen. Du kan inkludera upp till tre händelser.
* **[!UICONTROL Counted as]**: Den nedräkningsmetod som du vill använda för de markerade händelserna. Alternativen inkluderar [!UICONTROL Events per user], [!UICONTROL Events], [!UICONTROL Sessions]och [!UICONTROL Users].
* **[!UICONTROL Factors]**: Det finns två faktorer för den här vyn:
   * **[!UICONTROL Date]**: Hur långt tillbaka du vill börja leta efter den första användningshändelsen som har inträffat.
   * **[!UICONTROL Event]**: Den händelse som du vill söka efter för första gången, för att centrera analysen på.
* **[!UICONTROL Segments]**: Det segment som du vill mäta. Det valda segmentet filtrerar data så att de bara fokuserar på de personer som matchar dina segmentkriterier. Ett segment stöds för den här vytypen.

## Diagraminställningar

I vyn Första användning finns följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen är Line.

## Datumintervall

Datumval i effektanalys fungerar annorlunda än andra analystyper, eftersom analysen kretsar kring det datum som anges i frågespelaren. Följande alternativ är tillgängliga:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly]och [!UICONTROL Quarterly]. Om du ändrar intervallet påverkas alternativen för perioden Före och efter.
* **[!UICONTROL Before and after period]**: Hur lång tid det tar att analysera före och efter den första use-händelsen som anges i frågerinjen. Vilka alternativ som är tillgängliga beror på [!UICONTROL Interval] markering.
