---
description: Det nya systemet för intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet.
title: Översikt över intelligenta aviseringar
feature: Workspace Basics
role: User, Admin
source-git-commit: 8017754adfde8a7d6ecea6d17138368d5430c1a6
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Översikt över intelligenta aviseringar

>[!NOTE]
>
>Intelligenta aviseringar är tillgängliga för alla kunder. Om du vill använda avvikelseidentifiering i intelligenta aviseringar måste du ha Customer Journey Analytics Select, Prime eller Ultimate.

Med intelligenta aviseringar (eller bara &quot;aviseringar&quot;) i Customer Journey Analytics kan du få meddelanden när onormala händelser inträffar i dina data.

Du kan ange att aviseringar ska utlösas baserat på avvikelsetrösklar, ändrade procentsatser eller specifika datapunkter. Varningar innehåller detaljerade kontroller som integreras med [avvikelseidentifiering](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) och aktiveras när du behöver dem som mest.

Med intelligenta aviseringar kan du:

* Skapa aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %, % förändring i %, över/under)
* Förhandsgranska hur ofta en varning utlöses
* Skicka aviseringar via e-post eller SMS med länkar till autogenererade Analysis Workspace-projekt
* Skapa&quot;staplade&quot; aviseringar som fångar in flera mätvärden i en enda avisering

I följande videofilm visas en grundläggande översikt över aviseringar: [Intelligenta aviseringar](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Förstå hur varningar skiljer sig mellan Adobe Analytics och Customer Journey Analytics

Processen att använda intelligenta aviseringar i Customer Journey Analytics är nästan identisk med att använda intelligenta aviseringar i Adobe Analytics. Det finns dock viktiga skillnader.

Mer information finns i [Funktionsjämförelse för intelligenta aviseringar: Customer Journey Analytics och Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Anomalsökning efter aviseringar

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
>Om du använder tidsstämplade data för att skapa varningar kan det leda till att varningar utlöses felaktigt. Adobe rekommenderar att man använder data som inte är tidsstämplade för intelligenta aviseringar.

## Hantera aviseringar

Du kan hantera befintliga aviseringar i Varningshanteraren. Du kan utföra olika hanteringsåtgärder för varningar, som taggning, namnbyte, borttagning med mera.

Mer information om hur du hanterar befintliga aviseringar i Customer Journey Analytics finns i [Hantera aviseringar](/help/components/c-intelligent-alerts/alert-manager.md).

