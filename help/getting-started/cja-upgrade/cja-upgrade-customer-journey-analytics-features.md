---
title: Förstå funktioner som är unika för Customer Journey Analytics
description: Läs om funktioner som är unika för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '465'
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

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Kontakta Adobe kundtjänst om du vill generera en sammansatt datauppsättning"
>abstract="Om du har ett fält som innehåller en identifierare som finns i flera datauppsättningar men inte är den primära identifieraren, kan du använda det för att generera en ny datauppsättning med en konsekvent identifierare."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Integrera med CDP i realtid"
>abstract="Kombinera profildata från flera källor för att generera målgrupper och segment baserat på användaregenskaper."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Integrera tillfälligt med Adobe Target"
>abstract="Adobe rekommenderar att man integrerar med Adobe Journey Optimizer för personalisering. Det är möjligt att integrera med Adobe Target, men det är en tillfällig lösning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Integrera med Journey Optimizer"
>abstract="Leverera sammankopplade, kontextuella och personaliserade upplevelser till kunderna."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Integrera tillfälligt med Adobe Audience Manager"
>abstract="Adobe rekommenderar integrering med Adobe CDP i realtid för målgruppsbaserade användningsfall. Det är möjligt att integrera med Audience Manager, men det är en tillfällig lösning."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

I följande lista visas endast de Customer Journey Analytics-funktioner som behöver övervägas under uppgraderingsprocessen. En omfattande lista som visar vilka Adobe Analytics-funktioner som stöds, stöds delvis eller inte stöds i Customer Journey Analytics finns i [Stöd för Customer Journey Analytics-funktioner](/help/getting-started/aa-vs-cja/cja-aa.md).

Ta en titt på vilka av följande Customer Journey Analytics-funktioner du vill använda när du uppgraderar till Customer Journey Analytics:

| Funktionen Customer Journey Analytics | Funktion |
|---------|----------|
| [Koppla webbdata med data från andra kanaler, till exempel callcenter-data](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics kombineras med Experience Platform förmåga att lagra alla typer av datarotor och datatyper. Med [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. Adobe Analytics fokuserar främst på webb- och mobilanalysdata med vissa funktioner för att [importera data](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| [Häfta träffar från andra datauppsättningar med en anpassad dimension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Med Customer Journey Analytics kan du [kombinera data](/help/connections/combined-dataset.md) från flera rapportsviter som om de vore en enda rapportserie i Adobe Analytics. |
| [Integrera med Adobe CDP i realtid](/help/components/audiences/audiences-overview.md) | Du kan [skapa och publicera målgrupper](/help/components/audiences/audiences-overview.md) som identifieras i Customer Journey Analytics till kundprofilen i realtid i Adobe Experience Platform för kundanpassning och personalisering. |
| [Integrera tillfälligt med Adobe Target (A4T)](/help/integrations/at.md) | Med Target Reporting i Customer Journey Analytics kan du [mäta och rapportera Adobe Target-aktiviteter](/help/integrations/at.md) direkt i Customer Journey Analytics. |
| [Integrera med Adobe Journey Optimizer](/help/integrations/ajo.md) | Du kan konfigurera data som genererats av Journey Optimizer så att [utför avancerad analys i Customer Journey Analytics](/help/integrations/ajo.md). |
| Integrera tillfälligt med Adobe Audience Manager |  |
