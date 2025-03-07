---
title: Samla in sessions-ID:n för kvantmått i Customer Journey Analytics
description: Ändra implementeringen så att den inkluderar sessions-ID:n så att du kan analysera dem i Customer Journey Analytics.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: d71f39d25c52b0389d0441f238cb5b1809986b2d
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---

# Samla in sessions-ID:n för kvantmått i Customer Journey Analytics

Vissa användningsfall, som [att koppla Quantum Metric-sessionsåterspelningar](tie-session-replays.md) eller [med hjälp av kvantmetriska heatmaps](heatmap.md), kräver att du ändrar implementeringen för att samla in sessions-ID:t för kvantmetrisk. På den här sidan beskrivs processen för att överföra data till din befintliga implementering.

I de här stegen förutsätts att du använder taggar i Adobe Experience Platform Data Collection. Du kan anpassa datainsamlingsmetoderna till en manuell implementering av Web SDK om din organisation inte använder taggar.

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

Mer information finns i dokumentationen för [Quantum Metric-taggtillägget](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric).

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

Varje sessions-ID är nu en klickbar länk. Länkarna tar dig till Quantum Metric på en ny flik så att du kan analysera den sessionen mer i detalj. Mer information om hur du lägger till hyperlänkar i Analysis Workspace-dimensionsobjekt finns i [Skapa hyperlänkar i en frihandstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).
