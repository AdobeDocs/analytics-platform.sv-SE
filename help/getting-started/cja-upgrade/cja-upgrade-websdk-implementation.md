---
title: Förstå olika implementeringsalternativ för SDK på webben när du uppgraderar till Customer Journey Analytics
description: Läs om implementeringsalternativen för SDK på webben när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Förstå olika implementeringsalternativ för SDK på webben när du uppgraderar till Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript library (alloy.js)"
>abstract="Inkludera SDK Web Library (alloy.js) på alla sidor på webbplatsen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="SDK-taggtillägg"
>abstract="(Rekommenderas) Om du ännu inte använder taggar installerar du tagginläsaren på din plats. Om du redan använder taggar kan du lägga till tillägget Web SDK i taggegenskapen. Det här alternativet inkluderar implementeringar med hjälp av taggar i Adobe Experience Platform Data Collection och tagghanteringssystem från tredje part."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM-paket"
>abstract="Använd API:t för datainsamling för att skicka data direkt till en datastam. Både icke-autentiserade (klient-till-server) och autentiserade (server-till-server) typer stöds."

<!-- markdownlint-enable MD034 -->

Den rekommenderade processen att uppgradera från Adobe Analytics till Customer Journey Analytics är en ny implementering av Experience Platform Web SDK, vilket är den bästa datainsamlingsmetoden för Customer Journey Analytics.

Det finns tre sätt att använda Adobe Experience Platform Web SDK:

* [Webbtaggtillägg för SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): Adobe rekommenderar att du använder den här metoden. Installera en tagginläsare på webbplatsen och använd sedan användargränssnittet för Adobe Experience Platform Data Collection för att konfigurera implementeringen.

* [Webbbibliotek för SDK JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Referera till en CDN-värdbiblioteksfil eller använd din egen infrastruktur som värd för biblioteksfilen. Ring till biblioteket i koden på din webbplats.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): Installera Web SDK på din webbplats med NPM-pakethanteraren.

Mer information finns i [Översikt över Web SDK-installationen](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) i Experience Platform Web SDK Guide.



