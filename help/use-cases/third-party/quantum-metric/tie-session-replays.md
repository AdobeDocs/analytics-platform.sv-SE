---
title: Tie Quantum Metric-sessionen spelas upp på nytt till data i Customer Journey Analytics
description: Länka Quantum Metric-sessionen spelas upp igen med CJA-data för att bättre förstå"varför" bakom"vad".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---

# Tie Quantum Metric-sessionen spelas upp på nytt till data i Customer Journey Analytics

Genom att länka Quantum Metric-sessionsuppspelningar till CJA-data kan kunderna bättre förstå&quot;varför&quot; bakom&quot;vad&quot;.  Workspace kan användas för att upptäcka sessioner med friktion. Sedan kan du klicka på hyperlänkade sessions-ID:n för att utforska sessionsreprisen i Quantum Metric.  Dessa data gör det möjligt att visa beteenden i en session och bättre förstå vad som driver konsumentens friktion.  Genom sessionsrepriser som är knutna till CJA kan ni fånga upp viktiga kontexter kring kundbeteenden i er upplevelse.

## Förutsättningar

I de här stegen förutsätts att du använder taggar i Adobe Experience Platform Data Collection. Du kan anpassa datainsamlingsmetoderna till en manuell implementering av Web SDK om din organisation inte använder taggar.

Mer information finns i dokumentationen för [Quantum Metric-taggtillägget](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric).

## Steg 1: Hämta sessions-ID:t för kvantmått med tillägget för kvantmetriska taggar

Följ de här stegen för att lägga till Quantum Metric-sessions-ID:t till data som du skickar till Adobe Experience Platform.

1. Använd tillägget Quantum Metric i tagggränssnittet för att skicka data till Quantum Metric.
1. Skapa fyra dataelement:
   1. En som hämtar sessions-ID för kvantmått från Quantum Metrics cookie med namnet `QuantumMetricSessionID`
   1. En som extraherar Quantum Metric-sessions-ID från `localStorage`. Ibland läses det här dataelementet in snabbare än den cookie-fil som har angetts i det andra dataelementet.
   1. Använd dataelementassistenten eller anpassade JavaScript för att extrahera noden `s` från dataelementet `localStorage`.
   1. En som använder logik för att först leta efter cookie-dataelementet och returnera det till en XDM-objektsökväg om den hittas. Om värdet är odefinierat kan du försöka söka i det extraherade `localStorage`-objektdataelementet.
1. Skicka det sista dataelementet för Quantum Metric-sessions-ID till det XDM-objekt som skickas vid varje händelse.

>[!NOTE]
>Ibland körs Web SDK snabbare än Quantum Metric-koden. I dessa fall skickas sessions-ID vid nästa träff. Om en besökare studsar samlas inte sessions-ID:t in i dessa instanser.

## Steg 2: Bekräfta inkluderade datamängdsfält

Bekräfta att datauppsättningarna i din anslutning nu har ett sessions-ID för kvantmått i den önskade datauppsättningen.

## Steg 3: Lägg till sessions-ID för kvantmått som en tillgänglig dimension

Redigera den befintliga datavyn för att lägga till sessions-ID som en tillgänglig dimension i Customer Journey Analytics.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Data views]** på den översta menyn.
1. Välj önskad befintlig datavy.
1. Leta upp listan med sessions-ID för kvantmått till vänster och dra den till dimensionsområdet i mitten.
1. I den högra rutan anger du inställningen [persistence](/help/data-views/component-settings/persistence.md) till Session.
1. Klicka på **[!UICONTROL Save]**.

## Steg 4: Konfigurera Workspace för att anpassa dimensionen för sessions-ID

Skapa en friformstabell i Workspace och konfigurera den så att sessions-ID-värden är länkar direkt till kvantmätvärden.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Workspace]** på den översta menyn.
1. Välj ett befintligt projekt eller skapa ett projekt.
1. Skapa en [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Dra sessions-ID-dimensionen till Workspace Canvas.
1. Högerklicka på dimensionskolumnens rubrik och välj sedan **[!UICONTROL Create hyperlinks for all dimension items]**.
1. Välj **[!UICONTROL Create a custom URL]**.
1. Klistra in följande URL-struktur:

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. Klicka på **[!UICONTROL Create]**.

Varje sessions-ID är nu en klickbar länk. Mer information om hur du lägger till hyperlänkar i Analysis Workspace-dimensionsobjekt finns i [Skapa hyperlänkar i en frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).

## Steg 5: Visa sessioner från Customer Journey Analytics

När du har hittat ett intressant segment som du vill utforska sessionsuppspelningar kan du använda det på panelen som innehåller dina sessions-ID-länkar och filtrera efter segment. Tabellen returnerar alla sessioner i det segmentet och du kan klicka på någon av dem för att utforska mer i kvantmätaren.

Mer information finns i [Enterprise Guide to session replay](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) på Quantum Metric. Du kan också kontakta din kundsupportrepresentant för Quantum Metric eller skicka en begäran via [portalen för kvantmetrisk kundbegäran](https://community.quantummetric.com/s/public-support-page).
