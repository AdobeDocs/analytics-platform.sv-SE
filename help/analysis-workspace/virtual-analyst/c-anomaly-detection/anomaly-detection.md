---
description: Du kan visa och analysera dataanomalier i sammanhangsbaserat läge i Analysis Workspace.
title: Översikt över avvikelseidentifiering
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 7%

---


# Översikt över avvikelseidentifiering

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan visa och analysera dataanomalier i ett sammanhang i Analysis Workspace.

[Anomalys upptäckt på YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) 4:53)

Anomaly Detection är en statistisk metod för att fastställa hur ett givet mätresultat har ändrats i förhållande till tidigare data.

Anomaly Detection gör att du kan separera &quot;verkliga signaler&quot; från &quot;brus&quot; och sedan identifiera potentiella faktorer som bidrog till dessa signaler eller anomalier. Med andra ord kan man identifiera vilka statistiska fluktuationer som är viktiga och vilka som inte är det. Sedan kan du identifiera roten till en sann anomali. Dessutom kan du få tillförlitliga prognoser för mätning (KPI).

Exempel på avvikelser som du kan undersöka är:

* Drastiska droppar i genomsnittligt ordervärde
* Spikes i order med låg avkastning
* Spikes eller droppar i testregistreringar
* Droppar i landningssidvyerna
* Spikes i videobufferthändelser
* Spikes i låga videobithastigheter

Både anomalisk detektion och [Bidragsanalys](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) är centrala arbetsflöden i Analysis Workspace. Du kan köra kostnadsanalys mot varje daglig avvikelse och bädda in resultatet i Analysis Workspace-projektet.

>[!IMPORTANT]
>
>Det finns ännu inte någon kostnadsanalys i kundresanalysen.

Analysarbetsytans algoritm för onormal identifiering innehåller

* Stöd för granularitet per timme, vecka och månad, utöver den befintliga dagliga granulariteten.
* Kännedom om säsongsvariation (t.ex. &quot;Black Fredag&quot;) och helgdagar.

## Inaktivera avvikelseidentifiering

Du kan inaktivera avvikelsidentifiering på kolumnnivå genom att gå till kolumninställningarna och ta bort kontrollen **[!UICONTROL Anomalies]**.

![](assets/turnoff_anomalies.png)
