---
description: Du kan hämta data från Analysis Workspace genom att kopiera dem eller i PDF- och CSV-format.
title: Hämta Customer Journey Analytics-data
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 9a15cb4d771892ff656fe72b8e53d890a3fd99f7
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 0%

---

# Hämta Customer Journey Analytics-data

Du kan ladda ned Customer Journey Analytics-data till din personliga arbetsstation. Detta kan vara i form av kopierade data, CSV eller PDF. Ett PDF-program är att föredra om du vill att visualiseringar ska ingå i den hämtade filen. CSV och kopierade data är att föredra om du bara vill ha textdata.

Det finns även andra metoder för att exportera Customer Journey Analytics-data, vilket beskrivs i [Översikt över export](/help/analysis-workspace/export/export-project-overview.md).

## Hämta som CSV eller PDF {#download-project}

Tänk på följande när du hämtar projekt:

* När du hämtar projekt som en CSV- eller PDF-fil kan projektet sparas eller sparas utan att sparas när du begär en projekthämtning. Endast sparade projekt kan dock vara [schemalagda](/help/analysis-workspace/export/t-schedule-report.md).

* När du laddar ned projekt som PDF:
   * Det kan ta flera minuter att exportera nedladdningar eftersom projektet körs på nytt på Adobe-servrar innan det renderas i PDF-format. Vi rekommenderar att du inte lämnar projektet förrän PDF har hämtats i webbläsaren. Du kan dock fortsätta att göra ändringar i projektet medan du väntar. Om en PDF tar längre tid än fem minuter att återge uppmanas du att skicka den via e-post i stället.
   * Hämtningar återges som en sida utan sidnumrering.
   * PDF-återgivningar innehåller det som finns på sidan i Workspace. Om ett projekt har visualiseringar och paneler i anpassad storlek måste du ändra dem så att de storleksändras automatiskt (knappen i det övre högra hörnet) så att det inte finns något trunkerat innehåll.
   * Eventuella [hyperlänkar](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) som finns i frihandstabeller fungerar inte i det hämtade PDF-programmet.

Så här hämtar du ett projekt som en CSV- eller PDF-fil:

1. Gör något av följande, beroende på vilket format du vill att hämtningen ska vara i:

   * **PDF:** Välj **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.

     Välj det här alternativet om du vill att den hämtade filen ska innehålla alla tabeller och visualiseringar som visas i projektet.

   * **CSV:** Välj **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

     Välj det här alternativet om du vill att den hämtade filen ska vara oformaterad.

   ![Listrutan Projekt med alternativen Hämta CSV och Hämta PDF markerade.](assets/download-project.png)

1. (Villkorligt) Om du väljer att hämta en PDF-fil visas ett meddelande när projektet är klart att hämtas. Välj [!UICONTROL **Hämta**].

## Kopiera till Urklipp (snabbtangent: Ctrl+C) {#copy-data}

Med högerklicksalternativet **[!UICONTROL Copy to clipboard]** kan du snabbt kopiera Customer Journey Analytics-data från Workspace och klistra in dem i ett verktyg från tredje part.

* Om du vill att den visade tabellen ska kopieras högerklickar du på tabellrubriken och väljer **Kopiera data till Urklipp**.
* Om du vill att en delmängd av data ska kopieras gör du en markering i tabellen och högerklickar sedan > **Kopiera markering till Urklipp**.

>[!TIP]
>
>Du kan använda snabbtangenten `Ctrl+C` för att kopiera markeringen till Urklipp och sedan använda `Ctrl+V` för att klistra in den i ett verktyg från tredje part.


![Alternativet Kopiera markering till Urklipp. ](assets/copy-selection.png)

## Hämta som CSV {#download-data}

Med högerklicksalternativet **[!UICONTROL Download data as CSV]** kan du hämta en tabell med Customer Journey Analytics-data eller datakällan för en visualisering som en CSV-fil.

* Högerklicka och välj **[!UICONTROL Download data as CSV]** i huvudet på en tabell eller visualisering. Detta hämtar de visade Customer Journey Analytics-data i tabellen eller den underliggande datakällan för en visualisering som en CSV-fil.

  >[!NOTE]
  >
  >  Obs! Kartvyn stöder inte det här alternativet.


* Högerklicka i en tabell och välj **[!UICONTROL Download selection as CSV]**. Endast markeringen laddas ned med det här alternativet, i motsats till den fullständiga tabellen som visas.

![Alternativet Hämta data som CSV.](assets/download-data-viz.png)

## Hämta objekt som CSV {#download-items}

Om du vill analysera fler än de 400 synliga dataraderna i en tabell högerklickar du på tabellrubriken eller valfri rad och väljer **Hämta objekt som CSV (_Dimension namn_)**. Med det här alternativet exporteras upp till 50 000 dimensionsobjekt (baserat på tabellsortering) för den valda dimensionen med sorteringsalternativ och filter. Om du väljer det här alternativet överst i tabellen exporteras den första dimensionen i tabellen. Även om inga begränsningar används i friformstabellen rekommenderar vi att alternativet Hämta objekt används i tabeller med mindre än 20 kolumner för att optimera prestandan.

>[!TIP]
>
> Om din dimension överstiger 50 000 objekt hämtar du filen med olika sorteringsvärden eller använder ett segment. Du kan t.ex. sortera efter besök i en nedladdning och sedan stigande efter besök i en andra nedladdning. Det här tipset kan hjälpa dig att hämta objekt med längre svans.

Du kan utföra flera uppgifter samtidigt i projektet och till och med navigera till ett nytt Workspace-projekt på samma flik medan hämtningen pågår. Hämtningen pausas om du öppnar en ny flik i webbläsaren. Hämtningen avbryts om du lämnar Workspace helt eller stänger webbläsarfliken.

![Alternativet Hämta objekt som CSV (sida).](assets/download-items.png)

### Nedladdad objektfil {#items-file}

Tabellens funktioner kommer att tillämpas på den hämtade filen enligt följande:

* Alla panelsegment används som filter.
* Uppdelningar **ovanför** den valda dimensionen i tabellen används som filter ovanför varje kolumn.
* Uppdelningar **nedanför** av den valda dimensionen i tabellen tas bort.

I exemplet ovan hämtas sidobjekt med panelsegmentet (kunder med nya besökare) och komponenterna ovan (marknadsföringskanal = e-post) som filter, och komponenterna nedan (mobilenhetstyp) tas bort från den hämtade CSV-filen.

![Den hämtade CSV-filen som öppnats i Excel.](assets/downloaded-file.png)

### Hämta meddelanden {#notifications}

När filen laddas ned visas ett informationsmeddelande med förloppet. Du kan när som helst avbryta hämtningen genom att klicka på **[!UICONTROL Cancel download]**. Om du stänger popup-fönstret **avbryts inte** nedladdningen.

När filen är klar visas ett meddelande om att den är klar och filen hämtas till webbläsaren.

Om du begär mer än en nedladdning åt gången får du ett meddelande om att varje ytterligare nedladdning kommer att ställas i kö tills den tidigare nedladdningen är klar.

![Statusmeddelandet för nedladdningen visar hur många procent som har slutförts och en länk för att avbryta nedladdningen.](assets/toast.png)

## Hämta känsliga data {#sensitive}

Om **[!UICONTROL Enforce Download]** [datahanteringsprincipen](/help/data-views/data-governance.md) är aktiverad i datavyn som du rapporterar om, kommer eventuell hämtning (till exempel e-post eller delning av PDF-filer) av Workspace-projekt att hash-koda datafälten som är märkta som känsliga. Du kan fortfarande analysera dessa fält i Workspace, men om du försöker skicka ett e-postmeddelande eller på annat sätt dela ett projekt visas de blockerade fälten som tomma i .pdf- eller .csv-filen.

Om det finns datafält som är märkta som känsliga i [!UICONTROL Data View] begränsas alternativet att markera och kopiera data från skärmen för alla data i [!UICONTROL Data View].

## Vanliga frågor och svar {#faq}

| Fråga | Svar |
| --- | --- |
| Varför är min nedladdade PDF en sida? | Workspace paginerar för närvarande inte nedladdade PDF-filer. |
| Kan jag exportera mer än 50 000 objekt med alternativet &quot;Hämta objekt som CSV&quot;? | Varje nedladdning kan innehålla upp till 50 000 dimensionsobjekt, men du kan ändra sorteringsordningen i tabellen för att hämta längre slutobjekt eller använda ett filter för att hämta mer specifika objekt. |
| Vad gör **[!UICONTROL Copy visualization]**? | Till skillnad från [!UICONTROL **Kopiera data till Urklipp**] eller [!UICONTROL **Kopiera markering till Urklipp**] är alternativet **[!UICONTROL Copy visualization]** för högerklick inte ett exportalternativ. Du kan kopiera en visualisering eller panel från en plats i Workspace till en annan. Exempel: från en panel till en annan i samma projekt, eller från ett projekt till ett annat projekt. [Intralänkande video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=sv-SE) |
