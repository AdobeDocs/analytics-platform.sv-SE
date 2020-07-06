---
description: 'null'
title: Optimera prestanda för Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 0%

---


# Optimera prestanda för Analysis Workspace

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Vissa faktorer kan påverka ett projekts prestanda i Analysis Workspace. Det är viktigt att du vet vad dessa medarbetare är innan du börjar bygga ett projekt, så att du kan planera och bygga projektet på det optimala sättet. Nedan visas en lista med faktorer som påverkar prestanda och bästa praxis för optimering av projekt. Prestanda i Analysis Workspace är en av Adobes främsta prioriteringar och något som vi fortsätter att förbättra varje dag.

## Segmentlogikens komplexitet

Integrerade segment kan ha en betydande inverkan på projektresultatet. Faktorer som ökar komplexiteten i ett segment (i fallande effektordning) är bland annat:

* Operatorer för &quot;contains&quot;, &quot;contains any of&quot;, &quot;match&quot;, &quot;starting with&quot; eller &quot;ends with&quot;
* Sekventiell segmentering, särskilt när dimensionsbegränsningar (inom/efter) används
* Antal unika dimensionsobjekt inom dimensioner som används i segmentet (t.ex. Sida = &#39;A&#39; när sidan har 10 unika objekt blir snabbare än Sida = &#39;A&#39; när sidan har 100000 unika objekt)
* Antal olika dimensioner som används (t.ex. Page = &#39;Home&#39; och Page = &#39;Search results&#39; är snabbare än eVar 1 = &#39;red&#39; och eVar 2 = &#39;blue&#39;)
* Många OR-operatorer (i stället för AND)
* Kapslade behållare som varierar i omfång (t.ex. &quot;Träff&quot; inuti &quot;Besök&quot; inuti &quot;Besök&quot;)

**Bästa tillvägagångssätt för logikkomplexitet**

Vissa av komplexitetsfaktorerna kan inte förhindras, men tänk på möjligheter att minska komplexiteten i era segment. Ju mer specifik du kan vara med dina segmentkriterier, desto bättre. Exempel:

* Med behållare blir det snabbare att använda en enda behållare högst upp i segmentet än en serie kapslade behållare.
* Med operatorer blir&quot;lika&quot; snabbare än&quot;innehåller&quot;, och&quot;är lika med&quot; är snabbare än&quot;innehåller något av&quot;.
* Med många kriterier blir AND-operatorer snabbare än en serie OR-operatorer. Du kan också söka efter möjligheter att minska många OR-satser till en enda &quot;motsvarar&quot;-programsats.

Dessutom kan [klassificeringar](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html) hjälpa till att konsolidera många värden till koncisa grupper som du sedan kan skapa segment från. Segmentering i klassificeringsgrupper ger prestandafördelar jämfört med segment som innehåller många OR-satser eller&quot;contains&quot;-kriterier.

## Intervall med begärda data

De data som begärs i ett helt projekt påverkar Analysis Workspace prestanda.

**Bästa tillvägagångssätt för dataintervall**

Dra inte in mer data än du behöver när det är möjligt.

Kom ihåg att datumintervall (lila komponenter) åsidosätter panelens datumintervall. Om du använder olika datumintervall som kolumner (t.ex. sista månaden, sista veckan och sista kolumnen) behöver alltså inte panelens datumintervall omfatta alla kolumndatumintervall. Den kan helt enkelt ställas in på igår eftersom de dataområden som används i frihandstabellen åsidosätter panelen. Mer information om hur du arbetar med datumintervall i Analysis Workspace finns i [den här videon](https://www.youtube.com/watch?v=ybmv6EBmhn0) .

Använd [datumjämförelsealternativ](/help/components/date-ranges/time-comparison.md) för att hämta in de specifika tidsperioderna för data som du vill jämföra. Om du t.ex. vill visa data för förra månaden jämfört med samma månad förra året, i stället för att ställa in panelen på de sista 13 månaderna, använder du bara alternativet för att jämföra tidsperioder för att visa resultatet för varje år.

## Antal visualiseringar

Antalet grafvisualiseringar i ett projekt kommer att påverka Analysis Workspace allmänna svarstider.

**Bästa praxis för antal visualiseringar**

Minska antalet visualiseringar i projektet. Analysis Workspace arbetar mycket bakom kulisserna för varje bild som ni lägger till, så prioritera de bilder som är viktigast för rapportens konsument och dela upp stödet till ett separat, mer detaljerat projekt om det behövs.

## Komplexitet i visualiseringar (segment, mätvärden, filter)

Den typ av visualisering (t.ex. bortfall jämfört med frihandstabell) som läggs till i ett projekt påverkar inte projektets prestanda särskilt mycket. Det är komplexiteten i den visualisering som kommer att öka bearbetningstiden. Faktorer som gör en visualisering mer komplicerad:

* Intervall av begärda uppgifter enligt ovan
* Antal segment som används. till exempel segment som används som rader i en frihandstabell
* Användning av komplicerade segment
* Statiska objektrader eller kolumner i frihandstabeller
* Filter som används på rader i frihandstabeller
* Antal mätvärden som ingår, särskilt beräknade mätvärden som använder segment

**Bästa sättet att se på komplexitet**

Om du märker att dina projekt inte läses in så snabbt du vill kan du ersätta vissa segment med eVars och Filter där det är möjligt.

Om du hela tiden använder segment och beräknade värden för datapunkter som är viktiga för ditt företag bör du förbättra implementeringen för att hämta in dessa datapunkter mer direkt. Användning av en tagghanterare som Adobe Experience Platform Launch och Adobes bearbetningsregler kan göra implementeringsändringar snabba och enkla att implementera. Mer information om hur du förenklar komplicerade segment finns i&quot;Segmentlogikens komplexitet&quot; ovan.

## Antal paneler

En panel kan innehålla många visualiseringar, och därför kan antalet paneler också påverka Analysis Workspace allmänna svarstider.

**Bästa praxis för antal paneler**

Försök inte att lägga till allt i ett projekt, utan i stället skapa distinkta projekt som har ett specifikt syfte eller en grupp intressenter. Använd taggar för att ordna projekt i viktiga teman och dela relaterade projekt med grupper av intressenter.

Om du vill organisera fler projekt bör du tänka på att [direktlänkning](https://www.youtube.com/watch?v=6IOEewflG2U) till projektet är ett alternativ. Skapa ett internt projektindex så att intressenter enklare kan hitta det de behöver.

Om flera paneler behövs i en arbetsyta bör du komprimera panelerna innan du sparar och delar dem. När ett projekt har lästs in läser Analysis Workspace bara in innehåll för de utökade panelerna. Komprimerade paneler läses inte in förrän användaren expanderar dem. Detta tillvägagångssätt hjälper på två sätt:

* Komprimerade paneler sparar tid på den totala inläsningstiden för ett projekt
* Komprimerade paneler är ett bra sätt att ordna dina projekt på ett logiskt sätt för rapportens konsument

## Rapportsvitens storlek

Rapportsvitens storlek kan tyckas vara en drivkraft, men i själva verket spelar den bara en liten roll i projektresultatet på grund av hur Adobe hanterar databearbetningen

## Antal användare som samtidigt använder Analysis Workspace

Antalet användare som samtidigt använder Analysis Workspace eller särskilda projekt påverkar inte Analysis Workspace prestanda i någon större utsträckning, om användare använder olika rapportsviter. Om samtidiga användare använder samma rapportserie påverkas prestandan.

## Vanliga felmeddelanden i Analysis Workspace

Fel kan uppstå vid interaktion med Analysis Workspace. Fel kan uppstå av flera orsaker och de vanligaste är de som anges nedan.

| Felmeddelande | Varför inträffar detta? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | Din organisation försöker köra för många samtidiga begäranden mot en viss rapportserie. Medarbetare till det här felet är API-begäranden, schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapporteringsförfrågningar. Vi rekommenderar att era förfrågningar och tidsplaner för rapportsviten sprids jämnare under dagen. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe har ett problem som behöver lösas. Vi rekommenderar att du skickar felkoden via en kundtjänst. |
| `The request is too complex.` | Din rapporteringsbegäran är för stor och kan inte utföras. Medarbetare till det här felet är timeout på grund av begärans storlek, för många matchade objekt i ett segment eller sökfilter, för många mätvärden, inkompatibla mått- och mätkombinationer osv. Vi rekommenderar att du förenklar din begäran. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | Vi rekommenderar att du begränsar sökvillkoren och försöker utföra begäran igen. |
| `This dimension does not currently support non-default attribution models.` | Vi rekommenderar att du ersätter dimensionen i tabellen med en som är kompatibel med [Attribution IQ](../attribution/overview.md). |
| `Your request failed as a result of too many columns or pre-configured rows.` | Vi rekommenderar att du tar bort vissa kolumner eller rader, eller att du delar upp dem i separata visualiseringar. |
