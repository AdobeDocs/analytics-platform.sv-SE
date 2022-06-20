---
description: Du kan hämta data från Analysis Workspace genom att kopiera dem eller i formaten PDF och CSV.
title: Hämta PDF- eller CSV-filer
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 1%

---

# Hämta PDF- eller CSV-filer

Det finns flera olika sätt att exportera data från Analysis Workspace, beroende på vilken datauppsättning du vill analysera utanför verktyget och vem som behöver få informationen. Exporterade data kan vara i form av kopierade data, CSV- eller PDF-filer. Ett PDF är att föredra om du vill att visualiseringar ska inkluderas i filen, medan en CSV (eller kopierade data) föredras om du bara vill ha oformaterade textdata.

## Hämta projekt som CSV eller PDF {#download-project}

Du kan ladda ned ett helt projekt genom att gå till **[!UICONTROL Project > Download as PDF (or as CSV)]**. Den hämtade filen innehåller alla tabeller och visualiseringar som visas (synliga) i projektet. Ett PDF är att föredra om du vill att visualiseringar ska ingå i filen, medan en CSV-fil föredras om du bara vill ha oformaterade textdata.

![](assets/download-project.png)

När det gäller projektnedladdningar bör du tänka på följande:

* Projektet kan sparas eller inte sparas när du begär en projekthämtning. Endast sparade projekt kan dock [schemalagd](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html).
* Det kan ta flera minuter att exportera PDF som hämtats i webbläsaren eftersom projektet körs på Adobe-servrar igen innan det återges i PDF. Vi rekommenderar att du inte lämnar projektet förrän PDF har hämtats i webbläsaren. Du kan dock fortsätta att ändra projektet medan du väntar. Om det tar längre tid än fem minuter att återge ett PDF uppmanas du att skicka det via e-post i stället.
* Nedladdningar från PDF återges som en sida utan sidnumrering.
* När ett projekt återges för PDF återger vi det som finns på sidan. Om ett projekt har visualiseringar och paneler i anpassad storlek måste du ändra dem så att de storleksändras automatiskt (knappen i det övre högra hörnet) så att det inte finns något trunkerat innehåll.

## Kopiera data till Urklipp (snabbtangent: Ctrl+C) {#copy-data}

Högerklicksalternativet **[!UICONTROL Copy to clipboard]** Med kan du snabbt kopiera data från arbetsytan och klistra in dem någon annanstans.

* Om du vill att den visade tabellen ska kopieras högerklickar du på tabellrubriken och väljer **Kopiera data till Urklipp**.
* Om du vill att en delmängd av data ska kopieras markerar du den i tabellen och högerklickar sedan > **Kopiera markering till Urklipp**.

Dessutom trycker du på `Ctrl+C` kopierar markeringen till Urklipp. När du har kopierat kan du gå till ett annat verktyg och klistra in informationen (eller trycka på `Ctrl+V`).

![](assets/copy-selection.png)

## Hämta data som CSV {#download-data}

Högerklicksalternativet **[!UICONTROL Download data as CSV]** Med kan du hämta en datatabell eller datakällan för en visualisering som en CSV-fil.

* Högerklicka i huvudet på en tabell eller visualisering **[!UICONTROL Download data as CSV]**. Detta hämtar visade data i tabellen eller den underliggande datakällan för en visualisering som en CSV-fil. Obs! Kartvyn stöder inte det här alternativet.
* Om en markering har gjorts i tabellen, kan du välja att **[!UICONTROL Download selection as CSV]**. Endast markeringen laddas ned med det här alternativet, i motsats till den fullständiga tabellen som visas.

![](assets/download-data-viz.png)

## Hämta objekt som CSV {#download-items}

Om du vill analysera mer än de 400 synliga dataraderna i en tabell högerklickar du på tabellrubriken eller valfri rad och väljer **Hämta objekt som CSV (Dimensionens namn)**. Med det här alternativet exporteras upp till 50 000 dimensionsobjekt (baserat på tabellsortering) för den valda dimensionen med filter och filter. Om du väljer det här alternativet överst i tabellen exporteras den första dimensionen i tabellen. Även om inga begränsningar används i friformstabellen rekommenderar vi att alternativet Hämta objekt används i tabeller med mindre än 20 kolumner för att optimera prestandan.

>[!TIP]
>
> Om din dimension överstiger 50 000 objekt hämtar du filen med olika sorteringsmått tillämpade eller använder ett filter. Du kan t.ex. sortera efter besök i en nedladdning och sedan stigande efter besök i en andra nedladdning. Det här tipset kan hjälpa dig att hämta objekt med längre svans.

Du kan utföra flera uppgifter samtidigt i projektet och till och med navigera till ett nytt Workspace-projekt på samma flik medan hämtningen pågår. Hämtningen pausas om du öppnar en ny flik i webbläsaren. Hämtningen avbryts om du lämnar arbetsytan helt eller stänger webbläsarfliken.

![](assets/download-items.png)

### Nedladdad objektfil

Tabellens funktioner kommer att tillämpas på den hämtade filen enligt följande:

* Alla panelfilter används som filter.
* Uppdelningar **ovan** den valda dimensionen i tabellen används som filter ovanför varje kolumn.
* Uppdelningar **nedan** den valda dimensionen i registret tas bort.

I exemplet ovan hämtas sidobjekt med panelfiltret (kunder med nya besökare) och komponenterna ovan (marknadsföringskanal = e-post) tillämpade som filter, och komponenterna nedan (mobilenhetstyp) tas bort från den hämtade CSV-filen.

![](assets/downloaded-file.png)

### Hämta meddelanden

När filen hämtas visas ett informationsmeddelande med förloppet. Du kan när som helst avbryta nedladdningen genom att klicka på **[!UICONTROL Cancel download]**. Stänger popup **inte** avbryt nedladdningen.

När filen är klar visas ett meddelande om att den är klar och filen hämtas till webbläsaren.

Om du begär mer än en nedladdning åt gången får du ett meddelande om att varje ytterligare nedladdning kommer att ställas i kö tills den tidigare nedladdningen är klar.

![](assets/toast.png)

## Vanliga frågor {#faq}

| Fråga | Svar |
| --- | --- |
| Varför är min nedladdade PDF-sida? | Arbetsytan sidnumrerar inte PDF som har laddats ned just nu. |
| Kan jag exportera mer än 50 000 objekt med alternativet &quot;Hämta objekt som CSV&quot;? | Varje nedladdning kan innehålla upp till 50 000 dimensionsobjekt, men du kan ändra sorteringsordningen i tabellen för att hämta längre slutobjekt eller använda ett filter för att hämta mer specifika objekt. |
| Vad gör **[!UICONTROL Copy visualization]** eller? | **[!UICONTROL Copy visualization]** är inte ett exportalternativ. Du kan kopiera en visualisering eller panel från en plats i Workspace till en annan. Exempel: från en panel till en annan i samma projekt, eller från ett projekt till ett annat projekt. [Intralänkande video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |
