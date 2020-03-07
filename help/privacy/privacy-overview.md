---
title: Sekretessöversikt för Customer Journey Analytics
description: Beskriver hur sekretessinställningarna fungerar i kundreseanalysen.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Sekretessöversikt för Customer Journey Analytics

I allmänhet ärvs alla sekretessrelaterade inställningar i kundreseanalysen från Adobe Experience Platform.

## GDPR

Customer Journey Analytics kommer inte att prenumerera direkt på den centrala tjänsten i den allmänna dataskyddsförordningen (GDPR), utan ärver i stället alla datauppsättningsändringar som gjorts i Experience Platform. Vi förlitar oss på Platform Data Lake för att driva igenom förfrågningar om GDPR-borttagning och meddela oss när de har slutförts i pipeline. Vi lyssnar på Pipeline och synkroniserar alla ändringar av berörda grupper i kundreseanalysen för att se händelsedatamängder. Datauppsättningar för profiler och sökningar som påverkas av GDPR-borttagningsbegäranden importeras helt och hållet igen efter varje borttagningsbegäran. Vi kan garantera att begäranden om borttagning verkställs inom 7 dagar efter en raderingshändelse i Data Lake.

## CCPA

California Consumer Privacy Act (CCPA) förbättrar sekretessen och konsumentskyddet för personer bosatta i Kalifornien. Denna lag träder i kraft den 1 januari 2020.
CCPA ger personer bosatta i Kalifornien nya integritetsrättigheter, t.ex. rätten att få tillgång till och radera sina personuppgifter, att få veta om deras personuppgifter har sålts eller lämnats ut (och till vem) samt att vägra att sälja deras personuppgifter.
I väntan på CCPA-avtalet kommer integritetstjänsten att stödja ansökningar om att avanmäla sig från försäljning av personuppgifter.
