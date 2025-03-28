---
title: Content Analytics - översikt
description: En översikt över Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: bb9b9850368796fe6cf2c4945ff3ef93b881b363
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# Content Analytics - översikt

{{release-limited-testing}}

Med Content Analytics kan marknadsförarna förstå hur innehåll påverkar de nyckeltal som ett företag har definierat. Förutom beteendedata samlar Content Analytics in data om hur innehåll konsumeras och hur innehåll påverkar. Ger kunderna bättre respons på en viss ton röst, en viss färgpalett eller specifika teman? Denna information, tillsammans med specifikt utformade arbetsflöden och mallar för rapportering, kan hjälpa er att utföra ännu bättre analyser och få djupare insikter om kundresedata i Customer Journey Analytics.

I Content Analytics används en AI- och maskininlärningsbaserad **funktionstjänst** för att dela upp innehåll i komponenter och attribut. Genom att skapa en strukturerad metadataprofil för allt innehåll kan du analysera vilket innehåll och vilka attribut som detta innehåll ger affärsresultat.

Förutom att skapa den här strukturerade metadataprofilen innehåller Content Analytics en **identitetstjänst** som identifierar resurser och upplevelser med en enda identifierare. Identitetstjänsten känner igen när exakt samma resurs visas på mer än ett ställe. När det inträffar behandlas förekomsterna av den här resursen som samma resurs, vilket ger en mer helhetsbild av innehållets användning och förbrukning.

## Värde

Content Analytics ger ett ökat värde:

1. Innehåll **användning**: Med Content Analytics får du insikter om vilka resurser som tar emot visningar och var resurserna tar emot visningar. Dessa insikter hjälper dig att se om materialet används för lite eller inte alls i dina webbegenskaper.
1. Innehåll **engagemang**: Innehållsanalys kan ge engagemangsinsikter som den genomsnittliga klickfrekvensen för resurser med vissa attribut. Dessa insikter hjälper er att avgöra om specifika typer av upplevelser fortfarande är effektiva.
1. Innehåll **resor**: Om du kombinerar alla andra data som är tillgängliga i Experience Platform kan du dessutom få ytterligare insikter om dina innehållsresor. Till exempel om specifikt innehåll leder till konverteringar utöver engagemang. Och med den kunskapen kan du fastställa avkastningen på olika typer av innehåll.
1. Innehåll **personalisering**: Med Innehållsanalys kan ni agera utifrån era insikter och använda dessa insikter för att avgöra hur ni ska spendera pengar på innehåll. Ska jag till exempel skicka specifika typer av innehåll till specifika målgrupper? Vilket innehåll ger mig möjligheter till högpersonalisering?

## Terminologi

I Content Analytics används följande nyckeltermer:

![Assets och upplevelser](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Upplevelse**: En upplevelse är all text på en webbsida som kan återges med den URL som används av den ursprungliga användaren som besökte webbsidan. Varje upplevelse får en unik identifierare. Ändringar på sidan som leder till ändringar i HTML på sidan ger en ny upplevelse.
* **Resurs**: En resurs är en enskild och unik del av innehållet, som en bild. Varje resurs får också en unik identifierare och ett perceptuellt ID. Ett perceptuellt ID är en identifierare som delas med resurser som är visuellt identiska. Perceptuella ID:n hjälper till att ta bort dubbletter av resurser som kan ha en annan resurs-URL och därmed ett annat resurs-ID, men som är praktiskt taget identiska.
* **Attribut**: Ett attribut är ett beskrivande metadataelement som är associerat med en upplevelse eller resurs. Exempel på attribut är: stil på fotografi, läsbarhet, övertalningsstrategi, objektfärg, bakgrundsfärg.

## Så här fungerar det

I Content Analytics används webbbildvisningsdata som samlats in i händelsedatamängder i Experience Platform. Dessa data kan samlas in via de olika metoder som är tillgängliga: Experience Platform Edge Network (Web SDK, Server API) eller Analytics-källkopplingen.

![Innehållsanalys - Så fungerar det](assets/aca-overview.gif)


1. När en användare besöker en webbplats, [konfigurerad för Content Analytics](config/configuration.md), registrerar Experience Platform Web SDK visningar och interaktioner med innehåll.
1. Identitet- och funktionstjänsten bearbetar dessa interaktioner. Den processen består av en crawler som granskar de offentliga versionerna av de konfigurerade URL:erna som definierar interaktionen. För alla dessa crawlade URL:er identifierar identitetstjänsten unikt upplevelserna och resurserna. Och funktionstjänsten använder AI/ML-tjänster för att identifiera upplevelser och metadata och attribut för resurser.
1. Resultaten av dessa tjänster ([komponenter, attribut och identiteter](/help/content-analytics/report/components.md)) används för att uppdatera relevanta data för innehållsanalys i Experience Platform.
1. Data för innehållsanalys, tillsammans med beteendedata och andra sökdata, kan användas i en Customer Journey Analytics-konfiguration ([Anslutning](/help/connections/overview.md), [Datavy](/help/data-views/data-views.md) och [Workspace](/help/analysis-workspace/home.md)). Denna inställning ger grunden till de unika insikterna på makronivå om ditt innehåll. <br/>Du kan snabbt komma igång med Content Analytics-rapporter och -analyser med hjälp av mallen [Content Analytics](/help/content-analytics/report/report.md#template).

>[!NOTE]
>
>Content Analytics utnyttjar AI/ML-tjänster som kan ge felaktiga eller vilseledande resultat. Använd därför ditt omdöme för att granska och validera AI/ML-genererade utdata.
>
>Du kan använda fliken **[!UICONTROL Feedback]**, som är tillgänglig från ![ InfoOutline](/help/assets/icons/InfoOutline.svg) i huvudgränssnittet, för att ge feedback om AI/ML-genererade utdata.
>

>[!NOTE]
>
>Om du har licensierat tillägget Sekretess och säkerhetssköld ska du vara medveten om att (alla data som genereras av) upplevelser och resurser, som är föremål för Content Analytics, inte omfattas av DULE-märkning eller Kundhanterade nycklar.
>


>[!MORELIKETHIS]
>
>[Rapporter om innehållsanalys](report/report.md)
>[Konfigurera innehållsanalys](config/configuration.md)
>