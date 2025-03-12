---
title: Använd Quantum Metric-heatmaps med Customer Journey Analytics
description: Bättre förstå sidnivåsengagemang och optimera sidor baserat på konsumentbeteenden med hjälp av kvantmetriska heatmappdata.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: a0f82948895f3eac86cf00df1dec8abc2f723fc2
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Använd Quantum Metric-heatmaps med Customer Journey Analytics

Genom att länka kvantmetrisk heatmappning till CJA-data kan ni bättre förstå sidnivåengagemanget och optimera sidor baserat på kundens beteende. Workspace kan användas för att förstå konsumentflöden och se vilka vägar kunderna följer från en sida till nästa. Sedan kan du klicka på hyperlänkade sid-URL:er för att visuellt heatmappa hur användarna interagerar med innehållet.

Tabellen returnerar alla sessioner i det segmentet och du kan klicka på någon av dem för att utforska QM ytterligare.  Läs mer om Quantum Metric-sessionsuppspelning på https://www.quantummetric.com/platform/session-replay

## Förutsättningar

Det här användningsexemplet kräver att du samlar in Quantum Metrics sessions-ID tillsammans med resten av implementeringen. Mer information om hur du ändrar implementeringen finns i [Samla in sessions-ID:n för kvantmått i Customer Journey Analytics](collect-session-id.md).

Du måste vara berättigad till Quantum Metric-paketet **UX Ops** för att komma åt Quantum Metrics heatmap-funktioner.

## Skapa en friformstabell i Workspace och konfigurera den så att sessions-ID-värden är länkar direkt till kvantmätvärden.

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

1. Klicka på Skapa och testa sedan någon av länkarna för att se om den öppnas i URL:en med QM-tillägget öppet. Obs! Den öppnas på en separat flik så att du inte förlorar ditt arbete.


## Visa heatmaps genom att klicka på länkar i Customer Journey Analytics

När du har hittat en sida som du vill utforska heatmapping för kan du använda den på panelen som URL:en finns i. Tabellen returnerar en URL som gör att du kan utforska heatmaps för sidan i fråga, rullningsdjup och nyckelzoner för interaktion.  Läs mer om kvantmetriska värmekartor på https://www.quantummetric.com/platform/interaction-heatmaps


