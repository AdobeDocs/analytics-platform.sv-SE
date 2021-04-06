---
title: Lång detaljdimensionsartikel
description: Beskriver dimensionsposten "Long Tail" och varför den visas i rapporter.
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# Lång detaljdimensionsartikel

Om du använder en dimension som innehåller ett stort antal unika värden kan du ibland se ett värde i rapporten med namnet **[!UICONTROL Long Tail]**. Dimensionsobjektet innebär att den rapporteringsarkitektur som CJA använder innehåller för många unika värden för att kunna bearbeta den.

## CJA-bearbetningsarkitektur och unika värden

CJA bearbetar rapporter när de körs och distribuerar den kombinerade datauppsättningen till ett antal servrar. Data per bearbetningsserver grupperas efter person-ID, vilket innebär att en enda bearbetningsserver innehåller alla data för en viss person. När bearbetningen är klar överför den sin deluppsättning av bearbetade data till en aggregeringsserver. Alla deluppsättningar av bearbetade data kombineras och returneras i form av en Workspace-rapport.

Om någon enskild server som bearbetar en delmängd av data stöter på mer än 500 000 unika dimensionsobjekt returnerar den de 500 000 översta dimensionsobjekten i sin egen delmängd och returnerar resten under [!UICONTROL Long Tail]. Dimensionsobjektet [!UICONTROL Long Tail] som visas i en Workspace-rapport är den aggregerade summan av varje enskild bearbetningsservers värden som överskrider 500 kB unika värden.

## Skillnader mellan&quot;långrev&quot; och&quot;lågtrafik&quot;

I tidigare versioner av Adobe Analytics användes en annan bearbetningsarkitektur. Data bearbetades när de samlades in. Dimensioner placerades under Lågtrafik efter att en dimension uppnådde 500 kB unika värden och tillämpade mer aggressiv filtrering vid 1 MB unika värden. Det unika värdet återställdes i början av varje kalendermånad. Bearbetade uppgifter var permanenta. det fanns inget sätt att få bort befintliga data från lågtrafik.

I CJA placeras dimensionsobjekt bara i &quot;Long Tail&quot; om en enskild bearbetningsserver innehåller fler än 500 kB unika värden. Bearbetade data är inte permanenta, vilket innebär att du kan minska dimensionsobjektet Lång stjärna genom att ändra rapporten.

## Minska dimensionsobjektet Lång sek

Om du vill minska dimensionsobjektet &quot;Lång stjärna&quot; rekommenderar Adobe något av följande:

* Använd ett [filter](/help/components/filters/create-filters.md). Filter tillämpas när varje server bearbetar en delmängd av data. Om du begränsar antalet unika värden som returneras minskas dimensionsobjektet Lång sek.
* Använd en dimension för uppslagsdatauppsättning. Dimensionerna för uppslagsdatauppsättningen kombinerar dimensionsobjekt för händelsedatamängd, som begränsar antalet unika värden som returneras.

Generellt sett är det svårt att få en rapport som innehåller mer än 500 kB unika dimensionsposter. Om du använder ett filter eller en dimension för uppslagsdatauppsättning kan du minska förekomsten av&quot;Long Tail&quot; samtidigt som du gör rapporten lättare att använda. Adobe planerar att förbättra denna upplevelse när CJA utvecklas ytterligare.
