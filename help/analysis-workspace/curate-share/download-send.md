---
description: Du kan hämta sparade och osparade projekt i PDF- och CSV-format.
title: Hämta PDF- eller CSV-filer
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 3%

---


# Hämta PDF- eller CSV-filer

>[!NOTE] Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan hämta sparade och osparade projekt i PDF- och CSV-format.

Namnet på PDF- eller CSV-filen matchar projektets aktuella namn. För osparade projekt innehåller den hämtade filen de ändringar som inte sparats i projektet. Observera att du inte kan schemalägga osparade projekt i PDF eller CSV.

Tänk på detta:

* Vi stöder även Fallout-visualisering i CSV-format.
* När vi återger ett projekt till PDF återger vi bara det som finns på sidan. Om ett projekt har visualiseringar och paneler i anpassad storlek måste du ändra dem så att de storleksändras automatiskt (knappen i det övre högra hörnet) så att det inte finns något trunkerat innehåll.
* Det kan ta flera minuter att exportera PDF-filer som hämtas i webbläsaren. Det beror på att vi måste köra om hela projektet på våra servrar innan det återges i PDF-format. Vi rekommenderar att du inte lämnar projektet förrän PDF-filen har laddats ned i webbläsaren. Du kan dock fortsätta att ändra projektet medan du väntar.
* Vi är medvetna om att om du har mycket långa Workspace-projekt exporteras PDF-filer för närvarande som en enda jätteppage i stället för som ett sidnumrerat dokument. Vi arbetar på en förbättring av PDF-exporten till Workspace som tillåter sidnumrering.

1. Skapa eller öppna ett projekt.
1. Klicka på **[!UICONTROL Project]** > **[!UICONTROL Download CSV (or Download PDF).]**

Den 11 april 2019 gjordes flera ändringar av **[!CSV hämtningar]** (och **[!Ckopiering till Urklipp]**) från Analysis Workspace för att ta bort formatering från exporterade data.
* tusentalsavgränsaren tas inte med längre. (Decimalavgränsaren tas med och följer det format som definieras i **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* Inga valutasymboler visas.
* Inga procentsymboler visas.
* Procentsatserna anges i decimalform. 75 % representeras t.ex. som 0,75.
* Tiden visas i sekunder.
* Kohorttabeller visar endast råvärden. procenttal tas bort.
* Om ett tal är ogiltigt visas en tom cell.

>[!NObs!]
>
> Numeriska värden som använder kommatecken som decimalavgränsare fortsätter att citeras i den exporterade CSV-filen.
