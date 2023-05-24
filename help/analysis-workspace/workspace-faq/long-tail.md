---
title: Lång detaljdimensionsartikel
description: Beskriver dimensionsposten "Long Tail" och varför den visas i rapporter.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# Lång sidodimensionspost

När du använder en dimension som innehåller ett stort antal unika värden kan du ibland få en varning som säger **[!UICONTROL Results Truncated]**.  Detta innebär att den rapporteringsarkitektur som CJA använder innehåller för många unika värden för att kunna bearbeta effektivt. Som ett resultat. den tog bort de objekt som den ansåg vara minst viktiga.

## CJA-bearbetningsarkitektur och unika värden

CJA bearbetar rapporter när de körs och distribuerar den kombinerade datauppsättningen till ett antal servrar. Data per bearbetningsserver grupperas efter person-ID, vilket innebär att en enda bearbetningsserver innehåller alla data för en viss person. När servern är klar med bearbetningen överför den sin deluppsättning av bearbetade data till en aggregeringsserver. Alla deluppsättningar av bearbetade data kombineras och returneras i form av en Workspace-rapport.

Om någon enskild server samlar in en resultatmängd som överskrider ett tröskelvärde för storlek, kommer resultatet att trunkeras innan de skickas tillbaka. Detta håller nätverkstrafiken och aggregeringen inom gränserna för att möjliggöra snabb rapportering.  Eftersom resultaten trunkeras med enbart visning av egna data är det möjligt (även om det är osannolikt) att de objekt som visas i Analysis Workspace har felaktiga mätvärden.

Servern väljer vilka objekt som ska tas bort baserat på de mått som används för sorteringen.  Om det här är ett beräknat mått kanske det inte är uppenbart hur det ska sorteras, så resultatet blir kanske mindre exakt.  Vid beräkningen av&quot;Intäkt per person&quot; returneras till exempel det totala inkomstbeloppet och det totala antalet personer och aggregeras innan indelningen görs. Därför väljer varje nod ofta vilka objekt som ska tas bort, utan att veta hur resultatet påverkar den övergripande sorteringen.

## Skillnader mellan&quot;långrev&quot; och&quot;lågtrafik&quot;

I tidigare versioner av Adobe Analytics användes en annan bearbetningsarkitektur. Data bearbetades när de samlades in. Dimensioner placerades under Lågtrafik efter att en dimension uppnådde 500 kB unika värden och tillämpade mer aggressiv filtrering vid 1 MB unika värden. Antalet unika värden återställdes i början av varje kalendermånad. Bearbetade uppgifter var permanenta. det fanns inget sätt att få bort befintliga data från lågtrafik.

I CJA trunkeras dimensionsobjekt bara om resultatet av en rapport är för stort. Bearbetade data är inte permanenta, vilket innebär att du kan minska eller eliminera trunkeringen genom att ändra rapporten.

## Minska dimensionsobjektet Lång sek

Om du vill minska trunkeringen av &quot;Long Tail&quot; rekommenderar Adobe något av följande:

* Använd en [filter](/help/components/filters/create-filters.md). Filter tillämpas när varje server bearbetar en delmängd av data. Om du begränsar antalet unika värden som returneras minskas trunkeringen av&quot;Lång stjärna&quot;.
* Använd en sökning. Om du använder en sökning kommer de objekt som inte matchar sökningen att trunkeras först, vilket gör det lättare att se de objekt du vill ha.
* Använd en dimension för uppslagsdatauppsättning. Dimensionerna för uppslagsdatauppsättningen kombinerar dimensionsobjekt för händelsedatamängd, som begränsar antalet unika värden som returneras.

Generellt sett är det svårt att få en rapport som innehåller för många unika dimensionsobjekt. Om du tillämpar ett filter eller en dimension för uppslagsdatauppsättning kan du minska trunkeringen av&quot;Long Tail&quot; samtidigt som du gör rapporten lättare att använda.
