---
title: Översikt över sekretesspolicyn för kundresursanalys
description: Beskriver hur sekretessinställningarna fungerar i kundresekontrollen.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---


# Översikt över sekretesspolicyn för kundresursanalys

I allmänhet ärvs alla sekretessrelaterade inställningar i Customer Journey Analytics från Adobe Experience Platform.

## GDPR

Customer Journey Analytics prenumererar inte direkt på GDPR-centraltjänsten (General Data Protection Regulation) och ärver i stället alla datauppsättningsändringar som gjorts i Experience Platform. Vi är beroende av Platform Data Lake för att verkställa GDPR-begäranden om borttagning och meddela oss när de har slutförts i pipeline. Vi lyssnar på Pipeline och synkroniserar alla ändringar i de berörda batcharna i kundens Journey Analytics för händelsedatamängder. Profil- och uppslagsdatauppsättningar som påverkas av begäranden om GDPR-borttagning kommer att tas över helt efter varje begäran om borttagning. Vi kan garantera att begäran om borttagning utförs inom sju dagar efter en borttagningshändelse i Data Lake.

## CCPA

Kalifornien Consumer Privacy Act (CCPA) förbättrar integritetsskyddet och konsumentskyddet för invånare i Kalifornien, Förenta staterna. Denna lag ska träda i kraft den 1 januari 2020.
CCPA ger personer bosatta i Kalifornien nya rättigheter till skydd av personuppgifter, såsom rätten att få tillgång till och radera sina personuppgifter, att få veta om deras personuppgifter säljs eller lämnas ut (och till vem) och att vägra att sälja deras personuppgifter.
I väntan på CCPA kommer Privacy Service att stödja begäran om undantag från försäljning av personuppgifter.
