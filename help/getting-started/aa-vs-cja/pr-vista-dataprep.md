---
title: Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep för Analytics-källkopplingen
description: Läs mer om dataomvandling med bearbetningsregler och VISTA jämfört med Data Prep
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
role: User
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep

Adobe Analytics [bearbetningsregler och VISTA-regler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=sv-SE) är ett sätt att omvandla och ändra data som skickas till Adobe Analytics [datainsamling](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=sv-SE). Dessa omvandlingar sker som en del av databearbetningen i Adobe innan data lagras för rapportering och analys i Adobe Analytics.

[Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=sv-SE) är ett verktyg som gör att du kan använda radbaserade mappningar och omformningar på data som har importerats till [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=sv-SE). Dessa uppgifter görs sedan tillgängliga för Experience Platform, inklusive Customer Journey Analytics och andra. Dataprep är integrerat med många av plattformens [källanslutningar](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=sv-SE) och med [Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=sv-SE). Den här kopplingen är ett sätt att importera rapportsvitsdata från Adobe Analytics till Platform.

## Ytterligare omformning med Data Prep {#data-prep}

Data som samlas in av och lagras i Adobe Analytics kan omformas antingen med bearbetningsregler eller VISTA-regler eller både och. Men rapportsviter som sedan vidarebefordras till plattformen via Analytics-källkopplingen kan omvandlas ytterligare en gång med Data Prep. Detta kan vara önskvärt av flera skäl:

* **Åtgärdar schemaskillnader mellan rapportsviter för användning i Customer Journey Analytics och/eller RTCDP**. En rapportsvit A definierar till exempel `eVar1` som &quot;Sökord&quot; och rapportsvit B definierar `eVar2` som &quot;Sökord&quot;. Du kan använda dataprep för att mappa de två olika eVars-elementen till ett gemensamt fält som innehåller data från båda eVars-elementen. Detta gör det möjligt att [kombinera rapportsviter med olika scheman](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=sv-SE) i en [Customer Journey Analytics-anslutning](/help/connections/overview.md) eller för användning i [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=sv-SE).
* **Mappar `eVars` fält till semantiskt meningsfulla namn**. `eVars` och `props` som kommer via Analytics-källkopplingen mappas till fält som _\_experience.analytics.customDimensions.eVars.eVar1_. Dataprep kan användas för att mappa `eVar`- och `prop`-fält till nya fält som har mer meningsfulla namn för användarna eller som matchar namn som kommer från andra datakällor. (Detta kan även uppnås på andra sätt, till exempel genom att byta namn på fälten i en [Customer Journey Analytics datavy](/help/data-views/create-dataview.md).)
* **Omformar vanligtvis data**. Datapersonen har hundratals mappningsfunktioner som kan användas för att beräkna och beräkna nya fält baserat på data som kommer via Analytics-källkopplingen. Du kan dela upp avgränsade fält i separata fält. Du kan kombinera fält. Du kan ändra strängar. Du kan extrahera information från ett fält baserat på reguljära uttryck och mycket annat.

## Förberedelse och klassificering av data {#classifications}

Data Prep har korsat med [klassificeringar](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=sv-SE) i vissa situationer.

I ett avgränsat fält kan du till exempel använda Data Prep för att dela upp fältet i flera enskilda fält utan att använda klassificeringar. I allmänhet är klassificeringar ett sätt att lägga till metadata i ett fält genom att överföra en uppslagsfil som tillhandahålls utanför strömmen med inkommande Analytics-händelser.

Du kan till exempel överföra en klassificeringsfil som grupperar SKU:er till&quot;size&quot;,&quot;brand&quot;,&quot;color&quot; osv. En annan skillnad mellan klassificeringar och Data Prep är att klassificeringar gäller för data _både historiskt och framåt_. Dataplaceringsmappningar tillämpas å andra sidan _framåt_ på data från den tidpunkt då mappningen skapas.
