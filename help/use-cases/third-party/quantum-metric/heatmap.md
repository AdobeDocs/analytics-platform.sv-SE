---
title: Använd Quantum Metric-heatmaps med Customer Journey Analytics
description: Bättre förstå sidnivåsengagemang och optimera sidor baserat på konsumentbeteenden med hjälp av kvantmetriska heatmappdata.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: 95a107c6bbc6dce6cc43c4a1b51beeaa1fa7aff1
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Använd Quantum Metric-heatmaps med Customer Journey Analytics

Genom att länka kvantmetrisk heatmappning till CJA-data kan ni bättre förstå sidnivåengagemanget och optimera sidor baserat på kundens beteende. Workspace kan användas för att förstå konsumentflöden och se vilka vägar kunderna följer från en sida till nästa. Sedan kan du klicka på hyperlänkade sid-URL:er för att visuellt heatmappa hur användarna interagerar med innehållet. Genom att länka Quantum Metric Heatmapping till CJA kan du nu koppla sidnivåinteraktioner till affärsresultat, vilket tar din analys till nästa nivå.

Tabellen returnerar alla sessioner i det segmentet och du kan klicka på någon av dem för att utforska QM ytterligare.  Läs mer om Quantum Metric-sessionsuppspelning på https://www.quantummetric.com/platform/session-replay

## Förutsättningar

Du måste vara berättigad till Quantum Metric-paketet **UX Ops** för att komma åt Quantum Metrics heatmap-funktioner.

## Steg 1: Konfigurera länkar i Analysis Workspace

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Workspace]** på den översta menyn.
1. Välj ett befintligt projekt eller skapa ett projekt.
1. Skapa en [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Dra sidans URL-dimension till Workspace Canvas.
1. Högerklicka på dimensionskolumnens rubrik och välj sedan **[!UICONTROL Create hyperlinks for all dimension items]**.
1. Välj **[!UICONTROL Create a custom URL]**.
1. Klistra in följande URL-struktur:

   ```
   $value?qm-visible=true
   ```

1. Klicka på **[!UICONTROL Create]**.
1. Testa en av länkarna för att se om den öppnas i URL:en med tillägget Quantum Metric synligt. Länkarna öppnas på en ny flik så att ditt Workspace-projekt förblir öppet.

![Heatmap](assets/heatmap.png)

## Steg 2: Visa heatmaps genom att klicka på länkar i Customer Journey Analytics

När du har hittat en sida som du vill utforska heatmapping kan du använda den på den önskade panelen. Tabellen returnerar en URL som gör att du kan utforska heatmaps, rullningsdjup och nyckelzoner för interaktion med Quantum Metric. Mer information finns i [Produktöversikt för kvantmetrisk heatmap](https://www.quantummetric.com/platform/interaction-heatmaps). Du kan också kontakta din kundsupportrepresentant för Quantum Metric eller skicka en begäran via [portalen för kvantmetrisk kundbegäran](https://community.quantummetric.com/s/public-support-page).
