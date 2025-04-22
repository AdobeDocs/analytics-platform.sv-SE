---
description: Med varningar får du detaljkontroll över meddelanden och integrering med avvikelseidentifiering.
title: Översikt över aviseringar
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Översikt över aviseringar

Med varningar i Customer Journey Analytics kan du meddelas baserat på ändrade procentsatser eller specifika datapunkter.

Beroende på ditt Customer Journey Analytics-paket kan du även använda varningar som utlöses baserat på avvikelsetrösklar. Dessa aviseringar (kallas även&quot;Intelligent Alerts&quot;) ger detaljerade kontroller som kan integreras med [avvikelseidentifiering](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) och aktiveras när du behöver dem som mest.

Med varningar kan du:

* Förhandsgranska hur ofta en varning utlöses
* Skicka aviseringar via e-post eller SMS med länkar till autogenererade Analysis Workspace-projekt
* Skapa&quot;staplade&quot; aviseringar som fångar in flera mätvärden i en enda avisering
* Bygg aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %, % förändring, över/under) (endast tillgängligt för Customer Journey Analytics-kunder med något av paketen Select, Prime eller Ultimate)

I följande videofilm visas en grundläggande översikt över aviseringar: [Varningar](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

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
