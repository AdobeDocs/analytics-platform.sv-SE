---
title: Grundläggande om arbetsytan
description: Beskriver hur du hämtar grundläggande rapporter i Workspace
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# Grundläggande om arbetsytan

Här är några tips som hjälper dig att komma igång om du inte känner till verktyget Arbetsyta ännu.

Workspace är Adobes främsta verktyg för att fatta databaserade beslut som kan användas i organisationen. Den vanligaste visualiseringen, frihandstabellen, gör att du enkelt kan skapa anpassade rapporter med mått, mätvärden, segment och datumintervall.

## Hämta en grundläggande rankad rapport i Workspace

En rankad rapport visar en sammanställd totalvy över varje dimensionsvärde, med de största värdena först. Den här typen av rapporter är användbara för att se vilka komponenter på din webbplats som är mest effektiva, till exempel vilka sidor som får mest trafik eller vilka produkter som säljer mest.

1. Se till att du är inloggad på [analytics.adobe.com](https://analytics.adobe.com).
1. Klicka på i det övre navigeringsfältet **[!UICONTROL Workspace]**.
1. Klicka på **[!UICONTROL Create New Project]**.
1. Kontrollera att Tomt projekt är markerat i det modala popup-fönstret och klicka sedan på **[!UICONTROL Create]**.
1. Till vänster finns en lista med mått, mått, segment och datumintervall. Leta reda på siddimensionen (färgad orange) och dra den till arbetsytan där det står &#39;Släpp en dimension här&#39;.
1. En rapport över de översta sidorna för den här månaden visas. Analysis Workspace fyllde automatiskt i rapporten med [förekomstmåttet](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) .
1. Leta reda på Visits-måttet (grönt i färg) och dra det antingen **över** eller **bredvid** måtthuvudet Förekomster (undvik att placera det ovanför måttet). Om du drar Visits-måttet över förekomster ersätts måtten i rapporten. Om du drar Visits-måttet bredvid Förekomster visas båda måtten sida vid sida.
1. Om du vill spara projektet klickar du på **[!UICONTROL Project]>[!UICONTROL Save]**i den övre vänstra menyn.

## Hämta en grundläggande trendrapport i Workspace

En trendrapport visar en övertidsvy med mätvärden som använder det valda datumintervallet. Den här typen av rapporter är användbara för att identifiera trender över tid och kan användas för att mäta om affärsbeslut som fattas är lyckade eller inte. Du kan till exempel titta på en rapport över sidvisningar som trendas över tid för att se om en ny webbplatsdesign bidrog till att öka eller minska trafiken.

1. Se till att du är inloggad på [analytics.adobe.com](https://analytics.adobe.com).
1. Klicka på i det övre navigeringsfältet **[!UICONTROL Workspace]**.
1. Klicka på **[!UICONTROL Create New Project]**.
1. Kontrollera att Tomt projekt är markerat i det modala popup-fönstret och klicka sedan på **[!UICONTROL Create]**.
1. Till vänster finns en lista med mått, mått, segment och datumintervall. Leta reda på dimensionen Sidvisning och dra den till det lilla utrymmet på arbetsytan med etiketten **[!UICONTROL Drop a Metric Here]**. Undvik att släppa det i det utrymme som är reserverat för dimensioner (åtminstone för den här övningen).
1. Observera att om rapportsviten innehåller data bör du se en grundläggande rapport om sidvisningar som trendas över den aktuella månaden. Analysis Workspace infogade automatiskt datumintervallet &quot;Dag&quot; så att du kan se trenden för sidvisningar för den aktuella månaden.
1. Leta reda på datumintervallet för vecka (lila) i listan med datumintervallkomponenter till vänster. Klicka på datumintervallets rubrik för att expandera och visa alla datumintervallkomponenter, eller använd sökfältet.
1. Ersätt datumintervallet genom att dra datumintervallet Vecka över datumintervallhuvudet på arbetsytan.
1. Observera att din trendrapport nu är sammanställd per vecka istället för dag.
1. Om du vill spara projektet klickar du på **[!UICONTROL Project]>[!UICONTROL Save]**i den övre vänstra menyn.

## Experimentera med verktyget

Eftersom Workspace är ett rapportverktyg har det ingen effekt på datainsamlingen. Det får inga följder om man utan åtskillnad drar komponenter till ett projekt för att se vad som fungerar. Dra olika kombinationer av mått och mätvärden till arbetsyteprojektet för att se vad som är tillgängligt för dig.

Om du av misstag drar en ogiltig komponent till arbetsyteprojektet eller vill gå tillbaka ett steg, trycker du på Ctrl+Z (Windows) eller Cmd+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja med en ren skiva genom att klicka **[!UICONTROL Project]>[!UICONTROL New]**i den övre vänstra menyn.

## Felsökning

### När jag drar ett mätresultat över står det&quot;Ogiltiga data&quot;.

Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av dimensioner och mått som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Placera i stället måtten sida vid sida.

### När jag drar ett mätresultat över ser jag inga verkliga data - bara nollor.

Om du har skapat en rapport för arbetsytan men det inte finns några data kan du kontrollera några saker:

* Kontrollera att rapportsviten är ifylld med data.
* Om du använder ett segment i rapporten kanske segmentvillkoren inte matchar några data. Försök att ta bort segmentet eller justera segmentdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.
* Navigera till webbplatsen och använd Felsökning för att validera att data samlas in.

## Ytterligare resurser

Observera att följande resurser kan avse användning av Workspace i den traditionella Adobe Analytics-produkten, inte i kundreseanalysen.

* Blogginlägg:
   * [Möjliggör för organisationer med smartare analys](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Analysis Workspace: Hemliga såsen blir stastiare](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [Varför ska du använda Analysis Workspace?](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)
   * [5 tips för att maximera produktiviteten med Analysis Workspace](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/)

## Nästa steg

Det finns många vägar för att fördjupa din förståelse av Workspace. Här är några grunder som Adobe rekommenderar:

### För slutanvändare som vill utöka kunskapen om hur man använder arbetsytan

* [Information om gränssnittet](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html)för arbetsytan: Nu när du har skapat en grundläggande rapport blir du mer bekant med resten av gränssnittet.
* [Visualiseringar i arbetsytan](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html): Frihandsregister är bara en typ av visualisering i Analysis Workspace. Lär dig hur du använder andra visualiseringar, till exempel linjediagram, stolpdiagram och geokartor.
* [Dimensioner i arbetsytan](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html): Lär dig mer om vilka dimensioner som är och hur du använder dem i mer än bara rankade rapporter.
* [Mätvärden i arbetsytan](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html): Läs mer om vad mätvärden är och hur du använder dem i andra delar av frihandstabeller.
* [Introduktion till segmentering](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html): Lär dig mer om vilka segment som är och hämta en grundläggande rapport med ett segment.
* [Datumintervall i arbetsytan](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html): Lär dig mer om relativa och rullande datum och använd dem i arbetsyteprojekt.
* [Dela projekt](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html) i Workspace: Visa dina kollegor det fantastiska Workspace-projekt du skapat.

### För analytiker och administratörer som vill förbättra kvaliteten på arbetsytan i sin organisation

* [Behörigheter](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)för Analysis Workspace: Tilldela användarbehörigheter till arbetsytan via Adobe Admin Console.
* [Mallar i arbetsytan](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html): Skapa mallar så att dina kollegor kan börja med ett projektutrymme som är anpassat efter deras behov.
* [Arbetsyteurval](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html): Skapa ett projekt som begränsar antalet tillgängliga komponenter så att arbetsytan blir mer tillgänglig för dem som inte är vana vid verktyget
