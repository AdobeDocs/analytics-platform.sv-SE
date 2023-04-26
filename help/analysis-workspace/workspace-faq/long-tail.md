---
title: Lång detaljdimensionsartikel
description: Beskriver dimensionsposten "Long Tail" och varför den visas i rapporter.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 5603eef365365cea941ba5b261aeb56e58a84236
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 0%

---

# Trunkeringsvarning

När du använder en dimension som innehåller ett stort antal unika värden kan du ibland få en varning som säger **[!UICONTROL Results Truncated]**.  Det innebär att rapporteringsarkitekturen som CJA använder innehåller för många unika värden för att kunna bearbetas effektivt, vilket gör att de objekt som CJA gissade var minst viktiga.

## CJA-bearbetningsarkitektur och unika värden

CJA bearbetar rapporter när de körs och distribuerar den kombinerade datauppsättningen till ett antal servrar. Data per bearbetningsserver grupperas efter person-ID, vilket innebär att en enda bearbetningsserver innehåller alla data för en viss person. När bearbetningen är klar överför den sin deluppsättning av bearbetade data till en aggregeringsserver. Alla deluppsättningar av bearbetade data kombineras och returneras i form av en Workspace-rapport.

Om någon enskild server samlar in en resultatmängd som överskrider ett tröskelvärde för storlek, kommer resultatet att trunkeras innan de skickas tillbaka.  Detta håller nätverkstrafiken och aggregeringen inom gränserna för att möjliggöra snabb rapportering.  Eftersom resultatet trunkeras med enbart visning av dess egna data är det möjligt (men osannolikt) att de objekt som visas i Analysis Workspace har felaktiga mätvärden.

Det väljer vilka objekt som ska kastas bort baserat på det mått som används för sorteringen.  Om det här är ett beräknat mått kanske det inte är uppenbart hur det ska sorteras, så resultatet blir kanske mindre exakt.  När man beräknar intäkt per besökare returneras och sammanställs till exempel summan av intäkter och antal besökare innan delningen görs, och därför väljer varje nod vilka objekt som ska tas bort utan att veta hur deras resultat kommer att påverka den övergripande sorteringen.

## Skillnader mellan&quot;långrev&quot; och&quot;lågtrafik&quot;

I tidigare versioner av Analytics användes en annan bearbetningsarkitektur. Data bearbetades när de samlades in. Dimensioner placerades under Lågtrafik efter att en dimension uppnådde 500 kB unika värden och tillämpade mer aggressiv filtrering vid 1 MB unika värden. Det unika värdet återställdes i början av varje kalendermånad. Bearbetade uppgifter var permanenta. det fanns inget sätt att få bort befintliga data från lågtrafik.

I CJA trunkeras dimensionsobjekt bara om resultatet av en rapport är för stort. Bearbetade data är inte permanenta, vilket innebär att du kan minska eller eliminera trunkeringen genom att ändra rapporten.

## Minska dimensionsobjektet Lång sek

Om du vill minska trunkeringen av &quot;Long Tail&quot; rekommenderar Adobe något av följande:

* Använd en [filter](/help/components/filters/create-filters.md). Filter tillämpas när varje server bearbetar en delmängd av data. Om du begränsar antalet unika värden som returneras minskas trunkeringen av&quot;Lång stjärna&quot;.
* Använd en sökning.  Om du använder en sökning kommer de objekt som inte matchar sökningen att trunkeras först, vilket gör det mer sannolikt att du kommer att se de objekt som du vill ha.
* Använd en dimension för uppslagsdatauppsättning. Dimensionerna för uppslagsdatauppsättningen kombinerar dimensionsobjekt för händelsedatamängd, som begränsar antalet unika värden som returneras.

Generellt sett är det svårt att få en rapport som innehåller för många unika dimensionsobjekt. Om du tillämpar ett filter eller en dimension för uppslagsdatauppsättning kan du minska trunkeringen av&quot;Long Tail&quot; samtidigt som du gör rapporten lättare att använda.
