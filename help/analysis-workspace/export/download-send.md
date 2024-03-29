---
description: Du kan hämta data från Analysis Workspace genom att kopiera dem eller i formaten PDF och CSV.
title: Hämta Customer Journey Analytics-data
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 0%

---

# Hämta Customer Journey Analytics-data

Du kan hämta Customer Journey Analytics-data till din personliga arbetsstation. Detta kan vara i form av kopierade data, CSV eller PDF. Ett PDF är att föredra om du vill att visualiseringar ska ingå i den hämtade filen. CSV och kopierade data är att föredra om du bara vill ha textdata.

Det finns även andra metoder för att exportera data från Customer Journey Analytics, vilket beskrivs i [Exportera översikt](/help/analysis-workspace/export/export-project-overview.md).

## Hämta som CSV eller PDF {#download-project}

1. Gör något av följande, beroende på vilket format du vill att hämtningen ska vara i:

   * **PDF:** Välj **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.

     Välj det här alternativet om du vill att den hämtade filen ska innehålla alla tabeller och visualiseringar som visas i projektet.

   * **CSV:** Välj **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

     Välj det här alternativet om du vill att den hämtade filen ska vara oformaterad.

   ![Listrutan Projekt där alternativen Hämta CSV och Hämta PDF är markerade.](assets/download-project.png)

1. (Villkorligt) Om du väljer att hämta ett PDF visas ett meddelande när projektet är klart att hämtas. Välj [!UICONTROL **Ladda ned**].

När det gäller projektnedladdningar bör du tänka på följande:

* Projektet kan sparas eller inte sparas när du begär en projekthämtning. Endast sparade projekt kan dock [schemalagd](/help/analysis-workspace/export/t-schedule-report.md).
* Det kan ta flera minuter att exportera PDF som hämtats i webbläsaren eftersom projektet körs på Adobe-servrar igen innan det återges i PDF-format. Vi rekommenderar att du inte lämnar projektet förrän PDF har hämtats i webbläsaren. Du kan dock fortsätta att göra ändringar i projektet medan du väntar. Om det tar längre tid än fem minuter att återge ett PDF uppmanas du att skicka det via e-post i stället.
* Nedladdningar från PDF återges som en sida utan sidnumrering.
* När ett projekt återges för PDF återger vi det som finns på sidan. Om ett projekt har visualiseringar och paneler i anpassad storlek måste du ändra dem så att de storleksändras automatiskt (knappen i det övre högra hörnet) så att det inte finns något trunkerat innehåll.

## Kopiera till Urklipp (snabbtangent: Ctrl+C) {#copy-data}

Högerklicksalternativet **[!UICONTROL Copy to clipboard]** Med kan du snabbt kopiera Customer Journey Analytics data från arbetsytan och klistra in dem i ett verktyg från tredje part.

* Om du vill att den visade tabellen ska kopieras högerklickar du på tabellrubriken och väljer **Kopiera data till Urklipp**.
* Om du vill att en delmängd av data ska kopieras markerar du den i tabellen och högerklickar sedan > **Kopiera markering till Urklipp**.

>[!TIP]
>
>Du kan använda snabbtangenten `Ctrl+C` för att kopiera markeringen till Urklipp och sedan använda `Ctrl+V` för att klistra in den i ett verktyg från tredje part.


![Alternativet Kopiera markering till Urklipp. ](assets/copy-selection.png)

## Hämta som CSV {#download-data}

Högerklicksalternativet **[!UICONTROL Download data as CSV]** Med kan du hämta en tabell med data från Customer Journey Analytics eller datakällan för en visualisering som en CSV-fil.

* Högerklicka och välj i huvudet på en tabell eller visualisering **[!UICONTROL Download data as CSV]**. Detta hämtar de visade Customer Journey Analytics-data i tabellen eller den underliggande datakällan för en visualisering som en CSV-fil.

  >[!NOTE]
  >
  >  Obs! Kartvyn stöder inte det här alternativet.


* Högerklicka i en tabell och välj **[!UICONTROL Download selection as CSV]**. Endast markeringen laddas ned med det här alternativet, i motsats till den fullständiga tabellen som visas.

![Alternativet Hämta data som CSV.](assets/download-data-viz.png)

## Hämta objekt som CSV {#download-items}

Om du vill analysera mer än de 400 synliga dataraderna i en tabell högerklickar du på tabellrubriken eller valfri rad och väljer **Hämta objekt som CSV (_Dimensionens namn_)**. Med det här alternativet exporteras upp till 50 000 dimensionsobjekt (baserat på tabellsortering) för den valda dimensionen med sorteringsalternativ och filter. Om du väljer det här alternativet överst i tabellen exporteras den första dimensionen i tabellen. Även om inga begränsningar används i friformstabellen rekommenderar vi att alternativet Hämta objekt används i tabeller med mindre än 20 kolumner för att optimera prestandan.

>[!TIP]
>
> Om din dimension överstiger 50 000 objekt hämtar du filen med olika sorteringsmått tillämpade eller använder ett filter. Du kan t.ex. sortera efter besök i en nedladdning och sedan stigande efter besök i en andra nedladdning. Det här tipset kan hjälpa dig att hämta objekt med längre svans.

Du kan utföra flera uppgifter samtidigt i projektet och till och med navigera till ett nytt Workspace-projekt på samma flik medan hämtningen pågår. Hämtningen pausas om du öppnar en ny flik i webbläsaren. Hämtningen avbryts om du lämnar arbetsytan helt eller stänger webbläsarfliken.

![Alternativet Hämta objekt som CSV (sida).](assets/download-items.png)

### Nedladdad objektfil {#items-file}

Tabellens funktioner kommer att tillämpas på den hämtade filen enligt följande:

* Alla panelfilter används som filter.
* Uppdelningar **ovan** den valda dimensionen i tabellen används som filter ovanför varje kolumn.
* Uppdelningar **nedan** den valda dimensionen i registret tas bort.

I exemplet ovan hämtas sidobjekt med panelfiltret (kunder med nya besökare) och komponenterna ovan (marknadsföringskanal = e-post) tillämpade som filter, och komponenterna nedan (mobilenhetstyp) tas bort från den hämtade CSV-filen.

![Den hämtade CSV-filen som öppnas i Excel.](assets/downloaded-file.png)

### Hämta meddelanden {#notifications}

När filen laddas ned visas ett informationsmeddelande med förloppet. Du kan när som helst avbryta nedladdningen genom att klicka på **[!UICONTROL Cancel download]**. Stänger popup **inte** avbryt nedladdningen.

När filen är klar visas ett meddelande om att den är klar och filen hämtas till webbläsaren.

Om du begär mer än en nedladdning åt gången får du ett meddelande om att varje ytterligare nedladdning kommer att ställas i kö tills den tidigare nedladdningen är klar.

![Statusmeddelandet för nedladdningen visar hur många procent som har slutförts och en länk för att avbryta nedladdningen.](assets/toast.png)

## Hämta känsliga data {#sensitive}

Om **[!UICONTROL Enforce Download]** [datastyrningsprincip](/help/data-views/data-governance.md) är aktiverat i den datavy som du rapporterar om, kommer eventuell nedladdning (till exempel e-post eller delning av PDF-filer) av Workspace-projekt att hash-koda datafälten som är märkta som känsliga. Du kan fortfarande analysera dessa fält i Workspace, men om du försöker skicka ett e-postmeddelande eller på annat sätt dela ett projekt visas de blockerade fälten som tomma i PDF- eller CSV-filen.

## Vanliga frågor och svar {#faq}

| Fråga | Svar |
| --- | --- |
| Varför är min nedladdade PDF-sida? | Arbetsytan sidnumrerar inte PDF som har laddats ned just nu. |
| Kan jag exportera mer än 50 000 objekt med alternativet &quot;Hämta objekt som CSV&quot;? | Varje nedladdning kan innehålla upp till 50 000 dimensionsobjekt, men du kan ändra sorteringsordningen i tabellen för att hämta längre slutobjekt eller använda ett filter för att hämta mer specifika objekt. |
| Vad gör **[!UICONTROL Copy visualization]** eller hur? | Ogilla [!UICONTROL **Kopiera data till Urklipp**] eller [!UICONTROL **Kopiera markering till Urklipp**], **[!UICONTROL Copy visualization]** högerklicksalternativet är inte ett exportalternativ. Du kan kopiera en visualisering eller panel från en plats i Workspace till en annan. Exempel: från en panel till en annan i samma projekt, eller från ett projekt till ett annat projekt. [Intralänkande video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |
