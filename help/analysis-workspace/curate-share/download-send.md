---
description: Du kan hämta sparade och ej sparade projekt i PDF- och CSV-format.
title: Hämta PDF- eller CSV-filer
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 387e9755d963e70a9ba8dbc5f1f01f83541b5511
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 3%

---


# Hämta PDF- eller CSV-filer

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan hämta sparade och ej sparade projekt i PDF- och CSV-format.

Namnet på PDF- eller CSV-filen matchar projektets aktuella namn. För projekt som inte har sparats innehåller den hämtade filen de ändringar som inte har sparats i projektet. Observera att du inte kan schemalägga projekt som inte har sparats i PDF eller CSV.

Kom ihåg detta:

* Vi stöder också Fallout-visualiseringen i CSV-format.
* När vi återger ett projekt till PDF återger vi bara det som finns på sidan. Om ett projekt har skräddarsydda visualiseringar och paneler måste du ändra dem så att de blir automatiskt stora (knapp i det övre högra hörnet) så att det inte blir något trunkerat innehåll.
* PDF-filer som hämtas i webbläsaren kan ta flera minuter att exportera. Detta beror på att vi måste köra om hela projektet på våra servrar innan vi återger det i PDF-format. Vi rekommenderar att du inte lämnar projektet förrän PDF-filen hämtas i webbläsaren. Du kan dock fortsätta att göra ändringar i projektet medan du väntar.
* Vi är medvetna om att om du har mycket långa arbetsyteprojekt exporterar PDF-filer för närvarande som en jättelik sida i stället för som ett paginerat dokument. Vi arbetar på en förbättring av PDF-exporten till arbetsytan som möjliggör sidnumrering.

1. Skapa eller öppna ett projekt.
1. Klicka på **[!UICONTROL Project]** > **[!UICONTROL Download CSV (or Download PDF).]**

Den 11 april 2019 gjordes flera ändringar i **[!CSV nedladdningar]** och **[!Ckopiera till Urklipp]**) från Analysis Workspace om du vill ta bort formatering från exporterade data.
* Tusentalsavgränsaren ingår inte längre. (Decimalavgränsaren kommer även i fortsättningen att inkluderas och kommer att följa det format som anges i **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* Inga valutasymboler visas.
* Inga procentsymboler visas.
* Procenttalen anges i decimalform. t.ex. är 75 procent representerat som 0,75.
* Tiden visas i sekunder.
* Kohorttabellerna visar endast råvärden. procentandelar tas bort.
* Om ett tal är ogiltigt visas en tom cell.

>[!NOTE]
>
>Numeriska värden som använder ett kommatecken som decimalavgränsare citeras även i fortsättningen i den exporterade CSV.
