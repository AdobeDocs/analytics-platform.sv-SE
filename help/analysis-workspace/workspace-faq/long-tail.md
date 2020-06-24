---
title: Långt detaljdimensionsvärde
description: Förklarar dimensionsvärdet "Long Tail" och varför det visas i rapporter.
translation-type: tm+mt
source-git-commit: 8f59697b2bb282a1057267131343229e12dd5111
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Långt detaljdimensionsvärde

Om du använder en dimension som innehåller ett stort antal unika värden kan du ibland se ett värde i rapporten med etiketten&quot;Long Tail&quot;. Detta dimensionsvärde innebär att den rapporteringsarkitektur som CJA använder innehåller för många unika värden för att kunna bearbeta den.

## CJA-bearbetningsarkitektur och unika värden

CJA bearbetar rapporter när de körs och distribuerar den kombinerade datauppsättningen till ett antal servrar. Data per bearbetningsserver grupperas efter person-ID, vilket innebär att en enda bearbetningsserver innehåller alla data för en viss person. När bearbetningen är klar överför den sin deluppsättning av bearbetade data till en aggregeringsserver. Alla deluppsättningar av bearbetade data kombineras och returneras i form av en Workspace-rapport.

Om någon enskild server som bearbetar en delmängd av data stöter på mer än 500 000 unika dimensionsvärden, returnerar den de 500 000 översta dimensionsvärdena för sin egen delmängd och returnerar resten under &quot;Lång sek&quot;. Dimensionsvärdet Long Tail som visas i en Workspace-rapport är den aggregerade summan av varje enskild bearbetningsservers värden som överskrider 500 kB unika värden.

## Skillnader mellan&quot;långrev&quot; och&quot;lågtrafik&quot;

I tidigare versioner av Adobe Analytics användes en annan bearbetningsarkitektur. Data bearbetades när de samlades in. Dimensionsvärden placerades under Låg trafik efter att en dimension uppnådde 500 kB unika värden och tillämpade mer aggressiv filtrering vid 1M unika värden. Det unika värdet återställdes i början av varje kalendermånad. Bearbetade uppgifter var permanenta. det fanns inget sätt att få bort befintliga data från lågtrafik.

I CJA anges dimensionsvärden bara i &quot;Long Tail&quot; om en enskild bearbetningsserver innehåller fler än 500 kB unika värden. Bearbetade data är inte permanenta, vilket innebär att du kan minska dimensionsvärdet för Lång stjärna genom att ändra rapporten.

## Minska dimensionsvärdet Lång sek

Om du vill minska dimensionsvärdet &quot;Lång stjärna&quot; rekommenderar Adobe något av följande:

* Använd ett segment. Segmenten tillämpas när varje server bearbetar en delmängd av data. Om du begränsar antalet unika värden som returneras minskas dimensionsvärdet&quot;Lång stjärna&quot;.
* Använd en dimension för uppslagsdatauppsättning. Dimensionerna för uppslagsdatauppsättningen kombinerar dimensionsvärden för händelsedatamängd, som begränsar antalet unika värden som returneras.

Generellt sett är det svårt att få en rapport som innehåller mer än 500 kB unika dimensionsvärden. Om du använder ett segment eller en dimension för uppslagsdatauppsättning kan du minska förekomsten av&quot;Long Tail&quot; samtidigt som du gör rapporten lättare att använda. Adobe planerar att förbättra denna upplevelse när CJA utvecklas ytterligare.
