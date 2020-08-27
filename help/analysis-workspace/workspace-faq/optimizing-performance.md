---
description: 'null'
title: Optimera prestanda för Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: d49e07d14d1b202d9cc12f42d60083c052a1c364
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 0%

---


# Optimera prestanda för Analysis Workspace

Vissa faktorer kan påverka ett projekts prestanda inom Analysis Workspace. Det är viktigt att veta vilka dessa bidragsgivare är innan du börjar bygga ett projekt så att du kan planera och bygga projektet på bästa möjliga sätt. Nedan visas en lista över faktorer som påverkar prestanda och bästa praxis för optimering av dina projekt. Prestandan i Analysis Workspace är en av Adobes främsta prioriteringar och något som vi fortsätter att förbättra varje dag.

## Segmentlogikens komplexitet

Intrikala segment kan ha en betydande inverkan på projektresultaten. Faktorer som ökar komplexiteten i ett segment (i fallande kollisionsordning) omfattar:

* Operatorer för &quot;innehåller,&quot;, &quot;innehåller något av&quot;, &quot;matchar&quot;, &quot;börjar med,&quot; eller &quot;slutar med&quot;
* Sekventiell segmentering, särskilt när dimensionsbegränsningar (inom/efter) används
* Antal unika dimensioner som används i segmentet (t.ex. Page = &#39;A&#39; när sidan har 10 unika objekt blir snabbare än Page = &#39;A&#39; när sidan har 10000 unika objekt)
* Antal olika dimensioner som används (t.ex. Page = &#39;Home&#39; och Page = &#39;Search results&#39; är snabbare än eVar 1 = &#39;red&#39; och eVar 2 = &#39;blue&#39;)
* Många ELLER-operatorer (i stället för OCH)
* Kapade behållare som varierar i omfattning (t.ex. &quot;Träff&quot; inuti &quot;Besök&quot; inuti &quot;Besök&quot;)

**Bästa praxis för logisk komplexitet**

Vissa av komplexitetsfaktorerna kan inte förhindras, men tänk på möjligheterna att minska komplexiteten hos dina segment. I allmänhet, ju mer specifika du kan vara med dina segmentkriterier, desto bättre. Exempel:

* Med containrar är det snabbare att använda en enda behållare överst i segmentet än en serie kapslade behållare.
* Med operatorer blir &quot;lika&quot; snabbare än &quot;innehåller&quot; och &quot;lika med&quot; snabbare än &quot;innehåller&quot;.
* Med många kriterier är OCH-operatorer snabbare än en serie ELLER-operatorer. Sök också efter möjligheter att reducera många ELLER-satser till en enda &quot;lika med&quot;-sats.

Dessutom [klassificeringar](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html) kan hjälpa till att konsolidera många värden till koncisa grupper som du sedan kan skapa segment från. Segmentering i klassificeringsgrupper ger prestandafördelar över segment som innehåller många OR-satser eller &quot;innehåller&quot;-kriterier.

## Intervall för begärda data

Det dataintervall som begärs i ett projekt påverkar Analysis Workspace-prestanda.

**Bästa praxis för datumintervall**

Dra inte in mer data än vad du behöver. Begränsa panelkalendern till relevanta datum för analysen eller använd datumintervallskomponenter (lila komponenter) i frihandstabellerna. Datumintervall som används i en tabell åsidosätter panelens datumintervall. Du kan till exempel lägga till förra månaden, förra veckan och i går till tabellkolumnerna för att begära dessa specifika dataintervall. Mer information om hur du arbetar med datumintervall i Analysis Workspace finns på [det här videoklippet](https://www.youtube.com/watch?v=MIkT6FZ5gKk) .

Minimera antalet jämförelser över året som används i projektet. När en jämförelse mellan år och år beräknas, ser den ut över de 13 fullständiga månaderna av data mellan de berörda månaderna. Detta har samma effekt som att ändra panelens datumintervall till 13 månader.

## Antal visualiseringar

Antalet visualiseringar som ingår i ett projekt kommer att påverka analysens arbetsfärds allmänna respons. Detta beror på att varje visualisering, oavsett om det är en tabell eller ett diagram, har en datakälla som måste begäras.

**Bästa praxis för antal visualiseringar**

Minska antalet visualiseringar i projektet. Analysarbetsytan bearbetar mycket bakom kulisserna för varje visuell bild som du lägger till, så prioriterar de bilder som är viktigast för rapportens konsument och delar ut stödjande bilder till ett separat, mer detaljerat projekt om det behövs.

## Synualiseringarnas komplexitet (segment, mått, filter)

Den typ av visualisering (t.ex. fallout jämfört med ett frihandsregister) som läggs till i ett projekt i sig påverkar inte projektprestanda särskilt mycket. Det är visualiseringens komplexitet som kommer att öka bearbetningstiden. Faktorer som gör visualiseringen mer komplicerad omfattar:

* Intervall för begärda uppgifter enligt ovan
* Antal segment som tillämpats. till exempel segment som används som rader i en frihandstabell
* Användning av komplicerade segment
* [Statiskt objekt](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) rader eller kolumner i frihandstabeller
* Filter som används på rader i frihandstabeller
* Antal mått som ingår, särskilt beräknade mått som använder segment

**Bästa praxis för visualiseringens komplexitet**

Om du upptäcker att dina projekt inte laddas så snabbt som du vill kan du prova att ersätta vissa segment med eVars och filter, om det är möjligt.

Om du hela tiden använder segment och beräknade mått för datapunkter som är viktiga för ditt företag bör du överväga att förbättra implementeringen för att hämta dessa datapunkter mer direkt. Om du använder en tagghanterare som Adobe Experience Platform Launch och Adobes bearbetningsregler kan implementeringsändringarna göras snabbt och enkelt att implementera. För att bättre förstå hur man förenklar komplicerade segment, se &quot;Segment Logics komplexitet&quot; ovan.

## Antal paneler

En panel kan innehålla många visualiseringar, vilket innebär att antalet paneler också kan påverka analysytans övergripande respons.

**Bästa praxis för antal paneler**

Försök inte lägga till allt i ett projekt utan skapa specifika projekt som tjänar ett specifikt syfte eller en grupp av intressenter. Använd taggar för att organisera projekt i centrala teman och dela relaterade projekt med grupper av intressenter.

Om mer organisation av projekten önskas, kom ihåg att [direktkoppling](https://www.youtube.com/watch?v=6IOEewflG2U) för projektet är ett alternativ. Skapa ett internt projektindex så att intressenterna lättare kan hitta vad de behöver.

Om många paneler behövs i ett projekt komprimerar du panelerna innan du sparar och delar. När ett projekt läses in läser Analysis Workspace bara in innehåll för de expanderade panelerna. Komprimerade paneler läses inte in förrän användaren expanderar dem. Detta tillvägagångssätt bidrar på två sätt:

* Komprimerade paneler spara vid en projekts totala inläsningstid
* Kollapserade paneler är ett bra sätt att organisera dina projekt på ett logiskt sätt för betänkandets konsument

## Rapportsvitstorlek

Rapportsvitens storlek kan verka som en drivkraft, men i själva verket spelar den bara en liten roll för projektprestanda på grund av hur Adobe hanterar databehandling. Det kan finnas undantag från denna regel. samråda med implementeringsteamet eller en Adobe-expert för att ta reda på om det finns några implementeringsförbättringar som kan göras för att förbättra den övergripande erfarenheten i Adobe Analytics.

## Antal användare som samtidigt ansluter till Analysis Workspace

Antalet användare som samtidigt ansluter till Analysis Workspace eller specifika projekt har ingen väsentlig inverkan på Analysis Workspace-prestanda om användare använder olika rapportuppsättningar. Om samtidiga användare använder samma rapportsvit påverkas prestanda.

## Vanliga felmeddelanden i Analysis Workspace

Det kan uppstå fel när du interagerar med Analysis Workspace. Fel kan inträffa av flera skäl och de vanligaste är de som anges nedan.

| Felmeddelande | Varför inträffar detta? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | Din organisation försöker köra för många samtidiga förfrågningar mot en specifik rapportsvit. Medverkare till det här felet är API-begäranden, schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapportbegäranden. Vi rekommenderar att era krav och tidsplaner för rapportpaketet fördelas jämnare över dagen. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe har ett problem som måste lösas. Vi rekommenderar att du skickar felkoden via en kundvårdsbegäran. |
| `The request is too complex.` | Din rapporteringsbegäran är för stor och kan inte utföras. Medverkare till det här felet är timeout på grund av begärans storlek, för många matchade objekt i ett segment eller sökfilter, för många mått som ingår, inkompatibla dimensioner och metriska kombinationer osv. Vi rekommenderade att du skulle förenkla din begäran. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | Vi rekommenderar att du begränsar söktextkriterierna och försöker göra om begäran. |
| `This dimension does not currently support non-default attribution models.` | Vi rekommenderar att du ersätter dimensionen i tabellen med en som är kompatibel med [Attribut-IQ](../attribution/overview.md). |
| `Your request failed as a result of too many columns or pre-configured rows.` | Vi rekommenderar att du tar bort några av kolumnerna eller raderna, eller att du överväger att dela upp dem i separata visualiseringar. |
