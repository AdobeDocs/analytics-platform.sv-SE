---
description: Vanliga frågor om Workspace
title: Vanliga frågor och felsökningsarbetsyta
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 42%

---


# Frågor och svar

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

| Fråga | Svar |
|--- |--- |
| Vilka är förutsättningarna för att använda Analysis Workspace? | Om du använder Analysis Workspace krävs en fungerande implementering av kundens Journey Analytics. Kontrollera att din organisation skickar data till Adobe Experience Platform innan du använder verktyget. |
| Vilka är administrations- och åtkomstkraven för Analysis Workspace? | Se [Administrationskrav](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Kommer Analysis Workspace att påverka datainsamlingen? | Eftersom Analysis Workspace är ett rapportverktyg påverkar det inte datainsamlingen. Du kan dra komponenter till ett projekt för att se vad som fungerar utan att oroa dig för följderna. Dra olika kombinationer av mått och mätvärden till Workspace-projektet för att se vad som är tillgängligt för dig. Om du av misstag drar en ogiltig komponent till Workspace-projektet eller vill gå bakåt ett steg trycker du på Ctrl+Z (Windows) eller Kommando+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja från början genom att klicka på *[!UICONTROL Project] > [!UICONTROL New]* i den övre vänstra menyn. |
| Hur implementerar du Analysis Workspace? | Det krävs ingen särskild implementering. Analysis Workspace är tillgängligt för alla företag Customer Journey Analytics. Standardbehörigheter för innehåll (t.ex. projektkomponenter) gäller dock, och för att skapa och dela projekt. Se [Administrations- och tillträdeskrav](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Hur kan jag optimera prestanda för Analysis Workspace? | Se [Optimera prestanda](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Felsökning

**När jag drar ett mätvärde står det ”Ogiltiga data”.**

Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av mått och mätvärden som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Placera i stället måttet sida vid sida.

**När jag drar ett mätvärde ser jag inga data, bara nollor.**

Om du har skapat en arbetsyterapport men det inte finns några data finns det några saker du kan kontrollera:

* Dubbelkolla rapportsviten och kontrollera att den fylls i med data.
* Om du tillämpade ett segment i rapporten kanske segmentkriterierna inte matchar några data. Prova med att ta bort segmentet eller justera segmentdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det är inställt på ett värde som du förväntar dig.
* Navigera till webbplatsen och använd [Felsökning](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) för att validera att data samlas in.