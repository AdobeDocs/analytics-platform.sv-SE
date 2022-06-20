---
source-git-commit: de28f20583457e91aa5136c688a885045606b860
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 0%

---
# Virtuella rapportsviter, datavyer, AEP-sandlådor och Analytics Source Connector

Adobe erbjuder en mängd olika sätt att skapa virtuella rapportmiljöer och sandlådemiljöer. Det är användbart att förstå likheterna och skillnaderna mellan följande funktioner och hur dessa funktioner relaterar till [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en):

* Adobe Analytics virtuella rapportsviter
* CJA-datavyer
* AEP-sandlådor

## Adobe Analytics Virtual Report Suites (VRS)

Mer information finns i: [Översikt över virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en).

Ett VRS:

* Kan baseras på Adobe Analytics-segment.
* Kan tillämpas på både historiska och nya data på ett icke-förstörande sätt.
* Med det här alternativet kan du skapa en eller flera virtuella vyer ovanpå en Adobe Analytics-rapportserie som kan användas av olika affärsteam.
* Kan användas för att styra åtkomst till och strukturera olika typer av data för olika användare i Adobe Analytics.
* Tillval [rapporttidsbearbetning](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) för Adobe Analytics. I så fall kan ett VRS användas för att skapa en anpassad definition för&quot;besök&quot;.
* Används vid rapportkörning, ungefär som vid segmentutvärdering. Det här är _efter_ uppgifterna har samlats in och lagrats inom Adobe Analytics.
* Krävs för [Enhetsövergripande analys](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en) i Adobe Analytics.
* Har tillgång till samma antal variabler som ska användas som en vanlig Analytics Report Suite (250 eVars, 250 props, 1 000 händelser), även om VRS-kuration kan begränsa vilka variabler som exponeras för användarna.
* Stöder anpassade kalenderalternativ.

En virtuell rapportsvit är (gör inte):

* Gör det möjligt att kombinera rapportsviter.
* Finns i Adobe Analytics Data warehouse.
* Tillgängligt som källa för dataflöden till AEP via Analytics Source Connector. Endast fullständiga (icke-virtuella) rapportsviter är tillgängliga för användning med Analytics Source Connector.


## CJA-datavyer

Mer information finns i: [Översikt över datavyer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en).

En datavy:

* Kan baseras på CJA-filter.
* Kan tillämpas på både historiska och nya data på ett icke-förstörande sätt.
* Gör att du kan skapa en eller flera virtuella vyer ovanpå en CJA-anslutning som kan användas av olika affärsteam.
* Kan användas för att styra åtkomst till och strukturera olika typer av data för olika användare i CJA.
* Innehåller kraftfulla icke-förstörande alternativ för att omvandla och förbättra data som kommer in i CJA via en CJA-anslutning.
* Baseras på CJA:s funktioner för bearbetning under rapporttid.
* Tillåter användare att skapa en anpassad definition för &quot;session&quot;.
* Används vid rapportkörning, ungefär som vid filterutvärdering. Det här är _efter_ Källkopplingen (Adobe Analytics eller annan) har skrivit data till en datauppsättning i AEP-sjön. _efter_ data har importerats till CJA via en CJA-anslutning.
* Tillåter ett obegränsat antal variabler, även om kurering kan begränsa vilka variabler som exponeras för användare
* Tillåter anpassad namngivning av behållare för händelse, session och person.
* Stöder anpassade kalenderalternativ.

Datavyn innehåller inte följande:

* Tillhandahåll direkt ett sätt att kombinera rapportsviter eller andra datauppsättningar. I stället kombineras datauppsättningar med i en CJA-anslutning. De kombinerade data från CJA-anslutningen är tillgängliga för användning i alla datavyer som baseras på den anslutningen.

## AEP-sandlådor

Mer information finns i: [Översikt över sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en).

En AEP-sandlåda:

* Ger möjlighet att partitionera en enda AEP-instans i separata virtuella miljöer (dev, test, stage, production osv.) för att utveckla och utveckla applikationer för digitala upplevelser.
* Kan ses som en behållare som innehåller alla data och program för en viss miljö.

En AEP-sandlåda gör inte:

* Tillhandahåll liknande funktioner som virtuella rapportsviter, CJA-anslutningar eller datavyer.
* Kombinera enbart rapportsviter med eller utan andra datauppsättningar. Datauppsättningarna i en sandlåda kan emellertid kombineras i en CJA-anslutning.

Ytterligare:

* Data från olika sandlådor kan inte kombineras i CJA.
* Analyskällans koppling skickar rapportsvitsdata _till_ en specifik sandlåda. Varje rapportsvit kan konfigureras som en källa för en enskild sandlåda. Se [Dokumentation för Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) för mer information.