---
title: Tie Quantum Metric-sessionen spelas upp på nytt till data i Customer Journey Analytics
description: Länka Quantum Metric-sessionen spelas upp igen med CJA-data för att bättre förstå"varför" bakom"vad".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 752e8564c341cf02b5378a12a820f52ca6164a3d
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---

# Tie Quantum Metric-sessionen spelas upp på nytt till data i Customer Journey Analytics

Genom att länka Quantum Metric-sessionsuppspelningar till CJA-data kan kunderna bättre förstå&quot;varför&quot; bakom&quot;vad&quot;.  Workspace kan användas för att upptäcka sessioner med friktion. Sedan kan du klicka på hyperlänkade sessions-ID:n för att utforska sessionsreprisen i Quantum Metric.  Dessa data gör det möjligt att visa beteenden i en session och bättre förstå vad som driver konsumentens friktion.  Genom sessionsrepriser som är knutna till CJA kan ni fånga upp viktiga kontexter kring kundbeteenden i er upplevelse.

## Förutsättningar

Det här användningsexemplet kräver att du samlar in Quantum Metrics sessions-ID tillsammans med resten av implementeringen. Mer information om hur du ändrar implementeringen finns i [Samla in sessions-ID:n för kvantmått i Customer Journey Analytics](collect-session-id.md).

## Steg 1: Konfigurera Workspace för att anpassa dimensionen för sessions-ID

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

## Steg 2 Visa sessioner från Customer Journey Analytics

När du har hittat ett intressant segment som du vill utforska sessionsuppspelningar för kan du använda det på panelen som innehåller dina sessions-ID-länkar och filtrera efter segment. Tabellen returnerar alla sessioner i det segmentet och du kan klicka på någon av dem för att utforska mer i Quantum Metric.

Läs mer om Quantum Metric-sessionsuppspelning på [https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay). Om du behöver ytterligare resurser kontaktar du kundsupportrepresentanten för Quantum Metric eller skickar en begäran via Quantum Metric [Customer Request Portal](https://community.quantummetric.com/s/public-support-page).

