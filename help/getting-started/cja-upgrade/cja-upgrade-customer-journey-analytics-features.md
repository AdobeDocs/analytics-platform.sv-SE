---
title: Förstå funktioner som är unika för Customer Journey Analytics
description: Läs om funktioner som är unika för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: f4440148d26e81938d029d4a077cd787c868f1be
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Förstå funktioner som är unika för Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Sammanfoga data från olika källor"
>abstract="(Rekommenderas) Möjligheten att kombinera analysdata från andra kanaler är det primära användningsområdet för Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Häfta träffar från flera datauppsättningar"
>abstract="Om någon av dina datauppsättningar inte delar någon primär identifierare (t.ex. ett Experience Cloud-id), kan du fortfarande sammanfoga dessa data med en annan dimension, t.ex. inloggningsanvändarnamn eller e-postadress."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i [checklistan för uppgradering av Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

I följande lista visas endast de Customer Journey Analytics-funktioner som behöver övervägas under uppgraderingsprocessen. En omfattande lista som visar vilka Adobe Analytics-funktioner som stöds, stöds delvis eller inte stöds i Customer Journey Analytics finns i [Stöd för Customer Journey Analytics-funktioner](/help/getting-started/aa-vs-cja/cja-aa.md).

Ta en titt på vilka av följande Customer Journey Analytics-funktioner du vill använda när du uppgraderar till Customer Journey Analytics:

| Funktionen Customer Journey Analytics | Funktion |
|---------|----------|
| [Koppla webbdata med data från andra kanaler, till exempel callcenter-data](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics kombineras med Experience Platform förmåga att lagra alla typer av datarotor och datatyper. Med [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. Adobe Analytics fokuserar främst på webb- och mobilanalysdata med vissa funktioner för att [importera data](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| [Häfta träffar från andra datauppsättningar med en anpassad dimension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Med Customer Journey Analytics kan du [kombinera data](/help/connections/combined-dataset.md) från flera rapportsviter som om de vore en enda rapportserie i Adobe Analytics. |
| Integrera med Adobe CDP i realtid |  |
| [Integrera med Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) |  |


