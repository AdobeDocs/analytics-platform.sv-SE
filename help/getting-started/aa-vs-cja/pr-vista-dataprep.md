---
title: Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep för Analytics Source Connector
description: Läs mer om dataomvandling med bearbetningsregler och VISTA jämfört med Data Prep
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep

Adobe Analytics [bearbetningsregler och VISTA-regler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) erbjuder ett sätt att omvandla och hantera data som skickas till Adobe Analytics [datainsamling](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). Dessa omvandlingar sker som en del av databearbetningen i Adobe innan data lagras för rapportering och analys i Adobe Analytics.

[Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) är ett verktyg som gör att du kan använda radbaserade mappningar och omformningar på data som hämtas in till [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). Informationen görs sedan tillgänglig för Experience Platform, inklusive CJA och andra. Dataförberedelsen är integrerad med många av plattformarna [källkopplingar](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en), liksom med [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en). Den här kopplingen är ett sätt att importera rapportsvitsdata från Adobe Analytics till Platform.

## Ytterligare omformning med Data Prep {#data-prep}

Data som samlas in av och lagras i Adobe Analytics kan omformas antingen med bearbetningsregler eller VISTA-regler eller både och. Men rapportsviter som sedan vidarebefordras till plattformen via Analytics Source Connector kan omvandlas ytterligare en gång med Data Prep. Detta kan vara önskvärt av flera skäl:

* **Lösa schemaskillnader mellan rapportsviter för användning i CJA och/eller RTCDP**. Låt oss till exempel säga att rapportsviten A definierar `eVar1` som&quot;Sökord&quot; och rapportsvit B definierar `eVar2` som sökterm. Du kan använda dataprep för att mappa de två olika eVars-elementen till ett gemensamt fält som innehåller data från båda eVars-elementen. Detta gör det möjligt att [kombinera rapportsviter med olika scheman](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) i en [CJA-anslutning](/help/connections/overview.md) eller för användning i [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=en).
* **Mappning `eVars` fält till semantiskt meningsfulla namn**. `eVars` och `props` som kommer via Analytics Source Connector mappas till fält som _\_experience.analytics.customDimensions.eVars.eVar1_. Dataförinställningen kan användas för att mappa `eVar` och `prop` fält till nya fält som har mer meningsfulla namn för användarna eller som matchar namn från andra datakällor. (Detta kan även göras på andra sätt, t.ex. genom att byta namn på fälten i en [CJA-datavy](/help/data-views/create-dataview.md).)
* **Generellt omformande data**. Datapersonen har hundratals mappningsfunktioner som kan användas för att beräkna och beräkna nya fält baserat på data som kommer via Analytics Source Connector. Du kan dela upp avgränsade fält i separata fält. Du kan kombinera fält. Du kan ändra strängar. Du kan extrahera information från ett fält baserat på reguljära uttryck och mycket annat.

## Förberedelse och klassificering av data {#classifications}

Data Prep har korsning med [klassificeringar](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=en) i vissa situationer.

I ett avgränsat fält kan du till exempel använda Data Prep för att dela upp fältet i flera enskilda fält utan att använda klassificeringar. I allmänhet är klassificeringar ett sätt att lägga till metadata i ett fält genom att överföra en uppslagsfil som tillhandahålls utanför strömmen med inkommande Analytics-händelser.

Du kan till exempel överföra en klassificeringsfil som grupperar SKU:er i&quot;storlek&quot;,&quot;märke&quot;,&quot;färg&quot; osv. En annan skillnad mellan klassificeringar och Data Prep är att klassificeringar tillämpas på data _både historiskt och framåt_. Datapruppmappningar tillämpas å andra sidan _vidarebefordra_ till data från den tidpunkt då mappningen skapades.
