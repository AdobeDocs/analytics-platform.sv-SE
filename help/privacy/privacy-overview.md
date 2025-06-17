---
title: Customer Journey Analytics och datastyrning
description: Beskriver hur datastyrning fungerar i Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 40706e3118cbaf7582d8625d307358b16f1836ac
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Adobe Customer Journey Analytics och datastyrning

I allmänhet ärvs alla datastyrningsrelaterade inställningar i Customer Journey Analytics från Adobe Experience Platform.

## Dataförvaltning

Integrationen mellan Adobe Customer Journey Analytics och [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html) gör det möjligt att märka känsliga Customer Journey Analytics-data och tillämpa sekretesspolicyer.

Sekretessetiketter och integritetspolicyer som har skapats för datauppsättningar som används av Experience Platform kan visas i arbetsflödet för datavyer i Customer Journey Analytics. Dessa etiketter stoppar eller varnar användare som skapar mätvärden och/eller dimensioner från känsliga fält.

När data exporteras från Customer Journey Analytics (via rapportering, export, API osv.) läggs dessutom varningar eller etiketter till för att meddela användarna att en rapport innehåller känslig information som behöver behandlas på ett visst sätt.

Tack vare den här integreringen kan ni hantera regelefterlevnaden enklare. Datahanteringen i organisationen kan ange regler som begränsar användningen. Detta innebär att era Customer Journey Analytics-användare kan använda data med större tillförsikt, eftersom de vet att de följer de regler som definieras av datasegmenter.

[Läs mer](/help/data-views/data-governance.md)

## Sekretessförfrågningar

Adobe hanterar förfrågningar om sekretess i enlighet med gällande lokal och internationell lagstiftning.

Eftersom Customer Journey Analytics använder data som är tillgängliga i Adobe Experience Platform, erbjuder Adobe [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) för att skicka förfrågningar om dataåtkomst och borttagning. Förfrågningarna gäller både den ursprungliga och den inmatade datauppsättningen.

## GDPR

Customer Journey Analytics kommer inte att abonnera direkt på den centrala tjänsten i den allmänna dataskyddsförordningen (GDPR), utan i stället ärva alla datauppsättningsändringar som gjorts i Experience Platform. Customer Journey Analytics är beroende av Platform Data Lake för att driva igenom GDPR-raderingsbegäranden och meddela Customer Journey Analytics när förfrågningarna är klara. Alla ändringar av berörda grupper i Customer Journey Analytics för händelsedatamängder synkroniseras med plattformsdata. Datauppsättningar för profiler och sökningar som påverkas av GDPR-borttagningsbegäranden återimporteras helt efter varje borttagningsbegäran. Borttagningsbegäranden slutförs vanligtvis inom 7 dagar efter en raderingshändelse i Data Lake.

## CCPA

California Consumer Privacy Act (CCPA) förbättrar sekretessen och konsumentskyddet för personer bosatta i Kalifornien. Denna lag trädde i kraft den 1 januari 2020.
CCPA ger personer bosatta i Kalifornien nya integritetsrättigheter, t.ex. rätten att få tillgång till och radera sina personuppgifter, att få veta om deras personuppgifter har sålts eller lämnats ut (och till vem) samt att vägra att sälja deras personuppgifter.
I enlighet med CCPA stöder Privacy Service ansökningar om att avanmäla sig från försäljning av personuppgifter.

>[!MORELIKETHIS]
>
>* [Blogg: Så här behåller du effektiv styrning i Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4)
