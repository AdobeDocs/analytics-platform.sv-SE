---
title: Jämför CJA med BI-lösningar
description: Jämför Customer Journey Analytics med BI-lösningar
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 955f4543a132126deee52b7dfe3398b742022069
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Jämför CJA med BI-lösningar

I och med det fokus som nu ligger på kundupplevelsen behöver varumärken avancerade lösningar för att bättre förstå den holistiska kundresan. Genom att förstå den här fullständiga kundresan kan ni analysera och få värdefulla insikter om hur online- och offlinekanaler engagerar kunder och leder till ökad konvertering, lojalitet och lojalitet. En kundresa i det här sammanhanget kan vara en enkel onlineordning för en måltid i en sushi-näringskedja. Eller köp av en ny bil, där kunden kombinerar onlineforskning med besök i butiken och ett slutligt personligt köp.

Många organisationer har konsoliderat sina flerkanalsdata till en datasjö eller data warehouse. Business Intelligence-verktyg (BI) används ovanpå dessa datalager för att tillhandahålla rapporter, visualiseringar och insikter som företaget behöver för att förstå kundresan. Den här kombinationen av lösningar och verktyg är ofta av allmän natur och design och inte uttryckligen inriktad på kunden. Customer Journey Analytics (CJA) fokuserar på att ge de som ansvarar för kundupplevelsen möjlighet till det, som marknadsförare, dataanalytiker och datavetare. Verktyget gör att de kan visualisera kundresan i fullständigt sammanhang över alla kanaler i realtid utan begränsningar som många andra BI-verktyg har.

I det här avsnittet av dokumentationen förklaras de grundläggande skillnaderna mellan CJA och vanliga BI-verktyg, först genom att titta på det allmänna arbetsflöde som används för att uppnå det mål som nämns ovan: förstå kundresan. Sedan innehåller det mer information om hur data lagras, samlas in och frågas på olika sätt mellan CJA- och BI-verktyg. Slutligen förklaras skillnaderna i visualiseringsfunktioner.

## Traditionellt BI-arbetsflöde

Ett vanligt hinder för traditionella strategier för att analysera kundresor är att det inte är kundfokuserat. Varje team samlar in data i olika storlekar, analyserar och optimerar upplevelser baserat på de data de har tillgång till.

![Vanligt BI-arbetsflöde](./assets/biworkflow.png)

Om du vill förstå hur en viss digital kampanj påverkar en offlineåtgärd som lagras i en annan datasilo skickar du en begäran till BI-teamets kö. BI-teamet skriver den fråga som krävs för att hämta och omvandla data. När rådata har hämtats skapar BI-teamet visualiseringen. Informationen delas med dig och du lägger tid på att kombinera insikter och extrahera data för aktivering i andra system.

Vart och ett av dessa steg kan ta timmar, dagar eller till och med veckor. Om det finns uppföljningsfrågor eller problem med de data som efterfrågas kan det ta ännu mer tid innan dessa frågor besvaras och cykeln fortsätter. För kontinuerlig analys, utforskning och förståelse av kundresan är den här processen ineffektiv och inte skalbar. BI-team hanterar vanligtvis mer än bara kundreserelaterade frågor.

## CJA: Demokratiserat arbetsflöde för online- och offlinedata

CJA erbjuder en miljö för att koppla samman data över flera kanaler, både online och offline, på en övergripande kundnivå, enbart i syfte att förstå kundresan. Den första konfigurationen krävs för att [koppla](/help/connections/overview.md) och [definiera vyer](/help/data-views/data-views.md) till de uppgifter ni anser vara relevanta. När uppgifterna är ifyllda är de dock lätt tillgängliga för kontinuerlig analys och utforskning. Ni kan stegvis få insikter i och förstå kundresorna. Genom att demokratisera kombinerade online- och offlinedata kan ni besvara kundreserelaterade frågor på några sekunder.

![CJA-arbetsflöde](./assets/cjaworkflow.png)

Du kan använda CJA för att ställa frågor i den visuella Analysis Workspace-miljön och få insikter nästan direkt. Flerkanalsdata och rapporter är omedelbart tillgängliga, utan någon SQL-kod. Ytterligare frågor och analyser kan göras med en enkel dra och släpp-funktion i användargränssnittet, med helt korrelerade data. Du kan fortsätta ställa frågor och stegvis utforska fler detaljer när du behöver dem. Sedan kan ni vidta omedelbara åtgärder för de insikter ni hittar, som att dela ut målgrupper för aktivering och samordning.

## CJA:s kraftfulla rapporteringsmotor

CJA använder en kraftfull egen arkitektur som distribuerar analyser över hundratals eller till och med tusentals servrar för att visa data i Analysis Workspace på bara några sekunder. Några av de märkbara egenskaperna i den här bearbetningsarkitekturen är:

* **Optimerat för enskilda kundrelaterade frågor**: Tekniskt sett lagrar CJA data i en distribuerad rapportmotor som använder cache-lagring i stor utsträckning. Motorn är finjusterad för responsiva frågor om händelsedata på individnivå och optimerad som sådana för kundrelaterade frågor. Rapporteringsmotorn lagrar data i kolumnorienterade bitmappsindex som gör det möjligt att snabbt beräkna aggregerade mått. Den har en omfattande filtreringsmotor som möjliggör kraftfull segmentering/målgruppsanalys. Och det har en god förståelse för sekvensen bland datapunkter som är användbar när det gäller att analysera beteenden över dessa datapunkter (i den ordning som saker och ting inträffade) och för att tilldela attribuering med olika, komplexa modeller.

* **Snabb användning av komplex målning och komplexa filter**: Rapporteringsmotorn arbetar med delvis ordnade hierarkiska datauppsättningar (till exempel person -> sessioner -> händelser). Alla data för ett objekt på den översta nivån (enskilda profiler) finns på en enda bearbetningsnod för korrekta resultat. Den här partitioneringen gör att du snabbt kan använda komplexa målningar och filter. Komplexa åtgärder som sessionisering, attribuering, tillståndskänslig beständighet för dataattribut och komplexa datamanipuleringsalternativ utförs i stor skala med snabb rapporteringstid. I BI-världen kräver dessa typer av åtgärder vanligtvis att nya OLAP-kuber skapas för varje användningsfall. CJA:s rapportmotor ger ohanterlig åtkomst till hela datauppsättningen för varje fråga, vilket resulterar i fullständigt korrelerade data utan att det krävs någon kuggning i förväg.

* **Effektiv fråga om komplexa dataströmmar**: En av de största skillnaderna i rapporteringsmotorn jämfört med traditionella SQL- och NoSQL-databaser är möjligheten att fastställa predikat baserat på sekvensorienterade relationer på en grundläggande nivå. Dessa grundläggande frågeåtgärder kan titta på postströmmen, som består av många sammanflätade (och till och med kapslade) sekvenser. De utför en fråga mot alla dessa sammanflätade dataströmmar med samma effektivitet som en enda sammanhängande sekvensåtgärd.

* **Utformad för att snabbt besvara stora frågor**: Rapporteringsmotorn är inte lika generell som traditionella big data-system. Den är dock särskilt utformad för att svara på frågor som omfattar miljontals eller till och med miljarder poster (händelsedata/upplevelsehändelser), vanligtvis på mindre än en sekund. Till skillnad från andra stora datasystem gör den inte detta genom att sampla data eller genom att förberäkna svaren på alla frågor som du tror att du kan ställa. I stället kan de snabbt beräkna svaren för att ge stöd åt interaktiva frågetillfällen. Denna specifika utformning av CJA:s rapporteringsmotor gör det lättare att få tillgång till data snabbt och snabbt för pågående analyser och undersökningar, vilket gör att ni kan få insikter och förståelse för kundresor.

* **Fungerar som en headless BI-lösning**: Du definierar mått, mätvärden, filter på ett ställe, och sedan kan alla CJA-klienter (inklusive vårt publika CJA API) få åtkomst till dessa komponenter. Detta gör att komplexa frågor tas bort från slutanvändarna och garanterar att resultatet blir detsamma, oavsett vilken rapporterings- eller visualiseringsklient du använder.

## CJA:s unika visualiseringsfunktioner

Rapporteringsmotorn är avgörande för CJA så att ni kan interagera med och agera på alla kundresedata i den rapporteringsmotorn. CJA har en omfattande uppsättning komponenter som gör att du kan göra detta visuellt och genom att dra och släppa. Med BI-visualiseringsverktyg kan du utforska inom gränserna för SQL-förberedda data (som definieras av IT). CJA gör det möjligt att dela upp och dela upp och dela upp så mycket du vill, utan att behöva gå tillbaka till IT för att skapa ytterligare en SQL-vy.

&quot;Progressivt&quot; är ett nyckelbegrepp här: Till skillnad från de flesta visualiseringar i BI-verktyg gör det visuella dra-och-släpp-gränssnittet i CJA att du kontinuerligt kan dela upp dina data efter dina specifika behov: kan du interaktivt skapa visuella frågor med relevanta mått, dimensioner, filter (segment), beräkningar, tidslinjer, anteckningar och andra analysvärden.

De inbyggda visualiseringskomponenterna är smarta funktioner som:

* **Virtuella analysfunktioner** som [Analysidentifiering](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) som använder prediktiva algoritmer och maskininlärning för att ge insikter i vad som driver ovanliga beteenden i era data.

* **Avancerade analysfunktioner** som fokuserar specifikt på kundreseinsikter, som [flödesdiagram](/help/analysis-workspace/visualizations/c-flow/flow.md), [attribuerings-IQ](/help/analysis-workspace/attribution/overview.md), [utfallsdiagram](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)och [dimensionsindelning](/help/components/dimensions/t-breakdown-fa.md). Exempel på användningsklara visualiseringar är:

   * [Kundlojalitetsanalys via kohort-/latenstabeller](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), där du bara drar och släpper mätvärden/dimensioner i ett verktyg och du är klar på mindre än 30 sekunder,

   * [Utfall](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md) / [flöde](/help/analysis-workspace/visualizations/c-flow/create-flow.md) visualiseringar. Kan installeras på mindre än en minut.

   * [Attributionsmodeller](/help/analysis-workspace/attribution/algorithmic.md) som första beröring, sista beröring, deltagande, tidsminskning, till och med anpassade beröringar som tar några klick att ställa in.

* **Segmenteringsfunktioner i alla steg av din progressiva prospektering**: när du tycker att det är vettigt kan du publicera publiken i Experience Platform och därifrån till någon av de destinationer som stöds.

* **Yrkesställning** som är helt [anpassningsbar](/help/data-views/component-settings/persistence.md): bestämmer ni när en session, som en del av en kanal i en kundresa, börjar och slutar.

* **Curation and Democratization**: Kontrollpaneler som skapas i CJA kan vara:

   * [Kuraterad](/help/analysis-workspace/curate-share/curate.md) till andra individer i organisationen för kontinuerlig prospektering,
   * Exporterad till Excel med [Report Builder](/help/report-builder/report-buider-overview.md) (ett särskilt plugin-program),
   * [Delad](/help/analysis-workspace/curate-share/share-projects.md) i olika format, inklusive [PDF](/help/analysis-workspace/curate-share/download-send.md), [CSV](/help/analysis-workspace/curate-share/download-send.md) och via [dedikerad mobilapp](/help/mobile-app/home.md), till dem som är intresserade av slutrapporterna och/eller visualiseringarna.

Det är svårt att jämföra CJA:s visualiseringsfunktioner med vad BI-verktygen erbjuder på grund av de många olika visualiseringar som finns. Vissa BI-verktyg har mer avancerade visualiseringar, men CJA fokuserar på interaktiva och kompatibla visualiseringar av kundresan, som gör att du kan dela upp data på några sekunder utan att ta betalt för varje ytterligare fråga.


## Sammanfattning

CJA skiljer sig från BI-verktygen när det gäller hur det integrerar en optimerad rapportmotor som fokuserar på kundresan sömlöst med användarvänliga verktyg och komponenter för att utföra analyser och skapa rapporter och avancerade visualiseringar. Allt från ett och samma gränssnitt, utan att du behöver växla fram och tillbaka mellan frågemotorn och visualiseringsmiljön.
