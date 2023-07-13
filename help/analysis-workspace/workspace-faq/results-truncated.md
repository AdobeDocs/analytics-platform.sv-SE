---
title: Resultat av trunkerad dimensionspost
description: Beskriver dimensionsposten "Trunkerade resultat" och varför den visas i rapporter.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: cf3c451cbefa7d6f9d5ea326c69fc2e5944881ff
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Resultat av trunkerad dimensionspost

När du använder en dimension som innehåller många unika värden, kan en rapport returnera en dimensionsartikel med etiketten **[!UICONTROL Results Truncated]**. Dimensionsobjektet innebär att den begärda rapporten innehåller för många unika värden för att den ska kunna bearbetas effektivt. Det innebär att objekt som anses vara minst viktiga tas bort.

## Bearbetningsarkitektur och unika värden för Customer Journey Analytics

Customer Journey Analytics bearbetar rapporter när de körs och distribuerar den kombinerade datauppsättningen till flera servrar. Data per bearbetningsserver grupperas efter person-ID, vilket innebär att en enda bearbetningsserver innehåller alla data för en viss person. När servern är klar med bearbetningen överför den sin deluppsättning av bearbetade data till en aggregeringsserver. Alla deluppsättningar av bearbetade data kombineras och returneras i form av en Workspace-rapport.

Om någon enskild server samlar in en resultatmängd som är över en storlekströskel trunkeras resultaten innan de skickas tillbaka. Denna optimering håller nätverkstrafiken och aggregeringen inom gränserna för att möjliggöra snabb rapportering. Eftersom varje bearbetningsserver trunkerar resultat med enbart visning av egna data, är det möjligt att de objekt som visas i Analysis Workspace har måttvärden som är något obefintliga.

Servern väljer vilka dimensionsobjekt som ska tas bort baserat på det mått som används för sorteringen. Om sorteringsmåttet är ett beräknat mått, använder servern mått inom det beräknade måttet för att avgöra vilka dimensionsobjekt som ska trunkeras. Eftersom beräknade mätvärden kan innehålla flera mätvärden av varierande betydelse kan resultaten bli mindre exakta. Vid beräkningen av&quot;Intäkt per person&quot; returneras till exempel det totala inkomstbeloppet och det totala antalet personer och aggregeras innan indelningen görs. Därför väljer varje nod vilka objekt som ska tas bort utan att veta hur resultatet påverkar den övergripande sorteringen.

## Skillnader mellan Trunkerat resultat och lågtrafik

I tidigare versioner av Adobe Analytics användes en annan bearbetningsarkitektur. Data bearbetades när de samlades in. Dimensioner placerades under Låg trafik efter att en dimension uppnådde 500 000 unika värden och tillämpade mer aggressiv filtrering vid en miljon unika värden. Antalet unika värden återställdes i början av varje kalendermånad. Bearbetade uppgifter var permanenta. det fanns inget sätt att få bort befintliga data från lågtrafik.

I Customer Journey Analytics trunkeras dimensionsobjekt bara om resultatet av en rapport är för stort. Bearbetade data är inte permanenta, vilket innebär att du kan minska eller eliminera trunkeringen genom att ändra rapporten.

## Minska dimensionsobjektet Resultattrunkering

Om du vill minska antalet händelser i dimensionsobjektet Resultattrunkering rekommenderar Adobe något av följande:

* Använd en [Filter](/help/components/filters/create-filters.md). Filter tillämpas när varje server bearbetar en delmängd av data. Om du begränsar antalet unika värden som returneras minskas dimensionsobjektet Resultattrunkering.
* Använd en sökning. Om en sökning används tas de objekt som inte matchar sökningen bort från rapportresultaten, vilket gör det mer sannolikt att du ser de objekt som du vill ha.
* Använd en dimension för uppslagsdatauppsättning. Dimensionerna för uppslagsdatauppsättningen kombinerar dimensionsobjekt för händelsedatamängd, som begränsar antalet unika värden som returneras.
