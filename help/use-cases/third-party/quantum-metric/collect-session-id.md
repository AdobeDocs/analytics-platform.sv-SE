---
title: Samla in sessions-ID:n för kvantmått i Customer Journey Analytics
description: Ändra implementeringen så att den inkluderar sessions-ID:n så att du kan analysera dem i Customer Journey Analytics.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: 2d6c5d5b546ef8ba952d4ba4397d897ed4566283
workflow-type: tm+mt
source-wordcount: '419'
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


