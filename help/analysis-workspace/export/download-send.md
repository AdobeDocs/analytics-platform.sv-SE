---
description: Läs om de olika möjligheterna att hämta data från ditt Analysis Workspace-projekt.
title: Hämta projekt och data
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '1149'
ht-degree: 0%

---

# Hämta projekt och data

Du kan hämta Analysis Workspace-projekt och data till din lokala enhet. Den här hämtningen kan vara kopierade data, en CSV-fil (kommaavgränsade data) eller ett PDF-dokument (portabla dokumentformat).

* Välj alternativet PDF om du vill att visualiseringar ska ingå i den hämtade filen.
* Välj CSV och kopierade dataalternativ om du bara behöver textdata.

Ytterligare metoder för att exportera Customer Journey Analytics-data beskrivs i [Exportöversikt](/help/analysis-workspace/export/export-project-overview.md).

## Hämta som CSV eller PDF {#download-project}

![Listrutan Projekt med alternativen Hämta CSV och Hämta PDF markerade.](assets/download-project.png)

Tänk på följande när du hämtar ett projekt som PDF:

* Nedladdningen kan ta flera minuter eftersom projektet körs på nytt på Adobe-servrar för att återges i PDF-format. Lämna inte projektet förrän projektet har laddats ned i webbläsaren.  Du kan fortsätta att ändra projektet medan hämtningen renderas. Om det tar längre tid än fem minuter att återge en PDF uppmanas du att [skicka PDF](../curate-share/send-schedule-files.md) via e-post i stället.
* Hämtningar återges som en sida utan sidnumrering.
* PDF innehåller det som visas på webbläsarsidan i Analysis Workspace. Du behöver automatiskt storleksanpassa visualiseringar och paneler för att undvika trunkerat innehåll. Välj ![Ändra storlek](/help/assets/icons/Resize.svg) om du vill ändra storlek på en visualisering eller panel i anpassad storlek automatiskt.
* [Hyperlänkar](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) i frihandstabeller som hyperlänkar i den hämtade PDF-filen.



Så här hämtar du ett projekt som en PDF-fil:

1. Välj **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.
Ett grönt fält med meddelandet ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Your download has been requested. Please wait.]** visas.

1. När nedladdningen är klar visas ett grönt fält med meddelandet ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *Projektets namn *PDF.]**visas.
Välj**[!UICONTROL Download]**om du vill hämta PDF. Hur exakt PDF presenteras eller laddas ned beror på vilken webbläsarkonfiguration du har för att hantera PDF-dokument.


Så här hämtar du ett projekt som en CSV-fil:

* Välj **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**. Projektet hämtas direkt till den hämtningsmapp som är konfigurerad som en del av webbläsarkonfigurationen. Filnamnet består av *projektnamn* - *rapportsvitens namn* - *datum*, till exempel `Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`.

## Kopiera till Urklipp {#copy-data}

Med alternativet **[!UICONTROL Copy to clipboard]** på snabbmenyn kan du snabbt kopiera data från Analysis Workspace och klistra in data i ett verktyg från tredje part.

* Om du vill att tabelldata som visas ska kopieras markerar du tabellrubriken och väljer **Kopiera data till Urklipp** på snabbmenyn.
* Om du vill att en delmängd av data ska kopieras markerar du den i tabellen och väljer **Kopiera markering till Urklipp** på snabbmenyn.

>[!TIP]
>
>Du kan använda snabbtangenten **_cmd + c_** (macOS) eller **_ctrl + c_** (Windows) för att kopiera ditt val till Urklipp. Använd sedan **_cmd + v_** (macOS) eller **_ctrl + v_** (Windows) för att klistra in data.


![Alternativet Kopiera markering till Urklipp. ](assets/copy-clipboard.png){zoomable="yes"}

## Hämta som CSV {#download-data}

Med alternativen för att hämta som CSV på snabbmenyn kan du hämta en datatabell eller datakällan för en visualisering som en CSV-fil.

Så här gör du:

* Välj **[!UICONTROL Download data as CSV]** på snabbmenyn i en tabell eller visualisering. Detta hämtar visade data i tabellen eller den underliggande datakällan för en visualisering som en CSV-fil.

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* Välj **[!UICONTROL Download selection as CSV]** på snabbmenyn i en tabell. Endast markeringen laddas ned med det här alternativet, i motsats till den fullständiga tabellen som visas.

![Alternativet Hämta data som CSV.](assets/download-data-as-csv.png)

## Hämta objekt som CSV {#download-items}

Om du vill analysera fler än de 400 synliga dataraderna i en tabell väljer du **Hämta objekt som CSV (_Dimension name_)** på snabbmenyn för tabellhuvudet eller på en rad. Med det här alternativet exporteras upp till 50 000 dimensionsobjekt (baserat på tabellsortering) för den valda dimensionen med sorteringsalternativ och filter. Om du väljer det här alternativet överst i tabellen exporteras den första dimensionen i tabellen.

![Alternativet Hämta objekt som CSV (sida).](assets/download-items-as-csv.png)

Inga begränsningar används i frihandstabellen. För att få optimala prestanda bör du använda det här alternativet i tabeller med färre än 20 kolumner.

>[!TIP]
>
> Om din dimension överstiger 50 000 objekt hämtar du filen med olika sorteringsvärden eller använder ett segment. Du kan t.ex. sortera efter besök i en nedladdning och sedan stigande efter besök i en andra nedladdning. Det här tipset kan hjälpa dig att hämta objekt med längre svans.

Du kan utföra flera uppgifter samtidigt i projektet och till och med navigera till ett nytt Workspace-projekt på samma flik medan hämtningen pågår. Hämtningen pausas om du öppnar en ny flik i webbläsaren. Hämtningen avbryts om du lämnar Workspace helt eller stänger webbläsarfliken.


### Nedladdad objektfil {#items-file}

Följande funktioner i en frihandstabell används i den hämtade filen:

* Alla panelsegment används som filter.
* Uppdelningar **ovanför** den valda dimensionen i tabellen används som filter ovanför varje kolumn.
* Uppdelningar **nedanför** av den valda dimensionen i tabellen tas bort.

![Den hämtade CSV-filen som öppnats i Excel.](assets/download-items-file.png)

### Hämta meddelanden {#notifications}

När filen laddas ned visas följande meddelanden:

* Ett blått **[!UICONTROL _tabellnamn _-_Dimension _.csv har begärts._x _% slutfört]**anger förloppet. Om du vill avbryta hämtningen väljer du **[!UICONTROL Cancel download]**. Välj ![CrossSize100](/help/assets/icons/CrossSize100.svg) om du vill stänga meddelandet, som inte avbryter hämtningen.
* Ett grönt **[!UICONTROL _tabellnamn _-_Dimension _.csv har hämtats]**meddelande om slutförd filhämtning. Filen hämtas till den nedladdningsmapp som är konfigurerad för webbläsaren.

Om du begär mer än en nedladdning åt gången får du ett meddelande om att varje ytterligare nedladdning är i kö tills den tidigare nedladdningen är klar.


## Hämta känsliga data {#sensitive}

Tänk dig en [datastyrningspolicy](/help/data-views/data-governance.md) som förhindrar hämtning av data. Och att den här principen är aktiverad i datavyn som du rapporterar om. Det innebär att alla nedladdningar (till exempel när du skickar e-post eller delar PDF-filer) av projekt kommer att krascha datafälten som är märkta som känsliga. Du kan fortfarande göra analyser i dessa fält i Analysis Workspace. Om du försöker skicka ett projekt med e-post eller på annat sätt dela ett projekt visas de känsliga datafälten som tomma i PDF- eller CSV-filen.

Om datafält som är märkta som känsliga inkluderas i datavyn är alternativet att markera och kopiera data från skärmen begränsat för alla data i datavyn.

## Vanliga frågor och svar {#faq}

| Fråga | Svar |
| --- | --- |
| Varför består min nedladdade PDF av bara en sida? | Funktionen [Hämta PDF](#download-as-csv-or-pdf) numrerar inte hämtade PDF-filer. |
| Kan jag exportera mer än 50 000 objekt med alternativet **[!UICONTROL Download items as CSV]**? | Varje nedladdning kan innehålla upp till 50 000 dimensionsobjekt, men du kan ändra sorteringsordningen i tabellen för att hämta längre slutobjekt eller använda ett filter för att hämta mer specifika objekt. |
| Vad gör **[!UICONTROL Copy visualization]**? | Till skillnad från [!UICONTROL **Kopiera data till Urklipp**] eller [!UICONTROL **Kopiera markering till Urklipp**] är snabbmenyalternativet **[!UICONTROL Copy visualization]** inte ett exportalternativ. Med det här alternativet kan du [kopiera en visualisering](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu) eller [kopiera en panel](/help/analysis-workspace/c-panels/panels.md#context-menu) från en plats i Workspace till en annan. Exempel: från en panel till en annan i samma projekt, eller från ett projekt till ett annat projekt. |
