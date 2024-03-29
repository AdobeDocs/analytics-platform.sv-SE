---
title: Customer Journey Analytics och datastyrning
description: Beskriver hur datastyrning fungerar i Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Adobe Customer Journey Analytics och datastyrning

I allmänhet ärvs alla datastyrningsrelaterade inställningar i Customer Journey Analytics från Adobe Experience Platform.

## Datastyrning

Integrationen mellan Adobe Customer Journey Analytics och [Adobe Experience Platform datastyrning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html) möjliggör märkning av känsliga uppgifter från Customer Journey Analytics och tillämpning av integritetspolicyer.

Sekretessetiketter och integritetspolicyer som har skapats för datauppsättningar som används av Experience Platform kan visas i arbetsflödet för datavyer i Customer Journey Analytics. Dessa etiketter stoppar eller varnar användare som skapar mätvärden och/eller dimensioner från känsliga fält.

När data exporteras från Customer Journey Analytics (via rapportering, export, API osv.) läggs dessutom varningar eller etiketter till för att meddela användarna att en rapport innehåller känslig information som behöver behandlas på ett visst sätt.

Tack vare den här integreringen kan ni hantera regelefterlevnaden enklare. Datahanteringen i organisationen kan ange regler som begränsar användningen. Det innebär att dina Customer Journey Analytics-användare kan använda data med större tillförsikt, eftersom de vet att de följer de regler som definieras av datahanteringen.

[Läs mer](/help/data-views/data-governance.md)

## GDPR

Customer Journey Analytics kommer inte att abonnera direkt på den centrala tjänsten enligt den allmänna dataskyddsförordningen (GDPR), utan i stället ärva alla datauppsättningsändringar som gjorts i Experience Platform. Vi förlitar oss på Platform Data Lake för att driva igenom förfrågningar om GDPR-borttagning och meddela oss när de har slutförts i pipeline. Vi lyssnar på Pipeline och synkroniserar alla ändringar i berörda grupper i Customer Journey Analytics för händelsedatamängder. Datauppsättningar för profiler och sökningar som påverkas av GDPR-borttagningsbegäranden importeras helt och hållet igen efter varje borttagningsbegäran. Vi kan garantera att begäranden om borttagning verkställs inom 7 dagar efter en raderingshändelse i Data Lake.

## CCPA

California Consumer Privacy Act (CCPA) förbättrar sekretessen och konsumentskyddet för personer bosatta i Kalifornien. Denna lag trädde i kraft den 1 januari 2020.
CCPA ger personer bosatta i Kalifornien nya integritetsrättigheter, t.ex. rätten att få tillgång till och radera sina personuppgifter, att få veta om deras personuppgifter har sålts eller lämnats ut (och till vem) samt att vägra att sälja deras personuppgifter.
I enlighet med CCPA stöder Privacy Servicen ansökningar om att avanmäla sig från försäljning av personuppgifter.
