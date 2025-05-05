---
title: Förstå funktioner som är unika för Customer Journey Analytics
description: Läs om funktioner som är unika för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---

# Förstå funktioner som är unika för Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Sammanfoga data från olika källor"
>abstract="(Rekommenderas) Sammanställ data från olika webb-, mobil- och offlineegenskaper för att skapa en samlad bild av kundens beteende. Denna möjlighet att kombinera analysdata från andra kanaler är det primära användningsområdet för Customer Journey Analytics."

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
>abstract="Adobe rekommenderar att man integrerar med Adobe Journey Optimizer för personalisering. Det är möjligt att integrera med Adobe Target, men det är en kortsiktig lösning."

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
>abstract="Adobe rekommenderar integrering med Adobe CDP i realtid för målgruppsbaserade användningsfall. Det är möjligt att integrera med Audience Manager, men det är en kortsiktig lösning."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

I följande lista visas endast de Customer Journey Analytics-funktioner som behöver övervägas under uppgraderingsprocessen. En omfattande lista som visar vilka Adobe Analytics-funktioner som stöds, stöds delvis eller inte stöds i Customer Journey Analytics finns i [Stöd för Customer Journey Analytics-funktioner](/help/getting-started/aa-vs-cja/cja-aa.md).

Ta en titt på vilka av följande Customer Journey Analytics-funktioner du vill använda när du uppgraderar till Customer Journey Analytics:

| Funktionen Customer Journey Analytics | Funktion |
|---------|----------|
| [Koppla webbdata med data från andra kanaler, till exempel callcenter-data](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics kombineras med Experience Platform förmåga att lagra alla typer av datarotor och datatyper. Med [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) kan data representeras och struktureras på ett enhetligt sätt, vara klara för kombination och utforskande. Adobe Analytics fokuserar främst på webb- och mobilanalysdata med vissa funktioner för att [importera data](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=sv-SE). |
| [Häfta träffar från andra datauppsättningar med en anpassad dimension](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/stitching/overview) | Med Customer Journey Analytics kan du [kombinera data](/help/connections/combined-dataset.md) från flera rapportsviter som om de vore en enda rapportserie i Adobe Analytics. |
| [Integrera med Adobe CDP i realtid](/help/components/audiences/audiences-overview.md) | Du kan [skapa och publicera målgrupper](/help/components/audiences/audiences-overview.md) som identifieras i Customer Journey Analytics till kundprofilen i realtid i Adobe Experience Platform för kundanpassning och personalisering. |
| [Integrera med Adobe Target (A4T)](/help/integrations/at.md) | Med Target Reporting i Customer Journey Analytics kan du [mäta och rapportera Adobe Target-aktiviteter](/help/integrations/at.md) direkt i Customer Journey Analytics. Adobe rekommenderar dock att man integrerar med Adobe Journey Optimizer för personalisering. |
| [Integrera med Adobe Journey Optimizer](/help/integrations/ajo.md) | Du kan konfigurera data som genererats av Journey Optimizer så att [utför avancerad analys i Customer Journey Analytics](/help/integrations/ajo.md). |
| [Integrera med Adobe Audience Manager](https://experienceleague.adobe.com/sv/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Du kan [dela Audience Manager-egenskaper och segment till Adobe Experience Platform](https://experienceleague.adobe.com/sv/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). Adobe rekommenderar dock att man integrerar med Adobe CDP i realtid för målgruppsbaserade användningsfall. |
