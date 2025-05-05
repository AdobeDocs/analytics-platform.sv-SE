---
title: Virtuella rapportsviter, datavyer, Adobe Experience Platform-sandlådor och källkopplingen för Analytics
description: Läs mer om virtuella rapportmiljöer och sandlådemiljöer.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: Basics
role: User
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# Virtuella rapportsviter, datavyer, Adobe Experience Platform-sandlådor och källkopplingen för Analytics

Adobe har ett antal sätt att skapa virtuella rapportmiljöer och sandlådemiljöer. Det är praktiskt att förstå likheterna och skillnaderna mellan följande funktioner och hur dessa funktioner relaterar till [Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE):

* Adobe Analytics virtuella rapportsviter
* Customer Journey Analytics datavyer
* Adobe Experience Platform sandlådor

## Adobe Analytics virtuella rapportsviter

Mer information finns i: [Översikt över virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=sv-SE).

En virtuell rapportsvit:

* Kan baseras på Adobe Analytics-segment.
* Kan tillämpas på både historiska och nya data på ett icke-förstörande sätt.
* Med det här alternativet kan du skapa en eller flera virtuella vyer ovanpå en Adobe Analytics-rapportserie som kan användas av olika affärsteam.
* Kan användas för att styra åtkomst till och strukturera olika typer av data för olika användare i Adobe Analytics.
* Tillhandahåller tillvalsfunktioner för [rapporttidsbearbetning](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=sv-SE) för Adobe Analytics. I det här fallet kan en virtuell rapportserie användas för att skapa en anpassad definition för&quot;besök&quot;.
* Används vid rapportkörning, ungefär som vid segmentutvärdering. Detta är _efter_ att data har samlats in och lagrats i Adobe Analytics.
* Krävs för [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=sv-SE) i Adobe Analytics.
* Har tillgång till samma antal variabler som kan användas som en vanlig Analytics Report Suite (250 eVars, 250 props, 1 000 händelser), även om kurationen i den virtuella rapportsviten kan begränsa vilka variabler som exponeras för användarna.
* Stöder anpassade kalenderalternativ.

En virtuell rapportsvit är inte:

* Ett sätt att kombinera rapportsviter.
* Finns i Adobe Analytics Data Warehouse.
* Tillgängligt som källa för dataflöden till Adobe Experience Platform via Analytics-källkopplingen. Endast fullständiga (icke-virtuella) rapportsviter är tillgängliga för användning med Analytics-källkopplingen.


## Customer Journey Analytics datavyer

Mer information finns i: [Översikt över datavyer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=sv-SE).

En datavy:

* Kan baseras på Customer Journey Analytics-segment.
* Kan tillämpas på både historiska och nya data på ett icke-förstörande sätt.
* Gör att du kan skapa en eller flera virtuella vyer ovanpå en Customer Journey Analytics-anslutning, som kan användas av olika affärsteam.
* Kan användas för att styra åtkomst till och strukturera olika typer av data för olika användare i Customer Journey Analytics.
* Innehåller kraftfulla icke-förstörande alternativ för att omvandla och förbättra data som kommer in i Customer Journey Analytics via en Customer Journey Analytics-anslutning.
* Baseras på rapporttidsbearbetningen i Customer Journey Analytics.
* Tillåter användare att skapa en anpassad definition för &quot;session&quot;.
* Används vid rapportkörning, ungefär som vid en segmentutvärdering. Detta är _efter_ att Source Connector (Adobe Analytics eller någon annan) har skrivit data till en datauppsättning i Adobe Experience Platform-sjön och _efter_ att data har importerats till Customer Journey Analytics via en Customer Journey Analytics-anslutning.
* Tillåter ett obegränsat antal variabler, även om kurering kan begränsa vilka variabler som exponeras för användare
* Tillåter anpassad namngivning av behållare för händelse, session och person.
* Stöder anpassade kalenderalternativ.

Datavyn innehåller inte följande:

* Tillhandahåll direkt ett sätt att kombinera rapportsviter eller andra datauppsättningar. I stället kombineras datauppsättningar med i en Customer Journey Analytics-anslutning. De kombinerade data från Customer Journey Analytics-anslutningen är tillgängliga för användning i alla datavyer som baseras på den anslutningen.

## Adobe Experience Platform sandlådor

Mer information finns i: [Översikt över sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=sv).

En Adobe Experience Platform-sandlåda:

* Ger möjlighet att partitionera en enda Adobe Experience Platform-instans i separata virtuella miljöer (dev, test, stage, production osv.) för att utveckla och utveckla program för digitala upplevelser.
* Kan ses som en behållare som innehåller alla data och program för en viss miljö.

En Adobe Experience Platform-sandlåda gör inte följande:

* Tillhandahåll liknande funktioner som virtuella rapportsviter, Customer Journey Analytics-anslutningar eller datavyer.
* Kombinera enbart rapportsviter med eller utan andra datauppsättningar. Datauppsättningarna i en sandlåda kan dock kombineras i en Customer Journey Analytics-anslutning.

Observera att:

* Data från olika sandlådor kan inte kombineras i Customer Journey Analytics.
* Analytics Source Connector skickar rapportsvitsdata _till_ för en specifik sandlåda. Varje rapportsvit kan konfigureras som en källa för en enskild sandlåda. Mer information finns i [dokumentationen för Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE).
