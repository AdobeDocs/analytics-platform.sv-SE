---
title: Ange användarinställningar i Analysis Workspace
description: Du kan ange allmänna inställningar och projektinställningar för användare.
feature: CJA Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
source-git-commit: 2d96b246ecee6ce447b5a03216e093b71a83a8ac
workflow-type: tm+mt
source-wordcount: '3125'
ht-degree: 1%

---

# Användarinställningar

Du kan hantera inställningar för Analysis Workspace och dess relaterade komponenter för alla nya projekt eller paneler som du skapar. Befintliga projekt och paneler påverkas inte.

## Uppdatera inställningar

1. I Customer Journey Analytics går du till [!UICONTROL **Projekt**] landningssida, välj sedan [!UICONTROL **Inställningar**].

   ![Användarinställningar](assets/user-preferences.png)

1. Om du vill ha mer information om de tillgängliga inställningarna på varje flik kan du fortsätta med något av följande avsnitt i den här artikeln:

   * [Allmänna inställningar](#general-preferences)

   * [Projektinställningar](#project-preferences)

   * [Inställningar för frihandstabell](#freeform-table-preferences)

   * [Visualiseringsinställningar](#visualizations-preferences)

## Allmänna inställningar

Allmänna inställningar gäller för din CJA-upplevelse i webbläsaren.

| Inställningar | Alternativ |
| --- | --- |
| Landningssida | Välj vilken sida som ska visas som standardsida när du öppnar Adobe Analytics: <ul><li>Projektlista (standard)</li><li>Tomt projekt</li><li>Specifikt projekt valt från en lista</li></ul> |
| Visa tips | Visar tips i en blå ruta i det nedre högra hörnet av Analysis Workspace. <p>Det här alternativet är aktiverat som standard.</p> |
| Komponenter som visas i grupper med vänster skena | Välj hur många av varje komponent som ska visas på komponentmenyn i den vänstra listen. <p>Om du väljer 0 är komponenten inte längre tillgänglig från den vänstra listen på arbetsytorna.</p><p>Som standard visas fem komponenter för vart och ett av följande:</p> <ul><li>Mått</li><li>Mätvärden</li><li>Filter</li><li>Datumintervall</li></ul> <p>Mer information om komponenter i Analysis Workspace finns i [Komponenter - översikt](/help/components/overview.md).</p> |

## Projektinställningar

Du kan anpassa projektinställningarna för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt dessa inställningar finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan även anpassas för enskilda projekt, vilket beskrivs i [Projektöversikt](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

Klicka på de länkade inställningsrubrikerna för mer information och kontext om varje inställning.

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Visa** |  |  |
|  | [Visa densitet](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) | Välj hur mycket innehåll som ska visas på skärmen genom att minska den lodräta utfyllnaden av den vänstra listen, frihandstabeller och kohorttabeller. <ul><li>Kompakt</li><li>Bekväm</li><li>Utökad (standard)</li></ul> |
|  | [Färgpaletten](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html) | Välj den visualiseringsfärgpalett som används i Analysis Workspace. <ul><li>Paletter som tillhandahålls av Adobe (standard)</li><li>Paletten Villkorsstyrd formatering </li><li>Paletten Upp/ned (avvikande)<li>Egna paletter</li></ul> |
| **Data** |  |  |
|  | [Rapportsvit](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?#report-suite) | Välj var tabeller och visualiseringar ska hämta sina data. <ul><li>Senaste (standard)</li><li>Specifik rapportsvit som valts i en lista</li></ul> |
|  | [Kalender](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?#calendar) | Välj i en lista över: <ul><li>Intervall som tillhandahålls av Adobe (standard är denna månad)</li><li>Anpassade intervall</li></ul> |
|  | [Paneltyp](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) | <ul><li>Frihandsfigur (standard)</li><li>Tom</li><li>Snabba insikter</li></ul> |
|  | Antal upprepande instanser | Anger om upprepade instanser räknas i rapporter. Den här inställningen (när den är aktiverad) hanterar flera på varandra följande sidvyer till samma sida som flera sidvyer. När det är inaktiverat räknas de som en enda sidvy. <p>**Obs!** Den här inställningen påverkar endast vissa mått (t.ex. enkelsidiga besök) och den gäller inte för Flow- eller Fallout-visualiseringar.</p> |
|  | Nummerformat | <ul><li>1 000,00 (standard)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV-avgränsningstecken | <ul><li>Komma (standard)</li><li>Semikolon</li><li>Colon</li><li>Pipe</li><li>Period</li><li>Blanksteg</li><li>Tabb</li></ul> |
|  | Visa anteckningar | Välj om anteckningar ska visas i dina projekt. Mer information om anteckningar finns i [Översikt över anteckningar](/help/components/annotations/overview.md). |


## Inställningar för frihandstabell

Du kan anpassa inställningarna för frihandstabeller för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt dessa inställningar finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan även anpassas för enskilda tabeller.

Klicka på de länkade avsnittsrubrikerna för mer information och kontext om de tillgängliga inställningarna.

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Tabell** |  |  |
|  | Tabelltyp | <ul><li>Frihand</li><li>Table builder</li></ul> |
|  | Standardtabellmått | <ul><li>Förekomster</li><li>Unika besökare</li><li>Besök</li></ul> |
|  | Standardregisterdimension | Välj mellan Minute, Timme, Dag, Vecka, Månad, Kvartal eller År. |
|  | Justera datum | Välj det här alternativet om du vill justera datum från varje kolumn så att alla börjar på samma rad. |
| **[Kolumn](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** |  |  |
|  | Radbryt rubriktext | Gör att du kan radbryta rubriktexten i frihandstabeller så att rubrikerna blir mer läsbara och tabellerna mer delbara. Detta är användbart för .pdf-återgivning och för mått med långa namn. Aktiverat som standard. |
|  | Visa summor | Denna summa är vanligtvis lika med eller en delmängd av [!UICONTROL Grand Total]. Alla tabellfilter som används i frihandstabellen, inklusive [!UICONTROL Include None] alternativ. |
|  | Visa totalsummor | Denna summa representerar alla träffar som har samlats in, ibland kallade&quot;rapportsvitsummor&quot;. När ett segment används antingen på panelnivå eller i friformstabellen justeras det totala värdet så att alla träffar som matchar segmentvillkoren visas. Summan stöds inte för tabeller eller uppdelningar med [statiska rader](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
|  | Visa miniatyrdiagram | Visa eller dölj linjediagram längst ned i diagrammet. När teckenförklaringen är dold ändras den inte längre till att referera till raderna visuellt. |
|  | Nummer | Avgör om en cell visar/döljer det numeriska värdet för måttet. Om måttet till exempel är Sidvyer är det numeriska värdet antalet sidvyer för radobjektet. |
|  | Procent | Avgör om en cell visar/döljer procentvärdet för måttet. Om måttet till exempel är Sidvyer är procentvärdet antalet sidvyer för radobjektet delat med de totala sidvyerna för kolumnen.  Obs! Vi kan visa procenttal större än 100 % för att vara mer korrekta. Vi flyttar också det övre gränsvärdet till 1 000 % för att säkerställa att kolumnerna kan växa i för stora bredder. |
|  | Visa avvikelser <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Avgör om avvikelseidentifiering körs på värdena i den här kolumnen. |
|  | Tolka noll som inget värde | För celler med värdet 0 anger om en 0-cell eller en tom cell ska visas. Det här är användbart när du tittar på data för varje dag i en månad, och vissa dagar har inte inträffat än.  I stället för att visa 0 för framtida datum kan tomma celler visas i stället. Diagram följer även den här inställningen (d.v.s. de visar inte en linje eller en stapel med 0 värden när den här inställningen är markerad). |
|  | Bakgrund | Anger om en cell visar/döljer all cellformatering, inklusive stapeldiagrammet och villkorsstyrd formatering <ul><li>Stolpdiagram</li> Visar ett vågrätt stolpdiagram som representerar cellens värde i förhållande till totalvärdet för kolumnen. <li>Villkorsstyrd formatering</li>Mer information om villkorsstyrd formatering finns i&quot;Villkorsstyrd formatering&quot; i [Kolumninställningar](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
|  | Cellförhandsgranskning | Visar en förhandsvisning av hur varje cell visas med de valda formateringsalternativen. |
| **[Rad](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** |  |  |
|  | Uppdelning efter position | Välj det här alternativet om du vill att detaljerna ska ligga kvar vid objektets position i stället för själva objektet. Mer information om uppdelningar finns i [Dela upp dimensioner](/help/components/dimensions/t-breakdown-fa.md). |
|  | Procentberäkning | <ul><li>Kolumn</li><li>Rad</li></ul> |

## Visualiseringsinställningar

Du kan uppdatera visualiseringsinställningarna för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt dessa inställningar finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan också anpassas för individuella visualiseringar.

Klicka på de länkade avsnittsrubrikerna för mer information och kontext om de tillgängliga inställningarna.

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Allmänna standardinställningar** |  |  |
|  | Procenttal | Visar värden i procent för alla visualiseringar. |
|  | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för alla visualiseringar. |
|  | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln för alla visualiseringar. Detta kan vara användbart om du har en stor datauppsättning. |
|  | Visa dubbelaxel (om tillämpligt) | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
|  | Normalisering (om tillämpligt) | Tvingar måtten att ha samma proportioner. Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
|  | Fästpunkt Y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll, kommer diagrammets standardvärde att göra den nedre delen av y-axeln ICKE-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |
|  | Tillåt avvikelser att skala Y-axeln | Om du har flera mätvärden i ett diagram måste du hovra över varje avvikelse för att se konfidensintervallet för det måttet. För att göra visualiseringen mer läsbar skalas inte y-axeln automatiskt i konfidensintervallet för avvikelseidentifiering. Med det här alternativet kan konfidensintervallet skalförändra visualiseringen. <p>Mer information finns i [Visa avvikelser i Analysis Workspace](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md).</p> |
| **[Linjediagram](/help/analysis-workspace/visualizations/line.md)** |  |  |
|  | Procenttal | Visar värden i procent för linjevisualiseringar. |
|  | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för linjevisualiseringen. |
|  | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i linjevisualiseringen. Detta kan vara användbart om du har en stor datauppsättning. |
|  | Visa dubbelaxel (om tillämpligt) | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för det andra måttet). Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
|  | Normalisering (om tillämpligt) | Tvingar måtten att ha samma proportioner. Detta är praktiskt när plottade mätvärden har mycket olika förstoringsgrader. |
|  | Visa x-axel | Visar x-axeln i linjediagrammet. |
|  | Visa y-axel | Visar y-axeln i linjediagrammet. |
|  | Fästpunkt Y-axel | Om alla värden som är ritade i diagrammet ligger betydligt över noll, kommer diagrammets standardvärde att göra den nedre delen av y-axeln ICKE-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |
|  | Visa min | Täck över en minimivärdetikett för att snabbt markera värdena i ett mätresultat. Obs! Minsta värden hämtas från synliga datapunkter i visualiseringen, inte från hela uppsättningen värden i en dimension. |
|  | Visa max | lägg över en maxvärdetikett för att snabbt markera topparna i ett mätresultat. Obs! Maximivärdena härleds från synliga datapunkter i visualiseringen, inte från hela uppsättningen värden inom en dimension. |
|  | Visa trendlinje | Visa en regression eller en glidande medeltrendlinje i linjeserien. Trendlinjer hjälper till att beskriva ett tydligare mönster i data. |
| **[Kohort](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** |  |  |
|  | Kornighet | För trendvisualiseringar kan du ändra tidgranulariteten (dag, vecka, månad, kvartal eller år). Den här ändringen gäller även för datakälltabellen. |
|  | Visa endast procent | Tar bort talvärdet och visar bara procentvärdet. |
|  | Avrunda procent till närmaste heltal | Avrundar procentvärdet till närmaste heltal i stället för att visa decimalvärdet. |
|  | Visa genomsnittlig procentrad | Infogar en ny rad högst upp i tabellen och lägger sedan till medelvärdet för värdena i varje kolumn. |
|  | Förhandsgranska kohort | En förhandsvisning av hur färgpaletten visas i kohortvisualiseringen. |
|  | Kohortpalett | Den färgpalett som används i kohortvisualiseringen. |
| **[Kombinationsdiagram](/help/analysis-workspace/visualizations/combo-charts.md)** |  |  |
|  | Visa X-axel | Visar x-axeln i kombinationsdiagrammet. |
|  | Visa Y-axel | Visar y-axeln i kombinationsdiagrammet. |
|  | Visa streckade linjer | Visa streckade linjer i kombinationsdiagram. |
| **[Sammanfattning av nyckelmått](/help/analysis-workspace/visualizations/key-metric.md)** |  |  |
|  | Visningstyp för sammanfattning | <ul><li>Betonar procentuell ändring</li><li>Betonar talvärde</li></ul> |
|  | Visa miniatyrbilder | Visa eller dölj linjediagram längst ned i diagrammet. När teckenförklaringen är dold ändras den inte längre till att referera till raderna visuellt. |
|  | Visa max och min för miniatyrbilder | Visa lägsta och högsta värden i primära och jämförande raddiagram. |
|  | Visa jämförelse | Visa jämförelsedata. När det är dolt döljs både jämförelsetabellen och de sammanfattande ändringsobjekten. |
|  | Alternativ för talvärde | I [!UICONTROL **Sammanfattning av nyckelmått**] section <ul><li>Visa procentuell ändring</li><li>Visa rådifferens</li>Rådifferens mellan det totala värdet för måttet i det primära datumintervallet och det sekundära datumintervallet</ul> |
| **[Utfall](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** |  |  |
|  | Behållare | Gör att du kan växla mellan Besök och Besök för att analysera besökarbanan. Standardvärdet är Visitor. Dessa inställningar hjälper er att förstå besökarnas engagemang på besökarnivå (mellan besök) eller begränsa analysen till ett enda besök. <p>Följande alternativ är tillgängliga:</p> <ul><li>Gå in på</li><li>Besökare</li></ul> |
| **[Flöde](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** |  |  |
|  | Behållare | I [!UICONTROL **Flöde**] section <ul><li>Gå in på</li><li>Besökare</li></ul> |
|  | Radbryt etiketter | Etiketterna på Flow-elementen trunkeras normalt för att spara skärmutrymme, men du kan göra hela etiketten synlig genom att markera den här rutan. Standard = avmarkerat. |
|  | Inkludera upprepade förekomster | Flödesvisualiseringar baseras på instanser av en dimension. Den här inställningen ger dig möjlighet att inkludera eller exkludera upprepade instanser, t.ex. sidomladdning. Det går dock inte att ta bort upprepningar från Flow-visualiseringar som innehåller flervärdesdimensioner, som listVars, listProps, s.product, merchandising eVars osv. Standard = avmarkerat. |
|  | Visa verktygstips | Avgör om verktygstips som innehåller noddata ska visas när du hovrar över enskilda noder i en flödesvisualisering. |
|  | Antal kolumner | Anger hur många kolumner du vill ha i flödesdiagrammet. |
|  | Objekt utökade per kolumn | Hur många objekt du vill ha i varje kolumn. |
| **Staplade diagram** |  |  |
|  | 100 % staplad | Den här inställningen för staplade ytor, staplade staplar eller vågräta staplade visualiseringar gör att diagrammet blir en&quot;100 % staplade&quot; visualisering. <p>Mer information finns i [Stolpstreck och stapel](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Histogram](/help/analysis-workspace/visualizations/histogram.md)** |  |  |
|  | Antal fickor | Välj antalet dataintervall (bucket) i visualiseringen. Det högsta antalet bucklor är 50. <p>Mer information finns i [Histogram](/help/analysis-workspace/visualizations/histogram.md).</p> |
|  | Inventeringsmetod | Välj bland följande alternativ: <ul><li>Träff</li><li>Gå in på</li><li>Besökare</li></ul> <p>Om du till exempel använder det tillsammans med sidvyer kan du välja sidvyer per besökare, sidvyer för besök eller sidvyer per träff. För Träff används&quot;Förekomster&quot; som y-axelmått i en friformstabell.</p> |
| **[Sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md)** |  |  |
|  | Värde | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Procentuell ändring</li><li>Rådifferens</li></ul> |
|  | Procenttal | Visar värden i procent för visualiseringar av sammanfattningsändringar. |
|  | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för visualiseringen av Sammanfattningsändring. |
| **[Sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md)** |  |  |
|  | Procenttal | Visar värden i procent för visualiseringar av sammanfattningsnummer. |
|  | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för visualisering av sammanfattningsnummer. |
|  | Sammanfattningsvärde per | Välj mellan Max, Min, Medel, Median och Summa. |
|  | Förkortningsvärde | I [!UICONTROL **Sammanfattningsnummer**] section |
| **[Treemap-diagram](/help/analysis-workspace/visualizations/treemap.md)** |  |  |
|  | Procenttal | Visar värden i procent för Treemap-visualiseringar. |
|  | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i Treemaps visualisering. Detta kan vara användbart om du har en stor datauppsättning. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** |  |  |
|  | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för Vennvisualiseringen. |
| **[Spridning](/help/analysis-workspace/visualizations/scatterplot.md)** |  |  |
|  | Procenttal | Visar värden i procent för Spridningsvisualiseringar. |
|  | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för Spridningsvisualiseringen. |
|  | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i Spridningsvisualiseringen. Detta kan vara användbart om du har en stor datauppsättning. |
|  | Fästpunkt y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll, kommer diagrammets standardvärde att göra den nedre delen av y-axeln ICKE-ZERO. Om du markerar den här rutan kommer y-axeln att tvingas till noll (och diagrammet ritas om). |

## Företagsinställningar

>[!AVAILABILITY]
>
>Funktionen Public Access Links som beskrivs i det här avsnittet är i den begränsade testfasen av versionen och är kanske inte tillgänglig än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).

Du kan uppdatera företagsinställningarna som gäller för alla användare och projekt i organisationen. Mer information om hur du kommer åt dessa inställningar finns i [Uppdatera inställningar](#update-preferences).

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Projektdelning** |  |  |
|  | Tillåt endast delning med Workspace-användare | <p>När det här alternativet är aktiverat kan användare i organisationen inte se alternativet &quot;Dela med någon&quot; på menyn Dela. Det innebär att användare inte kan dela projekt med personer som inte har ett Analysis Workspace-konto i organisationen enligt beskrivningen i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md).</p><p>Det här alternativet är inaktiverat som standard för alla organisationer utom de inom hälso- och sjukvården. </p><p>Tänk på följande när du aktiverar eller inaktiverar det här alternativet:</p> <ul><li><p>När du aktiverar det här alternativet kan personer som tidigare fått åtkomst till ett projekt via delningsalternativet Dela med vem som helst inte längre få åtkomst till projektet.</p></li><li><p>Om det här alternativet är aktiverat (för att endast tillåta delning med Workspace-användare) och sedan inaktiverat (för att tillåta delning med vem som helst), kommer personer som tidigare fått åtkomst till ett projekt via delningsalternativet &quot;Dela med vem som helst&quot; inte automatiskt att få tillgång till projektet. I det här fallet måste användaren som delade projektet aktivera [!UICONTROL **Länken är aktiv**] som är tillgängligt när du delar ett projekt med någon ([!UICONTROL **Dela**] > [!UICONTROL **Dela med vem du vill**]), enligt beskrivningen i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md).</p></li><li><p>**För organisationer inom hälso- och sjukvården:** Det här alternativet är aktiverat och nedtonat som standard. Innan du kan inaktivera det här alternativet så att användare kan använda delningsalternativet Dela med vem som helst måste du först lägga till [!UICONTROL **Dela projektlänkar med vem som helst**] behörighet (finns under [!UICONTROL **Rapporteringsverktyg**]) i Adobe Admin Console. När behörigheten har lagts till kan du inaktivera det här alternativet och sedan godkänna det juridiska meddelandet. Mer information om hur du lägger till behörigheter i Admin Console finns i [Hantera produktbehörigheter i Admin Console](https://helpx.adobe.com/enterprise/using/manage-permissions-and-roles.html).</p></li> |
|  | Kräv autentisering av Experience Cloud | <p>När det här alternativet är aktiverat måste personer som får åtkomst till ett projekt från alternativet &quot;Dela med vem som helst&quot; i Analysis Workspace autentisera med sina inloggningsuppgifter för Experience Cloud.</p> <p>När det här alternativet är aktiverat aktiveras alternativet&quot;Kräv autentisering av Experience Cloud&quot; varje gång en användare delar ett projekt med delningsalternativet&quot;Dela med vem som helst&quot; i delningsdialogrutan och det kan inte inaktiveras av den användare som delar projektet. (Information om hur användare kan dela projekt med vem som helst finns i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md).)</p> <p>Tänk på följande när du aktiverar det här alternativet:</p><ul><li><p>När du aktiverar det här alternativet inaktiveras alla projekt som tidigare delats med delningsalternativet &quot;Dela med vem som helst&quot; och som inte har alternativet &quot;Kräv autentisering av Experience Cloud&quot; aktiverat.</p></li> <li><p>Om det här alternativet är aktiverat (för att kräva autentisering från Experience Cloud) och sedan inaktiverat (för att alla som har länken ska kunna komma åt projektet), kommer personer som tidigare fått åtkomst till ett projekt via delningsalternativet &quot;Dela med vem som helst&quot; inte automatiskt att få tillgång till projektet. I det här fallet måste användaren som delade projektet aktivera alternativet &quot;Länka är aktiv&quot; som är tillgängligt när ett projekt delas med någon ([!UICONTROL **Dela**] > [!UICONTROL **Dela med vem du vill**] > [!UICONTROL **Länken är aktiv**]), enligt beskrivningen i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md).</p></li> <li><p>Det här alternativet är bara tillgängligt om enkel inloggning har implementerats i din organisation. Mer information om hur systemadministratörer kan aktivera enkel inloggning för din organisation finns i [Konfigurera identitet och enkel inloggning](https://helpx.adobe.com/enterprise/using/set-up-identity.html){target=_blank}.</p><p>Om enkel inloggning har konfigurerats för din organisation kontrollerar du om någon typ av autokontoskapande har implementerats i konsolen. Vanligtvis konfigurerar en systemadministratör detta enligt beskrivningen i [Aktivera automatisk kontogenerering](https://helpx.adobe.com/enterprise/using/automatic-account-creation.html){target=_blank}.</p></li><li><p>Om organisationen befinner sig i en bransch där det krävs HIPAA-kompatibilitet aktiveras det här alternativet automatiskt och kan inte inaktiveras.</p></li></ul> |

{style="table-layout:auto"}

## Återställ standardinställningar

Du kan återställa alla dina användarinställningar till standardinställningarna. Detta påverkar inte administratörsinställningarna på fliken Företag.

Det går inte att ångra den här åtgärden.

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] **>** [!UICONTROL **Inställningar**].

   ![Användarinställningar](assets/user-preferences.png)

1. I det övre högra hörnet väljer du **[!UICONTROL Restore defaults]**.

1. Välj **[!UICONTROL Restore defaults]**.

## [!UICONTROL Dark theme]

Om du föredrar en mörk bakgrund för användargränssnittet i Adobe Analytics kan du växla till [!UICONTROL Dark theme].

1. Klicka på användarikonen Experience Cloud längst upp till höger.

   ![mörkt tema](assets/dark-theme.png)

1. Flytta **[!UICONTROL Dark theme]** till höger.

