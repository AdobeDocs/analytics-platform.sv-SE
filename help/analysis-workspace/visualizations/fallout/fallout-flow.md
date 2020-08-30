---
description: 'null'
title: Översikt över utfall
uuid: 2d98899e-e401-4d7a-8af0-de0002f84178
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 2%

---


# Översikt över utfall

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Utfallsvisualiseringar ger fler alternativ för att skapa utfallsrapporter. Rapporterna om utfall visar var besökarna lämnade (föll bort) och fortsatte igenom en fördefinierad sidsekvens.

Med hjälp av färdiga visualiseringar kan du

* Utför jämförelser sida vid sida av två olika segment i samma rapport.
* Dra, släpp och ordna om steg i tratten (kontaktytor)
* Blanda och matcha värden från olika dimensioner och mått
* Skapa en flerdimensionell utdatarapport
* Identifiera var kunder går omedelbart efter att de fallit ut

I Utfall visas konverterings- och utfallsfrekvenser mellan varje steg eller touchpoint i en sekvens.

Du kan till exempel spåra en besökares utfallspunkter under en inköpsprocess. Markera bara en pekpunkt och en slutpunkt och lägg till mellanliggande pekpunkter för att skapa en navigeringssökväg för webbplatsen. Men du kan också göra flerdimensionella utfall.

En visualisering av fallout är användbar vid analys av:

* Omräkningskurser genom specifika processer på webbplatsen (t.ex. en köp- eller registreringsprocess).
* Allmänna trafikflöden med bredare räckvidd: Av de personer som såg hemsidan visar detta flöde hur många som fortsatte att göra en sökning och sedan hur många av dem som slutligen gick vidare för att titta på ett specifikt objekt.
* Korrelation mellan händelser på webbplatsen. Korrelationer visar hur många procent av de personer som har tittat på din sekretesspolicy som har gått vidare för att köpa en produkt.

[Utfall visualisering på YouTube](https://www.youtube.com/watch?v=VcrfHSyIoj8&amp;index=52&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) 4.15

## Segmentering som grund för flöde och utfall {#section_654F37A398C24DDDB1552A543EE29AA9}

Segment som används på arbetsytepaneler fungerar något annorlunda än segment som används på utfall- och flödesrapporter i rapporter och analyser eller ad hoc-analys. De ger oftast exakt samma resultat. Den största skillnaden är att rapporten &amp; Analytics och Ad Hoc Analysis använder segmentet i varje steg i sekvensen. Detta kan leda till något olika resultat.

Låt oss ta ett exempel på nedfall med två steg:

![](assets/fallout_segments1.png)

Om du sedan tillämpar ett segment på arbetsytans panelnivå kombineras segmentet med utfallet så här:

![](assets/fallout_seg.png)

När rapporten &amp; Analytics och Ad Hoc Analysis däremot beräknar segmentet kombineras segmentet på följande sätt:

![](assets/fallout_segments3.png)

Rapporter och analys och ad hoc-analys kombinerar segmentet med varje steg. Om containrarna ligger på samma nivå som utfallet (t.ex. besöksnivå eller besöksnivå) kommer detta att resultera i att antalet besök eller besökare matchar.

Om segmentet som används på panelen är mindre än utfallsnivån (t.ex. träffnivå), visas dock olika resultat för segmentet på grund av hur det kombineras i rapporten. För att upprepa, under de flesta omständigheter matchar siffrorna i Analysis Workspace siffrorna i Reports &amp; Analytics och Ad Hoc Analysis. De kommer att **inte** matcha endast om samtliga fall nedan är sanna:

* Segmentet ligger inte på samma nivå som utfallet.
* Segmentet har en variabel där besökaren/besöket kan ha flera värden under ett besök/en besökare.

I det sällsynta fall där du måste ha Analysis Workspace som matchar metoden Reports &amp; Analytics för att tillämpa segment på utfall/flöde, släpper du helt enkelt segmentet i varje utfallssteg på arbetsytan och det resulterar i samma tal.
