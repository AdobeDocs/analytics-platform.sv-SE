---
title: Produktanalys i Customer Journey Analytics
description: Lär dig vilka funktioner du kan använda i Customer Journey Analytics för att effektivt utföra produktanalyser.
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Produktanalys i Customer Journey Analytics

Produktanalys är processen att förstå hur användarna interagerar med produkten under hela kundresan. Det handlar om att analysera data för att identifiera insikter om användarbeteende, produktprestanda och tillväxtmöjligheter. Effektiv produktanalys hjälper team att fatta välgrundade beslut för att förbättra användarupplevelserna, öka engagemanget och uppnå verksamhetsmålen.

Customer Journey Analytics ger team verktyg för att analysera och optimera produktupplevelser med funktioner för att:

* **Hantera produktdata i stor skala**: Importera, omvandla och hantera enkelt produktdata efter dina affärsbehov för att säkerställa tillförlitliga insikter.
* **Mät förvärv och aktivering**: Spåra hur nya användare identifierar produkten och engagerar sig i första värdeskapande händelser.
* **Mät engagemang och användning**: Lär dig hur användarna går igenom produkttratten, identifiera friktionspunkter och spåra användningen av nyckelfunktioner.
* **Mät kvarhållning och urn**: Analysera användarnas lojalitet över tid, identifiera bortfallsindikatorer och utveckla strategier för att minska bortfall och öka lojaliteten.
* **Åtgärda produktinsikter**: Förvandla datadrivna insikter till strategier som kan användas för att förbättra användarupplevelsen och få en hållbar produkttillväxt.
* **Dela insikter med din organisation**: Kommunicera viktiga resultat mellan olika team för att anpassa insatser, främja samarbete och se till att alla arbetar mot gemensamma produkt- och affärsmål.

Genom att utnyttja dessa funktioner kan Customer Journey Analytics utnyttja produktens fulla potential och skapa en smidig, datadriven metod för att driva användare och företag framåt.

## Hantera produktdata i stor skala

Korrekta produktdata är hörnstenen i en effektiv produktanalys. Intag av data avser processen att instrumentera och samla in produktdata, medan datahantering innebär att omvandla och underhålla dessa data för att säkerställa att de uppfyller era analytiska krav.

Följande funktioner i Adobe Experience Platform och Customer Journey Analytics gör att du kan importera och hantera dina produktdata i stor skala:

* Adobe Experience Platform
   * [Datauppsättningar &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/catalog/datasets/overview)
   * [&#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/data-prep/home)
   * [Data Distiller &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [&#x200B;](/help/connections/overview.md)
   * [Datavyer](/help/data-views/data-views.md), inklusive [härledda fält &#x200B;](/help/data-views/derived-fields/derived-fields.md)
   * [&#x200B;](/help/components/segments/seg-overview.md)
   * [Beräknade mått](/help/components/calc-metrics/calc-metr-overview.md)
   * [Guidad &#x200B;: &#x200B;](/help/guided-analysis/types/timeline.md)

## Mät förvärv och aktivering

Produkttillväxt är beroende av användbara insikter från de viktigaste funktionerna som lockar nya användare, avslöjar konverteringsvägar och eliminerar friktionen under kundresan.

* Anskaffningen spårar nya användare som kommer till produkten, inklusive hur de kommer fram och vilka satsningar som är mest eller mindre effektiva.
* Aktiveringen övervakar nya användare som engagerar sig i din första värdehändelse, definierad enligt dina specifika mål.

![Aktiv tillväxt](/help/guided-analysis/assets/active.png)

Med följande funktioner i Customer Journey Analytics kan ni effektivt mäta både förvärv och aktivering:

* [Guidad analys &#x200B;: aktiv tillväxt](/help/guided-analysis/types/active-growth.md)
* [Guidad analys: Nettotillväxt](/help/guided-analysis/types/net-growth.md)
* [Guidad analys: Trender](/help/guided-analysis//types/trends.md)
* [&#x200B; för attribueringspanelen](/help/analysis-workspace/c-panels/attribution.md)
* [Frihandsregister](/help/analysis-workspace/c-panels/freeform-panel.md) som innehåller marknadsföringskanaldimensionen (skapar med ett [härlett fält](/help/data-views/derived-fields/derived-fields.md))

## Mät engagemang och användning

Om du skaffar nya användare utökas den främsta delen av produkttratten. Engagemanget fokuserar på att vägleda användarna ytterligare nedåt och undanröja hinder för deras framgång. Deras framgångar driver direkt företagets framgång.

![Intresseanalys](/help/guided-analysis/assets/feature-matrix.png)

Följande funktioner i Customer Journey Analytics hjälper dig att spåra produktengagemang och produktanvändning:

* [Guidad analys: Engagemang](/help/guided-analysis/types/engagement.md)
* [Guidad analys: Trender](/help/guided-analysis/types/trends.md)
* [Guidad analys: Frekvens](/help/guided-analysis/types/frequency.md)
* [Guidad analys: Tratt](/help/guided-analysis/types/funnel.md)
* [Guidad analys: Konverteringstrender](/help/guided-analysis/types/conversion-trends.md)
* [Guidad analys: Frisläpp påverkan](/help/guided-analysis/types/release-impact.md)
* [Guidad analys: Första &#x200B;](/help/guided-analysis/types/first-use-impact.md)
* [Guidad analys: Tidslinje](/help/guided-analysis/types/timeline.md)
* [&#x200B; för frihandstabeller](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Flöde](/help/analysis-workspace/visualizations/c-flow/flow.md)

## Mät kvarhållande och bortfall

Kvarhållandet mäter hur många användare som fortsätter att interagera med produkten efter det första förvärvet och aktiveringen. Högpresterande produkter behåller en stabil, lojal användarbas genom att maximera interaktionen med de funktioner som mest korrelerar med fortsatt användning. En användare som behålls returnerar och interagerar med produkten över tiden, men det gör inte en kund. Produktteam håller reda på hur länge kunderna stannar kvar och kan identifiera de funktioner som driver ett kontinuerligt engagemang, och hur man gör designingrepp som förändrar kundens beteende mot ett bibehållet användarbeteende.

![Kvarhållningsanalys](/help/guided-analysis/assets/retention.png)

Följande funktioner i Customer Journey Analytics hjälper dig att effektivt spåra kundlojalitet och kundomsättning:

* [Guidad analys: Kvarhållning](/help/guided-analysis/types/retention.md) &#x200B;
* [Guidad analys: Aktiv tillväxt](/help/guided-analysis/types/active-growth.md)
* [Guidad analys: Nettotillväxt](/help/guided-analysis/types/net-growth.md)
* [&#x200B; för kohortabell](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## Användbara produktinsikter

Insikter ger värde bara när de skapar handling. Konvertera analysresultat till åtgärder som förbättrar användarupplevelsen och stöder långsiktig produkttillväxt.

Med följande funktioner i Experience Cloud kan ni agera effektivt utifrån insikter:

* [Skapa och publicera målgrupper](/help/components/audiences/publish.md) &#x200B; för aktivering från Customer Journey Analytics
* Aktivera målgrupper med Experience Cloud-produkter:
   * [Kör experiment](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment) i AJO och Adobe Target och mät effekten av variationer i Customer Journey Analytics med [Experimentationspanelen](/help/analysis-workspace/c-panels/experimentation.md)
   * [Leverera appengagemang](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/in-app/get-started-in-app) till användare i AJO
* [Aktivera målgrupper](https://experienceleague.adobe.com/sv/docs/experience-platform/destinations/ui/activate/activation-overview) till externa mål med Adobe CDP-&#x200B; i realtid

## Dela insikter till &#x200B;

Kommunicera viktiga resultat i olika team för att anpassa insatserna, främja samarbetet och se till att alla arbetar mot gemensamma produkt- och affärsmål.

![Guidad analys i Workspace](assets/guided-analysis-workspace.png)

Följande funktioner i Customer Journey Analytics hjälper dig att dela insikter effektivt:

* [Dela](/help/analysis-workspace/curate-share/share-projects.md) guidade analysvyer som är skräddarsydda för specifika affärsfrågor, så att konsumenterna kan själva besvara nästa fråga
* Kombinera guidade analyser, paneler och visualiseringar till en omfattande kontrollpanel i [Analysis Workspace](/help/analysis-workspace/home.md)
* Skapa ett [mobilstyrkort](/help/mobile-app/home.md) med viktiga produktinsikter för chefer och andra konsumenter i farten
