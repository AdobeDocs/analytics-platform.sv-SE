---
description: Lär dig hur du använder varningar för att få detaljkontroll över meddelanden och integrering med avvikelseidentifiering.
title: Varningar - översikt
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 2%

---

# Översikt över aviseringar

Med varningar i Customer Journey Analytics kan du meddelas baserat på ändrade procentsatser eller specifika datapunkter.

Beroende på ditt Customer Journey Analytics-paket kan du även använda varningar som utlöses baserat på avvikelsetrösklar. Dessa aviseringar (kallas även *Intelligent Alerts*) ger detaljerade kontroller som kan integreras med [avvikelseidentifiering](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) och aktiveras när du behöver dem som mest.

* Förhandsgranska hur ofta en varning utlöses.
* Skicka aviseringar via e-post eller SMS med länkar till automatiskt genererade Analysis Workspace-projekt.
* Skapa *staplade* aviseringar som fångar in flera mätvärden i en enda avisering.
* Bygg aviseringar baserade på:
   * Anomalier i mätvärden som finns, är över eller under förväntade tröskelvärden.

     [Analysidentifiering](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) skapar ett förväntat värde plus en övre och nedre gräns med historiska data. Om det faktiska måttvärdet ligger över den övre gränsen eller under den nedre gränsen, definierad som tröskelvärdet, betraktas händelsen som en avvikelse vid tröskelvärdet för konfidensnivå och utlöser varningen. Ett högre tröskelvärde (till exempel 99 % eller 99,9 %) innebär ett bredare band, vilket ger färre varningar som orsakas av mer extrema avvikelser. Ett lägre tröskelvärde (till exempel 90 %) innebär ett smalare band, vilket ger fler varningar som orsakas av mindre extrema avvikelser.
   * Förändringar i mätvärden med en viss procentandel.
   * Mätvärden som är över, under eller lika med ett specifikt värde. (endast för Adobe Analytics-kunder med ett Select-, Prime- eller Ultimate-paket)

Den här [videosjälvstudien](https://experienceleague.adobe.com/sv/docs/analytics-learn/tutorials/data-science/intelligent-alerts) ger en grundläggande översikt över varningar.



## Förstå hur varningar skiljer sig

Processen att använda varningar i Customer Journey Analytics är nästan identisk med att använda varningar i Adobe Analytics. Det finns dock viktiga skillnader.

Mer information finns i [Jämförelse av aviseringsfunktioner: Customer Journey Analytics och Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Anomalsökning efter aviseringar

>[!NOTE]
>
>Det går bara att använda aviseringar med avvikelseidentifiering (kallas även _Intelligent Alerts_) för organisationer som har ett Customer Journey Analytics Select-, Prime- eller Ultimate-paket.

Om en varning använder avvikelseidentifiering varierar utbildningsperioden beroende på den granularitet som valts för registreringen.

* Månatlig granularitet: 15 månader + samma intervall förra året
* Veckogranularitet: 15 veckor + samma intervall förra året
* Daglig kornighet: 35 dagar + samma intervall förra året
* Timgranularitet: 336 timmar

Mer information finns i [Statistiska tekniker som används vid avvikelseidentifiering](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Skapa aviseringar

Mer information om hur du skapar aviseringar i Customer Journey Analytics finns i [Skapa aviseringar](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Om du använder tidsstämplade data för att skapa varningar kan det leda till att varningar utlöses felaktigt. Adobe rekommenderar att du använder data som inte är tidsstämplade för varningar.

## Hantera aviseringar

Du kan hantera befintliga aviseringar i Varningshanteraren. Du kan utföra olika hanteringsåtgärder för varningar, som taggning, namnbyte, borttagning med mera.

Mer information om hur du hanterar befintliga aviseringar i Customer Journey Analytics finns i [Hantera aviseringar](/help/components/c-intelligent-alerts/alert-manager.md).
