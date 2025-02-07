---
title: Content Analytics - översikt
description: En översikt över Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 501a9fbd7c8abd8a63348c2c8d11b88b31a0f6df
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# Content Analytics - översikt

<!-- 
This is a placeholder article for upcoming Content Analytics documentation. Currently used to set up contextual help entries for developer working on onboarding UI and workspace UI 
-->

>[!WARNING]
>
>Den här artikeln är ett preliminärt inofficiellt utkast till en kommande slutversion och ingår i Content Analytics-dokumentationen. Allt innehåll kan ändras och inga rättsliga skyldigheter kan härledas från den aktuella versionen av den här artikeln.
>

{#release-limited-testing}

Med Content Analytics kan marknadsförarna förstå hur innehåll påverkar de nyckeltal som ett företag har definierat. Förutom de traditionella mikronivåbaserade funktionerna för att testa delar av innehåll (till exempel A/B-tester) ger Content Analytics insikter om hur innehåll påverkar på makronivå. Ger kunderna bättre respons på en viss ton röst, en viss färgpall eller specifika teman?

I Content Analytics används en AI- och maskininlärningsbaserad **funktionstjänst** för att dela upp innehåll i komponenter och attribut. Genom att skapa en strukturerad metadataprofil för allt innehåll kan du analysera vilket innehåll och vilka attribut som detta innehåll ger affärsresultat.

Förutom att skapa den här strukturerade metadataprofilen innehåller Content Analytics en **identitetstjänst** som identifierar resurser och upplevelser med en enda identifierare. Identitetstjänsten förstår om en resurs har ändrat storlek, beskurits eller sparats i ett annat filformat. Tjänsten tilldelar alla varianter av den tillgången till samma identifierare. Därför gör identitetstjänsten att du kan sammanställa en tillgångs prestanda baserat på dess olika former och placeringar.

## Värde

Content Analytics ger ett ökat värde:

1. Innehåll **användning**: Med Content Analytics får du insikter om vilka resurser som tar emot visningar och var resurserna tar emot visningar. Dessa insikter hjälper dig att se om materialet används för lite eller inte alls i dina webbegenskaper.
1. Innehåll **engagemang**: Innehållsanalys kan ge engagemangsinsikter som den genomsnittliga klickfrekvensen för resurser med vissa attribut. Dessa insikter hjälper er att avgöra om specifika typer av upplevelser fortfarande är effektiva.
1. Innehåll **resor**: Om du kombinerar alla andra data som är tillgängliga i Experience Platform kan du dessutom få ytterligare insikter om dina innehållsresor. Till exempel om specifikt innehåll leder till konverteringar utöver engagemang. Och med den kunskapen kan du fastställa avkastningen på olika typer av innehåll.
1. Innehåll **personalisering**: Med Innehållsanalys kan ni agera utifrån era insikter och använda dessa insikter för att avgöra hur ni ska spendera pengar på innehåll. Ska jag till exempel skicka specifika typer av innehåll till specifika målgrupper? Vilket innehåll ger mig möjligheter till högpersonalisering?

## Terminologi

I Content Analytics används följande nyckeltermer:

![Assets och upplevelser](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Upplevelse**: En upplevelse är all text på en webbsida som kan återges med den URL som används av den ursprungliga användare som besöker den webbsidan. Varje upplevelse får en unik identifierare.
* **Resurs**: En resurs är en enskild och unik del av innehållet, som en bild. Varje resurs får också en unik identifierare.
* **Attribut**: Ett attribut är ett beskrivande metadataelement som är associerat med en upplevelse eller resurs. Exempel på attribut är: stil på fotografi, läsbarhet, övertalningsstrategi, objektfärg, bakgrundsfärg.

## Så här fungerar det

I Content Analytics används webbbildvisningsdata som samlats in i händelsedatamängder i Experience Platform. Dessa data kan samlas in via de olika metoder som är tillgängliga: Experience Platform Edge Network (Web SDK, Server API) eller Analytics-källkopplingen.

![Innehållsanalys - Så fungerar det](assets/how-it-works.png)


1. Identifieringsdelen av funktionstjänsten aktiveras när en ny ögonblicksbild av data hämtas från en händelsedatamängd som är aktiverad för Content Analytics.
1. Tjänsten för funktionsidentifiering avgör vilka data i ögonblicksbilden som är relevanta för innehållsanalys och granskar upplevelsen och resurserna i dessa webbilder.
1. Vid granskningen samlas specifika innehållsanalysdata in via en korrekt konfiguration av Experience Platform Web SDK och Experience Platform Edge Network. Och sedan skickas data till en dedikerad datauppsättning för innehållsanalys och relevanta uppslagsdatauppsättningar.
1. Tjänsten för funktionssammansättning och identitetstjänsten bearbetar granskade data.
1. Resultaten av dessa tjänster (komponenter, attribut och identiteter) används för att uppdatera relevanta data för innehållsanalys i Experience Platform.
1. Data från innehållsanalysen, tillsammans med beteendedata och andra uppslagsdatauppsättningar, kan sedan användas i en Customer Journey Analytics-konfiguration (Connection, Data view och Workspace). Denna konfiguration utgör grunden för de unika insikterna på makronivå om ditt innehåll.

>[!MORELIKETHIS]
>
>[Rapporter om innehållsanalys](#report/report.md)
>[Konfigurera innehållsanalys](config/configuration.md)
