---
source-git-commit: 8943af2bc81de5ece238dc7647ff3f66b14b9776
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%

---
# Adobe Analytics bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep för Analytics Source Connector

[Bearbetningsregler och VISTA-regler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) erbjuder ett sätt att omvandla och hantera data som skickas till Adobe Analytics [datainsamling](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). Dessa omvandlingar sker som en del av databearbetningen i Adobe innan data lagras för rapportering och analys i Adobe Analytics.


[Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) är ett verktyg som gör att du kan använda radbaserade mappningar och omformningar på data som hämtas till [AEP](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en) innan data görs tillgängliga för AEP-program, inklusive CJA och andra. Dataförberedelsen är integrerad med många av AEP:s [källkopplingar](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) och nu även är integrerat med [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en), som är ett sätt att importera rapportsvitsdata från Adobe Analytics till AEP.

Data som samlas in av och lagras i Adobe Analytics kan omformas antingen med bearbetningsregler eller VISTA-regler eller både och. Men rapportsviter som sedan vidarebefordras till AEP via Analytics Source Connector kan omvandlas ytterligare en gång med Data Prep. Detta kan vara önskvärt av flera skäl:

* **Lösa schemaskillnader mellan rapportsviter för användning i CJA och/eller RTCDP**. Om rapportsviten A till exempel definierar eVar1 som sökterm och rapportregel B definierar eVar2 som sökterm, kan du använda dataprep för att mappa de två olika eVars-elementen till ett gemensamt fält som innehåller data från båda eVars-elementen. Detta gör det möjligt att [kombinera rapportsviter med olika scheman](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) i en CJA-anslutning eller för användning i RTCDP.
* **Mappa eVars-fält till semantiskt meningsfulla namn**. eVars och props som kommer via Analytics Source Connector mappas till fält som _\_experience.analytics.customDimensions.eVars.eVar1_.  Dataprep kan användas för att mappa eVar- och prop-fält till nya fält som har mer meningsfulla namn för användarna eller som matchar namn som kommer från andra datakällor. (Detta kan även göras på andra sätt, t.ex. genom att ändra namn på fälten i CJA-datavyn.)
* **Generellt omformande data**. Datapersonen har hundratals mappningsfunktioner som kan användas för att beräkna och beräkna nya fält baserat på data som kommer via ADC. Du kan dela upp avgränsade fält i separata fält. Du kan kombinera fält. Du kan ändra strängar. Du kan extrahera information från ett fält baserat på reguljära uttryck och mycket annat.


Du kan också lägga märke till att Data Prep har krympt med [klassificeringar](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=en) i vissa situationer. Om du till exempel har ett avgränsat fält kan du använda Data Prep för att dela upp fältet i flera enskilda fält utan att använda klassificeringar. I allmänhet är klassificeringar ett sätt att lägga till metadata i ett fält genom att överföra en uppslagsfil som tillhandahålls utanför strömmen med inkommande Analytics-träffar. Du kan till exempel överföra en klassificeringsfil som grupperar SKU:er i&quot;storlek&quot;,&quot;märke&quot;,&quot;färg&quot; osv. En annan skillnad mellan klassificeringar och Data Prep är att klassificeringar gäller data både historiskt och framåt. Förmappningar av data tillämpas däremot på data från och med den tidpunkt då mappningen skapas framåt.