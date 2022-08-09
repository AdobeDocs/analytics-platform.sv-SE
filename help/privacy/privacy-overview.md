---
title: Customer Journey Analytics och datastyrning
description: Beskriver hur datastyrning fungerar i Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 61850e8a1da80a115bf850c64358a512770f852e
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# Customer Journey Analytics och datastyrning

I allmänhet ärvs alla datastyrningsrelaterade inställningar i Customer Journey Analytics från Adobe Experience Platform.

## Datastyrning

CJA stöder etiketter och policyer för datastyrning som har konfigurerats i Adobe Experience Platform. Mer information finns i CJA-stöd för Adobe Experience Platform Data Governance.

## GDPR

Customer Journey Analytics kommer inte att abonnera direkt på den centrala tjänsten enligt den allmänna dataskyddsförordningen (GDPR), utan i stället ärva alla datauppsättningsändringar som gjorts i Experience Platform. Vi förlitar oss på Platform Data Lake för att driva igenom förfrågningar om GDPR-borttagning och meddela oss när de har slutförts i pipeline. Vi lyssnar på Pipeline och synkroniserar alla ändringar i berörda grupper i Customer Journey Analytics för händelsedatamängder. Datauppsättningar för profiler och sökningar som påverkas av GDPR-borttagningsbegäranden importeras helt och hållet igen efter varje borttagningsbegäran. Vi kan garantera att begäranden om borttagning verkställs inom 7 dagar efter en raderingshändelse i Data Lake.

## CCPA

California Consumer Privacy Act (CCPA) förbättrar sekretessen och konsumentskyddet för personer bosatta i Kalifornien. Denna lag träder i kraft den 1 januari 2020.
CCPA ger personer bosatta i Kalifornien nya integritetsrättigheter, t.ex. rätten att få tillgång till och radera sina personuppgifter, att få veta om deras personuppgifter har sålts eller lämnats ut (och till vem) samt att vägra att sälja deras personuppgifter.
I väntan på CCPA kommer Privacy Servicen att stödja ansökningar om att avanmäla sig från försäljning av personuppgifter.
