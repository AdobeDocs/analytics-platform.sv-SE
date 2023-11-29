---
description: Läs mer om att upptäcka dataavvikelser i Analysis Workspace.
title: Hur avvikelseidentifiering fungerar
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
source-git-commit: 689235eb0b982f4e572282f1c73e4606f9d82b12
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# Översikt över avvikelseidentifiering

Ni kan visa och analysera dataavvikelser i sitt sammanhang inom Analysis Workspace.

[Videosjälvstudiekurs om avvikelseidentifiering](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html) (4:53)

Analysidentifiering är en statistisk metod för att fastställa hur ett givet mätresultat har ändrats i förhållande till tidigare data.

Anomaly Detection gör det möjligt att skilja &quot;sanna signaler&quot; från &quot;brus&quot; och sedan identifiera potentiella faktorer som bidragit till dessa signaler eller avvikelser. Med andra ord kan du identifiera vilka statistiska fluktuationer som är viktiga och vilka som inte gör det. Sedan kan du identifiera roten till en sann avvikelse. Dessutom kan du få tillförlitliga KPI-prognoser.

Exempel på avvikelser du kan undersöka är:

* Drastiska droppar i genomsnittligt ordervärde
* Inträffar i order med låg intäkt
* Taggar eller droppar i testregistreringar
* Droppar i landningssidvyer
* Inslag i videobufferthändelser
* Taggar i låga videobithastigheter

Analysis Workspace avvikelseavkänningsalgoritm innehåller

* Stöd för kornighet varje timme, vecka och månad, utöver den befintliga kornigheten.
* Kännedom om säsongsvaraktighet (t.ex. &quot;Black Friday&quot;) och semester.
