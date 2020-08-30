---
title: Dimensionsartikel för lång sikt
description: Beskriver dimensionsposten "Long Tail" och varför den visas i rapporteringen.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Dimensionsartikel för lång sikt

Om du använder en dimension som innehåller ett stort antal unika värden kan du ibland se ett värde i rapporteringen som heter &quot;Long Tail&quot;. Den här dimensionsposten innebär att rapportarkitekturen CJA använder för många unika värden för att bearbeta den.

## CJA-bearbetningsarkitektur och unika värden

CJA bearbetar rapporter när de körs och distribuerar den kombinerade datauppsättningen till ett antal servrar. Data per bearbetningsserver grupperas efter person-ID, vilket innebär att en enda bearbetningsserver innehåller alla data för en viss person. När bearbetningen är klar överlåter den sin delmängd av bearbetade data till en aggregeringsserver. Alla deluppsättningar med bearbetade data kombineras och returneras i form av en arbetsyterapport.

Om en enskild server som bearbetar en delmängd av data stöter på mer än 500 000 unika dimensionsobjekt returnerar den de 500 000 översta dimensionsobjekten i sin egen delmängd och returnerar resten under &quot;Long Tail&quot;. Dimensionsobjektet Long Tail som visas i en arbetsyterapport är den sammanlagda summan av varje enskild bearbetningsservers värden som översteg 500 000 unika värden.

## Skillnader mellan &quot;Long Tail&quot; och &quot;Low Traffic&quot;

I tidigare versioner av Adobe Analytics användes en annan bearbetningsarkitektur. Data bearbetades när de samlades in. Dimensionsobjekt placerades under &quot;Låg trafik&quot; efter att en dimension uppnådde 500 000 unika värden och tillämpade mer aggressiv filtrering vid 1 miljon unika värden. Unikt värdeantal återställdes i början av varje kalendermånad. Bearbetade uppgifter var permanenta. Det fanns inget sätt att få fram befintliga data från lågtrafik.

I CJA placeras dimensionsobjekt bara i Long Tail om en enskild bearbetningsserver innehåller mer än 500 000 unika värden. Bearbetade data är inte permanenta, vilket innebär att du kan minska dimensionsobjektet Long Tail genom att ändra rapporten.

## Minska dimensionsobjektet Long Tail

Om du vill minska dimensionsobjektet Long Tail rekommenderar Adobe något av följande:

* Använd ett segment. Segment tillämpas när varje server bearbetar en delmängd data. Om du begränsar antalet unika värden som returneras minskas dimensionsobjektet Long Tail.
* Använd en uppslagsdatamängdsdimension. Dimensionerna för uppslagna datamängder kombinerar dimensionsobjekt för händelsedatamängder, vilket begränsar antalet unika värden som returneras.

På det hela taget är det svårt att använda en rapport som innehåller mer än 500 000 unika dimensionsartiklar. Om du använder ett segment eller en uppslagsdatamängdsdimension kan du minska förekomsten av Long Tail samtidigt som du gör det enklare att konsumera rapporten. Adobe planerar att förbättra den här upplevelsen när CJA utvecklas ytterligare.
